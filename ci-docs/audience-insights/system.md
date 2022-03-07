---
title: Konfiguracija sistema u uvidima o korisnicima
description: Saznajte više o sistemskim podešavanjima u Dynamics 365 Customer Insights mogućnosti uvida o korisnicima.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2c52f7b8a7d41ae4a985745c7b79bbc62f59bb5a
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354250"
---
# <a name="system-configuration"></a>Konfiguracija sistema

Da biste pristupili konfiguracijama sistema u korisnici uvidima, sa leve trake za navigaciju **izaberite AdminSystem** > **da** biste prikazali listu sistemskih zadataka i procesa.

Stranica **Sistem** sadrži sledeće kartice:
- [Status](#status-tab)
- [Raspored](#schedule-tab)
- [API korišćenje](#api-usage-tab)
- [Osnovne informacije](#about-tab)
- [Opšte](#general-tab)
- [Bezbednost](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Kartica „Podešavanja“ na sistemskoj stranici.":::

## <a name="status-tab"></a>Kartica Status

Kartica **"Status"** vam omogućava da pratite tok zadataka, unošenje podataka, izvoz podataka i nekoliko drugih važnih procesa proizvoda. Pregledajte informacije na ovoj kartici da biste se uverili u dovršavanje aktivnih zadataka i procesa.

Ova kartica uključuje tabele sa informacijama o statusu i obradi za razne procese. Svaka tabela prati **Ime** zadatka i odgovarajućeg entiteta, **Status** poslednjeg pokretanja i kada je **poslednji put ažuriran**. Detalje poslednjih nekoliko trčanja možete da prikažete tako što ćete izabrati zadatak ili ime procesa. 

Izaberite status pored zadatka ili procesa u koloni Status da **biste** otvorili okno sa **detaljima o toku**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Okno sa detaljima o toku sistema":::

### <a name="status-definitions"></a>Definicije statusa

Sistem koristi sledeće statuse za zadatke i procese:

|Status  |Definicija  |
|---------|---------|
|Otkazana |Obradu je korisnik otkazao pre nego što je završena.   |
|Neuspeh   |Unos podataka je naišao na greške.         |
|Neuspešno  |Obrada nije uspela.  |
|Nije započeto   |Izvor podataka još nema unetih podataka ili je još uvek u režimu radne verzije.         |
|Obrađuje se  |Zadatak ili proces je u toku.  |
|Osvežavanje    |Unos podataka je u toku. Ovu operaciju možete otkazati ako izaberete **Zaustavi osvežavanje** u koloni **Radnje**. Zaustavljanje osvežavanja izvora podataka vratiće ga u poslednje stanje osvežavanja.       |
|Preskočena  |Zadatak ili proces su preskočeni. Jedan ili više procesa na nižem toku od kojih ovaj zadatak zavisi nisu uspeli ili su preskočeni.|
|Uspešno  |Zadatak ili proces su uspešno dovršeni. Za izvore podataka ukazuje na to da su podaci uspešno uneti ako je vreme pomenuto u koloni "Osveženje **·**".|
|Na čekanju | Obrada je stavljena u red i počeće kada se dovrše svi uzvodni zadaci i procesi. Više informacija potražite u članku Osvežavanje [procesa](#refresh-processes).|

### <a name="refresh-processes"></a>Osvežavanje procesa

Osvežavanje zadataka i procesa se izvršava u skladu sa [konfigurisanim rasporedom](#schedule-tab). 

|Proces  |Opis  |
|---------|---------|
|Aktivnost  |Pokreće ručno (jednostruko osvežavanje). Zavisi od procesa objedinjavanja. Uvidi zavise od njegove obrade.|
|Povezivanje analize |Pokreće ručno (jednostruko osvežavanje). Zavisi od segmenata.  |
|Priprema analize |Pokreće ručno (jednostruko osvežavanje). Zavisi od segmenata.  |
|Priprema podataka   |Zavisi od objedinjavanja.   |
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

## <a name="schedule-tab"></a>Kartica Raspored

Koristite karticu **Raspored** za zakazivanje automatskog osvežavanja svih [unetih izvora podataka](data-sources.md). Automatsko osvežavanje osigurava da se ispravke iz izvora podataka prikazuju na objedinjenim profilima korisnika.

> [!NOTE]
> Izvore podataka kojima upravljate osvežavate po sopstvenim rasporedima. Da biste isplanirali osvežavanje izvora podataka kojima upravljate, konfigurišite postavke osvežavanja na izvor podataka stranici **izvora podataka**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Postavke osvežavanja dataflow-a.":::

1. U uvidima o klijentima idite na **Administrator** >  **Sistem** i izaberite karticu **Raspored**.

2. Podrazumevano stanje za planirano osvežavanje je **Isključeno**. Da biste omogućili planirana osvežavanja, promenite preklopnik na vrhu ekrana na **Uključeno**.

3. Izaberite između **Nedeljnog** (podrazumevano) i **Svakodnevnog** osvežavanja. Ako nameravate da zakažete nedeljno osvežavanje, izaberite jedan ili više dana u kojima želite da pokrenete osvežavanje.

4. Podesite **vremensku zonu**, a zatim pomoću padajućeg menija **Vreme** podesite vreme osvežavanja. Kada završite, izaberite **Podesi**. Ako želite da zakažete više osvežavanja u jednom danu, izaberite **Dodaj drugo vreme**.

5. Izaberite **Sačuvaj** da primenite promene.

## <a name="about-tab"></a>Kartica Osnovne informacije

Kartica **Osnovni podaci** sadrži **Ime za prikaz** organizacije, aktivni **ID okruženja**, **Region** i **ID sesije**. Ako imate više od jednog radnog okruženja, treba svakom da date lako prepoznatljivo ime za prikaz.

## <a name="general-tab"></a>Kartica Opšti podaci

Jezik i format zemlje/regiona možete da promenite na kartici **Opšti podaci**.

Uvidi klijenata [podržavaju mnoge jezike](/dynamics365/get-started/availability). Aplikacija koristi vaše jezičke preference za prikazivanje elemenata poput menija, teksta oznake na kontrolnoj tabli i sistemskih poruka na jeziku kome korisnik daje prednost.

Uvezeni podaci i informacije koje ste ručno uneli se ne prevode.

### <a name="update-the-settings"></a>Ažuriranje podešavanja

Da biste promenili željeni jezik, izaberite **Jezik** iz padajuće liste.

Da biste promenili željeno oblikovanje datuma, vremena i brojeva, koristite padajuću listu **Format zemlje/regiona**. Ispod ovog polja prikazuje se pregled oblikovanja. Sistem će automatski predložiti izbor kada odaberete novi jezik.

Izaberite **Sačuvaj** da potvrdite izbore.

## <a name="api-usage-tab"></a>Kartica za upotrebu API-ja

Pronađite detalje o upotrebi API-ja u realnom vremenu i pogledajte koji su se događaji dogodili u datom vremenskom okviru. Birate vremenski okvir u padajućem meniju **Izaberite vremenski okvir**. 

**Korišćenje API-ja** sadrži tri odeljka: 
- **API pozivi** – grafikon koji prikazuje ukupni broj poziva API-ju u izabranom vremenskom okviru.

- **Prenos podataka** – grafikon koji prikazuje količinu podataka koja je preneta preko API-ja u izabranom vremenskom okviru.

-  **Operacije** – tabela sa redovima za svaku dostupnu API operaciju i detalje o upotrebi operacija. Možete izabrati naziv operacije na koju želite da idete u [referenci za API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operacije koje koriste [unošenje podataka u realnom vremenu](real-time-data-ingestion.md) sadrže dugme sa dvoglednim simbolom za prikaz upotrebe API-ja u realnom vremenu. Izaberite dugme da biste otvorili bočno okno koje sadrži detalje o upotrebi API-ja u trenutnom okruženju.   
   Koristite okvir **Grupiši po** u oknu **Korišćenje API-ja u realnom vremenu** da biste izabrali kako najbolje da predstavite svoje interakcije u realnom vremenu. Možete grupisati podatke prema API metodi, nazivu kvalifikovanog entiteta (uneti entitet), vremenu kreiranja (izvor događaja), rezultatu (uspelo ili neuspelo) ili kodovima grešaka. Podaci su dostupni kao vremenski grafikon i tabela.

## <a name="security-tab"></a>Kartica „Bezbednost“

Kartica **Bezbednost** vam omogućava da povežete sopstveni [Azure Key Vault](/azure/key-vault/general/basic-concepts) sa okruženjem.
Namensko bezbednosno skladište može da se koristi za postavljanje i korišćenje tajni u granicama usklađenosti organizacije. Uvidi u ciljnu grupu mogu koristiti tajne u Azure Key Vaultu za [uspostavljanje veza](connections.md) sa sistemima trećih strana.

Za više informacija pogledajte članak [Dovedite sopstveni Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
