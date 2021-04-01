---
title: Izvezite Customer Insights podatke u DotDigital
description: Saznajte kako da konfigurišete vezu sa uslugom DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598034"
---
# <a name="connector-for-dotdigital-preview"></a>Konektor za DotDigital (verzija za pregled)

Izvezite segmente objedinjenih profila kupaca u DotDigital adresare i koristite ih za kampanje, marketing putem e-pošte i za izgradnju segmenata kupaca pomoću usluge DotDigital. 

## <a name="prerequisites"></a>Preduslovi

-   Imate [DotDigital nalog](https://dotdigital.com/) i odgovarajuće akreditive administratora.
-   Postoji postojeća publika u adresarima u usluzi DotDigital i odgovarajući ID-ovi. ID se može naći u URL-u kada odaberete i otvorite adresar. Za više informacija pogledajte [adresare za DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   [Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="connect-to-dotdigital"></a>Povezivanje sa uslugom DotDigital

1. Idite na **Administrator** > **Odredišta za izvoz**.

1. U odeljku **DotDigital**, izaberite **Podesi**.

1. Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Okno za konfiguraciju izvoza usluge DotDigital.":::

1. Unesite svoje **korisničko ime i lozinku za DotDigital**.

1. Unesite **[ID DotDigital adresara](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Poveži se** za inicijalizaciju veze sa uslugom DotDigital.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sledeće** da biste konfigurisali izvoz.

## <a name="configure-the-connector"></a>Konfigurisanje konektora

1. U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta. Ponovite iste korake za druga opcionalna polja kao što su **Ime**, **Prezime**, **Puno ime**, **Pol** i **Poštanski broj**.

1. Izaberite segmente koje želite da izvezete. U usluzi DotDigital možete ukupno izvesti do 1 milion korisničkih profila.

1. Izaberite stavku **Sačuvaj**.

## <a name="export-the-data"></a>Izvoz podataka

Možete da [izvezete podatke na zahtev](export-destinations.md). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab). U usluzi DotDigital sada možete da pronađete svoje segmente u [DotDigital adresarima](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Poznata ograničenja

- Do 1 milion profila po izvozu u usluzi DotDigital.
- Izvoz u DotDigital je ograničen na segmente.
- Izvoz segmenata sa ukupno 1 milion profila može trajati do 3 sata zbog ograničenja na strani dobavljača. 
- Broj profila koje možete da izvezete u DotDigital zavisi od i ograničen je vašim ugovorom sa kompanijom DotDigital.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u DotDigital, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da DotDigital ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]