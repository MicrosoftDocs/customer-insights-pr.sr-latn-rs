---
title: Segmenti u uvidima u ciljnu grupu
description: Pregled segmenata i način kreiranja i upravljanja njima.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306274"
---
# <a name="segments-overview"></a>Pregled segmenata

Segmenti vam omogućavaju da grupišete klijente na osnovu demografskih, transakcionih ili atributa ponašanja. Možete da koristite segmente za ciljanje promotivnih kampanja, prodajnih aktivnosti i aktivnosti podrške klijenata kako biste postigli svoje poslovne ciljeve.

Korisnički profili koji se podudaraju sa filterima definicije segmenta nazivaju se *članovima* segmenta. Neka [ograničenja usluga](service-limits.md) se primenjuju.

## <a name="create-a-new-segment"></a>Kreirajte novi segment

Postoji više načina za kreiranje novog segmenta: 

- Složeni segment sa kreatorom segmenata: [Prazan segment](segment-builder.md#create-a-new-segment)
- Jednostavni segmenti sa jednim operatorom: [Brzi segment](segment-builder.md#quick-segments)
- Način omogućen veštačkom inteligencijom za pronalaženje sličnih klijenata: [Slični klijenti](find-similar-customer-segments.md)
- Predlozi omogućeni veštačkom inteligencijom zasnovani na merama ili atributima: [Predloženi segmenti za poboljšanje mera](suggested-segments.md)
- Predlozi zasnovani na aktivnostima: [Predloženi segmenti na osnovu aktivnosti klijenata](suggested-segments-activity.md)

## <a name="manage-existing-segments"></a>Upravljanje postojećim segmentima

Idite na stranicu **Segmenti** da biste prikazali sve sačuvane segmente i upravljali njima.

Svaki segment predstavljen je redom koji sadrži dodatne informacije o segmentu.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Izabrani segment sa padajućom listom opcija i dostupnim opcijama.":::

Sledeća radnja je dostupna kada odaberete segment:

- **Prikaz** detalja segmenta, uključujući trend broja članova, pregled članova segmenta.
- **Uredite** segment da biste promenili njegova svojstva.
- **Napravite duplikat** segmenta. Možete odabrati da uredite njegova svojstva ili jednostavno sačuvate duplikat.
- **Osvežite** segment tako da uključuje najnovije podatke.
- **Aktivirajte** ili **Deaktivirajte** segment. Segmenti imaju dva moguća stanja - aktivno ili neaktivno. Ova stanja dobro dođu prilikom uređivanja segmenta. Za neaktivne segmente definicija segmenta postoji, ali još uvek ne sadrži klijente. Kada aktivirate segment, njegovo stanje se menja iz „neaktivan“ u „aktivan“ i on počinje da traži klijente koji odgovaraju definiciji segmenta. Ako je [zakazano osvežavanje](system.md#schedule-tab) konfigurisano, neaktivni segmenti imaju **Status** naveden kao **Preskočeno**, što ukazuje da osvežavanje nije ni pokušano. Kada se aktivira neaktivni segment, osvežiće se i biće uključen u zakazana osvežavanja.
  Alternativno, možete da koristite funkcionalnost **Isplaniraj za kasnije** u padajućoj listi **Aktiviraj/Deaktiviraj** da navedete budući datum i vreme za aktivaciju i deaktivaciju određenog segmenta.
- **Preimenujte** segment.
- **Preuzmite** listu članova kao .CSV datoteku.
- **Upravljanje izvozima** da biste videli segment povezan sa izvozom i upravljali njime. [Saznajte više o izvozima.](export-destinations.md)
- **Izbrišite** segment.

## <a name="refresh-segments"></a>Osvežavanje segmenata

Možete da osvežite sve segmente odjednom ako izaberete **Osvežite sve** na stranici **Segmenti**, a možete i da osvežiti jedan ili više segmenata kada ih izaberete, pa odaberete **Osveži** iz opcija. Alternativno, možete konfigurisati ponavljajuće osvežavanje u odeljku **Administrator** > **Sistem** > **Raspored**.

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies). Možete izabrati status procesa da biste videli detalje o toku celog posla. Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.

## <a name="export-segments"></a>Izvoz segmenata

Segment možete izvesti sa stranice segmenata ili [stranica izvoza](export-destinations.md). 

1. Idite na stranicu **Segmenti**.

1. Izaberite **Prikaži još [...]** za segment koji želite da izvezete.

1. Izaberite **Upravljanje izvozom** sa padajuće liste radnji.

1. Otvara se stranica **Izvozi (pregled) za segment**. Možete da vidite sve konfigurisane izvoze grupisane prema izvozima koji sadrže trenutni segment ili ga ne sadrže.

   1. Da biste izabrani segment dodali u izvoz, izaberite izvoz na listi i izaberite **Dodaj segment**.

   1. Da biste kreirali novi izvoz sa izabranim segmentom, izaberite **Dodaj izvoz**. Za više informacija o kreiranju izvoza, pogledajte [Podešavanje novog izvoza](export-destinations.md#set-up-a-new-export).

1. Izaberite **Nazad** da se vratite na glavnu stranicu za segmente.

## <a name="view-processing-history-and-segment-members"></a>Pogledajte istoriju obrade i članove segmenta

Konsolidovane podatke o segmentu možete videti tako što ćete pregledati njegove detalje.

Na stranici **Segmenti** izaberite segment koji želite da pregledate.

Gornji deo stranice sadrži grafikon trenda koji vizuelno prikazuje promene u broju članova. Zadržite pokazivač iznad tačaka podataka da biste videli broj članova određenog datuma.

Možete da ažurirate vremenski okvir vizuelizacije.

> [!div class="mx-imgBorder"]
> ![Vremenski period segmenta](media/segment-time-range.png "Vremenski period segmenta")

Donji deo sadrži listu članova segmenta.

> [!NOTE]
> Polja koja se pojavljuju na ovoj listi zasnivaju se na atributima entiteta vašeg segmenta.
>
>Lista je pregled odgovarajućih članova segmenta i pokazuje prvih 100 zapisa vašeg segmenta tako da ga možete brzo proceniti i pregledati njegove definicije, ako je potrebno. Da biste videli sve odgovarajuće zapise, morate da [izvezete segment](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
