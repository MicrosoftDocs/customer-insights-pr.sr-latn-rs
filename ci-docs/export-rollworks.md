---
title: Izvoz segmenata u RollWorks (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvezete u RollWorks.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 83c3f2437b9822d29d1d2f99ead96815b1b0881a
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055185"
---
# <a name="export-segments-to-rollworks-preview"></a>Izvoz segmenata u RollWorks (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u RollWorks i koristite ih za oglašavanje. 

## <a name="prerequisites-for-a-connection"></a>Preduslovi za vezu

-   Imate [RollWorks nalog](https://www.rollworks.com/) i odgovarajuće akreditive administratora.
-   Konfigurisali [ste segmente u programu](segments.md) "Uvidi kupaca".
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Možete izvoziti do 250.000 profila klijenata po izvozu u RollWorks.
- Ne možete izvoziti segmente sa manje od 100 profila klijenata u RollWorks. 
- Izvoz u RollWorks ograničen je na segmente.
- Izvoz do 250.000 profila klijenata u RollWorks može potrajati do 10 minuta. 
- Broj profila klijenata koje možete izvesti u RollWorks zavisi i ograničen je na vaš ugovor sa RollWorks-om.

## <a name="set-up-connection-to-rollworks"></a>Podešavanje veze sa uslugom RollWorks

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **RollWorks** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Povežite se** da bi se inicijalizovala veza sa uslugom RollWorks.

1. Izaberite **Potvrdite identitet pomoću usluge RollWorks** i obezbedite svoje administratorske akreditive za RollWorks.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka RollWorks. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. Unesite svoj **ID RollWorks oglašavača** [RollWorks oglas](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta. To je potrebno da izvezete segmente u RollWorks.

1. Izaberite segmente koje želite da izvezete. Izaberite segment sa najmanje 100 članova. Ne možete izvoziti manje segmente. Pored toga, maksimalna veličina segmenta za izvoz je 250.000 članova po izvozu. 

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite Dynamics 365 Customer Insights za prenos podataka u RollWorks, dozvoljavate prenos podataka izvan granica usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da RollWorks ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.