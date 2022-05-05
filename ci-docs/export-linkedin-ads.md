---
title: Izvoz Customer Insights podataka u LinkedIn Ads
description: Saznajte kako da konfigurišete vezu i izvozite u LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bf1d12ffbd7a4cfd7d268fea8a1f90cc37589e00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643925"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Izvoz segmenata u LinkedIn Ads (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u LinkedIn Ads da biste kreirali podudarnu ciljnu grupu. Koristite podudarnu ciljnu grupu za ciljanje preduzeća i ciljanje kontakata.

## <a name="prerequisites"></a>Preduslovi

-   Imate [LinkedIn Campaign Manager nalog](https://business.linkedin.com/marketing-solutions/ads) i odgovarajuće akreditive administratora.
-   Konfigurisali [ste segmente u programu](segments.md) "Uvidi kupaca".
-   Korisnički profili u izvezenim segmentima sadrže polje sa adresom e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Vaš segment u uvidima kupaca treba da sadrži najmanje 300 jedinstvenih profila. 
- Možete izvoziti do 100.000 profila klijenata po izvozu u LinkedIn Ads.
- Izvoz u LinkedIn Ads ograničen je na segmente.
- Izvoz do 100.000 profila klijenata u LinkedIn Ads može potrajati do 10 minuta. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Podesite vezu sa uslugom LinkedIn Ads

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **LinkedIn Ads** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevaju se Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite svoj [ID LinkedIn Campaign Manager naloga](https://www.linkedin.com/help/lms/answer/a424270).

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Povežite se** da bi se inicijalizovala veza sa uslugom Campaign Monitor.

1. Izaberite **Potvrdite identitet pomoću usluge LinkedIn** i obezbedite svoje administratorske akreditive za LinkedIn Campaign Manager.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka LinkedIn Ads. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. Odaberite da li želite da izvezete podatke da obavite [kontakt ciljanje](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ili [ciljanje kompanije](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) u usluzi LinkedIn. 

1. U odeljku **Podudaranje podataka**, za ciljanje kontakata izaberite najmanje jedno polje koje predstavlja e-adresu klijenta, Apple Ad ID, ID Google oglasa, Google ID korisnika, ili ime i prezime. Ako odaberete ciljanje preduzeća, izaberite barem jedno polje koje predstavlja naziv preduzeća, domen e-pošte, URL LinkedIn stranice, simbol akcije ili veb-lokaciju. Dodatna polja se mogu izabrati za dodatnu definiciju izvoza. 

1. Izaberite segmente koje želite da izvezete. Publika koja se podudara u usluzi LinkedIn Campaign Manager automatski će se kreirati sa nazivom segmenata koje ste izabrali za izvoz. Svaki segment će rezultirati zasebnom podudarnom ciljnom grupom. 

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite Dynamics 365 Customer Insights za prenos podataka u LinkedIn Ads, dozvoljavate prenos podataka izvan granica usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da LinkedIn Ads ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.
