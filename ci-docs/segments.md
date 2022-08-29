---
title: Pregled segmenata
description: Pregled segmenata i način kreiranja i upravljanja njima.
ms.date: 08/12/2022
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
ms.openlocfilehash: d4de3a6af6bc7d54305a23e3fbd3cc95d464d352
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304812"
---
# <a name="segments-overview"></a>Pregled segmenata

Segmenti vam omogućavaju da grupišete klijente na osnovu demografskih, transakcionih ili atributa ponašanja. Možete da koristite segmente za ciljanje promotivnih kampanja, prodajnih aktivnosti i aktivnosti podrške klijenata kako biste postigli svoje poslovne ciljeve.

Profili kupaca ili kontakata koji se podudaraju sa filterima definicije segmenta nazivaju se *članovi* segmenta. Neka [ograničenja usluga](/dynamics365/customer-insights/service-limits) se primenjuju.

## <a name="create-a-segment"></a>Kreiranje segmenta

Odaberite način kreiranja segmenta na osnovu ciljne korisnici.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

- Složeni segmenti sa izradom segmenata: [Napravite sopstveni](segment-builder.md)
- Jednostavni segmenti sa jednim operatorom: [Brzi segment](segment-quick.md)
- Način pronalaženja sličnih klijenata sa AI napajanjem: [Slični kupci](find-similar-customer-segments.md)
- Predlozi sa AI napajanjem na osnovu mera ili atributa: Predloženi [segmenti zasnovani na merama](suggested-segments.md)
- Predlozi zasnovani na aktivnostima: [Predloženi segmenti na osnovu aktivnosti klijenata](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Poslovni nalozi (B-to-B)](#tab/b2b)

Segment naloga ili segment kontakata (pregled) sa izradom segmenata: [Napravite sopstveni](segment-builder.md)

> [!NOTE]
> Većina izvoznih odredišta zahteva kontakt informacije u marketinške svrhe. Zbog toga kreirajte segmente kontakata koje ćete koristiti za te izvoze.

---

## <a name="manage-existing-segments"></a>Upravljanje postojećim segmentima

Idite na stranicu **"Segmenti** " da biste prikazali segmente koje ste kreirali, njihov status i stanje i poslednji put kada su podaci osveženi. Listu segmenata možete sortirati po bilo kojoj koloni ili koristiti polje za pretragu da biste pronašli segment kojim želite da upravljate.

> [!TIP]
> U B-to-B okruženjima kolona **korisnici Tip** identifikuje da li je segment zasnovan na poslovnim kontaktima ili kontaktima.

Izaberite segment da biste prikazali dostupne radnje.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Izabrani segment sa padajućom listom opcija i dostupnim opcijama." lightbox="media/segments-selected-segment.png":::

- [**Prikažite**](#view-segment-details) detalje segmenta, uključujući trend brojanja članova i pregled članova segmenta.
- **Preuzmite** listu članova kao .CSV datoteku.
- **Uredite** segment da biste promenili njegova svojstva.
- **Napravite duplikat** segmenta. Možete odabrati da odmah uredite njegova svojstva ili da sačuvate duplikat.
- [**Osvežite**](#refresh-segments) segment da biste uključili najnovije podatke.
- **Aktivirajte** ili **Deaktivirajte** segment. Neaktivni segmenti se neće osvežiti tokom planiranog [osvežavanja i](schedule-refresh.md)**status će** **biti naveden kao "Preskočen**", što ukazuje na to da osveženje nije ni pokušano. Aktivni segmenti se osvežavaju na osnovu njihovog tipa: statični ili dinamički.
- **Napravite statički ili** učinite **dinamiku** tipom segmenta. Statički segmenti moraju biti osveženi ručno. Dinamički segmenti se automatski osvežavaju tokom osvežavanja sistema.
- [**Pronađite slične**](find-similar-customer-segments.md) kupce iz segmenta.
- **Preimenujte** segment.
- **Oznaka**[za upravljanje oznakama](work-with-tags-columns.md#manage-tags) za segment.
- [**Upravljajte izvozom da**](#export-segments) biste videli segmente vezane za izvoz i upravljali njima. [Saznajte više o izvozima.](export-destinations.md)
- **Izbrišite** segment.
- **Kolone** za [prilagođavanje kolona](work-with-tags-columns.md#customize-columns) koje se prikazuju.
- **Filtriranje** po [oznakama](work-with-tags-columns.md#filter-on-tags).
- **Pretražite ime** za pretraživanje po imenu segmenta.

## <a name="view-segment-details"></a>Prikaz detalja segmenta

Na stranici **"Segmenti** " izaberite segment za prikaz istorije obrade i članova segmenta.

Gornji deo stranice sadrži grafikon trenda koji vizuelno prikazuje promene u broju članova. Zadržite pokazivač iznad tačaka podataka da biste videli broj članova određenog datuma. Promenite vremenski okvir vizuelizacije.

:::image type="content" source="media/segment-time-range.png" alt-text="Vremenski period segmenta.":::

Donji deo sadrži listu članova segmenta.

> [!NOTE]
> Polja koja se pojavljuju na ovoj listi zasnivaju se na atributima entiteta vašeg segmenta.
>
> Lista je pregled odgovarajućih članova segmenta i pokazuje prvih 100 zapisa vašeg segmenta tako da ga možete brzo proceniti i pregledati njegove definicije, ako je potrebno. Da biste videli sve zapise koji se podudaraju, izaberite pogledajte **više koji otvara** stranicu [**"Entiteti"**](entities.md) ili izvezite segment [.](export-destinations.md)

## <a name="refresh-segments"></a>Osvežavanje segmenata

Segmenti se mogu osvežiti automatskim rasporedom ili ručno osvežiti na zahtev. Da biste ručno osvežili jedan ili više segmenata, izaberite ih i odaberite stavku **Osveži**.

Da biste [zakazali automatsko osvežavanje](schedule-refresh.md), idite **na administrativni** > **plan** > **sistema**. Primenjuju se sledeća pravila:

- Svi segmenti sa tipom "Dinamika **·**" ili **"Ekspanzija**" biće automatski osveženi na postavljenom kadentu. Kada se osvežavanje dovrši **, Status** označava da li je bilo problema u osvežavanju segmenta. Poslednje **osveženje prikazuje vreme** poslednjeg uspešnog osvežavanja. Ako dođe do greške, izaberite grešku da biste videli detalje o tome šta se dogodilo.
- Segmenti sa tipom **"Static** *" neće* biti automatski osveženi. Poslednje **osveženje prikazuje** vremensku osu poslednjeg puta kada je statički segment pokrenuti ili osveženi ručno.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Izvoz segmenata

Izvezite segmente u druge aplikacije da biste dalje koristili podatke. Izvezite segment sa stranice sa segmentima ili sa stranice [za izvoz](export-destinations.md).

1. Idite na stranicu **"Segmenti** " i izaberite segment koji želite da izvezete.

1. Izaberite **stavku Upravljanje izvozom**. Otvara se stranica **Izvozi (pregled) za segment**. Prikažite sve konfigurisane izvoze grupisane po tome da li sadrže trenutni segment ili ne.

   1. Da biste izabrani segment dodali izvozu, **Uredite** odgovarajući izvoz da biste izabrali odgovarajući segment, a zatim sačuvajte. U okruženjima za pojedinačne kupce izaberite izvoz sa liste i izaberite Dodaj **segment da** biste postigli isti ishod.

   1. Da biste kreirali novi izvoz sa izabranim segmentom, izaberite **Dodaj izvoz**. Za više informacija o kreiranju izvoza, pogledajte [Podešavanje novog izvoza](export-destinations.md#set-up-a-new-export).

1. Izaberite **Nazad** da se vratite na glavnu stranicu za segmente.

## <a name="track-usage-of-a-segment"></a>Praćenje korišćenja segmenta

Ako koristite segmente u aplikacijama koje se zasnivaju na istoj organizaciji Microsoft Dataverse koja je povezana sa uvidom kupaca, možete da pratite korišćenje segmenta. Za [segmente uvida kupaca koji se koriste u putovanjima kupaca u Dynamics 365 Marketingu](/dynamics365/marketing/real-time-marketing-ci-profile), sistem vas obaveštava o korišćenju tog segmenta.

Prilikom uređivanja segmenta koji se koristi u okruženju "Uvidi kupaca" ili u put koji pređe korisnik u okviru stavke "Marketing", [baner u](segment-builder.md) izradi segmenata vas obaveštava o zavisnostima. Proverite detalje zavisnosti direktno od reklamnog natpisa ili izborom opcije "Korišćenje **"** u izradi segmenta.

Okno **za korišćenje** segmenta prikazuje detalje o korišćenju ovog segmenta u aplikacijama zasnovanim Dataverse na tome. Za segmente koji se koriste u putovanjima kupaca, pronaći ćete vezu za pregled putovanja u marketingu gde se ovaj segment koristi. Ako imate dozvole za pristup marketinškoj aplikaciji, tamo prikažite više detalja.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Bočno okno sa detaljima korišćenja segmenta u izradi segmenta.":::

Sistem vas obaveštava o korišćenju praćenog segmenta kada pokušate da ga izbrišete. Ako se segment koji ćete izbrisati koristi u put koji pređe korisnik u marketingu, to putovanje će prestati za sve korisnike u segmentu. Ako je putovanje deo marketinške kampanje, brisanje će uticati na samu kampanju. Međutim, segment i dalje možete da izbrišete uprkos upozorenjima.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dijalog za potvrđivanje brisanja segmenta kada se segment koristi u aplikaciji Dataverse .":::

### <a name="supported-apps"></a>Podržane aplikacije

Korišćenje se trenutno prati u sledećim aplikacijama Dataverse:

- [Putovanja kupaca u Dynamics 365 marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
