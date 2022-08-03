---
title: Izvoz segmenata u iterable (pregled)
description: Saznajte kako da konfigurišete vezu i izvezete je u iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ccf10b6e3a28a75f9d1bd3d8da3bf870ebc2b1b2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195446"
---
# <a name="export-segments-to-iterable-preview"></a>Izvoz segmenata u iterable (pregled)

Izvezite segmente objedinjenih profila kupaca u Iterable i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduslovi

- Iterable [nalog i](https://iterable.com/) odgovarajuće akreditive administratora.
- Iterable [API ključ](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milion profila klijenata do Iterable-a, što može da potraje i do 30 minuta. Broj profila klijenata koje možete da izvezete u iterable zavisi od ugovora sa uslugom Iterable.
- Samo segmenti.

## <a name="set-up-connection-to-iterable"></a>Podešavanje veze sa iterableom

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **dodaj vezu i** odaberite **stavku Iterable**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Obezbedite API ključ koji možete da obezbedite da biste nastavili da se prijavljujete.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odeljka "Iterable". Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta. Lista kreirana u programu Iterable dobiće potpuno isto ime kao ime segmenta u programu Dynamics 365 Customer Insights.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
