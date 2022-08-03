---
title: Izvoz segmenata u DotDigital (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvezete u DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196089"
---
# <a name="export-segments-to-dotdigital-preview"></a>Izvoz segmenata u DotDigital (verzija za pregled)

Izvezite segmente objedinjenih profila kupaca u DotDigital adresare i koristite ih za kampanje, marketing putem e-pošte i za izgradnju segmenata kupaca pomoću usluge DotDigital.

## <a name="prerequisites"></a>Preduslovi

- DotDigital [nalog](https://dotdigital.com/) i [API korisnik](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- DotDigital ID iz novog ili [postojećeg](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) adresara u dotDigitalu. ID se može naći u URL-u kada odaberete i otvorite adresar.
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milion profila klijenata po izvozu u DotDigital, što može da potraje i do tri sata zbog ograničenja na strani provajdera. Broj profila klijenata koje možete da izvezete u DotDigital zavisi od vašeg ugovora sa DotDigital.
- Samo segmenti.

## <a name="set-up-connection-to-dotdigital"></a>Podešavanje veze u usluzi DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Kliknite **na dugme Dodaj** vezu i odaberite **stavku DotDigital**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoje **korisničko ime i lozinku za DotDigital API**.

1. Unesite **ID dotDigital adresara**.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka DotDigital. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta.

1. Opcionalno, ime, prezime, Puno ime **,** Pol **i Poštanski** broj **.** **·** **·**

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

U dotDigital-u pronađite svoje segmente u [DotDigital adresarima](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
