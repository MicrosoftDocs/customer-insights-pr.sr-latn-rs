---
title: Redigovanje ujedinjenja podataka
description: Pregledajte korake za ujedinjenje podataka, kreirajte objedinjene profile klijenata i pregledajte rezultate
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303984"
---
# <a name="review-data-unification"></a>Redigovanje ujedinjenja podataka

Redigujte rezime promena, kreirajte objedinjeni profil i pregledajte rezultate.

## <a name="review-and-create-customer-profiles"></a>Pregled i kreiranje profila klijenata

Ovaj poslednji korak u procesu ujedinjenja prikazuje rezime koraka u procesu i pruža šansu da izvršite promene pre nego što kreirate objedinjeni profil.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Snimak ekrana pregleda i kreiranje profila klijenata.":::

1. Izaberite **uredite** bilo koji od koraka za ujedinjenje podataka da biste pregledali i napravili bilo kakve promene.

1. Ako ste zadovoljni izborom, izaberite stavku Kreiraj **profile kupaca** (ili Kreiraj **profile naloga** za B-na-B). Stranica **"Ujedini** " prikazuje se dok se kreira objedinjeni profil kupca.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Snimak ekrana stranice &quot;Ujedini&quot; sa pločicama koje prikazuju red ili osvežavanje.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritam ujedinjenja zahteva neko vreme da se dovrši i ne možete da promenite konfiguraciju dok se ona ne dovrši.

## <a name="view-the-results-of-data-unification"></a>Prikaz rezultata ujedinjenja podataka

Nakon ujedinjenja, stranica **"Ujedinjenje** > **podataka** " prikazuje broj objedinjenih profila klijenata (ili profila naloga za B-na-B). Rezultati svakog koraka u procesu ujedinjenja prikazuju se na svakoj pločici. Na primer, **polja izvora** prikazuju broj mapiranih atributa (polja) i dupliranih **zapisa koji** prikazuje broj pronađenih dupliranih zapisa.

:::image type="content" source="media/m3_unified.png" alt-text="Snimak ekrana stranice &quot;Ujedinjavanje podataka&quot; nakon objedinjenih podataka.":::

> [!TIP]
> Pločica **"Podudarni** uslovi" prikazuje se samo ako je izabrano više entiteta.

Preporučujemo da pregledate rezultate, posebno kvalitet pravila podudaranja i da [ih usavršite](data-unification-update.md#manage-match-rules) ako je potrebno.

Kada je to potrebno, [promenite postavke ujedinjenja i ponovo](data-unification-update.md) pokrenite objedinjeni profil.

### <a name="verify-output-entities-from-data-unification"></a>Provera izlaznih entiteta iz ujedinjenja podataka

Idite na **entitete** > **podataka** da biste proverili izlazne entitete.

Objedinjeni entitet profila kupca pod *nazivom*"Kupac" prikazuje se u odeljku **"Profili**". Prvo uspešno pokretanje ujedinjenja kreira objedinjeni entitet *kupca*. Sva naredna trčanja proširuju taj entitet.

Deduplication and conflation entiteti se kreiraju i prikazuju u odeljku **Sistem**. Deduplicated entitet za svaki od izvornih entiteta se kreira sa **Deduplication_DataSource_Entity**. Entitet **ConflationMatchPairs sadrži** informacije o podudaranjima sa više entiteta.

Izlazni entitet uklanjanja duplikata sadrži sledeće informacije:
- ID-ovi/Ključevi
  - Primarni ključ i polja alternativnog ID-a. Polje alternativnog ID-a se sastoji od svih alternativnih ID-ova identifikovanih za zapis.
  - Polje Deduplication_GroupId prikazuje grupu ili klaster identifikovane u okviru entiteta koji grupiše sve slične zapise na osnovu navedenih polja uklanjanja duplikata. Ovo se koristi u svrhe obrade sistema. Ako nisu navedena ručna pravila za uklanjanje duplikata i ako se primenjuju sistemski definisana pravila za uklanjanje duplikata, ovo polje možda nećete pronaći u izlaznom entitetu uklanjanja duplikata.
  - Deduplication_WinnerId: Ovo polje sadrži ID pobednika iz identifikovanih grupa ili klastera. Ako je Deduplication_WinnerId ista kao vrednost primarnog ključa za zapis, to znači da je taj zapis dobitni.
- Polja koja se koriste za definisanje pravila za uklanjanje duplikata.
- Odredite pravila i ocenite polja da označite koja su od pravila za uklanjanje duplikata primenjena i koji rezultat vraća algoritam za podudaranje.

## <a name="next-step"></a>Sledeći korak

- Za B-to-B opcionalno izvršite ujedinjenje [kontakata](data-unification-contacts.md).

- Za B-to-C konfigurišite [aktivnosti](activities.md), [obogaćivanje](enrichment-hub.md), [odnosi](relationships.md) ili [mere](measures.md) za sticanje više uvida o vašim klijentima.

[!INCLUDE[footer-include](includes/footer-banner.md)]
