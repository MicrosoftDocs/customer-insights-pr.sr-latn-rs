---
title: Kreiranje objedinjenog profila kontakata (pregled)
description: Pređite kroz proces ujedinjenja podataka da biste kreirali jedan glavni skup kontakata.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305094"
---
# <a name="create-a-unified-contact-profile-preview"></a>Kreiranje objedinjenog profila kontakata (pregled)

Nakon ujedinjenja [poslovnih naloga](map-entities.md), opcionalno možete da ujedinite kontakte za ta konta i povežete objedinjene kontakte sa objedinjenim nalozima. Proces ujedinjenja kontakata mapira kontakt podatke iz više izvora podataka, uklanja duplikate, podudara se sa podacima u entitetima, podešava semantičko mapiranje, kreira odnosi između kontakata i naloga, a zatim kreira objedinjeni profil kontakata.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Prvih nekoliko koraka su identični koracima za ujedinjavanje naloga.

## <a name="prerequisites"></a>Preduslovi

Zapisi naloga i kontakata moraju imati jedinstveni ključ (koji se naziva strani ključ) koji ih povezuje. Na primer, ID konta koji postoji u zapisu poslovnog kontakta i zapisu kontakta koji povezuje nalog i kontakt.

## <a name="preview-limitations"></a>Ograničenja pregleda

- Kontakti bez veze sa nalogom se odlaћu.
- Ako je nalog deduplicated, zapis pobednika se identifikuje na osnovu željenih opcija objedinjavanja. Gubitnički zapisi nisu izabrani i zato se odustaju. Kontakti povezani sa izgubljenim zapisima se odlaћu.
- Nalog može imati više kontakata, ali je kontakt povezan sa jednim nalogom.
- Atributi kontakta mapirani u semantičkom koraku mapiranja su jedini atributi koji se mogu prikazati na kartici "Kupac". Međutim, na raspolaganju je 17 atributa.

## <a name="select-source-fields"></a>Izbor izvornih polja

1. U okviru **Ujedini kontakte (pregled), izaberite** stavku Prvi **koraci**.

1. [Izaberite entitete i polja za](map-entities.md) izvore podataka kontakta, uključujući primarne ključeve i tipove atributa.

1. Izaberite **Sledeće**.

## <a name="remove-duplicate-records"></a>Uklanjanje dupliranih zapisa

1. Opcionalno, [definišite pravila deduplikacije](remove-duplicates.md) za izabrane entitete.

1. Izaberite **Sledeće**.

## <a name="match-conditions"></a>Uslovi podudaranja

1. [Definišite redosled podudaranja i pravila za](match-entities.md) podudaranje sa unakrsnim entitetom.

1. Izaberite **Sledeće**.

## <a name="unify-contact-fields"></a>Objedinjavanje polja kontakata

1. [Kombinujte i izuzmite polja kontakata](merge-entities.md).

1. Izaberite **Sledeće**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Definisanje semantičkih polja za objedinjene kontakte

Ovaj korak u procesu ujedinjenja mapira vaša objedinjena polja kontakata u semantičke tipove. U programu B-na-B, kartice kupaca prikazuju konta. Kada je kartica izabrana, svi kontakti povezani sa nalogom će biti prikazani. Polja koja mapirate u ovom koraku su polja koja će biti prikazana na karticama.

1. Izaberite semantički tip koji se mapira u svako objedinjeno polje. Izaberite **nijednu** ako semantički tip nije dostupan.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Snimak ekrana stranice semantičkih polja da bi se definisali semantički tipovi." lightbox="media/semantic_mapping.png":::

1. Kada mapišete sva objedinjena polja, kliknite na dugme " **Dalje"**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Postavljanje relacije između kontakata i poslovnih kontakata

Ovaj korak u procesu ujedinjenja povezuje podatke o kontaktu sa odgovarajućim podacima naloga.

1. Za svaki entitet unesite sledeće informacije:

   - **Strani ključ iz entiteta kontakta**: Odaberite atribut koji povezuje entitet kontakta sa nalogom.
   - **Da biste nalogili** entitet: Odaberite entitet naloga povezan sa kontaktom.

   :::image type="content" source="media/contact_relationship.png" alt-text="Snimak ekrana stranice &quot;Relacija&quot; da biste povezali entitete kontakta i naloga.":::

1. Izaberite **Sledeće**.

## <a name="review-contact-unification"></a>Redigovanje ujedinjenja kontakta

Redigujte rezime promena, kreirajte objedinjeni profil i pregledajte rezultate.

### <a name="review-and-create-contact-profiles"></a>Pregled i kreiranje profila kontakata

