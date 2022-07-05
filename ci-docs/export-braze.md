---
title: Izvoz segmenata u Braze (pregled)
description: Saznajte kako da konfigurišete vezu i izvezete u Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082687"
---
# <a name="export-segments-to-braze-preview"></a>Izvoz segmenata u Braze (pregled)

Izvezite segmente objedinjenih profila kupaca u Braze i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduslovi

- Braze [nalog i](https://www.braze.com/) odgovarajući administratorski akreditivi.
- Postojeći [segmenti u Brazeu](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.
- Objedinjeni profili kupaca u izvezenim segmentima sadrže polje koje predstavlja e-adresu i ID kupca Brazea.

## <a name="known-limitations"></a>Poznata ograničenja

- Izvoz u Braze je ograničen na segmente.
- Izvoz do milion profila kupaca u Braze može da potraje i do 40 minuta.
- Broj profila kupaca koje možete da izvezete u Braze zavisi i ograničen je na vaš ugovor sa Brazeom.

## <a name="set-up-connection-to-braze"></a>Uspostavi vezu sa Brazeom

1. Idite na **Administrator** > **Veze**.

1. Kliknite **na dugme Dodaj** vezu i odaberite **Braze** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Obezbedite [braze API ključ da biste](https://www.braze.com/docs/api/basics/) nastavili da se prijavljujete.

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu sa Brazeom.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz** odaberite vezu iz odeljka Braze. Ako ne vidite ovaj odeljak, ne postoje veze ovog tipa koje su vam dostupne.  

1. Dodajte **ime za prikaz** za izvoz.

1. Dodajte API identifikator segmenta Braze u koji želite da izvezete **u polje Braze Segment API Identifikator**. Identifikator možete pronaći u detaljima segmenta na Braze platformi.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta. U polju **ID kupca** izaberite polje koje predstavlja Braze ID kupca. Potrebno je izvoziti segmente u Braze. Opcionalno možete odabrati više polja.

1. Izaberite **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite prenos Dynamics 365 Customer Insights podataka Brazeu, dozvoljavate prenos podataka izvan granice usaglašenosti za, uključujući Dynamics 365 Customer Insights potencijalno osetljive podatke kao što su lični podaci. Microsoft će preneti takve podatke po vašem uputstvu, ali vi ste odgovorni da obezbedite da Braze ispuni sve obaveze privatnosti ili bezbednosti koje možda imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.
