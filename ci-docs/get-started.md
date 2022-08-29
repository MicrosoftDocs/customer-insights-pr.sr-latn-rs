---
title: Započnite rad sa sistemom Dynamics 365 Customer Insights
description: Pregled uvida klijenata pomaže resursima da se brzo pokrenu.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: audience-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: ce0336c4bf853bc81ec01c45410169a63b69eb03
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304628"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Započnite rad sa sistemom Dynamics 365 Customer Insights

Uvidi klijenata vam mogu pomoći da izgradite dublje razumevanje svojih klijenata. Povežite podatke iz raznih transakcionih, posmatračkih i izvora ponašanja da biste kreirali sveobuhvatni prikaz klijenta. Koristite ove uvide da biste podstakli iskustva i procese koji se fokusiraju na klijenta. Objedinite i razumite podatke o klijentima i iskoristite ih za inteligentan uvid i radnje.

## <a name="step-1-create-an-environment"></a>1. korak: Kreiranje okruženja

Prvo, kreirajte okruženje u kome ćete raditi. Ako je vaša organizacija već kupila licencu, pogledajte [Kreiranje okruženja](create-environment.md). Da biste započeli probnu pomoć za uvid u kupce, pogledajte [podešavanje probnog okruženja](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>2. korak: Istraživanje uvida klijenata

Kada se prvi put prijavite u "Uvid kupca", konfigurišite postavke i istražite proizvod.

1. [prijavite se na korisničke uvide](https://home.ci.ai.dynamics.com) koristeći Microsoft Azure Active Directory (AAD) korisnički nalog.

1. Promenite okruženje da biste videli demo podatke i istražili [uvide klijenata](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>3. korak: Unesite, objedinite i podesite odnose za svoje podatke

Objedinjeni profili su osnova za dobijanje uvida i preduzimanje radnji nad podacima. Donesite podatke iz različitih izvora i pokrenite proces objedinjavanja podataka da biste kombinovali objedinjene profile. Navedite odnosi između unetih entiteta i koristite funkcije obogaćivanja da biste dodali informacije profilima.

1. Unosite podatke kreiranjem izvora podataka iz više opcija. Odaberite jednu [Azure Data Lake Storage od njih, uključujući uobičajeni model](connect-common-data-model.md)[Azure Synapse Analytics](connect-synapse.md) podataka [Microsoft Dataverse](connect-dataverse-managed-lake.md) ili linije [Power Query spajanja](connect-power-query.md).

1. Pokrenite [proces ujedinjenja podataka](data-unification.md) tako što ćete identifikovati izvorna [polja](map-entities.md), ukloniti [duplikate](remove-duplicates.md), uslove [podudaranja](match-entities.md) i [ujedinjati polja](merge-entities.md).

1. Upoznajte se sa [entitetima koje sistem kreira](entities.md) i kreirajte [odnose između unetih entiteta](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>4. korak: Poboljšajte objedinjene profile predviđanjima, aktivnostima i merama

Sa podešenim objedinjenim profilima poboljšajte podatke i dodatno povećajte informacije koje oni pružaju.

1. Birajte iz proširene biblioteke dobavljača obogaćivanja da biste [obogatili podatke o klijentima](enrichment-hub.md).

1. Koristite [gotove modele](predictions-overview.md) za predviđanje verovatnoće gubitka ili očekivanih prihoda.

1. [Konfigurišite aktivnosti](activities.md) na osnovu unetih podataka i vizuelizujte interakcije sa svojim klijentima u hronološkoj vremenskoj osi.

1. [Izgradite mere](measures.md) za merenje svojih poslovnih ciljeva i KPI-jeva.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>5. korak: Kreiranje segmenata i aktiviranje podataka kroz različite opcije izvoza

Sada kada su vaši podaci dovršeni i sadrže širok spektar informacija o klijentima, potražite načine da preduzmete radnje u vezi sa tim podacima.

1. [Kreirajte segmente](segments.md), podskupove vaše baze klijenata, kako biste bili sigurni da su vaše radnje relevantne za ciljane klijente.

1. Pregledajte proširivi katalog [opcija izvoza](export-destinations.md) gde možete koristiti podatke o klijentima. Na primer, možete koristiti podatke za upravljanje promocijama i ostvariti kontakt sa digitalnim marketingom.

1. Pregledajte opcije integracije, na primer u druge Dynamics 365 aplikacije pomoću programskog [dodatka "Kartica kupca"](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
