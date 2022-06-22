---
title: Izvoz Customer Insights podataka u Snapchat
description: Saznajte kako da konfigurišete vezu i izvezete u Snapchat.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d64b482c322af8632e29ec41d6e34c390c5e646c
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947293"
---
# <a name="export-segments-to-snapchat-preview"></a>Izvoz segmenata u Snapchat (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u Snapchat i koristite ih za oglašavanje. 

## <a name="prerequisites-for-a-connection"></a>Preduslovi za vezu

-   Imate [Snapchat Business nalog](https://business.snapchat.com/), [Snapchat Ads nalog](https://ads.snapchat.com/) i odgovarajuće akreditive administratora. YOu mora biti bar član naloga organizacije i menadžer podataka određenog naloga oglasa. 
-   Imate najmanje jedan korisnici Snapchat korisnici tipa SAM (Snap korisnici Match). 
-   Konfigurisali [ste segmente u programu](segments.md) "Uvidi kupaca".
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Izvoz u Snapchat ograničen je na segmente.
- Izvoz do 1 miliona profila klijenata u Snapchat može potrajati do 15 minuta. 

## <a name="set-up-connection-to-snapchat"></a>Podešavanje veze u usluzi Snapchat

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **Snapchat** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Povežite se** da bi se inicijalizovala veza sa uslugom Snapchat.

1. Izaberite **Potvrdite identitet pomoću usluge Snapchat** i obezbedite svoje administratorske akreditive za Snapchat. 

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Snapchat. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. Unesite [**Snapchat segment/korisnici ID**](https://businesshelp.snapchat.com/s/article/custom-audiences). ID datoteke se korisnici u URL adresi nakon što izaberete korisnici u programu Snapchat korisnici Manager. 

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta. To je potrebno da izvezete segmente u Snapchat.

1. Izaberite segmente koje želite da izvezete. 

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite Dynamics 365 Customer Insights za prenos podataka u Snapchat, dozvoljavate prenos podataka izvan granica usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Snapchat ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.
