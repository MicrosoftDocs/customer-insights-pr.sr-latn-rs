---
title: Koristite izvore podataka radi unosa podataka
description: Naučite kako da uvezete podatke iz različitih izvora.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: bcc50c6fa8f8e2a66ef6164bfa9022e068c0e374
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643062"
---
# <a name="data-sources-overview"></a>Pregled izvora podataka



Dynamics 365 Customer Insights povezuje se sa podacima iz širokog skupa izvora. Povezivanje sa izvorom podataka se često naziva procesom *unošenja podataka*. Nakon unošenja podataka, možete ih [objediniti](data-unification.md) i preduzeti radnju nad njima.

## <a name="add-a-data-source"></a>Dodavanje izvora podataka

Pogledajte detaljne članke o tome kako da dodate izvor podataka, u zavisnosti od opcije koju odaberete.

Možete da dodate sledeće izvore podataka:

- [Kroz desetine konektora Power Query](connect-power-query.md)
- [Iz Common Data Model fascikle](connect-common-data-model.md)
- [Iz vašeg sopstvenog Microsoft Dataverse jezera](connect-dataverse-managed-lake.md)
- [Iz baze podataka Azure Synapse Analytics](connect-synapse.md)

> [!NOTE]
> Ako koristite probnu verziju, odeljak "Metodi uvoza" sadrži opciju biblioteke **podataka "Uvidi kupaca** ". Odaberite ovu opciju da biste izabrali probni skup podataka dostupan za različite industrije. Više informacija potražite u članku [Dynamics 365 Customer Insights Suđenje](trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Dodavanje podataka iz lokalnih izvora podataka

Na osnovu priliva podataka podržano Microsoft Power Platform je lokalni podataka iz izvora podataka. Pomoću podešavanja okruženja možete da omogućite dataflows [Microsoft Dataverse u uvidima klijenata tako što ćete obezbediti URL](create-environment.md) adresu okruženja.

Izvori podataka koji su kreirani nakon povezivanje okruženja sa Dataverse uvidom klijenata podrazumevano [Power Platform koriste priliv podataka](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Tokovi podataka podržavaju lokalnu povezanost pomoću mrežnog prolaza za podatke. Možete da uklonite i ponovo kreirate izvore podataka koji su postojali pre Dataverse nego što je okruženje [bilo povezano lokalni mrežnim prolazima podataka](/data-integration/gateway/service-gateway-app).

Mrežni prolazi za podatke iz postojećeg Power BI ili Power Apps okruženja će biti vidljivi i možete ponovo da ih koristite u usluzi Customer Insights. Stranica sa izvorima podataka prikazuje veze do Microsoft Power Platform okruženja u kojem možete da pregledate i lokalne mrežne prolaze za podatke.

> [!IMPORTANT]
> Uverite se da su mrežni prolazi ažurirani u najnoviju verziju. Možete direktno da instalirate ispravku i ponovo konfigurišete mrežni prolaz sa upita prikazanog na ekranu mrežnog prolaza ili da preuzmete [najnoviju verziju](https://powerapps.microsoft.com/downloads/). Ako ne koristite najnoviju verziju mrežnog prolaza, osvežavanje priliva podataka neće uspeti **sa porukama o greškama kao što je Ključna reč nije podržano: svojstva konfiguracije. Naziv parametra: ključna reč**.

## <a name="review-ingested-data"></a>Pregled unetih podataka
Ako vaše okruženje sadrži tok Power Platform podataka, stranica "Izvori **podataka"** navodi tri odeljka: 
- **Deljeno**: Izvori podataka kojima mogu upravljati svi administratori korisničkog uvida. Power BI priliv podataka, sopstveni nalog za skladištenje i prilaganje Dataverse uz jezero sa podacima kojim upravljate su primeri deljenih izvora podataka.
- **Njime upravljam**: Power Platform priliv podataka kreiran i njime možete upravljati samo vi. Drugi administratori korisničkih uvida mogu da pregledaju samo ove podatke, ali ne i da ih uređuju, osvežavaju ili brišu.
- **Njima upravljaju drugi**: Power Platform priliv podataka koji su kreirali drugi administratori. Možete samo da ih videli. On navodi vlasnika priliva podataka da bi se obratiti za svaku pomoć.
> [!NOTE]
> Sve entitete mogu da pregledaju i koriste drugi korisnici. Kontekstualnost korisnika se primenjuje samo na izvore podataka, a ne i na entitete koji su rezultat ovih priliva podataka.

Ako se Power Platform ne koristi priliv podataka, nećete videti grupe ili odeljke. Stranica **"Izvori podataka** " sadrži samo listu svih izvora podataka.

Videćete naziv svakog unetog izvora podataka, njegov status i poslednji put kada su podaci osveženi za taj izvor. Spisak izvora podataka možete sortirati po svakoj koloni.

> [!div class="mx-imgBorder"]
> ![Izvor podataka je dodat.](media/configure-data-datasource-added.png "Izvor podataka je dodat")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Učitavanje podataka može potrajati. Nakon uspešnog osvežavanja, uneseni podaci mogu se pregledati sa stranice **Entiteti**. Za više informacija, pogledajte članak [Entiteti](entities.md).

## <a name="refresh-a-data-source"></a>Osvežite izvor podataka

Izvori podataka mogu se osvežavati po automatskom rasporedu ili ručno na zahtev. 

Idite na **Administrator** > **Sistem** > [**Raspored**](system.md#schedule-tab) da biste konfigurisali zakazana osvežavanja svih unetih izvora podataka.

Da biste osvežili izvor podataka na zahtev, sledite ove korake:

1. Idite na **Podaci** > **Izvori podataka**.

2. Izaberite vertikalne tri tačke pored izvora podataka koje želite da osvežite i izaberite **Osveži** iz padajuće liste.

3. Izvor podataka je sada aktiviran za ručno osvežavanje. Osvežavanjem izvora podataka ažuriraće se i šema entiteta i podaci za sve entitete navedene u izvoru podataka.

4. Izaberite **Prestanite sa osvežavanjem** ako želite da otkažete postojeće osvežavanje i izvor podataka će se vratiti na svoj poslednji status osvežavanja.

## <a name="delete-a-data-source"></a>Izbriši izvor podataka

1. Idite na **Podaci** > **Izvori podataka**.

2. Izaberite vertikalne tri tačke pored izvora podataka koje želite da uklonite i izaberite **Izbriši** iz padajućeg menija.

3. Potvrdite brisanje.


[!INCLUDE [footer-include](includes/footer-banner.md)]
