---
title: Izvoz segmenata u Snapchat (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvezete u Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195399"
---
# <a name="export-segments-to-snapchat-preview"></a>Izvoz segmenata u Snapchat (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u Snapchat i koristite ih za oglašavanje.

## <a name="prerequisites"></a>Preduslovi

- [Snapchat Poslovni nalog,](https://business.snapchat.com/)[Snapchat Oglasni nalog i](https://ads.snapchat.com/) odgovarajući administratorski akreditivi. Morate biti bar član naloga organizacije i upravljač podacima određenog naloga oglasa.
- Najmanje jedan korisnici snapchat korisnici tipa SAM (Snap korisnici Match).
- [ID Snapchat segmenta/korisnici segmenta](https://businesshelp.snapchat.com/s/article/custom-audiences). ID datoteke se korisnici u URL adresi nakon što izaberete korisnici u programu Snapchat korisnici Manager.
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milion profila klijenata, što može da potraje i do 15 minuta.
- Samo segmenti.

## <a name="set-up-connection-to-snapchat"></a>Podešavanje veze u usluzi Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **dodaj vezu i** odaberite **Snapchat**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu.

1. Izaberite **Potvrdite identitet pomoću usluge Snapchat** i obezbedite svoje administratorske akreditive za Snapchat.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Snapchat. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Unesite **Snapchat segment/korisnici ID**.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
