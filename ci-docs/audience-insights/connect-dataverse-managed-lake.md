---
title: Povezivanje sa tabelama u usluzi Microsoft Dataverse
description: Uvoz podataka iz Microsoft Dataverse upravljanog jezera podataka.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: f92d64723e6a4d2fcebdbb3758519d4bfd4aeaf4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692591"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Povežite se sa podacima u Microsoft Dataverse upravljanom jezeru podataka

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Ovaj članak pruža informacije o tome kako Dataverse korisnici mogu brzo da se povežu sa svojim analitičkim entitetima u Dataverse upravljanom jezeru. Morate biti administrator Dataverse organizacije kako biste nastavili i videli spisak entiteta dostupnih u upravljanom jezeru.

## <a name="important-considerations"></a>Važna razmatranja

Podaci uskladišteni u mrežnim uslugama, kao što je Azure Data Lake Storage, mogu se skladištiti na lokaciji različitoj od one na kojoj se podaci obrađuju ili skladište u usluzi Dynamics 365 Customer Insights. Uvozom ili povezivanjem podataka uskladištenih u mrežnoj usluzi, slažete se da se podaci mogu preneti i skladištiti u usluzi Dynamics 365 Customer Insights. [Saznajte više u Microsoft centru za pouzdanost.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Povežite se sa Dataverse upravljanim jezerom

1. U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.

2. Izaberite **Dodaj izvor podataka**.

3. Izaberite **Povezivanje sa Microsoft Dataverse upravljanim jezerom** i izaberite **Dalje**.

4. Unesite **Naziv** izvora podataka i izaberite **Sledeće**. Smernice za nazive: 
   - Započnite slovom.
   - Koristite samo slova i brojeve. Posebni znakovi i razmaci nisu dozvoljeni.
   - Koristite između 3 i 64 znaka.

5. Navedite **Adresu servera** za Dataverse organizaciju i izaberite **Prijavite se**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Ekran u koraku unosa podataka gde korisnik može da unese URL Dataverse okruženja.":::

6. Izaberite tabele koje želite da unesete kao entitete u uvide u ciljnu grupu sa dostupne liste.    

   > [!NOTE]
   > Ako su neke tabele već izabrane, mogu ih koristiti druge Dynamics 365 aplikacije (poput Dynamics 365 Sales Insights ili Customer Service Insights). Ne možete promeniti izbor. Ove tabele će biti dostupne kao entiteti kada se kreira izvor podataka.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dijalog koji prikazuje listu entiteta u Dataverse okruženju.":::

7. Sačuvajte svoj izbor da biste započeli sinhronizaciju izabranih tabela iz usluge Dataverse. Novododatu vezu ćete pronaći na stranici **Izvori podataka**. Biće stavljeno u red za osvežavanje i prikazaće broj entiteta kao 0 dok se sve izabrane tabele ne sinhronizuju.

Samo jedan izvor podataka okruženja može istovremeno da koristi isto Dataverse nadgledano jezero.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Uredite izvor podataka za Dataverse upravljano jezero

Izbor entiteta uređujete tek nakon što kreirate izvor podataka. Na primer, ako su dodati dodatni entiteti u uslugu Dataverse, a želite i da ih uvozite.    
Da biste se povezali sa drugim Dataverse jezerom podataka, [kreirajte novi izvor podataka](#connect-to-a-dataverse-managed-lake).

1. U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.

2. Pored izvora podataka koji želite da ažurirate, izaberite tri tačke.

3. Izaberite opciju **Uredi** sa liste.

4. Izaberite dodatne entitete s dostupne liste entiteta i izaberite **Sačuvaj**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]