---
title: Izvoz Customer Insights podataka u AdRoll
description: Saznajte kako da konfigurišete vezu sa uslugom AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697091"
---
# <a name="connector-for-adroll-preview"></a>Konektor za AdRoll (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u AdRoll i koristite ih za oglašavanje. 

## <a name="prerequisites"></a>Preduslovi

-   Imate [AdRoll nalog](https://www.adroll.com/) i odgovarajuće akreditive administratora.
-   [Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="connect-to-adroll"></a>Povežite se sa uslugom AdRoll

1. Idite na **Administrator** > **Odredišta za izvoz**.

1. U odeljku **AdRoll** izaberite **Podesi**.

1. Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Okno za konfiguraciju za vezu sa uslugom AdRoll.":::

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Poveži se** za inicijalizaciju veze sa uslugom AdRoll.

1. Izaberite **Potvrdite identitet u usluzi AdRoll** i navedite svoje akreditive administratora za AdRoll. 

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Unesite svoj **ID AdRoll oglašavača** [koji može da se oglašava u usluzi AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Izaberite **Sledeće** da biste konfigurisali izvoz.

## <a name="configure-the-connector"></a>Konfigurisanje konektora

1. U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta. To je potrebno za izvoz segmenata u AdRoll.

1. Izaberite segmente koje želite da izvezete. Izaberite segment sa najmanje 100 članova. Ne možete izvoziti manje segmente. Pored toga, maksimalna veličina segmenta za izvoz je 250.000 članova po izvozu. 

1. Izaberite stavku **Sačuvaj**.

## <a name="export-the-data"></a>Izvoz podataka

Možete da [izvezete podatke na zahtev](export-destinations.md). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).

## <a name="known-limitations"></a>Poznata ograničenja

- U uslugu AdRoll možete da izvezete ukupno do 250.000 profila po izvozu.
- U AdRoll ne možete da izvezete segmente sa manje od 100 profila. 
- Izvoz u AdRoll je ograničen na segmente.
- Izvoz do 250.000 profila u AdRoll može da potraje do 10 minuta. 
- Broj profila koje možete da izvezete u AdRoll zavisi od i ograničen je vašim ugovorom sa kompanijom AdRoll.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u AdRoll, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da AdRoll ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.
