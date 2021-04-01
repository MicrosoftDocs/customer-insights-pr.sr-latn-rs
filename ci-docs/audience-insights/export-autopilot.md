---
title: Izvezite Customer Insights podatke u Autopilot
description: Saznajte kako da konfigurišete vezu sa uslugom Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596148"
---
# <a name="connector-for-autopilot-preview"></a>Konektor za Autopilot (pregled)

Izvezite segmente objedinjenih profila klijenata u Autopilot i koristite ih za marketing putem e-pošte u usluzi Autopilot. 

## <a name="prerequisites"></a>Preduslovi

-   Imate [Autopilot nalog](https://www.autopilothq.com/) i odgovarajuće akreditive administratora.
-   [Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="connect-to-autopilot"></a>Povezivanje sa uslugom Autopilot

1. Idite na **Administrator** > **Odredišta za izvoz**.

1. U delu **Autopilot** izaberite **Podesi**.

1. Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Okno za konfiguraciju za vezu sa uslugom Autopilot.":::

1. Unesite svoj **API ključ za Autopilot** [API ključ za Autopilot](https://autopilot.docs.apiary.io/#).

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Poveži se** za inicijalizaciju veze sa uslugom Autopilot.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sledeće** da biste konfigurisali izvoz.

## <a name="configure-the-connector"></a>Konfigurisanje konektora

1. U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta. Ponovite iste korake za druga opcionalna polja kao što su **Ime**, **Prezime**.

1. Izaberite segmente koje želite da izvezete. Izričito **preporučujemo da ne izvozite ukupno više od 100.000 profila klijenata** u Autopilot. 

1. Izaberite stavku **Sačuvaj**.

## <a name="export-the-data"></a>Izvoz podataka

Možete da [izvezete podatke na zahtev](export-destinations.md). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).

## <a name="known-limitations"></a>Poznata ograničenja

- U uslugu Autopilot možete da izvezete ukupno do 100.000 profila.
- Izvoz u Autopilot je ograničen na segmente.
- Izvoz do 100.000 profila u Autopilot može da potraje do nekoliko sati. 
- Broj profila koje možete da izvezete u Autopilot zavisi od vašeg ugovora sa kompanijom Autopilot i ograničen je njime.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Autopilot, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Autopilot ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]