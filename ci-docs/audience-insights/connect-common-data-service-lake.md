---
title: Povežite se sa entitetima u Common Data Service nadgledanom jezeru
description: Uvoz podataka iz Common Data Service upravljanog jezera podataka.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596976"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Povežite se sa podacima u Common Data Service upravljanom jezeru podataka

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Ovaj članak pruža informacije o tome kako postojeći Dynamics 365 korisnici mogu brzo da se povežu sa svojim analitičkim entitetima u Common Data Service upravljanom jezeru. Morate biti administrator Common Data Service organizacije kako biste nastavili i videli spisak entiteta dostupnih u upravljanom jezeru.

## <a name="important-considerations"></a>Važna razmatranja

Podaci uskladišteni u mrežnim uslugama, kao što je Azure Data Lake Storage, mogu se skladištiti na lokaciji različitoj od one na kojoj se podaci obrađuju ili skladište u usluzi Dynamics 365 Customer Insights. Uvozom ili povezivanjem podataka uskladištenih u mrežnoj usluzi, slažete se da se podaci mogu preneti i skladištiti u usluzi Dynamics 365 Customer Insights. [Saznajte više u Microsoft centru za pouzdanost.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Povežite se sa Common Data Service upravljanim jezerom

1. U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.

2. Izaberite **Dodaj izvor podataka**.

3. Izaberite **Povezivanje sa uslugom Common Data Service** i izaberite **Sledeće**.

4. Unesite **Naziv** izvora podataka i izaberite **Sledeće**. Smernice za nazive: 
   - Započnite slovom.
   - Koristite samo slova i brojeve. Posebni znakovi i razmaci nisu dozvoljeni.
   - Koristite između 3 i 64 znaka.

5. Navedite **Adresu servera** za vašu Common Data Service organizaciju i izaberite **Prijavite se**.

   > [!div class="mx-imgBorder"]
   > ![Dijalog za unos Common Data Service adrese servera](media/enter-CDS-org-details.png)

6. Izaberite entitete koje želite da unesete sa dostupne liste.    

   > [!NOTE]
   > Ako su neki entiteti već izabrani, mogu ih koristiti druge Dynamics 365 aplikacije (kao što su Dynamics 365 Sales Insights ili Customer Service Insights). Ne možete promeniti izbor. Ovi entiteti će biti dostupni nakon kreiranja izvora podataka.

   > [!div class="mx-imgBorder"]
   > ![Dijalog koji prikazuje listu entiteta u Common Data Service organizaciji](media/select-analytical-entities.png)

7. Sačuvajte svoj izbor da biste započeli sinhronizaciju izabranih entiteta sa Common Data Service upravljanim jezerom. Novododatu vezu ćete pronaći na stranici **Izvori podataka**. Biće postavljena u red za osvežavanje i prikazaće brojeve entiteta kao 0 dok se svi entiteti ne sinhronizuju.

Samo jedan izvor podataka okruženja može istovremeno da koristi isto Common Data Service nadgledano jezero.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Uredite izvor podataka za Common Data Service upravljano jezero

Izbor entiteta uređujete tek nakon što kreirate izvor podataka. Na primer, ako su dodati dodatni entiteti u uslugu Common Data Service, a želite i da ih uvozite.    
Da biste se povezali sa drugom uslugom Common Data Service, [kreirajte novi izvor podataka](#connect-to-a-common-data-service-managed-lake).

1. U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.

2. Pored izvora podataka koji želite da ažurirate, izaberite tri tačke.

3. Izaberite opciju **Uredi** sa liste.

4. Izaberite dodatne entitete s dostupne liste entiteta i izaberite **Sačuvaj**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]