Ovaj poslednji korak u procesu ujedinjenja prikazuje rezime koraka u procesu i pruža šansu za promene pre nego što kreirate objedinjeni profil kontakata.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Snimak ekrana redigovanje i kreiranje profila kontakata.":::

1. Izaberite **uredite** bilo koji od koraka ujedinjenja kontakta da biste pregledali i napravili bilo kakve promene.

1. Ako ste zadovoljni izborom, izaberite stavku Kreiraj **profile kontakata**. Stranica **"Ujedini** " se prikazuje dok se kreira objedinjeni profil kontakta.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Snimak ekrana stranice &quot;Ujedini kontakte&quot; sa pločicama koje prikazuju redosled ili osvežavanje.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritam ujedinjenja zahteva neko vreme da se dovrši i ne možete da promenite konfiguraciju dok se ona ne dovrši.

### <a name="view-the-results-of-contact-unification"></a>Prikaz rezultata ujedinjenja kontakta

Kada se objedini, stranica **"Ujedinjenje** > **podataka** " prikazuje broj objedinjenih profila kontakata. Rezultati svakog koraka u procesu ujedinjenja prikazuju se na svakoj pločici. Na primer, **polja izvora** prikazuju broj mapiranih atributa (polja) i dupliranih **zapisa koji** prikazuje broj pronađenih dupliranih zapisa.

:::image type="content" source="media/unified_contacts.png" alt-text="Snimak ekrana stranice &quot;Ujedinjenje podataka&quot; nakon objedinjenih kontakata.":::

> [!TIP]
> Pločica **"Podudarni** uslovi" prikazuje se samo ako je izabrano više entiteta.

Preporučujemo da pregledate rezultate, posebno kvalitet pravila podudaranja i da [ih usavršite](data-unification-update.md#manage-match-rules) ako je potrebno.

Kada je to potrebno, [promenite postavke ujedinjenja kontakta i](data-unification-update.md) ponovo pokrenite objedinjeni profil.

### <a name="verify-output-entities-from-data-unification"></a>Provera izlaznih entiteta iz ujedinjenja podataka

Idite na **entitete** > **podataka** da biste proverili izlazne entitete.

Objedinjeni entitet profila kontakata pod nazivom *"Kontaktprofile*" prikazuje se u odeljku **Semantički entiteti**. Prvim uspešnim pokretanjem ujedinjenja kreira se objedinjeni *entitet ContactProfile*. Sva naredna trčanja proširuju taj entitet.

Entitet *ContactsCustomer* (pregled) se kreira i prikazuje u odeljku **Profili**. Ovaj entitet sadrži podatke o kontaktu bez veza sa nalozima. Ovaj entitet se koristi kao ulaz u semantičko mapiranje i korake relacija ujedinjenja kontakata.

Deduplication and conflation entiteti se kreiraju i prikazuju u odeljku **Sistem**. Deduplicated entitet za svaki od izvornih entiteta se kreira sa **Deduplication_DataSource_Entity**. Entitet **ContactsConflationMatchPairs sadrži** informacije o podudaranjima sa više entiteta.

Izlazni entitet uklanjanja duplikata sadrži sledeće informacije:
- ID-ovi/Ključevi
  - Primarni ključ i polja alternativnog ID-a. Polje alternativnog ID-a se sastoji od svih alternativnih ID-ova identifikovanih za zapis.
  - Polje Deduplication_GroupId prikazuje grupu ili klaster identifikovane u okviru entiteta koji grupiše sve slične zapise na osnovu navedenih polja uklanjanja duplikata. Ovo se koristi u svrhe obrade sistema. Ako nisu navedena ručna pravila za uklanjanje duplikata i ako se primenjuju sistemski definisana pravila za uklanjanje duplikata, ovo polje možda nećete pronaći u izlaznom entitetu uklanjanja duplikata.
  - Deduplication_WinnerId: Ovo polje sadrži ID pobednika iz identifikovanih grupa ili klastera. Ako je Deduplication_WinnerId ista kao vrednost primarnog ključa za zapis, to znači da je taj zapis dobitni.
- Polja koja se koriste za definisanje pravila za uklanjanje duplikata.
- Odredite pravila i ocenite polja da označite koja su od pravila za uklanjanje duplikata primenjena i koji rezultat vraća algoritam za podudaranje.

## <a name="next-step"></a>Sledeći korak

Konfigurišite aktivnosti, obogaćivanje [ili](activities.md) odnosi biste [stekli više uvida u svoje kontakte.](enrichment-hub.md)[...](relationships.md)
