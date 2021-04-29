---
title: Izvoz Customer Insights podataka u AdRoll
description: Saznajte kako da konfigurišete vezu i izvezete u AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895976"
---
# <a name="export-segment-lists-to-adroll-preview"></a>Izvoz listi segmenata u AdRoll (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u AdRoll i koristite ih za oglašavanje. 

## <a name="prerequisites-for-a-connection"></a>Preduslovi za vezu

-   Imate [AdRoll nalog](https://www.adroll.com/) i odgovarajuće akreditive administratora.
-   [Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- U uslugu AdRoll možete da izvezete ukupno do 250.000 profila po izvozu.
- U AdRoll ne možete da izvezete segmente sa manje od 100 profila. 
- Izvoz u AdRoll je ograničen na segmente.
- Izvoz do 250.000 profila u AdRoll može da potraje do 10 minuta. 
- Broj profila koje možete da izvezete u AdRoll zavisi od i ograničen je vašim ugovorom sa kompanijom AdRoll.

## <a name="set-up-connection-to-adroll"></a>Podešavanje veze u usluzi AdRoll

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **AdRoll** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Poveži se** za inicijalizaciju veze sa uslugom AdRoll.

1. Izaberite **Potvrdite identitet u usluzi AdRoll** i navedite svoje akreditive administratora za AdRoll. 

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka AdRoll. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. Unesite svoj **ID AdRoll oglašavača** Za više informacija, pogledajte članak [Profili AdRoll oglašavača](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta. To je potrebno za izvoz segmenata u AdRoll.

1. Izaberite segmente koje želite da izvezete. Izaberite segment sa najmanje 100 članova. Ne možete izvoziti manje segmente. Pored toga, maksimalna veličina segmenta za izvoz je 250.000 članova po izvozu. 

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u AdRoll, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da AdRoll ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.
