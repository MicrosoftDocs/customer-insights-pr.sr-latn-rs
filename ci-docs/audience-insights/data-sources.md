---
title: Koristite izvore podataka radi unosa podataka
description: Naučite kako da uvezete podatke iz različitih izvora.
ms.date: 12/06/2021
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
ms.openlocfilehash: e7bcf82c4fe3625ef791ec2b0a7651be0356a006
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354066"
---
# <a name="data-sources-overview"></a>Pregled izvora podataka



Sposobnost uvida o korisnicima u usluzi Dynamics 365 Customer Insights povezuje se sa podacima iz širokog skupa izvora. Povezivanje sa izvorom podataka se često naziva procesom *unošenja podataka*. Nakon unošenja podataka, možete ih [objediniti](data-unification.md) i preduzeti radnju nad njima.

## <a name="add-a-data-source"></a>Dodavanje izvora podataka

Pogledajte detaljne članke o tome kako da dodate izvor podataka, u zavisnosti od opcije koju odaberete.

Možete da dodate sledeće izvore podataka:

- [Kroz desetine konektora Power Query](connect-power-query.md)
- [Iz Common Data Model fascikle](connect-common-data-model.md)
- [Iz vašeg sopstvenog Microsoft Dataverse jezera](connect-dataverse-managed-lake.md)
- [Iz baze podataka Azure Synapse Analytics](connect-synapse.md)

> [!NOTE]
> Ako koristite probnu verziju, odeljak "Metodi uvoza" sadrži opciju biblioteke **podataka "Uvidi kupaca** ". Odaberite ovu opciju da biste izabrali probni skup podataka dostupan za različite industrije. Više informacija potražite u članku [Dynamics 365 Customer Insights Suđenje](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Dodavanje podataka iz lokalnih izvora podataka

Unošenje podataka iz lokalnih izvora podataka u uslugu Uvidi u korisnike podržano je na osnovu Microsoft Power Platform tokova podataka. Pomoću podešavanja okruženja možete da omogućite dataflows [Microsoft Dataverse u uvidima klijenata tako što ćete obezbediti URL](create-environment.md) adresu okruženja.

Izvori podataka koji su kreirani nakon povezivanje okruženja sa Dataverse uvidom klijenata podrazumevano [Power Platform koriste priliv podataka](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Tokovi podataka podržavaju lokalnu povezanost pomoću mrežnog prolaza za podatke. Možete da uklonite i ponovo kreirate izvore podataka koji su postojali pre Dataverse nego što je okruženje [bilo povezano lokalni mrežnim prolazima podataka](/data-integration/gateway/service-gateway-app).

Mrežni prolazi za podatke iz postojećeg Power BI ili Power Apps okruženja će biti vidljivi i možete ponovo da ih koristite u usluzi Customer Insights. Stranica sa izvorima podataka prikazuje veze do Microsoft Power Platform okruženja u kojem možete da pregledate i lokalne mrežne prolaze za podatke.

## <a name="review-ingested-data"></a>Pregled unetih podataka

Videćete naziv svakog unetog izvora podataka, njegov status i poslednji put kada su podaci osveženi za taj izvor. Spisak izvora podataka možete sortirati po svakoj koloni.

> [!div class="mx-imgBorder"]
> ![Izvor podataka je dodat.](media/configure-data-datasource-added.png "Izvor podataka je dodat")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Učitavanje podataka može potrajati. Nakon uspešnog osvežavanja, uneseni podaci mogu se pregledati sa stranice **Entiteti**. Za više informacija, pogledajte članak [Entiteti](entities.md).

## <a name="refresh-a-data-source"></a>Osvežite izvor podataka

Izvori podataka mogu se osvežavati po automatskom rasporedu ili ručno na zahtev. 

Idite na **Administrator** > **Sistem** > [**Raspored**](system.md#schedule-tab) da biste konfigurisali zakazana osvežavanja svih unetih izvora podataka.

Da biste osvežili izvor podataka na zahtev, sledite ove korake:

1. U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.

2. Izaberite vertikalne tri tačke pored izvora podataka koje želite da osvežite i izaberite **Osveži** iz padajuće liste.

3. Izvor podataka je sada aktiviran za ručno osvežavanje. Osvežavanjem izvora podataka ažuriraće se i šema entiteta i podaci za sve entitete navedene u izvoru podataka.

4. Izaberite **Prestanite sa osvežavanjem** ako želite da otkažete postojeće osvežavanje i izvor podataka će se vratiti na svoj poslednji status osvežavanja.

## <a name="delete-a-data-source"></a>Izbriši izvor podataka

1. U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.

2. Izaberite vertikalne tri tačke pored izvora podataka koje želite da uklonite i izaberite **Izbriši** iz padajućeg menija.

3. Potvrdite brisanje.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
