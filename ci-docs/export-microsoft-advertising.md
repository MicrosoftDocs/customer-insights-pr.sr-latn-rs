---
title: Izvoz segmenata u Microsoft Advertising (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvezete sadržaj u Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196549"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Izvoz segmenata u Microsoft Advertising (verzija za pregled)

Izvezite Customer Insights segmente u Microsoft Advertising da biste kreirali ciljne grupe za podudaranje klijenata. Koristite ove ciljne grupe za svoje oglasne kampanje.

## <a name="prerequisites"></a>Preduslovi

- [Microsoft nalog za oglašavanje](https://ads.microsoft.com/) i odgovarajući administratorski akreditivi.
- ID klijenta Microsoft oglašavanja i ID naloga. Pronađite ID kupca (`cid`) i ID naloga (`aid`) u parametrima URL adrese kada ste prijavljeni u Microsoft oglašavanje.
- Prihvaćeni su uslovi korišćenja podudaranja sa kupcem.
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do 500.000 profila kupaca po izvozu u Microsoft Advertising, što može da potraje i do 10 minuta.
- Samo segmenti.

## <a name="set-up-connection-to-microsoft-advertising"></a>Podešavanje veze sa Microsoft oglašavanjem

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **dodaj vezu i** odaberite **Microsoft Advertising**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **ID klijenta za Microsoft oglašavanje**.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu.

1. Izaberite **Potvrdi identitet pomoću usluge Microsoft Advertising** i obezbedite svoje administratorske akreditive za Microsoft Advertising.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Microsoft Advertising. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Izaberite segmente za izvoz. Ciljne grupe za podudaranje klijenata u usluzi Microsoft Advertising automatski se kreira sa nazivom segmenata izabranih za izvoz. Svaki segment će rezultirati zasebnom ciljnom grupom za podudaranje klijenata.

1. Unesite svoj **ID Microsoft Advertising klijenta i ID naloga**.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje sa e-adresom klijenta.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
