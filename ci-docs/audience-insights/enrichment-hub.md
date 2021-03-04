---
title: Obogatite objedinjene profile klijenata
description: Koristite mogućnosti za obogaćivanje podataka o klijentima.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269485"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Obogaćivanje za profile korisnika (pregled)

Koristite podatke iz izvora kao što su Microsoft i drugi partneri da biste obogatili podatke o klijentima.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stranica čvorišta za obogaćivanje":::

U uvidima o korisnicima idite na **Podaci** > **Obogaćivanje** da biste koristili opcije obogaćivanja.    
Da biste kreirali ili menjali obogaćivanja, morate da imate dozvole saradnika ili administratora. Više informacija potražite u [dozvolama](permissions.md).

Na kartici **Otkrivanje** ćete pronaći sledeća obogaćivanja:

- [Brendovi](enrichment-microsoft-graph.md) koje pruža Microsoft Graph
- [Interesovanja](enrichment-microsoft-graph.md) koje pruža Microsoft Graph
- [Podaci o kompaniji](enrichment-leadspace.md) koje pruža Leadspace
- [Demografski podaci](enrichment-experian.md) koje pruža Experian
- [Podatke o lokaciji](enrichment-here.md) pruža HERE Technologies
- [Prilagođeni podaci](enrichment-SFTP-custom-import.md) pomoću protokola Secure File Transfer Protocol (SFTP)

Na kartici **Moja obogaćivanja** možete da vidite obogaćivanja koja ste konfigurisali i da menjate njihova svojstva.

## <a name="manage-existing-enrichments"></a>Upravljanje postojećim obogaćivanjima

Idite na **Moja obogaćivanja** da vidite sva konfigurisana obogaćivanja. Svako obogaćivanje predstavljeno je kao red koji uključuje dodatne informacije o obogaćivanju.

Izaberite obogaćivanje da biste videli dostupne opcije. Alternativno, možete odabrati tri tačke (...) na stavki liste da biste videli opcije.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcije za upravljanje obogaćivanjima na listi obogaćivanja":::

- **Prikažite** detalje obogaćivanja sa brojem obogaćenih profila klijenata.
- **Uređujte** konfiguraciju obogaćivanja.
- **Pokrenite** obogaćivanje radi ažuriranja profila klijenata najnovijim podacima.
- **Deaktivirajte** postojeće obogaćivanje kako bi se zaustavili automatsko osvežavanje sa svakim zakazanim osvežavanjem. Podaci iz poslednjeg uspešnog osvežavanja i dalje će biti dostupni. **Aktivirajte** neaktivno obogaćivanje da biste ponovo pokrenuli automatsko osvežavanje sa svakim zakazanim osvežavanjem.
- **Izbrišite** obogaćivanje.

Možete da pokrenete ili deaktivirate više obogaćivanja odjednom tako što ćete ih izabrati na listi. Opcije pregleda i uređivanja nisu dostupne kao masovna radnja i rade samo za jedno obogaćivanje.


[!INCLUDE[footer-include](../includes/footer-banner.md)]