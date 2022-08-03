---
title: Izvoz segmenata u Google Ads (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvezete u Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fd7498ecf17ef8a3a8f22dcc49ae204bef88b47f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196595"
---
# <a name="export-segments-to-google-ads-preview"></a>Izvoz segmenata u Google Ads (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata na Google Ads listu ciljnih grupa i koristite ih za oglašavanje na Google pretrazi, Gmailu, YouTubeu i Google mreži multimedijalnog oglašavanja.

## <a name="prerequisites"></a>Preduslovi

- Google [Ads nalog i](https://ads.google.com/) odgovarajući administratorski akreditivi.
- Google [Ads ID kupca](https://support.google.com/google-ads/answer/1704344).
- Ispunjeni su zahtevi smernica [za podudaranje](https://support.google.com/adspolicy/answer/6299717) kupaca.
- Ispunjeni su zahtevi [veličine liste remarketinga](https://support.google.com/google-ads/answer/7558048).
- [Konfigurisani segmenti](segments.md).
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polja koja predstavljaju e-adresu, telefon, ID mobilnog oglašivača, ID korisnika nezavisnog proizvođača ili adresu.

## <a name="known-limitations"></a>Poznata ograničenja

- Izvezite milion profila kupaca po izvozu u Google Ads, što može da potraje i do 30 minuta zbog ograničenja na strani provajdera.
- Samo segmenti.
- Podudaranje u Google Oglasima može da potraje i do 48 sati.

## <a name="set-up-connection-to-google-ads"></a>Podešavanje veze sa uslugom Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i odaberite **Google Ads**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj Google Ads ID kupca.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Izaberite **Potvrdite identitet u Google oglasima** i navedite akreditive za Google oglase.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Google Ads. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Odaberite da li želite da koristite postojeću korisnici ili da kreirate novu:
   - Da biste ažurirali postojeći Google Ads korisnici, unesite svoj [Google Ads korisnici ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Da biste kreirali novu korisnici, ostavite google korisnici ID polje prazno. Customer Insights će automatski kreirati novi korisnici u vašem Google Ads nalogu i koristiti ime izvezenog segmenta.

1. U odeljku **Podudaranje podataka** izaberite jedno ili više polja podataka za izvoz i izaberite polje koje predstavlja odgovarajuća polja podataka u uvidima kupaca.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
