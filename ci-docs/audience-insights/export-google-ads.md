---
title: Izvezite Customer Insights podatke u Google oglasima
description: Saznajte kako da konfigurišete vezu sa Google oglasima.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568493"
---
# <a name="connector-for-google-ads-preview"></a>Konektor za Google oglase (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u listu korisnika Google oglasa i koristite ih za oglašavanje u Google pretrazi, na Gmail-u, YouTube-u i Google mreži multimedijalnog oglašavanja. 

## <a name="prerequisites"></a>Preduslovi

-   Imate [nalog Google oglasa](https://ads.google.com/) i odgovarajuće akreditive administratora.
-   Postoji postojeća publika u Google oglasima i odgovarajući ID-ovi. Za više informacija pogledajte [Korisnici Google oglasa](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Imate [konfigurisane segmente](segments.md)
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polja koja predstavljaju adresu e-pošte, ime i prezime

## <a name="connect-to-google-ads"></a>Povežite se sa Google oglasima

1. Idite na **Administrator** > **Odredišta za izvoz**.

1. U odeljku **Google oglasi**, izaberite **Podesi**.

1. Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.

1. Unesite **[ID klijenta za Google oglase](https://support.google.com/google-ads/answer/1704344)**.

1. Unesite **[token odobrenog programera za Google oglase](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Unesite **[ID korisnika za Google oglase](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** i izaberite **Povežite se** da biste započeli povezivanje sa Google oglasima.

1. Izaberite **Potvrdite identitet u Google oglasima** i navedite akreditive za Google oglase.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Izvezite snimak ekrana za vezu sa Google oglasima":::

1. Izaberite **Sledeće** da biste konfigurisali izvoz.

## <a name="configure-the-connector"></a>Konfigurisanje konektora

1. U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta. Ponovite iste korake za polja **Ime** i **Prezime**.

1. Izaberite segmente koje želite da izvezete. U Google oglasima možete ukupno izvesti do 1 milion korisničkih profila.

1. Izaberite stavku **Sačuvaj**.

## <a name="export-the-data"></a>Izvoz podataka

Možete da [izvezete podatke na zahtev](export-destinations.md). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab). U Google oglasima sada možete pronaći segmente u odeljku [Korisnici Google oglasa](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Poznata ograničenja

- Do 1 milion profila po izvozu u Google oglasima.
- Izvoz u Google oglase je ograničen na segmente.
- Izvoz segmenata sa ukupno 1 milion profila može trajati do 5 minuta zbog ograničenja na strani dobavljača. 
- Podudaranje u Google oglasima može da potraje do 48 sati.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Google oglase, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Google oglasi ispunjavaju sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.
