---
title: Razumevanje i upravljanje merama
description: Saznajte kako mere pomažu u analizi i odražavanju performansi vašeg poslovanja.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 84a3a10a2517258c1f895800882b9c67391ec3de
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643306"
---
# <a name="measures-overview"></a>Pregled mera

Mere vam pomažu da bolje razumete ponašanje klijenata i poslovne rezultate. Oni gledaju na relevantne vrednosti iz [objedinjenih profila](data-unification.md). Na primer, preduzeće želi da vidi *ukupnu potrošnju po klijentu* da biste razumeli istoriju kupovine pojedinačnog klijenta ili meru *ukupne prodaje preduzeća* da biste razumeli ukupni prihod u celom preduzeću.  

Mere se kreiraju pomoću [izrade mera](measure-builder.md), platforme za upite podataka sa različitim operatorima i jednostavnim opcijama mapiranja. Omogućava vam da filtrirate podatke, grupišete rezultate, otkrivate [putanje relacija između entiteta](relationships.md) i pregledate izlaz. Unapred definisane [predloške možete koristiti](measure-templates.md) za efikasno konfigurisanje najčešće korišćenih mera.

Koristite kreator mera za planiranje poslovnih aktivnosti tako što ćete potražiti podatke o klijentima i izvući uvide. Na primer, kreiranje mere *ukupna potrošnja po klijentu* i *ukupan povraćaj po klijentu* pomaže u identifikovanju grupe klijenata sa visokom potrošnjom, ali i visokim povraćajem. Segment možete [kreirati na osnovu](segments.md) ovih mera da biste disk jedinicu sledeće najbolje radnje.

## <a name="manage-your-measures"></a>Upravljanje merama

Spisak mera možete pronaći na stranici **Mere**.

Pronaći ćete informacije o tipu mere, autoru, datumu nastanka, statusu i stanju. Kada na listi izaberete meru, možete da pregledate izlaz i preuzmete CSV datoteku.

:::image type="content" source="media/measures-actions.png" alt-text="Radnje za upravljanje jedinstvenim merama."lightbox="media/measures-actions.png":::

Prilikom izbora mere dostupne su sledeće radnje:

- **Uredite** konfiguraciju mere.
- **Dupliraj** meru. Možete odabrati da uredite njegova svojstva ili jednostavno sačuvate duplikat.
- **Osvežite** meru na osnovu najnovijih podataka. Da biste istovremeno osvežili sve mere, izaberite sve mere, a zatim **osvežite**.
- **Preimenujte** meru.
- **Aktivirajte** ili **Deaktivirajte**. Neaktivne mere se neće osvežavati tokom [zakazanog osvežavanja](system.md#schedule-tab).
- **Oznaka**[za upravljanje oznakama](work-with-tags-columns.md#manage-tags) za segment.
- **Izbrišite** meru.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Sledeći korak

Možete koristiti postojeće mere da biste kreirali [segment klijenata](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
