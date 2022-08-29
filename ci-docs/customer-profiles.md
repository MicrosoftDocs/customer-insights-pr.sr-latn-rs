---
title: Prikaz profila klijenata
description: Prikazivanje objedinjenih podataka o klijentima, uključujući korišćenje pretrage i filtriranja
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 0c8edfd8f45ce7770d568811df2b38be1b04e73a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303800"
---
# <a name="view-customer-profiles"></a>Prikaz profila klijenata

Profili klijenata su dostupni kada kreirate [objedinjeni *entitet* kupca](data-unification.md). Kombinovani prikaz objedinjenih profila klijenata prikazuje se na stranici " **Kupci** ". Klijenti mogu biti pojedinci ili organizacije.

Idite na stranicu **"** Kupci" da biste prikazali kupce i njihove profile. Svaki profil klijenta predstavljen je pločicom. Koristite kontrole paginacije da biste dobili više zapisa. Kartica prikazuje polja iz entiteta *Klijent* kako je definisano u **Indeks pretrage i filtriranja**. Sistem bira redosled polja unutar svake kartice.

> [!NOTE]
> Ako ne možete da vidite pločice kada izaberete **opciju "Kupci**", administrator mora [da definiše bar jedan atribut koji se može pretraživati](search-filter-index.md) u indeksu **Search & filter**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Stranica &quot;Kupci&quot; koja prikazuje pločice rezultata.":::

Izaberite neku od sledećih radnji:
- [Prikaz detalja o kupcu](#view-customer-details)
- [Upravljanje indeksom pretrage & filtera](search-filter-index.md) (samo administratori)
- [Filtriranje klijenata](#filter-customers)
- **Razvijanje kartica** ili skupljanje **kartica** da biste razvili ili skupili informacije prikazane na pločici kupca
- **Sortiranje po** određenom atributu
- [Pretraga klijenata](#search-for-customers)

  > [!NOTE]
  > Da bi koristio pretragu i filter, administrator mora da konfiguriše atribute koji se mogu pretraživati i definiše polja koja se mogu filtrirati pomoću indeksa search & filter.

## <a name="search-for-customers"></a>Pretraga klijenata

Potražite kupce unošenjem imena ili nekog drugog atributa u kupce **pretrage**. Atribute koji se mogu pretraživati definiše administrator i potiиu iz objedinjeni entitet *klijenta*.

> [!NOTE]
> **Niska** je jedini tip podataka koji je uključen u pretragu. Koristite ga u polju Pretraži **kupce** na stranici "Kupci" da biste potražili kupce.

## <a name="filter-customers"></a>Filtriranje klijenata

Filtrirajte kupce po poljima *entiteta* kupca. Administrator definiše polja koja se mogu filtrirati.

1. Na stranici **"** Kupci" izaberite stavku **Prikaži filtere**. Prikazaće se okno "Filter".

1. Označite polja pored atributa po kojima želite da filtrirate klijente.

1. Uklonite sve filtere tako što ćete potvrditi **izbor u polju za** potvrdu Obriši filtere ili o opozovite izbor u polju za potvrdu pored izabranog atributa.

1. Kliknite **na dugme Sakrij filtere** da biste zatvorili okno sa filterima.

1. Da biste sačuvali rezultate filtera kao [segment](segments.md), izaberite sačuvaj **filtere kao segment**.
   1. Unesite ime segmenta.
   1. Kliknite **na dugme** "Sačuvaj" da biste sačuvali segment.
   1. Odaberite da li ćete odmah pokrenuti segment tako što ćete izabrati stavku **Aktiviraj** ili pokreni **kasnije**.

## <a name="view-customer-details"></a>Prikaz detalja o kupcu

Na stranici **"** Kupci" izaberite pločicu kupca da biste videli detalje za izabranog kupca.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Stranica sa detaljima o kupcu.":::

Detalji o klijentu obuhvataju:

**Pločica profila kupca** prikazuje različite vrednosti iz objedinjeni *entitet* kupca. Ako polje nema vrednost za izabrani profil kupca, neće se prikažeti osim polja adrese. Pločica je strukturirana u delove:

- Prvi odeljak prikazuje unapred definisan skup polja, nakon čega slede sva polja koja su deo indeksa pretrage i filtriranja. Sva polja vezana za adresu se kombinuju u jedan red, što pokazuje čak i ako profil ne sadrži informacije o adresi.
- **Kontakti za ovog kupca** prikazuju se u okruženjima za poslovne naloge (od B do B). Svaki kontakt je prikazan sa svojim poljima. Prazna polja su skrivena.
- **Dodatna** polja prikazuju preostala polja izabranog kupca, osim ID-ova.
- **ID-ove** navodi sve ID-ove pod odgovarajućim imenom entiteta. Polja su identifikovana kao lične id-ove po svojoj semantici.

**Vremenska osa** aktivnosti prikazuje podatke ako ste konfigurisali [aktivnosti](activities.md). Prikaz vremenske ose sadrži hronološki sortirane aktivnosti izabranog klijenta, počevši od najnovije aktivnosti.

**Uvidi**:

- **Mere pokazuju** da li ste konfigurisali [mere atributa klijenta](measures.md). Uključuju izračunate KPI-jeve oko vaših klijenata na nivou pojedinačnog klijenta.

- **Potencijalna interesovanja, potencijalni brendovi** pokazuju da li ste konfigurisali brend [ili obogaćivanje afiniteta interesovanja](enrichment-microsoft.md). Predstavlja potencijalna interesovanja i afinitete za brendove zasnovane na drugim klijentima čiji je profil sličan profilu izabranog klijenta.

Da biste se vratili na stranicu **"** Kupci", kliknite na dugme **"Nazad na kupce"**.

## <a name="next-steps"></a>Sledeći koraci

[Dodajte još izvora podataka](data-sources.md), [obogatite objedinjene profile](enrichment-hub.md) ili [kreirajte segmente](segments.md) za rad sa objedinjenim profilima klijenata u drugim aplikacijama.

[!INCLUDE [footer-include](includes/footer-banner.md)]
