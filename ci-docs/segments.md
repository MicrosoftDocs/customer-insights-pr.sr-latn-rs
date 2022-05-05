---
title: Segmenti u uvidima kupaca
description: Pregled segmenata i način kreiranja i upravljanja njima.
ms.date: 03/30/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 9791e971387eb7db91ed7c4e4fe76552656013ba
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643545"
---
# <a name="segments-overview"></a>Pregled segmenata

Segmenti vam omogućavaju da grupišete klijente na osnovu demografskih, transakcionih ili atributa ponašanja. Možete da koristite segmente za ciljanje promotivnih kampanja, prodajnih aktivnosti i aktivnosti podrške klijenata kako biste postigli svoje poslovne ciljeve.

Korisnički profili koji se podudaraju sa filterima definicije segmenta nazivaju se *članovima* segmenta. Neka [ograničenja usluga](/dynamics365/customer-insights/service-limits) se primenjuju.

## <a name="create-a-new-segment"></a>Kreirajte novi segment

Postoji više načina za kreiranje novog segmenta: 

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

- Složeni segment sa graditeljem segmenata: [Napravite svoje](segment-builder.md#create-a-new-segment) 
- Jednostavni segmenti sa jednim operatorom: [Brzi segment](segment-builder.md#quick-segments) 
- Način omogućen veštačkom inteligencijom za pronalaženje sličnih klijenata: [Slični klijenti](find-similar-customer-segments.md) 
- Predlozi omogućeni veštačkom inteligencijom zasnovani na merama ili atributima: [Predloženi segmenti za poboljšanje mera](suggested-segments.md) 
- Predlozi zasnovani na aktivnostima: [Predloženi segmenti na osnovu aktivnosti klijenata](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Poslovni nalozi (B-to-B)](#tab/b2b)

- Složeni segment sa graditeljem segmenata: [Napravite svoje](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Upravljanje postojećim segmentima

Idite na stranicu **"Segmenti** " da biste prikazali sve sačuvane segmente i upravljali njima.

Svaki segment predstavljen je redom koji sadrži dodatne informacije o segmentu.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Izabrani segment sa padajućom listom opcija i dostupnim opcijama." lightbox="media/segments-selected-segment.png":::

Prilikom izbora segmenta dostupne su sledeće radnje:

- **Prikaz** detalja segmenta, uključujući trend broja članova, pregled članova segmenta.
- **Preuzmite** listu članova kao .CSV datoteku.
- **Uredite** segment da biste promenili njegova svojstva.
- **Napravite duplikat** segmenta. Možete odabrati da uredite njegova svojstva ili jednostavno sačuvate duplikat.
- **Osvežite** segment tako da uključuje najnovije podatke.
- **Aktivirajte** ili **Deaktivirajte** segment. Za neaktivne segmente definicija segmenta postoji, ali još uvek ne sadrži klijente. Aktivni segment traži kupce koji se podudaraju sa definicijom segmenta. Ako je [zakazano osvežavanje](system.md#schedule-tab) konfigurisano, neaktivni segmenti imaju **Status** naveden kao **Preskočeno**, što ukazuje da osvežavanje nije ni pokušano. Kada se aktivira neaktivni segment, osvežiće se i biće uključen u zakazana osvežavanja.
  Alternativno, možete da koristite funkcionalnost **Isplaniraj za kasnije** u padajućoj listi **Aktiviraj/Deaktiviraj** da navedete budući datum i vreme za aktivaciju i deaktivaciju određenog segmenta.
- **[Pronađite slične](find-similar-customer-segments.md)** kupce iz segmenta.
- **Preimenujte** segment.
- **Oznaka**[za upravljanje oznakama](work-with-tags-columns.md#manage-tags) za segment.
- **Preuzmite** listu članova kao .CSV datoteku.
- **Upravljanje izvozima** da biste videli segment povezan sa izvozom i upravljali njime. [Saznajte više o izvozima.](export-destinations.md)
- **Izbrišite** segment.
- **Kolone** za [prilagođavanje kolona](work-with-tags-columns.md#customize-columns) koje se prikazuju.
- **Filtriranje** po [oznakama](work-with-tags-columns.md#filter-on-tags).
- **Pretražite ime** za pretraživanje po imenu segmenta.

## <a name="refresh-segments"></a>Osvežavanje segmenata

Možete da osvežite sve segmente odjednom ako izaberete **Osvežite sve** na stranici **Segmenti**, a možete i da osvežiti jedan ili više segmenata kada ih izaberete, pa odaberete **Osveži** iz opcija. Alternativno, možete konfigurisati ponavljajuće osvežavanje u odeljku **Administrator** > **Sistem** > **Raspored**. Kada je periodično osvežavanje konfigurisano, primenjuju se sledeća pravila:
- Svi segmenti sa tipom "Dinamika **·**" ili **"Ekspanzija**" biće automatski osveženi na postavljenom kadentu. Kada se osvežavanje **dovrši, Status** označava da li je bilo problema u osvežavanju segmenta. Poslednje **osveženje prikazuje vreme** poslednjeg uspešnog osvežavanja. Ako dođe do greške, izaberite grešku da biste videli detalje o tome šta se dogodilo.
- Segmenti sa tipom **"Static** *" neće* biti automatski osveženi. Poslednje **osvežavanje** prikazuje vremensku osu poslednjeg ručnog pokretanje ili osvežavanje statičkih segmenata.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Izvoz segmenata

Segment možete izvesti sa stranice segmenata ili [stranica izvoza](export-destinations.md). 

1. Idite na stranicu **Segmenti**.

1. Izaberite **Prikaži još [...]** za segment koji želite da izvezete.

1. Izaberite **Upravljanje izvozom** sa padajuće liste radnji.

1. Otvara se stranica **Izvozi (pregled) za segment**. Možete videti sve konfigurisane izvoze grupisane prema tome da li sadrže trenutni segment ili ne.

   1. Da biste izabrani segment dodali izvozu, **Uredite** odgovarajući izvoz da biste izabrali odgovarajući segment, a zatim sačuvajte. U okruženjima za pojedinačne klijente možete umesto toga izabrati izvoz sa liste i izabrati **Dodaj segment** da biste postigli isti ishod.

   1. Da biste kreirali novi izvoz sa izabranim segmentom, izaberite **Dodaj izvoz**. Za više informacija o kreiranju izvoza, pogledajte [Podešavanje novog izvoza](export-destinations.md#set-up-a-new-export).

1. Izaberite **Nazad** da se vratite na glavnu stranicu za segmente.

## <a name="view-processing-history-and-segment-members"></a>Pogledajte istoriju obrade i članove segmenta

Konsolidovane podatke o segmentu možete videti tako što ćete pregledati njegove detalje.

Na stranici **Segmenti** izaberite segment koji želite da pregledate.

Gornji deo stranice sadrži grafikon trenda koji vizuelno prikazuje promene u broju članova. Zadržite pokazivač iznad tačaka podataka da biste videli broj članova određenog datuma.

Možete da ažurirate vremenski okvir vizuelizacije.

> [!div class="mx-imgBorder"]
> ![Vremenski period segmenta.](media/segment-time-range.png "Vremenski period segmenta")

Donji deo sadrži listu članova segmenta.

> [!NOTE]
> Polja koja se pojavljuju na ovoj listi zasnivaju se na atributima entiteta vašeg segmenta.
>
>Lista je pregled odgovarajućih članova segmenta i pokazuje prvih 100 zapisa vašeg segmenta tako da ga možete brzo proceniti i pregledati njegove definicije, ako je potrebno. Da biste videli sve odgovarajuće zapise, morate da [izvezete segment](export-destinations.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
