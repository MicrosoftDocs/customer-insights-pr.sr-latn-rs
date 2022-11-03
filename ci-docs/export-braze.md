---
title: Izvoz segmenata u Braze (pregled)
description: Saznajte kako da konfigurišete vezu i izvezete u Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a3967008ec166cb6f099659b0791f1318126c0da
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725233"
---
# <a name="export-segments-to-braze-preview"></a>Izvoz segmenata u Braze (pregled)

Izvezite segmente objedinjenih profila kupaca u Braze i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduslovi

- Braze [nalog i](https://www.braze.com/) odgovarajući administratorski akreditivi.
- Braze [API ključ](https://www.braze.com/docs/api/basics/)
- Vaš [Braze REST krajnja tačka](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.
- Objedinjeni profili kupaca u izvezenim segmentima sadrže polje koje predstavlja e-adresu i ID kupca Brazea.

## <a name="known-limitations"></a>Poznata ograničenja

- Privatna veza u kombinaciji sa "Donesi sopstveno skladište" (BYOS) nije podržana.
- Do Brazea je potrebno do milion profila klijenata, što može da potraje i do 40 minuta. Broj profila kupaca koje možete da izvezete u Braze zavisi od vašeg ugovora sa Brazeom.
- Samo segmenti.
- Azure privatna veza nije podržana za izvoz Brazea.

## <a name="set-up-connection-to-braze"></a>Uspostavi vezu sa Brazeom

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Kliknite **na dugme Dodaj vezu** i odaberite **Braze**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Obezbedite braze API ključ da biste nastavili da se prijavljujete.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odeljka Braze. Ako veza nije dostupna, obratite se administratoru.

1. Unesite opciju REST krajnja tačka polje **Hostname** u sledećem formatu:`rest.iad-03.braze.com`.

1. Unesite ime za izvoz.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta. U polju **ID kupca** izaberite polje koje predstavlja Braze ID kupca. Segmenti u Brazeu će biti kreirani pod istim imenom segmenta kao i .Dynamics 365 Customer Insights Možete odabrati više opcionalnih polja za podudaranje podataka.

1. Izaberite entitete ili segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
