---
title: Pregled segmenata
description: Pregled segmenata i način kreiranja i upravljanja njima.
ms.date: 05/20/2022
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
ms.openlocfilehash: 8b2c2f9b84bf8b7f37d1468b871946ecb3e6aa98
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050964"
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
- **Napravite duplikat** segmenta. Možete odabrati da odmah uredite njegova svojstva ili da sačuvate duplikat.
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

- Svi segmenti sa tipom "Dinamika **·**" ili **"Ekspanzija**" biće automatski osveženi na postavljenom kadentu. Kada se osvežavanje dovrši **, Status** označava da li je bilo problema u osvežavanju segmenta. Poslednje **osveženje prikazuje vreme** poslednjeg uspešnog osvežavanja. Ako dođe do greške, izaberite grešku da biste videli detalje o tome šta se dogodilo.
- Segmenti sa tipom **"Static** *" neće* biti automatski osveženi. Poslednje **osvežavanje** prikazuje vremensku osu poslednjeg ručnog pokretanje ili osvežavanje statičkih segmenata.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Izvoz segmenata

Segment možete izvesti sa stranice segmenata ili [stranica izvoza](export-destinations.md). 

1. Idite na stranicu **Segmenti**.

1. Izaberite vertikalnu elipsu () za&vellip; segment koji želite da izvezete.

1. Izaberite **Upravljanje izvozom** sa padajuće liste radnji.

1. Otvara se stranica **Izvozi (pregled) za segment**. Možete videti sve konfigurisane izvoze grupisane prema tome da li sadrže trenutni segment ili ne.

   1. Da biste izabrani segment dodali izvozu, **Uredite** odgovarajući izvoz da biste izabrali odgovarajući segment, a zatim sačuvajte. U okruženjima za pojedinačne kupce, umesto toga možete izabrati izvoz sa liste i izabrati stavku Dodaj **segment da** biste postigli isti ishod.

   1. Da biste kreirali novi izvoz sa izabranim segmentom, izaberite **Dodaj izvoz**. Za više informacija o kreiranju izvoza, pogledajte [Podešavanje novog izvoza](export-destinations.md#set-up-a-new-export).

1. Izaberite **Nazad** da se vratite na glavnu stranicu za segmente.

## <a name="track-usage-of-a-segment"></a>Praćenje korišćenja segmenta

Ako segmente koristite u aplikacijama, koje se zasnivaju na istoj organizaciji Microsoft Dataverse koja je povezana sa uvidom kupaca, možete da pratite korišćenje segmenta. Za [segmente uvida kupaca koji se koriste u putovanjima kupaca u Dynamics 365 Marketingu](/dynamics365/marketing/real-time-marketing-ci-profile), sistem vas obaveštava o korišćenju tog segmenta.

Prilikom uređivanja segmenta koji se koristi u okruženju "Uvidi kupaca" ili u put koji pređe korisnik u okviru stavke "Marketing", [baner u](segment-builder.md) izradi segmenata vas obaveštava o zavisnostima. Detalje zavisnosti možete da proverite direktno sa reklamnog natpisa ili izborom opcije "Korišćenje **"** u izradi segmenta.

Okno **za korišćenje** segmenta prikazuje detalje o korišćenju ovog segmenta u aplikacijama zasnovanim Dataverse na tome. Za segmente koji se koriste u putovanjima kupaca, pronaći ćete vezu za pregled putovanja u marketingu gde se ovaj segment koristi. Ako imate dozvole za pristup marketinškoj aplikaciji, tamo možete pristupiti više detalja.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Bočno okno sa detaljima korišćenja segmenta u izradi segmenta.":::

Sistem vas obaveštava o korišćenju praćenog segmenta kada pokušate da ga izbrišete. Ako se segment koji ćete izbrisati koristi u put koji pređe korisnik u marketingu, to putovanje će prestati za sve korisnike u segmentu. Ako je putovanje deo marketinške kampanje, brisanje će uticati na samu kampanju. Međutim, segment i dalje možete da izbrišete uprkos upozorenjima.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dijalog za potvrđivanje brisanja segmenta kada se segment koristi u aplikaciji Dataverse .":::

### <a name="supported-apps"></a>Podržane aplikacije

Korišćenje se trenutno prati u sledećim aplikacijama Dataverse:

- [Putovanja kupaca u Dynamics 365 marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

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
