---
title: Kreiranje i uređivanje mera
description: Definišite mere koje se odnose na klijenta kako biste analizirali i odražavali performanse određenih oblasti poslovanja.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406819"
---
# <a name="define-and-manage-measures"></a>Definišite i upravljajte merama

**Mere** predstavljaju ključne pokazatelje performansi (KPI) koji odražavaju performanse i ispravnost određenih poslovnih oblasti. Uvidi o korisnicima pružaju intuitivno iskustvo za izgradnju različitih vrsta mera, koristeći kreator upita koji ne zahteva ručno kodiranje ili validaciju mera. Možete pratiti svoje poslovne mere na stranici **Početak**, pogledajte mere za određene klijente na stranici **Kartica klijenta** i koristite mere za definisanje segmenata korisnika na stranici **Segmenti**.

## <a name="create-a-measure"></a>Kreiranje mere

Ovaj odeljak vas vodi kroz kreiranje mere ispočetka. Možete izgraditi mere pomoću podataka iz više izvora podataka koji su povezani preko entiteta Klijenta. Neka [ograničenja usluga](service-limits.md) se primenjuju.

1. U uvidima o korisnicima idite na **Mere**.

2. Izaberite **Nova mera**.

3. Odaberite **Tip** mere:

   - **Atribut klijenta**: Jedno polje po klijentu koje odražava rezultat, vrednost ili stanje za klijenta. Atributi korisnika kreiraju se kao atributi u novom sistemski generiranom entitetu koji se zove **Customer_Measure**.

   - **Mera klijenta**: Uvid u ponašanje klijenata sa analizom po odabranim dimenzijama. Kreira se novi entitet za svaku meru, potencijalno sa više zapisa po korisniku.

   - **Poslovna mera**: Prati vaše poslovne rezultate i stanje vašeg poslovanja. Poslovne mere mogu imati dva različita izlaza: numerički izlaz koji se prikazuje na stranici **Početak** ili novi entitet koji ćete pronaći na stranici **Entiteti**.

4. Navedite **Ime** i opcionalno **Ime za prikaz**, a zatim izaberite **Sledeće**.

5. U odeljku **Entitet**, izaberite prvi entitet sa padajuće liste. U ovom trenutku, trebalo bi da odlučite da li su potrebni dodatni entiteti kao deo vaše definicije mera.

   > [!div class="mx-imgBorder"]
   > ![Definicija mere](media/measure-definition.png "Definicija mere")

   Da biste dodali još entiteta, izaberite **Dodajte entitet** i izaberite entitete koje želite da koristite za meru.

   > [!NOTE]
   > Možete izabrati samo one entitete koji imaju relaciju sa početnim entitetom. Više informacija o definisanju relacija potražite u članku [Relacije](relationships.md).

6. Opcionalno, možete da konfigurišete promenljive. U odeljku **Promenljive**, izaberite **Nova promenljiva**.

   Promenljive su proračuni koji se obavljaju na svim izabranim zapisima. Na primer, sabiranje prodajnog mesta (POS) i prodaja putem interneta za sve zapise vaših klijenata.

7. Navedite **Naziv** za promenljivu.

8. U oblasti **Izraz** odaberite polje za početak izračunavanja.

9. Unesite izraz u oblast **Izraz** dok birate više polja koja će se uključiti u vaš proračun.

   > [!NOTE]
   > Trenutno su podržani samo aritmetički izrazi. Pored toga, izračunavanje promenljivih nije podržano za entitete iz različitih [putanja entiteta](relationships.md).

10. Izaberite **Gotovo**.

11. U odeljku **Definicija mere**, definisaćete kako se izabrani entiteti i izračunate promenljive agregiraju u novu celinu ili atribut mere.

12. Izaberite **Nova dimenzija**. O dimenziji možete razmišljati kao o funkciji *grupiši prema*. Izlaz podataka vašeg entiteta ili atributa Mera biće grupisan po svim vašim definisanim dimenzijama.

    > [!div class="mx-imgBorder"]
    > ![Izaberite agregatni ciklus](media/measures-businessreport-measure-definition2.png "Izaberite agregatni ciklus")

    Izaberite ili unesite sledeće informacije kao deo definicije vaše dimenzije:

    - **Entitet**: Ako definišete entitet Mera, on treba da sadrži najmanje jedan atribut. Ako definišete atribut Mera, on će podrazumevano sadržavati samo jedan atribut. Ovaj izbor se odnosi na izbor entiteta koji uključuje taj atribut.
    - **Polje**: Izaberite određeni atribut koji će se uključiti u vašu mernu jedinicu ili atribut.
    - **Kontejner**: Izaberite da li želite da objedinite podatke na dnevnoj, mesečnoj ili godišnjoj osnovi. To je obavezan izbor samo ako ste izabrali atribut tipa Datum.
    - **Kao**: Definiše ime vašeg novog polja.
    - **Ime za prikaz**: Definiše ime za prikaz vašeg polja.

    > [!NOTE]
    > Vaša poslovna mera će biti sačuvana kao entitet s jednim brojem i prikazaće se na stranici **Početak** ukoliko u meru ne dodate više dimenzija. Nakon dodavanja više dimenzija, mera se *neće* prikazivati na stranici **Početak**.

13. Opcionalno, dodajte funkcije agregacije. Svako združivanje koje stvorite rezultira novom vrednošću unutar entiteta ili atributa Mere. Podržane funkcije agregacije su: **Min**, **Maks**, **Prosek**, **Medijana**, **Zbir**, **Broj jedinstvenih**, **Prvi** (uzima prvi zapis vrednosti dimenzije) i **Poslednji** (uzima poslednji zapis koji je dodat u dimenziju).

14. Izaberite **Sačuvaj** da biste primenili promene na meru.

## <a name="manage-your-measures"></a>Upravljanje merama

Nakon što napravite bar jednu meru, videćete listu mera na stranici **Mere**.

Pronaći ćete informacije o vrsti mere, kreatoru, datumu i vremenu kreiranja, datumu i vremenu poslednje izmene, statusu (da li je mera aktivna, neaktivna ili neuspela) i poslednjem datumu i vremenu osvežavanja. Kada sa liste izaberete meru, možete videti pregled njenog rezultata.

Da biste istovremeno osvežili sve mere, izaberite **Osvežite sve** bez izbora određene mere.

> [!div class="mx-imgBorder"]
> ![Radnje za upravljanje jedinstvenim merama](media/measure-actions.png "Radnje za upravljanje jedinstvenim merama")

Alternativno, izaberite meru sa liste i izvršite jednu od sledećih radnji:

- Izaberite naziv mere da biste videli njene detalje.
- **Uredite** konfiguraciju mere.
- **Preimenujte** meru.
- **Izbrišite** meru.
- Izaberite tri tačke (...), a zatim **Osveži** da biste započeli postupak osvežavanja mere.
- Izaberite tri tačke (...), a zatim **Preuzmi** da biste preuzeli .CSV datoteku mere.

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies). Možete izabrati status procesa da biste videli detalje o toku celog posla. Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.

## <a name="next-step"></a>Sledeći korak

Možete da koristite postojeće mere da biste kreirali svoj prvi segment korisnika na stranici **Segmenti**. Za više informacija, pogledajte članak [Segmenti](segments.md).
