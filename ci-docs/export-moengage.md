---
title: Izvoz segmenata u MoEngage
description: Saznajte kako da konfigurišete vezu i izvezete u MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199237"
---
# <a name="export-segments-to-moengage-preview"></a>Izvoz segmenata u MoEngage (pregled)

Izvezite segmente objedinjenih profila klijenata u MoEngage i koristite ih za marketing e-pošte u MoEngageu.

## <a name="prerequisites-for-a-connection"></a>Preduslovi za vezu

- [MoEngage nalog i](https://www.moengage.com/) odgovarajući administratorski akreditivi.
- MoEngage API ključ iz podešavanja > API u MoEngageu.
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.

## <a name="known-limitations"></a>Poznata ograničenja

- Do 100.000 profila kupaca po izvozu u MoEngage, što može da potraje i do 15 minuta. Broj profila klijenata koje možete da izvezete u MoEngage zavisi od vašeg ugovora sa MoEngageom.
- Samo segmenti.

## <a name="set-up-connection-to-moengage"></a>Uspostavi vezu sa MoEngageom

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Kliknite **na dugme Dodaj** vezu i odaberite **opciju MoEngage** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite [Svoj MoEngage Data API ID i API ključ](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu sa moEngageom.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odeljka MoEngage. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta. Ponovite iste korake za druga opcionalna polja.

1. Izaberite segmente koje želite da izvezete. Kreiraćemo jedan ili više segmenata sa istim imenom kao izabrani segmenti u MoEngageu u okviru **"Segmenti prilagođenih** > **segmenata"**.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
