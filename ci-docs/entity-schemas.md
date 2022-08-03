---
title: Šeme entiteta u platformi Common Data Model
description: Radite sa entitetima u usluzi Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: cc65314f1b083694b60ac0a2625bea906be7272b
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183510"
---
# <a name="entity-schemas-in-common-data-model"></a>Šeme entiteta u platformi Common Data Model

[Common Data Model](/common-data-model/) je deklarativna specifikacija i definicija standardnih entiteta koji predstavljaju uobičajene koncepte i aktivnosti u poslovnim i produktivnim aplikacijama. Ovaj model se proširuje i na posmatračke i analitičke podatke. Common Data Model pruža dobro definisane, modularne i proširive poslovne entitete – poput poslovnog kontakta, poslovne jedinice, predmeta, kontakta, potencijalnog klijenta, mogućnosti za poslovanje i proizvoda – kao i interakcije sa dobavljačima, radnicima i klijentima – kao što su aktivnosti i ugovori o nivou usluga. Svako može da izgradi i proširi Common Data Model definicije da bi pronašao dodatne ideje specifične za poslovanje.

Ovaj zajednički model podataka omogućava aplikacijama i integratorima podataka da lakše sarađuju pružajući objedinjenu definiciju podataka. Common Data Model uključuje bogat sistem metapodataka sa standardnim entitetima, relacijama, hijerarhijama, osobinama i još mnogo toga. Nastao je iz Dynamics 365 aplikacija i otvoren je na GitHubu sa preko 260 standardnih entiteta. Veliki sistem unutrašnjih i spoljnih partnera doprinosi industrijskim konceptima platformi Common Data Model.

Više sistema i platformi danas primenjuju Common Data Model, uključujući Power BI tokove podataka i Azure Data Services. Već je podržano u uslugama Microsoft Dataverse, Dynamics 365, Power Apps, Power BI i predstojećim Azure uslugama podataka, koje direktno pripisuju vrednost prema inicijativi [Open Data Initiative](https://dynamics.microsoft.com/en-us/open-data-initiative/).

## <a name="customer-insights-entity-schemas"></a>Šeme Customer Insights entiteta

Da bismo uspostavili sveobuhvatan pogled na klijenta i učinili Customer Insights modele dostupnim platformi Common Data Model radi proširivosti, objavili smo sledeće šeme entiteta:

| Entitet | Opis |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Aktivnost koju obavlja korisnik koja ima posmatračku vrednost za preduzeće. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Osoba ili organizacija koja je ili obavljala ili ima potencijal da se bavi poslovnim aktivnostima. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definicija KPI-ova izdeljenih u nula ili više dimenzija (kao što su Mesečno aktivni korisnici, Ukupna potrošnja po klijentu, Prosečni troškovi kupovine klijenta) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definiše grupu članova sa zajedničkim osobinama. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Članovi koji učestvuju u određenom segmentu. |

Za više informacija, pogledajte dokumentaciju o [Customer Insights šemama entiteta u platformi Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Prikaz entiteta korišćenjem Common Data Model navigatora entiteta

Prikažite entitete u navigatoru [entiteta zajedničkog modela podataka](https://microsoft.github.io/CDM/). Izaberite entitet iz odeljka aplikacije Insights da biste dobili listu Customer Insights entiteta i njihove definicije.

:::image type="content" source="media/CDM-entity-navigator.png" alt-text="Navigator CDM entiteta koji prikazuje entitet CustomerActivity.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
