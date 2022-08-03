---
title: Pregled mera
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
ms.openlocfilehash: ead57ccbdcaf9f86ee54d1f15de71a63f2e1081b
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170865"
---
# <a name="measures-overview"></a>Pregled mera

Mere vam pomažu da bolje razumete ponašanje klijenata i poslovne rezultate. Oni gledaju na relevantne vrednosti iz [objedinjenih profila](data-unification.md). Na primer, preduzeće želi da vidi *ukupnu potrošnju po klijentu* da biste razumeli istoriju kupovine pojedinačnog klijenta ili meru *ukupne prodaje preduzeća* da biste razumeli ukupni prihod u celom preduzeću.

Kreirajte mere za planiranje poslovnih aktivnosti tako što ćete ispitati podatke o kupcima i izdvojiti uvide. Na primer, kreirajte meru ukupne ukupne potrošne *vrednosti po kupcu* *i ukupan povraćaj po kupcu* da biste identifikovali grupu kupaca sa velikom potnošuom, a ipak visokim povraćajem. Zatim kreirajte [segment zasnovan](segments.md) na ovim merama da biste vozili sledeće najbolje radnje.

## <a name="create-a-measure"></a>Kreiranje mere

Odaberite način kreiranja mere na osnovu ciljne korisnici.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

- Od nule sa graditeljem mera: [Izgradite sopstveni](measure-builder.md).
- Iz najčešće korišćenih mera: koristite [unapred definisane predloške](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Poslovni nalozi (B-to-B)](#tab/b2b)

Od nule sa graditeljem mera: [Izgradite sopstveni](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Upravljanje postojećim merama

Idite na **stranicu "** Mere" da biste prikazali mere koje ste kreirali, njihov status, tip mere i poslednji put kada su podaci osveženi. Listu mera možete da sortirate po bilo kojoj koloni ili da koristite polje za pretragu da biste pronašli meru kojom želite da upravljate.

Izaberite pored mere da biste prikazali dostupne radnje. Izaberite ime mere da biste pregledali izlaz i preuzeli CSV datoteku.

:::image type="content" source="media/measures-actions.png" alt-text="Radnje za upravljanje jedinstvenim merama."lightbox="media/measures-actions.png":::

- **Uredite** meru da biste promenili njena svojstva.
- **Osvežite** meru da biste uključili najnovije podatke.
- **Preimenujte** meru.
- **Aktivirajte** **ili deaktivirajte** meru. Neaktivne mere se neće osvežiti tokom planiranog [osvežavanja i](system.md#schedule-tab)**status će** **biti naveden kao "Preskočen**", što ukazuje na to da osveženje nije ni pokušano.
- **Oznaka** za [upravljanje oznakama](work-with-tags-columns.md#manage-tags) za ovu meru.
- **Izbrišite** meru.
- **Kolone** za [prilagođavanje kolona](work-with-tags-columns.md#customize-columns) koje se prikazuju.
- **Filtriranje** po [oznakama](work-with-tags-columns.md#filter-on-tags).
- **Pretražite ime** za pretraživanje po imenu mere.

## <a name="refresh-measures"></a>Mere osvežavanja

Mere se mogu osvežiti automatskim rasporedom ili osvežiti ručno na zahtev. Da biste ručno osvežili jednu ili više mera, izaberite ih i odaberite stavku **Osveži**. Da biste [zakazali automatsko osvežavanje](system.md#schedule-tab), idite **na administrativni** > **plan** > **sistema**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
