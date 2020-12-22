---
title: Konfiguracija sistema u uvidima o korisnicima
description: Saznajte više o sistemskim podešavanjima u Dynamics 365 Customer Insights mogućnosti uvida o korisnicima.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406820"
---
# <a name="system-configuration"></a>Konfiguracija sistema

Stranica **Sistem** sadrži četiri kartice: **Status**, **Raspored**, **Osnovni podaci** i **Opšti podaci**.

> [!div class="mx-imgBorder"]
> ![Sistemska stranica](media/system-tabs.png "Sistemska stranica")

## <a name="status-tab"></a>Kartica Status

Kartica **Status** vam omogućava da pratite napredak unosa podataka, izvoza podataka i nekoliko važnih procesa proizvoda. Pregledajte informacije na ovoj kartici da biste se uverili u kompletnost aktivnih procesa.

Ova kartica sadrži tabele sa statusima za **izvore podataka**, **sistemske procese** i **pripremu podataka**. Svaka tabela prati **Ime** zadatka i odgovarajućeg entiteta, **Status** poslednjeg pokretanja i kada je **poslednji put ažuriran**.

Pregledajte detalje poslednjih nekoliko pokretanja zadataka odabirom imena.

### <a name="status-types"></a>Vrste statusa

Postoji šest vrsta statusa za zadatke. Sledeće vrste statusa se takođe prikazuju na stranicama *Podudaranje*, *Spajanje*, *Izvori podataka*, *Segmenti*, *Mere*, *Obogaćivanje*, *Aktivnosti* i *Predviđanja*:

- **Obrada:** Zadatak je u toku. Status se može promeniti u Uspešno ili Neuspešno.
- **Uspešno:** Zadatak je uspešno završen.
- **Preskočen:** Zadatak je preskočen. Jedan ili više procesa na nižem toku od kojih ovaj zadatak zavisi nisu uspeli ili su preskočeni.
- **Neuspešno:** Obrada zadatka nije uspela.
- **Otkazano:** Korisnik je obradu otkazao pre nego što je završio.
- **U redu čekanja:** Obrada je u redu i započeće čim se završe svi posledični zadaci. Za više informacija pogledajte članak [Osvežavanje smernica](#refresh-policies).

### <a name="refresh-policies"></a>Osvežavanje smernica

Ova lista prikazuje smernice osvežavanja za svaki od glavnih procesa:

- **Izvori podataka:** Pokreće se prema [konfigurisanom rasporedu](#schedule-tab). Ne zavisi ni od jednog drugog procesa. Podudaranje zavisi od uspešnog završetka ovog procesa.
- **Podudaranje:** Pokreće se prema [konfigurisanom rasporedu](#schedule-tab). Zavisi od obrade izvora podataka koji se koriste u definiciji podudaranja. Spajanje zavisi od uspešnog završetka ovog procesa.
- **Spajanje**: Pokreće se prema [konfigurisanom rasporedu](#schedule-tab). Zavisi od uspešnog završetka procesa podudaranja. Segmenti, mere, obogaćivanje, pretraga, aktivnosti, predviđanja i priprema podataka zavise od uspešnog završetka ovog procesa.
- **Segmenti**: Pokreće se ručno (jednokratno osvežavanje) i u skladu sa [konfigurisanim rasporedom](#schedule-tab). Zavisi od spajanja. Uvidi zavise od njegove obrade.
- **Mere**: Pokreće se ručno (jednokratno osvežavanje) i u skladu sa [konfigurisanim rasporedom](#schedule-tab). Zavisi od spajanja.
- **Aktivnosti**: Pokreće se ručno (jednokratno osvežavanje) i u skladu sa [konfigurisanim rasporedom](#schedule-tab). Zavisi od spajanja.
- **Obogaćivanje**: Pokreće se ručno (jednokratno osvežavanje) i u skladu sa [konfigurisanim rasporedom](#schedule-tab). Zavisi od spajanja.
- **Pretraga**: Pokreće se ručno (jednokratno osvežavanje) i u skladu sa [konfigurisanim rasporedom](#schedule-tab). Zavisi od spajanja.
- **Priprema podataka**: Pokreće se prema [konfigurisanom rasporedu](#schedule-tab). Zavisi od spajanja.
- **Uvidi**: Pokreće se ručno (jednokratno osvežavanje) i u skladu sa [konfigurisanim rasporedom](#schedule-tab). Zavisi od segmenata.

Izaberite status zadatka da biste videli detalje o toku celog posla u kojem je bio. Gorenavedene smernice za osvežavanje mogu vam pomoći da shvatite šta možete učiniti da biste se obratili pažnju na zadatak koji je **Preskočen** ili **U redu za čekanje**.

## <a name="schedule-tab"></a>Kartica Raspored

Koristite karticu **Raspored** za zakazivanje automatskog osvežavanja svih [unetih izvora podataka](data-sources.md). Automatsko osvežavanje osigurava da se ispravke iz izvora podataka prikazuju na objedinjenim profilima korisnika.

1. U uvidima o klijentima idite na **Administrator** >  **Sistem** i izaberite karticu **Raspored**.

2. Podrazumevano stanje za planirano osvežavanje je **Isključeno**. Da biste omogućili planirana osvežavanja, promenite preklopnik na vrhu ekrana na **Uključeno**.

3. Izaberite između **Nedeljnog** (podrazumevano) i **Svakodnevnog** osvežavanja. Ako nameravate da zakažete nedeljno osvežavanje, izaberite jedan ili više dana u kojima želite da pokrenete osvežavanje.

4. Podesite **vremensku zonu**, a zatim pomoću padajućeg menija **Vreme** podesite vreme osvežavanja. Kada završite, izaberite **Podesi**. Ako želite da zakažete više osvežavanja u jednom danu, izaberite **Dodaj drugo vreme**.

5. Izaberite **Sačuvaj** da primenite promene.

## <a name="about-tab"></a>Kartica Osnovne informacije

Kartica **Osnovni podaci** sadrži **Ime za prikaz** organizacije, aktivni **ID okruženja**, **Region** i **ID sesije**. Ako imate više od jednog radnog okruženja, treba svakom da date lako prepoznatljivo ime za prikaz.

## <a name="general-tab"></a>Kartica Opšti podaci

Postoje dve opcije na kartici **Opšti podaci**, **Jezik** i **Format zemlje/regiona**.

Aplikacija [podržava brojne jezike](supported-languages.md). Da biste promenili željeni jezik, izaberite **Jezik** iz padajuće liste.

Da biste promenili željeno oblikovanje datuma, vremena i brojeva, koristite padajuću listu **Format zemlje/regiona**. Ispod ovog polja prikazuje se pregled oblikovanja. Sistem će automatski predložiti izbor kada odaberete novi jezik.

Izaberite **Sačuvaj** da potvrdite izbore.

## <a name="api-usage-tab"></a>Kartica za upotrebu API-ja

Pronađite detalje o upotrebi API-ja u stvarnom vremenu i pogledajte koji su se događaji desili u datom vremenskom periodu. Više informacija potražite u članku [Unos podataka u realnom vremenu](real-time-data-ingestion.md).
