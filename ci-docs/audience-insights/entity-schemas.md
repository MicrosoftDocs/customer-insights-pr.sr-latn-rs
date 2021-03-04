---
title: Šeme Customer Insights entiteta u usluzi Common Data Model
description: Radite sa entitetima u usluzi Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9e7a6e944d37d25f4c25846644278b39b3ddd08e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269301"
---
# <a name="entity-schemas-in-common-data-model"></a>Šeme entiteta u platformi Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](https://docs.microsoft.com/common-data-model/) je deklarativna specifikacija i definicija standardnih entiteta koji predstavljaju uobičajene koncepte i aktivnosti u poslovnim i produktivnim aplikacijama. Ovaj model se proširuje i na posmatračke i analitičke podatke. Common Data Model pruža dobro definisane, modularne i proširive poslovne entitete – poput poslovnog kontakta, poslovne jedinice, predmeta, kontakta, potencijalnog klijenta, mogućnosti za poslovanje i proizvoda – kao i interakcije sa dobavljačima, radnicima i klijentima – kao što su aktivnosti i ugovori o nivou usluga. Svako može da izgradi i proširi Common Data Model definicije da bi pronašao dodatne ideje specifične za poslovanje.

Ovaj zajednički model podataka omogućava aplikacijama i integratorima podataka da lakše sarađuju pružajući objedinjenu definiciju podataka. Common Data Model uključuje bogat sistem metapodataka sa standardnim entitetima, relacijama, hijerarhijama, osobinama i još mnogo toga. Nastao je iz Dynamics 365 aplikacija i otvoren je na GitHubu sa preko 260 standardnih entiteta. Veliki sistem unutrašnjih i spoljnih partnera doprinosi industrijskim konceptima platformi Common Data Model.

Više sistema i platformi danas primenjuje Common Data Model, uključujući Power BI tokove podataka i Azure Data Services. To je već podržano u uslugama Common Data Service, Dynamics 365, Power Apps, Power BI i predstojećim Azure uslugama podataka, koje direktno prikupljaju vrednost prema [Otvorenoj inicijativi za podatke](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Šeme Customer Insights entiteta

Da bismo uspostavili sveobuhvatan pogled na klijenta i učinili Customer Insights modele dostupnim platformi Common Data Model radi proširivosti, objavili smo sledeće šeme entiteta:

| Entitet | Opis |
|---------|---------|
|[CustomerActivity](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Aktivnost koju obavlja korisnik koja ima posmatračku vrednost za preduzeće. |
|[CustomerProfile](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Osoba ili organizacija koja je ili obavljala ili ima potencijal da se bavi poslovnim aktivnostima. |
|[MeasureDefinition](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definicija KPI-ova izdeljenih u nula ili više dimenzija (kao što su Mesečno aktivni korisnici, Ukupna potrošnja po klijentu, Prosečni troškovi kupovine klijenta) |
|[Segment](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definiše grupu članova sa zajedničkim osobinama. |
|[SegmentMembership](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Članovi koji učestvuju u određenom segmentu. |

Za više informacija, pogledajte dokumentaciju o [Customer Insights šemama entiteta u platformi Common Data Model](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Prikaz entiteta korišćenjem Common Data Model navigatora entiteta

Možete pregledati entitete u [Navigatoru Common Data Model entiteta](https://microsoft.github.io/CDM/). Izaberite dugme **Učitaj sa GitHuba!** i idite do **foundationCommon** > **crmCommon** > **rešenja** > **customerInsights**, gde ćete naći listu Customer Insights entiteta i njihove definicije.
> [!div class="mx-imgBorder"]
> ![Navigator CDM entiteta koji prikazuje entitet CustomerActivity](media/CDM-entity-navigator.png "Navigator CDM entiteta koji prikazuje entitet CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]