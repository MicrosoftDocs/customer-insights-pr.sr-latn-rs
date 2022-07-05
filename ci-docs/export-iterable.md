---
title: Izvoz segmenata u iterable (pregled)
description: Saznajte kako da konfigurišete vezu i izvezete je u iterable.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 98d5aeab6b0e932d291213053d509ec72da82e47
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052252"
---
# <a name="export-segments-to-iterable-preview"></a>Izvoz segmenata u iterable (pregled)

Izvezite segmente objedinjenih profila kupaca u Iterable i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduslovi

-   Imate Iterable [nalog i odgovarajuće](https://iterable.com/) akreditive administratora.
-   Konfigurisali [ste segmente u programu](segments.md) "Uvidi kupaca".
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Izvoz u Iterable je ograničen na segmente.
- Izvoz do milion profila klijenata u Iterable može da potraje do 30 minuta. 
- Broj profila klijenata koje možete da izvezete u Iterable zavisi i ograničen je na ugovor sa uslugom Iterable.

## <a name="set-up-connection-to-iterable"></a>Podešavanje veze sa iterableom

1. Idite na **Administrator** > **Veze**.

1. Kliknite **na dugme Dodaj** vezu i odaberite **opciju Iterable** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Obezbedite API [ključ koji možete da obezbedite da](https://support.iterable.com/hc/en-us/articles/360043464871) biste nastavili da se prijavljujete. 

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu sa iterable.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odeljka "Iterable". Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

3. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta. Potrebno je da izvezete segmente u Iterable.Lista kreirana u programu Iterable će dobiti potpuno isto ime kao i ime segmenta u programu Dynamics 365 Customer Insights.

1. Izaberite **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite prenos Dynamics 365 Customer Insights podataka u iterable, dozvoljavate prenos podataka izvan granice usaglašenosti za, uključujući Dynamics 365 Customer Insights potencijalno osetljive podatke kao što su lični podaci. Microsoft će preneti takve podatke na vaše uputstvo, ali vi ste odgovorni da obezbedite da Iterable ispunjava sve obaveze privatnosti ili bezbednosti koje možda imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.
