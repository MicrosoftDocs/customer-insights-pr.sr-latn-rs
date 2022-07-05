---
title: Povežite se sa podacima u Microsoft Dataverse upravljanom jezeru podataka
description: Uvoz podataka iz Microsoft Dataverse upravljanog jezera podataka.
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 9ae0b964d8d39835715b7ddadc712e2338b855af
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082162"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Povežite se sa podacima u Microsoft Dataverse upravljanom jezeru podataka

Microsoft Dataverse korisnici mogu brzo da se povežu sa analitičkim entitetima u upravljanom Microsoft Dataverse jezeru.

> [!NOTE]
> Morate biti administrator organizacije da biste Dataverse nastavili i pregledali listu entiteta dostupnih u kontrolisanom jezeru.

## <a name="important-considerations"></a>Važna razmatranja

1. Podaci uskladišteni u mrežnim uslugama, kao što je Azure Data Lake Storage, mogu se skladištiti na lokaciji različitoj od one na kojoj se podaci obrađuju ili skladište u usluzi Dynamics 365 Customer Insights.Uvozom ili povezivanjem sa podacima uskladištenim u uslugama na mreži slažete se da se podaci mogu prenositi i skladištiti sa programom Dynamics 365 Customer Insights. [Saznajte više u Microsoft centru za pouzdanost](https://www.microsoft.com/trust-center).
2. Vidljivi Dataverse su samo entiteti [sa omogućenim](/power-platform/admin/enable-change-tracking-control-data-synchronization) praćenjem promena. Ovi entiteti se mogu izvesti u jezero sa podacima Dataverse kojim se upravlja i koristiti u uvidima kupaca. Tabele bez okvira Dataverse podrazumevano imaju omogućeno praćenje promena. Potrebno je da uključite praćenje promena za prilagođene tabele. Da biste proverili da Dataverse li je tabela omogućena za praćenje promena, idite na tabele [Power Apps](https://make.powerapps.com) > **podataka** > **·**. Pronađite tabelu koja vas interesuje i izaberite je. Idite na **opcije** > **"Više opcija postavki"** i pregledajte postavku **praćenja** promena.

## <a name="connect-to-a-dataverse-managed-lake"></a>Povežite se sa Dataverse upravljanim jezerom

1. Idite na **Podaci** > **Izvori podataka**.

1. Izaberite **Dodaj izvor podataka**.

1. Izaberite stavku **Microsoft Dataverse**.

1. Unesite **ime** za izvor podataka i opcionalni **opis**.

1. Navedite **Adresu servera** za Dataverse organizaciju i izaberite **Prijavite se**.

1. Izaberite tabele koje želite da unestite kao entitete u uvid kupca sa dostupne liste.

   > [!NOTE]
   > Ako su neke tabele već izabrane, mogu ih koristiti druge Dynamics 365 aplikacije (poput Dynamics 365 Sales Insights ili Customer Service Insights). Ne možete promeniti izbor. Ove tabele će biti dostupne kao entiteti kada se kreira izvor podataka.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dijalog koji prikazuje listu entiteta u Dataverse okruženju.":::

1. Sačuvajte svoj izbor da biste započeli sinhronizaciju izabranih tabela iz usluge Dataverse. Novododatu vezu ćete pronaći na stranici **Izvori podataka**. Biće stavljeno u red za osvežavanje i prikazaće broj entiteta kao 0 dok se sve izabrane tabele ne sinhronizuju.

Samo jedan izvor podataka okruženja može istovremeno da koristi isto Dataverse nadgledano jezero.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Uredite izvor podataka za Dataverse upravljano jezero

Izbor entiteta uređujete tek nakon što kreirate izvor podataka. Na primer, ako su dodati dodatni entiteti u uslugu Dataverse, a želite i da ih uvozite.
Da biste se povezali sa drugim Dataverse jezerom podataka, [kreirajte novi izvor podataka](#connect-to-a-dataverse-managed-lake).

1. Idite na **Podaci** > **Izvori podataka**.

1. Pored izvor podataka želite da ažurirate, izaberite stavku **Uredi**.

1. Izaberite dodatne entitete s dostupne liste entiteta i izaberite **Sačuvaj**.
