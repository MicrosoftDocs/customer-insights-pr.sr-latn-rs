---
title: Izvoz Customer Insights podataka u ActiveCampaign
description: Saznajte kako da konfigurišete vezu i izvezete je u uslugu ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314668"
---
# <a name="export-segments-to-activecampaign-preview"></a>Izvoz segmenata u ActiveCampaign (verzija za pregled)

Izvezite segmente objedinjenih profila kupaca u ActiveCampaign i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduslovi

-   Imate [ActiveCampaign nalog](https://www.activecampaign.com/) i odgovarajuće akreditive administratora.
-   [Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.
-   Objedinjeni korisnički profili u izvezenim segmentima sadrže polje sa adresom e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Možete izvoziti do 1 milion profila po izvozu u ActiveCampaign, a to može potrajati i do 90 minuta.
- Izvoz u ActiveCampaign je ograničen na segmente.
- Broj profila koje možete da izvezete u ActiveCampaign zavisi od vašeg ugovora sa uslugom ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Podesite vezu sa uslugom ActiveCampaign

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i izaberite **ActiveCampaign** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj [ActiveCampaign API ključ i ime hosta REST krajnje tačke](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). Ime hosta REST krajnje tačke je samo ime hosta, bez https://. 

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Poveži se** za inicijalizaciju veze sa uslugom ActiveCampaign.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, izaberite vezu iz odeljka ActiveCampaign. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. Unesite [**ID ActiveCampaign liste**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

3. U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta. U ActiveCampaign morate izvoziti segmente. Opcionalno, možete da izvezete polja Ime, Prezime i Telefon da biste kreirali personalizovanije adrese e-pošte. Izaberite Dodaj atribut za mapiranje ovih polja.

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite Dynamics 365 Customer Insights za prenos podataka u ActiveCampaign, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da ActiveCampaign ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.