---
title: Planiranje osvežavanja sistema
description: Planiranje vremena osvežavanja sistema
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610345"
---
# <a name="schedule-system-refresh"></a>Planiranje osvežavanja sistema

Planirajte automatsko osvežavanje svih [nanetih izvora podataka](data-sources.md). Automatsko osvežavanje osigurava da se ispravke iz izvora podataka prikazuju na objedinjenim profilima korisnika.

> [!NOTE]
> Power Query izvore podataka kojima upravljate osvežavate po sopstvenim rasporedima. Da biste isplanirali osvežavanje Power Query ovih izvora podataka, konfigurišite postavke osvežavanja na izvor podataka sa stranice **"Izvori podataka**". Poravnajte vremenski raspored sa rasporedom osvežavanja uzvodnih podataka tako da se osvežavanje ne dešava odjednom.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Postavke osvežavanja dataflow-a.":::

## <a name="set-system-refresh-schedule"></a>Podešavanje rasporeda osvežavanja sistema

1. Idite na **administratorski** > **sistem i** izaberite karticu **"Raspored** ".

   :::image type="content" source="media/schedule_refresh.png" alt-text="Planiranje kartice &quot;Osvežavanje&quot; sa stranice &quot;Sistem&quot;.":::

1. Podrazumevano stanje za planirano osvežavanje je **Isključeno**. Da biste omogućili planirana osvežavanja, promenite preklopnik na vrhu ekrana na **Uključeno**.

1. Izaberite između **Nedeljnog** (podrazumevano) i **Svakodnevnog** osvežavanja. Ako nameravate da zakažete nedeljno osvežavanje, izaberite jedan ili više dana u kojima želite da pokrenete osvežavanje.

1. Podesite **vremensku zonu**, a zatim pomoću padajućeg menija **Vreme** podesite vreme osvežavanja. Ako želite da zakažete više osvežavanja u jednom danu, izaberite **Dodaj drugo vreme**. Možete da dodate do četiri osvežavanja.

1. Izaberite **Sačuvaj** da primenite promene.

[!INCLUDE [footer-include](includes/footer-banner.md)]
