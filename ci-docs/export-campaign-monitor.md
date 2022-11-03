---
title: Izvoz segmenata u Campaign Monitor (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvezete sadržaj u Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 82303c7bcb269ee68419c9639ee743e13451f273
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724701"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Izvoz segmenata u Campaign Monitor (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u Campaign Monitor i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduslovi

- Nalog [nadgledanja kampanje i](https://www.campaignmonitor.com/) odgovarajuće akreditive administratora.
- [ID liste nadgledanja kampanje](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Generisani [API ključ iz postavki](https://www.campaignmonitor.com/api/getting-started/) naloga **u programu** "Nadgledanje kampanje" da biste dobili ID API liste.
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Privatna veza u kombinaciji sa "Donesi sopstveno skladište" (BYOS) nije podržana.
- Do milion profila klijenata po izvozu u nadgledanje kampanje, što može da potraje i do 20 minuta. Broj profila klijenata koje možete da izvezete u nadgledanje kampanje zavisi od ugovora sa nadgledanje kampanje.
- Samo segmenti.

## <a name="set-up-connection-to-campaign-monitor"></a>Podešavanje veze sa uslugom Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **stavku Dodaj vezu** i odaberite **nadgledanje kampanje**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Izaberite **Povežite se** da bi se inicijalizovala veza sa uslugom Campaign Monitor.

1. Izaberite **Potvrdite identitet pomoću usluge Campaign Monitor** i obezbedite svoje administratorske akreditive za Campaign Monitor.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Campaign Monitor. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Unesite ID **liste nadgledanja kampanje**.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta. To je potrebno da izvezete segmente u Campaign Monitor.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
