---
title: Prikaz profila klijenata
description: Steknite kombinovani prikaz objedinjenih podataka o klijentima.
ms.date: 09/30/2021
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
ms.openlocfilehash: 45ef6abcd612178a097569825e32ff9ac779de01
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643071"
---
# <a name="customer-profiles"></a>Profili klijenata

Stranica **Klijenti** prikazuje kombinovani prikaz vaših objedinjenih profila klijenata. Profili klijenata dostupni su nakon što [kreirate objedinjeni entitet klijenta](data-unification.md). Stranica vam omogućava da pretražujete klijente i definišete indeks za tu pretragu.

Klijenti mogu biti pojedinci ili organizacije. Svaki profil klijenta predstavljen je pločicom. Koristite kontrole paginacije da biste dobili više zapisa. Kartica prikazuje polja iz entiteta *Klijent* kako je definisano u **Indeks pretrage i filtriranja**. Sistem bira redosled polja unutar svake kartice.

Izaberite pločicu da biste videli podatke o izabranom klijentu na namenskoj stranici pod nazivom [Stranica sa detaljima o korisniku](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Stranica klijenata prikazuje pločice rezultata](media/customers-page-result-tiles-B2C.png "Stranica klijenata prikazuje pločice rezultata")

> [!NOTE]
> Ako ne vidite pločice kada izaberete **Klijenti** u navigaciji, vaš administrator mora da [definiše barem jedan atribut koji može da se pretražuje](search-filter-index.md) u **Indeks pretrage i filtriranja**.

## <a name="search-for-customers"></a>Pretraga klijenata

Pretražujte klijente unosom imena ili nekog drugog atributa u polje za pretragu. Pretraga funkcioniše samo u okviru entiteta _Klijent_ kreiran tokom procesa objedinjavanja podataka.

Kao administrator, možete konfigurisati atribute pretraživanja koristeći stranicu **Indeks pretrage i filtriranja**. Za više informacija idite na [Upravljanje indeksom pretrage i filtriranja](search-filter-index.md).

## <a name="filter-customers"></a>Filtriranje klijenata

Klijente možete filtrirati prema poljima entiteta _Klijent_. Slično pretraživanju, vaš administrator će prvo morati da definiše polja tako da se mogu filtrirati na stranici **Indeks pretrage i filtriranja**.

1. Izaberite **Prikaži filtere** na stranici **Klijenti**.

1. Označite polja pored atributa po kojima želite da filtrirate klijente.

1. Uklonite filtere izborom **Obriši filtere** na stranici **Klijenti**.

## <a name="customer-details-page"></a>Stranica sa detaljima o klijentima

Izaberite bilo koju pločicu klijenta da biste otvorili **stranicu sa detaljima o klijentu**. Ovaj prikaz sadrži objedinjene informacije za izabranog klijenta. Podaci o klijentima uključuju sledeći sadržaj:

**Pločica profila klijenta**: Ova pločica prikazuje različite vrednosti objedinjenog entiteta _Klijent_. Ako polje nema vrednost za izabrani profil klijenta, neće se prikazati. Pločica je strukturirana u delove:  
  - Prvi odeljak prikazuje unapred definisan skup polja, nakon čega slede sva polja koja su deo indeksa pretrage i filtriranja. Sva polja vezana za adresu kombinuju se u jedan red ako profil sadrži takva polja. 
  - **Kontakti za ovog klijenta**: U okruženjima za poslovne naloge, videćete sve povezane kontakte za ovog klijenta kao drugi odeljak. Svaki kontakt je prikazan sa svojim poljima. Prazna polja su skrivena.
  - **Dodatna polja**: Prikazuje preostala polja izabranog klijenta, osim ID-ova. 
  - **ID-ovi**: Navodi sve ID-ove pod odgovarajućim nazivom entiteta. Polja su identifikovana kao ID-ovi svojom semantikom, koja ih kategoriše kao takve.

**Vremenska osa aktivnosti**: Prikazuje podatke ako ste konfigurisali aktivnosti. Prikaz vremenske ose sadrži hronološki sortirane aktivnosti izabranog klijenta, počevši od najnovije aktivnosti. Više informacija potražite u [aktivnostima klijenta](activities.md).

**Uvidi**:  
  - **Mere**: Prikazuje da li ste konfigurisali jednu ili više mera atributa klijenta. Uključuju izračunate KPI-jeve oko vaših klijenata na nivou pojedinačnog klijenta. Za više informacija idite na [Definisanje mera i upravljanje njima](measures.md).

  - **Potencijalna interesovanja, potencijalni brendovi**: Prikazuje da li ste konfigurisali obogaćivanje afiniteta prema brendu ili interesovanju. Predstavlja potencijalna interesovanja i afinitete za brendove zasnovane na drugim klijentima čiji je profil sličan profilu izabranog klijenta. Za više informacija idite na [Obogaćivanje profila klijenata afinitetima prema brendovima i interesovanjima](enrichment-microsoft.md).

Da biste se vratili na stranicu za pretragu klijenata, izaberite **Natrag na klijente**.

## <a name="next-steps"></a>Sledeći koraci

[Dodajte još izvora podataka](data-sources.md), [obogatite objedinjene profile](enrichment-hub.md) ili [kreirajte segmente](segments.md) za rad sa objedinjenim profilima klijenata u drugim aplikacijama.


[!INCLUDE [footer-include](includes/footer-banner.md)]
