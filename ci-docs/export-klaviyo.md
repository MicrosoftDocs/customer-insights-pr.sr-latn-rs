---
title: Izvoz segmenata u Klaviyo (pregled)
description: Saznajte kako da konfigurišete vezu i izvezete je u uslugu Klaviyo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e45ca5827afa29d97a746bd1a474c2346cc32d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196779"
---
# <a name="export-segments-to-klaviyo-preview"></a>Izvoz segmenata u Klaviyo (pregled)

Izvezite segmente objedinjenih profila klijenata u Klaviyo i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduslovi

- [Klaviyo nalog i odgovarajući](https://www.klaviyo.com/) administratorski akreditivi.
- [Klaviyo API kljuи](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys).
- ID [Klaviyo liste](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milion profila kupaca po izvozu u Klaviyo, što može da potraje i do 20 minuta. Broj profila kupaca koje možete da izvezete u Klaviyo zavisi od vašeg ugovora sa Klaviyom.
- Samo segmenti.

## <a name="set-up-connection-to-klaviyo"></a>Podešavanje veze sa uslugom Klaviyo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i odaberite **Klaviyo**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite svoj Klaviyo API ključ da biste nastavili sa prijavljivanjem.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu.

1. Izaberite **Potvrdite autentičnost sa uslugom Klaviyo** i navedite administratorske akreditive za Klaviyo.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Klaviyo. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Unesite **ID Klaviyo liste**.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
