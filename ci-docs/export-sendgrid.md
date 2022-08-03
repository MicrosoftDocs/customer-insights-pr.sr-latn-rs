---
title: Izvoz segmenata u SendGrid (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvezete u SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f2990ad410dda0cbf952f82f3fc30b3a53a7bcd4
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197009"
---
# <a name="export-segments-to-sendgrid-preview"></a>Izvoz segmenata u SendGrid (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u SendGrid liste kontakata i koristite ih za kampanje i marketing u usluzi SendGrid.

## <a name="prerequisites"></a>Preduslovi

- Nalog [za slanje i odgovarajuće](https://sendgrid.com/) akreditive administratora.
- [Postojeće liste kontakata u opciji "Pošaljigrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) " i odgovarajućiM ID-ovima.
- SendGrid [API ključ](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Ukupno do 100.000 profila kupaca za SendGrid, što može da potraje i do nekoliko sati. Broj profila kupaca koje možete da izvezete u SendGrid zavisi od ugovora sa uslugom SendGrid.
- Samo segmenti.

## <a name="set-up-connection-to-sendgrid"></a>Podešavanje veze u usluzi SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **dodaj vezu i** odaberite opciju **Pošaljigrid**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **SendGrid API ključ**.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka SendGrid. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Unesite **ID liste "Pošaljigrid"**.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta.

1. Opcionalno, izaberite polja kao **što su ime**, **prezime**, **Država/region**, **Država**, **Grad** i **Poštanski broj**.

1. Izaberite segmente koje želite da izvezete nakon poznatih ograničenja.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
