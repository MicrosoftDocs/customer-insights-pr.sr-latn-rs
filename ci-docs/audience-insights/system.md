---
title: Konfiguracija sistema u uvidima o korisnicima
description: Saznajte više o sistemskim podešavanjima u Dynamics 365 Customer Insights mogućnosti uvida o korisnicima.
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 09d449e51a3a47ec916ab3d017419c9d9be1ffcf
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305727"
---
# <a name="system-configuration"></a>Konfiguracija sistema

Stranica **Sistem** sadrži sledeće kartice:
- [Status](#status-tab)
- [Raspored](#schedule-tab)
- [API korišćenje](#api-usage-tab)
- [Osnovne informacije](#about-tab)
- [Opšte](#general-tab)

> [!div class="mx-imgBorder"]
> ![Sistemska stranica](media/system-tabs.png "Sistemska stranica")

## <a name="status-tab"></a>Kartica Status

Kartica **Status** omogućava vam praćenje napretka unosa podataka, izvoza podataka i nekoliko drugih važnih procesa proizvoda. Pregledajte informacije na ovoj kartici da biste se uverili u kompletnost aktivnih procesa.

Ova kartica uključuje tabele sa informacijama o statusu i obradi za razne procese. Svaka tabela prati **Ime** zadatka i odgovarajućeg entiteta, **Status** poslednjeg pokretanja i kada je **poslednji put ažuriran**.

Pregledajte detalje poslednjih nekoliko pokretanja zadataka odabirom imena.

### <a name="status-types"></a>Vrste statusa

Postoji šest vrsta statusa za zadatke. Sledeće vrste statusa se takođe prikazuju na stranicama *Podudaranje*, *Spajanje*, *Izvori podataka*, *Segmenti*, *Mere*, *Obogaćivanje*, *Aktivnosti* i *Predviđanja*:

- **Obrada:** Zadatak je u toku. Status se može promeniti u Uspešno ili Neuspešno.
- **Uspešno:** Zadatak je uspešno završen.
- **Preskočen:** Zadatak je preskočen. Jedan ili više procesa na nižem toku od kojih ovaj zadatak zavisi nisu uspeli ili su preskočeni.
- **Neuspešno:** Obrada zadatka nije uspela.
- **Otkazano:** Korisnik je obradu otkazao pre nego što je završio.
- **Stavljeno u red:** Obrada je stavljena u red čekanja i započeće kada se završe svi uzlazni zadaci. Za više informacija pogledajte članak [Osvežavanje smernica](#refresh-policies).

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

Pronađite detalje o upotrebi API-ja u realnom vremenu i pogledajte koji su se događaji dogodili u datom vremenskom okviru. Birate vremenski okvir u padajućem meniju **Izaberite vremenski okvir**. 

**Korišćenje API-ja** sadrži tri odeljka: 
- **API pozivi** – grafikon koji prikazuje ukupni broj poziva API-ju u izabranom vremenskom okviru.

- **Prenos podataka** – grafikon koji prikazuje količinu podataka koja je preneta preko API-ja u izabranom vremenskom okviru.

-  **Operacije** – tabela sa redovima za svaku dostupnu API operaciju i detalje o upotrebi operacija. Možete izabrati naziv operacije na koju želite da idete u [referenci za API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operacije koje koriste [unošenje podataka u realnom vremenu](real-time-data-ingestion.md) sadrže dugme sa simbolom dvogleda za prikaz korišćenja API-ja u realnom vremenu. Izaberite dugme da biste otvorili bočno okno koje sadrži detalje o upotrebi API-ja u trenutnom okruženju.   
   Koristite okvir **Grupiši po** u oknu **Korišćenje API-ja u realnom vremenu** da biste izabrali kako najbolje da predstavite svoje interakcije u realnom vremenu. Možete grupisati podatke prema API metodi, nazivu kvalifikovanog entiteta (uneti entitet), vremenu kreiranja (izvor događaja), rezultatu (uspelo ili neuspelo) ili kodovima grešaka. Podaci su dostupni kao vremenski grafikon i tabela.


[!INCLUDE[footer-include](../includes/footer-banner.md)]