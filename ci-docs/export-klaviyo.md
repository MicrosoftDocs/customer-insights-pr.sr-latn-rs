---
title: Izvoz segmenata u Klaviyo (pregled)
description: Saznajte kako da konfigurišete vezu i izvezete je u uslugu Klaviyo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e2b60d9818a753e81e69f2bee6b1663e1840cb10
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051332"
---
# <a name="export-segments-to-klaviyo-preview"></a>Izvoz segmenata u Klaviyo (pregled)

Izvezite segmente objedinjenih profila klijenata u Klaviyo i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduslovi

-   Imate [Klaviyo nalog](https://www.klaviyo.com/) i odgovarajuće akreditive administratora.
-   Konfigurisali [ste segmente u programu](segments.md) "Uvidi kupaca".
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Možete izvoziti do 100.000 profila klijenata po izvozu u Klaviyo.
- Izvoz u Klaviyo je ograničen na segmente.
- Izvoz do milion profila klijenata u Klaviyo može potrajati do 20 minuta. 
- Broj profila klijenata koje možete izvesti u Klaviyo zavisi i ograničen je na vaš ugovor sa Klaviyo-om.

## <a name="set-up-connection-to-klaviyo"></a>Podešavanje veze sa uslugom Klaviyo

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **Klaviyo** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite svoj [Klaviyo API ključ](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) da biste nastavili sa prijavljivanjem. 

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Poveži se** da biste pokrenuli vezu sa uslugom Klaviyo.

1. Izaberite **Potvrdite autentičnost sa uslugom Klaviyo** i navedite administratorske akreditive za Klaviyo.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Klaviyo. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. Unesite svoj [**ID Klaviyo liste**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta. U Klaviyo morate izvoziti segmente.

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite Dynamics 365 Customer Insights za prenos podataka u Klaviyo, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Klaviyo ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.
