---
title: Izvoz segmenata u Autopilot (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvezete u Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b4b14ba9de2c7e20175fac664a705f2212a411fd
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724819"
---
# <a name="export-segments-to-autopilot-preview"></a>Izvoz segmenata u Autopilot (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u Autopilot i koristite ih za marketing putem e-pošte u usluzi Autopilot.

## <a name="prerequisites-for-a-connection"></a>Preduslovi za vezu

- Nalog [autopilota i](https://www.autopilothq.com/) odgovarajući administratorski akreditivi.
- API [ključ za autopilot](https://autopilot.docs.apiary.io/#)
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Privatna veza u kombinaciji sa "Donesi sopstveno skladište" (BYOS) nije podržana.
- Do 100.000 profila kupaca po izvozu u Autopilot, što može da potraje i do nekoliko sati. Broj profila klijenata koje možete da izvezete u Autopilot zavisi od ugovora sa autopilotom.
- Samo segmenti.

## <a name="set-up-connection-to-autopilot"></a>Podešavanje veze sa uslugom Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **dodaj vezu** i odaberite **opciju "Automatskipilot"**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj API ključ za Autopilot.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Autopilot. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta.

1. Opcionalno, izvezite druga polja kao **što su ime** i **prezime**.

1. Izaberite segmente koje želite da izvezete u poznata ograničenja.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
