---
title: Izvezite Customer Insights podatke u SendGrid
description: Saznajte kako da konfigurišete vezu sa uslugom SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268749"
---
# <a name="connector-for-sendgrid-preview"></a>Konektor za SendGrid (pregled)

Izvezite segmente objedinjenih profila klijenata u SendGrid liste kontakata i koristite ih za kampanje i marketing u usluzi SendGrid. 

## <a name="prerequisites"></a>Preduslovi

-   Imate [SendGrid nalog](https://sendgrid.com/) i odgovarajuće akreditive administratora.
-   Postoje postojeće liste kontakata u usluzi SendGrid i odgovarajući ID-ovi. Za više informacija pogledajte [SendGrid – Upravljanje kontaktima](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   [Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="connect-to-sendgrid"></a>Povežite se sa uslugom SendGrid

1. Idite na **Administrator** > **Odredišta za izvoz**.

1. U delu **SendGrid** izaberite **Podesi**.

1. Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Okno za konfiguraciju izvoza u usluzi SendGrid.":::

1. Unesite svoj **SendGrid API ključ** [SendGrid API ključ](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Unesite **[ID SendGrid liste](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Poveži se** za inicijalizaciju veze sa uslugom SendGrid.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sledeće** da biste konfigurisali izvoz.

## <a name="configure-the-connector"></a>Konfigurisanje konektora

1. U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta. Ponovite iste korake za druga opcionalna polja kao što su **Ime**, **Prezime**, **Zemlja/Region**, **Država**, **Grad** i **Poštanski broj**.

1. Izaberite segmente koje želite da izvezete. Izričito **preporučujemo da ne izvozite ukupno više od 100.000 profila klijenata** u SendGrid. 

1. Izaberite stavku **Sačuvaj**.

## <a name="export-the-data"></a>Izvoz podataka

Možete da [izvezete podatke na zahtev](export-destinations.md). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).

## <a name="known-limitations"></a>Poznata ograničenja

- Ukupno do 100.000 profila u SendGrid.
- Izvoz u SendGrid je ograničen na segmente.
- Izvoz do 100.000 profila u SendGrid može da potraje do nekoliko sati. 
- Broj profila koje možete da izvezete u SendGrid zavisi od vašeg ugovora sa kompanijom SendGrid i ograničen je njime.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u SendGrid, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da SendGrid ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]