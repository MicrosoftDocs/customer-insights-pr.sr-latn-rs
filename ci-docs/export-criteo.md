---
title: Izvoz segmenata u Criteo (pregled)
description: Saznajte kako da konfigurišete vezu i izvezete u Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082792"
---
# <a name="export-segments-to-criteo-preview"></a>Izvoz segmenata u Criteo (pregled)

Izvezite segmente objedinjenih profila klijenata da biste generisali kampanje, obezbedili marketing e-pošte i koristili određene grupe klijenata sa programom Criteo.

## <a name="prerequisites-for-connection"></a>Preduslovi za vezu

-   Imate [Criteo Dynamics Retargeting nalog i odgovarajuće](https://www.criteo.com/login/) akreditive administratora.
-   Imate [konfigurisane segmente](segments.md).
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milion profila klijenata po izvozu u Criteo.
- Izvoz u Criteo je ograničen na segmente.
- Izvoz segmenata sa ukupno milion profila kupaca može da potraje do 30 minuta. 
- Broj profila klijenata koje možete da izvezete u Criteo zavisi i ograničen je na vaš ugovor sa Criteom.

## <a name="set-up-connection-to-criteo"></a>Uspostavi vezu sa Criteom

1. Idite na **Administrator** > **Veze**.

1. Kliknite **na dugme Dodaj** vezu i odaberite **Criteo** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izaberite **opciju Slažem** se da potvrdim **privatnost i usaglašenost podataka** i izaberite **poveži** se da biste povezali vezu sa Criteom.

1. Izaberite **potvrdu identiteta pomoću programa Criteo** i obezbedite administratoru korisničko ime i akreditive za Criteo. 

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odeljka Criteo. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne. 

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta. 

1. Opcionalno, možete da izvezete **ID oglašivača** i **ime**

1. Izaberite segmente koje želite da izvezete. 

1. Izaberite **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite Dynamics 365 Customer Insights prenos podataka u Criteo, dozvoljavate prenos podataka izvan granice usaglašenosti za, uključujući Dynamics 365 Customer Insights potencijalno osetljive podatke kao što su lični podaci. Microsoft će preneti takve podatke na vaše uputstvo, ali vi ste odgovorni za to da osigurate da Criteo ispunjava sve obaveze privatnosti ili bezbednosti koje možda imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.


[!INCLUDE[footer-include](includes/footer-banner.md)]
