---
title: Izvoz segmenata u RollWorks (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvezete u RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e13aeca4ee5309f85e7de2986cd1a2ba5d2992fb
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195629"
---
# <a name="export-segments-to-rollworks-preview"></a>Izvoz segmenata u RollWorks (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u RollWorks i koristite ih za oglašavanje.

## <a name="prerequisites"></a>Preduslovi

- RollWorks [nalog i](https://www.rollworks.com/) odgovarajući administratorski akreditivi.
- ID [oglašivača rollWorksa](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do 250.000 profila kupaca po izvozu u RollWorks, što može da potraje i do 10 minuta. Broj profila kupaca koje možete da izvezete u RollWorks zavisi od ugovora sa rollWorks-om.
- Samo segmenti.

## <a name="set-up-connection-to-rollworks"></a>Podešavanje veze sa uslugom RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **dodaj vezu i** odaberite **RollWorks**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu.  Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu.

1. Izaberite **Potvrdite identitet pomoću usluge RollWorks** i obezbedite svoje administratorske akreditive za RollWorks.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka RollWorks. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Unesite ID **oglašivača rollWorksa**.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
