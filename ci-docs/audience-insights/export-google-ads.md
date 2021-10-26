---
title: Izvezite Customer Insights podatke u Google oglasima
description: Saznajte kako da konfigurišete vezu i izvezete u Google Ads.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ce9579f3d31207e666665237fd8935bb86889f8d
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617940"
---
# <a name="export-segments-to-google-ads-preview"></a>Izvoz segmenata u Google Ads (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata na Google Ads listu ciljnih grupa i koristite ih za oglašavanje na Google pretrazi, Gmailu, YouTubeu i Google mreži multimedijalnog oglašavanja. 

> [!IMPORTANT]
> Trenutno možete da kreirate novu vezu i izvozite podatke u Google Ads samo ako već imate odobreni token programera za Google Ads. Zbog promena smernica, uskoro ćemo ažurirati Google Ads izvoz i obezbediti opciju izvoza koja neće zahtevati token programera kako bismo osigurali kontinuitet vašeg iskustva i pojednostavili izvoz u Google Ads. Preporučujemo vam da ne konfigurišete više veza sa Google Ads radi lakšeg prelaska na novu opciju izvoza.

## <a name="prerequisites-for-connection"></a>Preduslovi za vezu

-   Imate [nalog Google oglasa](https://ads.google.com/) i odgovarajuće akreditive administratora.
-   Imate [odobreni token za Google Ads programera](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   Ispunjavate zahteve [politike podudaranja klijenata](https://support.google.com/adspolicy/answer/6299717).
-   Ispunjavate zahteve [za veličine lista za ponovno oglašavanje](https://support.google.com/google-ads/answer/7558048).
-   Postoji postojeća publika u Google oglasima i odgovarajući ID-ovi. Za više informacija pogledajte [Korisnici Google oglasa](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Imate [konfigurisane segmente](segments.md).
-   Objedinjeni korisnički profili u izvezenim segmentima sadrže polja koja predstavljaju adresu e-pošte, ime i prezime.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milion profila klijenata po izvozu u Google Ads.
- Izvoz u Google oglase je ograničen na segmente.
- Izvoz segmenata sa ukupno milion profila klijenata može potrajati do 5 minuta zbog ograničenja na strani provajdera. 
- Podudaranje u Google oglasima može da potraje do 48 sati.

## <a name="set-up-connection-to-google-ads"></a>Podešavanje veze sa uslugom Google Ads

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **Google Ads** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **[ID klijenta za Google oglase](https://support.google.com/google-ads/answer/1704344)**.

1. Unesite **[token odobrenog programera za Google oglase](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Potvrdite identitet u Google oglasima** i navedite akreditive za Google oglase.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu. 

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Google Ads. Ako ne vidite naziv ovog odeljka, tada vam nisu dostupne veze ovog tipa.

1. Unesite **[ID korisnika za Google oglase](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** i izaberite **Povežite se** da biste započeli povezivanje sa Google oglasima.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta.

1. Izaberite segmente koje želite da izvezete. U Google oglasima možete ukupno izvesti do 1 milion korisničkih profila.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). 

Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Google oglase, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Google oglasi ispunjavaju sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
