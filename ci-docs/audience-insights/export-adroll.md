---
title: Izvoz Customer Insights podataka u AdRoll
description: Saznajte kako da konfigurišete vezu i izvezete u AdRoll.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f9373ea18e77723c988392a5a2959baa66d8eae9
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617366"
---
# <a name="export-segments-to-adroll-preview"></a>Izvoz segmenata u AdRoll (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u AdRoll i koristite ih za oglašavanje. 

## <a name="prerequisites-for-a-connection"></a>Preduslovi za vezu

-   Imate [AdRoll nalog](https://www.adroll.com/) i odgovarajuće akreditive administratora.
-   [Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- U AdRoll možete istovremeno izvoziti do 250.000 profila klijenata.
- Ne možete izvoziti segmente sa manje od 100 profila klijenata u AdRoll. 
- Izvoz u AdRoll je ograničen na segmente.
- Izvoz do 250.000 profila klijenata u AdRoll može potrajati do 10 minuta. 
- Broj profila klijenata koje možete izvesti u AdRoll zavisi od vašeg ugovora sa AdRoll-om.

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

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka AdRoll. Ako ne vidite naziv ovog odeljka, tada vam nisu dostupne veze ovog tipa.

1. Unesite svoj **ID AdRoll oglašavača**. Za više informacija, pogledajte članak [Profili AdRoll oglašavača](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta. To je potrebno za izvoz segmenata u AdRoll.

1. Izaberite segmente koje želite da izvezete. Izaberite segment sa najmanje 100 članova. Ne možete izvoziti manje segmente. Pored toga, maksimalna veličina segmenta za izvoz je 250.000 članova po izvozu. 

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). 

Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u AdRoll, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da AdRoll ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.
