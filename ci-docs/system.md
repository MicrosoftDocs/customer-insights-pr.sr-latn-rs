---
title: Prikaži konfiguraciju sistema
description: Saznajte o sistemskim podešavanjima u usluzi Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2498814a3d2e6330124fb97c036b9b310bcf1f7a
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246264"
---
# <a name="view-system-configuration"></a>Prikaži konfiguraciju sistema

Prikažite informacije o sistemu, status sistema i upotrebu API-ja.

## <a name="view-api-usage"></a>Prikaži upotrebu API-ja

Prikažite detalje o korišćenju API-ja u realnom vremenu i pogledajte koji su se događaji dogodili u datoj vremenski okvir.

1. Idite na administratorski **sistem** > **i izaberite karticu** za upotrebu API-ja **·**.

1. **Izaberite vremenski okvir** da biste prikazali.

   Stranica **za upotrebu** API-ja sadrži tri odeljka:

   - **API pozivi** – grafikon koji prikazuje ukupni broj poziva API-ju u izabranom vremenskom okviru.
   - **Prenos podataka** – grafikon koji prikazuje količinu podataka koja je preneta preko API-ja u izabranom vremenskom okviru.
   - **Operacije** – tabela sa redovima za svaku dostupnu API operaciju i detalje o upotrebi operacija. Izaberite ime operacije da biste išli [na API referencu](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operacije koje koriste [unošenje podataka u realnom vremenu](real-time-data-ingestion.md) sadrže dvogledni simbol za prikaz upotrebe API-ja u realnom vremenu.

   1. Izaberite dvogled da biste otvorili okno **za korišćenje API-ja u realnom** vremenu koje sadrži detalje o korišćenju operacije.
   1. **Izaberite vremenski okvir** da biste prikazali.
   1. Koristite polje **"Grupiši** po" da biste odabrali kako da na najbolji način predstavite interakcije u realnom vremenu. Podatke grupisanje po API metodu, kvalifikovanom imenu entiteta **(uneti entitet),** kreiranom **po (izvoru događaja),** rezultatu (uspehu **ili neuspehu) ili kodovima** grešaka **.** **·** Podaci su dostupni kao vremenski grafikon i tabela.

## <a name="view-system-information"></a>Prikaz informacija o sistemu

Prikažite ID ime za prikaz okruženja, ID, region, tip i ID sesije.

1. Idite na administratorski **sistem** > **i** izaberite karticu Osnovni **podaci**.

1. Izaberite karticu "Opšte postavke" da biste prikazali jezik i državu **/** region.

### <a name="update-preferred-language-or-countryregion"></a>Ažuriranje željenog jezika ili države/regiona

Uvidi klijenata [podržavaju mnoge jezike](/dynamics365/get-started/availability). Aplikacija koristi vaše jezičke preference za prikazivanje elemenata poput menija, teksta oznake na kontrolnoj tabli i sistemskih poruka na jeziku kome korisnik daje prednost.

Uvezeni podaci i informacije koje ste ručno uneli se ne prevode.

1. Idite na **administratorski** > **sistem i** izaberite karticu **Opšte** postavke.

1. Da biste promenili željeni jezik, izaberite **Jezik** iz padajuće liste.

1. Da biste promenili željeno oblikovanje datuma, vremena i brojeva, koristite padajuću listu **Format zemlje/regiona**. Prikazaće se pregled oblikovanja. Sistem automatski predlaže selekciju kada odaberete novi jezik.

1. Izaberite **Sačuvaj**.

## <a name="view-system-status"></a>Prikaz statusa sistema

Praćenje napretka zadataka, unošenja podataka, izvoza podataka i nekoliko drugih važnih procesa proizvoda. Pregledajte informacije da biste se uverili u dovršavanje aktivnih zadataka i procesa.

1. Idite na **administratorski** > **sistem i** izaberite karticu **Status**.

   Prikazane su informacije o statusu i obradi različitih procesa. Prikažite **ime** zadatka, **status njegovog** poslednjeg vođenja i kada je poslednji put **ažuriran**.

1. Izaberite zadatak ili ime procesa da biste prikazali detalje poslednjih nekoliko runs.

1. Izaberite status da biste videli detalje toka zadatka. Prikazaće **se okno** sa detaljima o toku.

   :::image type="content" source="media/system-progress-details.png" alt-text="Okno sa detaljima o toku sistema":::

1. Izaberite ceo tok posla da biste prikazali detalje toka posla za **sve zadatke**.

### <a name="status-definitions"></a>Definicije statusa

Sistem koristi sledeće statuse za zadatke i procese:

|Status  |Definicija  |
|---------|---------|
|Otkazana |Korisnik je otkazao zadatak ili proces pre nego što je završen.   |
|Neuspeh   |Zadatak ili proces naišli su na greške.         |
|Neuspešno  |Zadatak ili proces nisu uspeli.  |
|Nije započeto   |Izvor podataka nema unete podatke ili je zadatak još uvek u režimu radne verzije.         |
|Obrađuje se  |Zadatak ili proces je u toku.  |
|Osvežavanje    |Zadatak ili proces je u toku. Da biste otkazali ovu operaciju, izaberite opciju **"Osvežavanje** " i **"Otkaži posao"**. Zaustavljanje osvežavanja zadatka ili procesa će ga vratiti u stanje poslednjeg osvežavanja.       |
|Preskočena  |Zadatak ili proces su preskočeni. Jedan ili više procesa na nižem toku od kojih ovaj zadatak zavisi nisu uspeli ili su preskočeni.|
|Uspešno  |Zadatak ili proces su uspešno dovršeni. Za izvore podataka ukazuje na to da su podaci uspešno uneti ako je vreme pomenuto u koloni "Osveženje **·**".|
|Na čekanju | Obrada je stavljena u red i počeće kada se dovrše svi uzvodni zadaci i procesi. Više informacija potražite u članku Osvežavanje [procesa](#refresh-processes).|

### <a name="refresh-processes"></a>Osvežavanje procesa

Osvežavanje zadataka i procesa se izvršava u skladu sa [konfigurisanim rasporedom](schedule-refresh.md).

|Proces  |Opis  |
|---------|---------|
|Aktivnost  |Pokreće ručno (jednostruko osvežavanje). Zavisi od procesa objedinjavanja. Uvidi zavise od njegove obrade.|
|Povezivanje analize |Pokreće ručno (jednostruko osvežavanje). Zavisi od segmenata.  |
|Priprema analize |Pokreće ručno (jednostruko osvežavanje). Zavisi od segmenata.  |
|Priprema podataka   |Potreban mu je entitet za pokretanje. Izvor podataka entiteti zavise od unošenja. Obogaćeni entiteti zavise od bogaćenja. Entitet kupca zavisi od objedinjavanja.  |
|Izvori podataka   |Ne zavisi ni od jednog drugog procesa. Podudaranje zavisi od uspešnog završetka ovog procesa.  |
|Obogaćivanja   |Pokreće ručno (jednostruko osvežavanje). Zavisi od procesa objedinjavanja. |
|Izvoz odredišta |Pokreće ručno (jednostruko osvežavanje). Zavisi od segmenata.  |
|Uvidi |Pokreće ručno (jednostruko osvežavanje). Zavisi od segmenata.  |
|Informacije   |Zavisi od objedinjavanja.   |
|Podudaranje |Zavisi od obrade izvora podataka koji se koriste u definiciji podudaranja.      |
|Mere  |Pokreće ručno (jednostruko osvežavanje). Zavisi od procesa objedinjavanja.  |
|Objedini   |Zavisi od uspešnog završetka procesa podudaranja. Segmenti, mere, obogaćivanje, pretraga, aktivnosti, predviđanja i priprema podataka zavise od uspešnog završetka ovog procesa.   |
|Profili   |Pokreće ručno (jednostruko osvežavanje). Zavisi od procesa objedinjavanja. |
|Pretražite   |Pokreće ručno (jednostruko osvežavanje). Zavisi od procesa objedinjavanja. |
|Segmenti  |Pokreće ručno (jednostruko osvežavanje). Zavisi od procesa objedinjavanja. Uvidi zavise od njegove obrade.|
|Sistemsko   |Zavisi od uspešnog završetka procesa podudaranja. Segmenti, mere, obogaćivanje, pretraga, aktivnosti, predviđanja i priprema podataka zavise od uspešnog završetka ovog procesa.   |
|User  |Pokreće ručno (jednostruko osvežavanje). Zavisi od entiteta.  |

Izaberite status procesa da biste videli detalje o toku celog posla u kojem se zatekao. Gorenavedeni procesi osvežavanja mogu pomoći da razumete šta možete da uradite da biste rešili preskočeni **ili** **poređani** zadatak ili proces.


[!INCLUDE [footer-include](includes/footer-banner.md)]
