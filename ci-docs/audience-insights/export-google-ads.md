---
title: Izvezite Customer Insights podatke u Google oglasima
description: Saznajte kako da konfigurišete vezu i izvezete u Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7a85237f7aff564d6b540b2c11553a52f875fac4
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523822"
---
# <a name="export-segments-to-google-ads-preview"></a>Izvoz segmenata u Google Ads (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata na Google Ads listu ciljnih grupa i koristite ih za oglašavanje na Google pretrazi, Gmailu, YouTubeu i Google mreži multimedijalnog oglašavanja. 


## <a name="prerequisites-for-connection"></a>Preduslovi za vezu

-   Imate [nalog Google oglasa](https://ads.google.com/) i odgovarajuće akreditive administratora.
-   Ispunjavate zahteve [politike podudaranja klijenata](https://support.google.com/adspolicy/answer/6299717).
-   Ispunjavate zahteve [za veličine lista za ponovno oglašavanje](https://support.google.com/google-ads/answer/7558048).
-   Imate [konfigurisane segmente](segments.md).
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polja koja predstavljaju e-adresu, telefon, ID mobilnog oglašivača, ID korisnika nezavisnog proizvođača ili adresu.

## <a name="known-limitations"></a>Poznata ograničenja

- Izvoz u Google oglase je ograničen na segmente.
- Izvoz segmenata sa ukupno milion profila klijenata može da potraje do 30 minuta zbog ograničenja na strani dobavljača. 
- Podudaranje u Google oglasima može da potraje do 48 sati.

## <a name="set-up-connection-to-google-ads"></a>Podešavanje veze sa uslugom Google Ads

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **Google Ads** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **[ID klijenta za Google oglase](https://support.google.com/google-ads/answer/1704344)**.

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Potvrdite identitet u Google oglasima** i navedite akreditive za Google oglase.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu. 

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Google Ads. Ako ne vidite naziv ovog odeljka, tada vam nisu dostupne veze ovog tipa.

1. Ako želite da kreirate novi korisnici, ostavite Google korisnici ID polje prazno. Automatski ćemo kreirati novi korisnici u vašem Google Ads nalogu i koristiti ime izvezenog segmenta. Ako želite da ažurirate postojeći Google Ads korisnici, unesite svoj [Google Ads korisnici ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. U odeljku **Podudaranje podataka** izaberite jedno ili više polja podataka za izvoz i izaberite polje koje predstavlja odgovarajuća polja podataka u uvidima kupaca.

1. Izaberite segmente koje želite da izvezete. 

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). 

Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Google oglase, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Google oglasi ispunjavaju sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
