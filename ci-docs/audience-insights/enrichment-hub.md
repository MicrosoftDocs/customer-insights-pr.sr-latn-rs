---
title: Obogatite objedinjene profile klijenata
description: Koristite mogućnosti za obogaćivanje podataka o klijentima.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954504"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Obogaćivanje za profile korisnika (pregled)

Koristite podatke iz izvora kao što su Microsoft i drugi partneri da biste obogatili podatke o klijentima.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stranica čvorišta za obogaćivanje":::

U uvidima o korisnicima idite na **Podaci** > **Obogaćivanje** da biste koristili opcije obogaćivanja.    
Da biste kreirali ili menjali obogaćivanja, morate da imate dozvole saradnika ili administratora. Više informacija potražite u [dozvolama](permissions.md).

Na kartici **Otkrivanje** ćete pronaći sledeća obogaćivanja:

- [Brendove](enrichment-microsoft.md) obezbeđuje Microsoft
- [Interesovanja](enrichment-microsoft.md) obezbeđuje Microsoft
- [Poboljšane adrese](enrichment-enhanced-addresses.md) obezbeđuje Microsoft
- [Podaci o kompaniji](enrichment-leadspace.md) koje pruža Leadspace
- [Demografski podaci](enrichment-experian.md) koje pruža Experian
- [Podatke o lokaciji](enrichment-here.md) pruža HERE Technologies
- [Prilagođeni podaci](enrichment-SFTP-custom-import.md) pomoću protokola Secure File Transfer Protocol (SFTP)

Na kartici **Moja obogaćivanja** možete da vidite obogaćivanja koja ste konfigurisali i da menjate njihova svojstva.

## <a name="manage-existing-enrichments"></a>Upravljanje postojećim obogaćivanjima

Idite na **Moja obogaćivanja** da vidite sva konfigurisana obogaćivanja. Svako obogaćivanje predstavljeno je kao red koji uključuje dodatne informacije o obogaćivanju.

Izaberite obogaćivanje da biste videli dostupne opcije. Takođe možete odabrati tri tačke (...) na stavci liste da biste videli opcije.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcije za upravljanje obogaćivanjima na listi obogaćivanja":::

- **Prikažite** detalje obogaćivanja sa brojem obogaćenih profila klijenata.
- **Uređujte** konfiguraciju obogaćivanja.
- **Pokrenite** obogaćivanje radi ažuriranja profila klijenata najnovijim podacima.
- **Deaktivirajte** postojeće obogaćivanje kako bi se zaustavili automatsko osvežavanje sa svakim zakazanim osvežavanjem. Podaci iz poslednjeg uspešnog osvežavanja i dalje će biti dostupni. **Aktivirajte** neaktivno obogaćivanje da biste ponovo pokrenuli automatsko osvežavanje sa svakim zakazanim osvežavanjem.
- **Izbrišite** obogaćivanje.

Možete da pokrenete ili deaktivirate više obogaćivanja odjednom tako što ćete ih izabrati na listi. Opcije pregleda i uređivanja nisu dostupne kao masovna radnja i rade samo za jedno obogaćivanje.

## <a name="enrichments-and-connections"></a>Obogaćivanja i veze

Obogaćenja trećih lica se konfigurišu pomoću [veza](connections.md) koje administrator postavlja sa akreditivima i daje saglasnost za prenos podataka. Vezu mogu da koriste administratori i saradnici da bi konfigurisali obogaćivanja.  

## <a name="multiple-enrichments-of-the-same-type"></a>Višestruka obogaćivanja istog tipa

Entitet koji treba obogatiti navodi se tokom konfiguracije obogaćivanja, što vam omogućava da obogatite samo podskup svojih profila. Na primer, obogatite podatke samo za određeni segment. Možete da konfigurišete nekoliko obogaćivanja istog tipa i da ponovo koristite istu vezu. Neka obogaćivanja će imati ograničenja u broju obogaćivanja istog tipa koja se mogu kreirati. Ograničenja i trenutna upotreba mogu se videti na stranici **Obogaćivanje**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
