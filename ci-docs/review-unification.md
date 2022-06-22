---
title: Redigovanje ujedinjenja podataka
description: Pregledajte korake za ujedinjenje podataka, kreirajte objedinjene profile klijenata i pregledajte rezultate
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844103"
---
# <a name="review-data-unification"></a>Redigovanje ujedinjenja podataka

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Ovaj poslednji korak u procesu ujedinjenja prikazuje rezime koraka u procesu i pruža šansu da izvršite promene pre nego što kreirate objedinjeni profil.

:::image type="content" source="media/m3_review.png" alt-text="Snimak ekrana pregleda i kreiranje profila klijenata.":::

## <a name="review-the-data-unification-steps"></a>Redigovanje koraka za ujedinjenje podataka

1. Izaberite **uredite** bilo koji od koraka za ujedinjenje podataka da biste pregledali i napravili bilo kakve promene.

1. Ako ste zadovoljni izborom, izaberite stavku Kreiraj **profile kupaca**. Stranica **"Ujedini** " prikazuje se dok se kreira objedinjeni profil kupca. Sve pločice osim polja izvora **prikazuju status reda** čekanja ili **osvežavanja** **.**

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Snimak ekrana stranice &quot;Ujedini&quot; sa pločicama koje prikazuju red ili osvežavanje.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritam ujedinjenja zahteva neko vreme da se dovrši i ne možete da promenite konfiguraciju dok se ona ne dovrši. Kada se proces ujedinjenja dovrši, objedinjeni entitet profila kupca, pod *nazivom*"Kupac", naveden je na **stranici "** Entiteti" u odeljku **"Profili**". Prvo uspešno pokretanje ujedinjenja kreira objedinjeni entitet *kupca*. Sva naredna trčanja proširuju taj entitet.

## <a name="review-the-results-of-data-unification"></a>Pregled rezultata ujedinjenja podataka

Nakon ujedinjenja, stranica " **Ujedinjenje** > **podataka** " prikazuje broj objedinjenih profila klijenata. Rezultati svakog koraka u procesu ujedinjenja prikazuju se na svakoj pločici. Na primer, **polja izvora** prikazuju broj mapiranih atributa (polja) i dupliranih **zapisa koji** prikazuje broj pronađenih dupliranih zapisa.

:::image type="content" source="media/m3_unified.png" alt-text="Snimak ekrana stranice &quot;Ujedinjavanje podataka&quot; nakon objedinjenih podataka.":::

> [!TIP]
> Pločica **"Podudarni** uslovi" prikazuje se samo ako je izabrano više entiteta.

Preporučujemo da pregledate rezultate, posebno kvalitet pravila podudaranja i da [ih usavršite](data-unification-update.md#manage-match-rules) ako je potrebno.

Kada je to potrebno, [promenite postavke ujedinjenja i ponovo](data-unification-update.md) pokrenite objedinjeni profil.

## <a name="next-step"></a>Sledeći korak

Konfigurišite [aktivnosti](activities.md), [obogaćivanje](enrichment-hub.md), [odnosi](relationships.md) ili [mere da](measures.md) biste stekli više uvida o svojim klijentima.

[!INCLUDE[footer-include](includes/footer-banner.md)]
