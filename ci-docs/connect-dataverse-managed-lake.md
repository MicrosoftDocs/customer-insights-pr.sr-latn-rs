---
title: Povezivanje sa tabelama u usluzi Microsoft Dataverse
description: Uvoz podataka iz Microsoft Dataverse upravljanog jezera podataka.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: e8a294a4bad1581539b5905160cddcd625699d90
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643108"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Povežite se sa podacima u Microsoft Dataverse upravljanom jezeru podataka

Ovaj članak pruža informacije o tome kako Dataverse korisnici mogu brzo da se povežu sa analitičkim entitetima u upravljanom Microsoft Dataverse jezeru. 

> [!NOTE]
> Morate biti administrator organizacije da biste Dataverse nastavili i pregledali listu entiteta dostupnih u kontrolisanom jezeru.

## <a name="important-considerations"></a>Važna razmatranja

1. Podaci uskladišteni u mrežnim uslugama, kao što je Azure Data Lake Storage, mogu se skladištiti na lokaciji različitoj od one na kojoj se podaci obrađuju ili skladište u usluzi Dynamics 365 Customer Insights.Uvozom ili povezivanjem sa podacima uskladištenim u uslugama na mreži slažete se da se podaci mogu prenositi i skladištiti sa programom Dynamics 365 Customer Insights. [Saznajte više u Microsoft centru za pouzdanost](https://www.microsoft.com/trust-center).
2. Vidljivi Dataverse su samo entiteti [sa omogućenim](/power-platform/admin/enable-change-tracking-control-data-synchronization) praćenjem promena. Ovi entiteti se mogu izvesti u jezero sa podacima Dataverse kojim se upravlja i koristiti u uvidima kupaca. Tabele bez okvira Dataverse podrazumevano imaju omogućeno praćenje promena. Potrebno je da uključite praćenje promena za prilagođene tabele. Da biste proverili da Dataverse li je tabela omogućena za praćenje promena, idite na DataTables [Power Apps](https://make.powerapps.com) > **·** > **·**. Pronađite tabelu koja vas interesuje i izaberite je. Idite na **opcije** > **"PostavkeAdvanced" i pregledajte** postavku **Praćenja** promena.

## <a name="connect-to-a-dataverse-managed-lake"></a>Povežite se sa Dataverse upravljanim jezerom

1. U usluzi Customer Insights, idite na **Podaci** > **Izvori podataka**.

2. Izaberite **Dodaj izvor podataka**.

3. Izaberite i **Microsoft Dataverse** kliknite na dugme **Dalje**.

4. Unesite **Naziv** izvora podataka i izaberite **Sledeće**. 

5. Navedite **Adresu servera** za Dataverse organizaciju i izaberite **Prijavite se**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Ekran u koraku unosa podataka gde korisnik može da unese URL Dataverse okruženja.":::

6. Sa dostupne liste izaberite tabele koje želite da unesete kao entitete u uvide kupaca.    

   > [!NOTE]
   > Ako su neke tabele već izabrane, mogu ih koristiti druge Dynamics 365 aplikacije (poput Dynamics 365 Sales Insights ili Customer Service Insights). Ne možete promeniti izbor. Ove tabele će biti dostupne kao entiteti kada se kreira izvor podataka.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dijalog koji prikazuje listu entiteta u Dataverse okruženju.":::

7. Sačuvajte svoj izbor da biste započeli sinhronizaciju izabranih tabela iz usluge Dataverse. Novododatu vezu ćete pronaći na stranici **Izvori podataka**. Biće stavljeno u red za osvežavanje i prikazaće broj entiteta kao 0 dok se sve izabrane tabele ne sinhronizuju.

Samo jedan izvor podataka okruženja može istovremeno da koristi isto Dataverse nadgledano jezero.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Uredite izvor podataka za Dataverse upravljano jezero

Izbor entiteta uređujete tek nakon što kreirate izvor podataka. Na primer, ako su dodati dodatni entiteti u uslugu Dataverse, a želite i da ih uvozite.    
Da biste se povezali sa drugim Dataverse jezerom podataka, [kreirajte novi izvor podataka](#connect-to-a-dataverse-managed-lake).

1. Idite na **Podaci** > **Izvori podataka**.

2. Pored izvora podataka koji želite da ažurirate, izaberite tri tačke.

3. Izaberite opciju **Uredi** sa liste.

4. Izaberite dodatne entitete s dostupne liste entiteta i izaberite **Sačuvaj**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
