---
title: Kreiranje segmenata i upravljanje njima
description: Napravite segmente klijenata da biste ih grupisali na osnovu različitih atributa.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406828"
---
# <a name="create-and-manage-segments"></a>Kreiranje segmenata i upravljanje njima

Segmenti vam omogućavaju da grupišete klijente na osnovu demografskih, transakcionih ili atributa ponašanja. Možete da koristite segmente za ciljanje promotivnih kampanja, prodajnih aktivnosti i aktivnosti podrške klijenata kako biste postigli svoje poslovne ciljeve.

Možete definisati složene filtere oko entiteta Profil klijenta i s njim povezanih entiteta. Svaki segment nakon obrade kreira skup korisničkih zapisa koje možete da izvoziti i za koje možete da preduzimate neke korake. Neka [ograničenja usluga](service-limits.md) se primenjuju.

Ako nije drugačije naznačeno, svi segmenti su **Dinamički segmenti**, koji se osvežavaju po redovnom rasporedu.

Sledeći primer ilustruje korišćenje mogućnosti segmentacije. Definisali smo segment za klijente koji su naručili robu za najmanje 500 USD u poslednjih 90 dana *i* koji su bili uključeni u poziv korisničke službe koji je prosleđen.

> [!div class="mx-imgBorder"]
> ![Više grupa](media/segmentation-group1-2.png "Više grupa")

## <a name="create-a-new-segment"></a>Kreirajte novi segment

Segmentima se upravlja na stranici **Segmenti**.

1. U uvidima o korisnicima idite na stranicu **Segmenti**.

2. Izaberite **Novo** > **Prazan segment**.

3. U oknu **Novi segment** odaberite tip segmenta i navedite **Ime**.

   Opcionalno, unesite ime za prikaz i opis koji pomaže u prepoznavanju segmenta.

4. Izaberite **Sledeće** da dođete na stranicu **Graditelj segmenata** na kojoj definišete grupu. Grupa je skup klijenata.

5. Odaberite entitet koji obuhvata atribute po kojima želite da segmentirate.

6. Odaberite atribut po segmentu. Ovaj atribut može imati jedan od četiri tipa vrednosti: numerički, niska, datum ili logički.

7. Odaberite operator i vrednost za izabrani atribut.

   > [!div class="mx-imgBorder"]
   > ![Prilagođeni filter grupe](media/customer-group-numbers.png "Filter grupe klijenata")

   |Broj |Definicija  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribut          |
   |3    |Operator         |
   |4    |Vrednost         |

8. Ako je entitet povezan putem objedinjenog entiteta klijenta putem [odnosa](relationships.md), morate definisati putanju odnosa da biste kreirali važeći segment. Dodajte entitete iz putanje odnosa dok ne budete mogli da izaberete entitet **Klijent: CustomerInsights** iz padajuće liste. Zatim odaberite **Svi zapisi** za svaki uslov.

   > [!div class="mx-imgBorder"]
   > ![Putanja odnosa tokom kreiranja segmenta](media/segments-multiple-relationships.png "Putanja odnosa tokom kreiranja segmenta")

9. Izaberite **Sačuvaj** da biste sačuvali segment. Vaš segment će biti sačuvan i obrađen ukoliko su svi zahtevi potvrđeni. U suprotnom, biće sačuvan kao radna verzija.

10. Izaberite **Nazad na segmente** da biste se vratili na stranicu **Segmenti**.

## <a name="manage-existing-segments"></a>Upravljanje postojećim segmentima

Na stranici **Segmenti**, možete videti sve sačuvane segmente i njima upravljati.

Svaki segment predstavljen je redom koji sadrži dodatne informacije o segmentu.

Segmente možete sortirati u koloni odabirom naslova kolone.

Koristite polje **Pretraga** u gornjem desnom uglu da biste filtrirali segmente.

> [!div class="mx-imgBorder"]
> ![Opcije za upravljanje postojećim segmentom](media/segments-selected-segment.png "Opcije za upravljanje postojećim segmentom")

Sledeća radnja je dostupna kada odaberete segment:

- **Prikaz** detalja segmenta, uključujući trend broja članova, pregled članova segmenta.
- **Uredite** segment da biste promenili njegova svojstva.
- **Osvežite** segment tako da uključuje najnovije podatke.
- **Aktivirajte** ili **Deaktivirajte** segment. Segmenti imaju dva moguća stanja - aktivno ili neaktivno. Ova stanja dobro dođu prilikom uređivanja segmenta. Za neaktivne segmente definicija segmenta postoji, ali još uvek ne sadrži klijente. Kada aktivirate segment, njegovo stanje se menja iz „neaktivan“ u „aktivan“ i on počinje da traži klijente koji odgovaraju definiciji segmenta. Ako je [zakazano osvežavanje](system.md#schedule-tab) konfigurisano, neaktivni segmenti imaju **Status** naveden kao **Preskočeno**, što ukazuje da osvežavanje nije ni pokušano. Kada se aktivira neaktivni segment, osvežiće se i biće uključen u zakazana osvežavanja.
  Alternativno, možete da koristite funkcionalnost **Isplaniraj za kasnije** u padajućoj listi **Aktiviraj/Deaktiviraj** da navedete budući datum i vreme za aktivaciju i deaktivaciju određenog segmenta.
- **Preimenujte** segment.
- **Preuzmite** listu članova kao .CSV datoteku.
- Opcija **Dodaj u** šalje listu ID-ova klijenata u segmentu na obradu u drugoj aplikaciji.
- **Izbrišite** segment.

## <a name="refresh-segments"></a>Osvežavanje segmenata

Možete da osvežite sve segmente odjednom ako izaberete **Osvežite sve** na stranici **Segmenti**, a možete i da osvežiti jedan ili više segmenata kada ih izaberete, pa odaberete **Osveži** iz opcija. Alternativno, možete konfigurisati ponavljajuće osvežavanje u odeljku **Administrator** > **Sistem** > **Raspored**.

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies). Možete izabrati status procesa da biste videli detalje o toku celog posla. Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.

## <a name="download-and-export-segments"></a>Preuzimanje i izvoz segmenata

Možete preuzeti svoje segmente u CSV datoteku ili ih izvesti u Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Preuzmite segmente u CSV datoteku

1. U uvidima o korisnicima idite na stranicu **Segmenti**.

2. Izaberite tri tačke na pločici određenog segmenta.

3. Izaberite **Preuzmi kao CSV** sa padajuće liste radnji.

### <a name="export-segments-to-dynamics-365-sales"></a>Izvoz segmenata u Dynamics 365 Sales

Pre izvoza segmenata u Dynamics 365 Sales, administrator treba [kreiraj odredište za izvoz](export-destinations.md) za Dynamics 365 Sales.

1. U uvidima o korisnicima idite na stranicu **Segmenti**.

2. Izaberite tri tačke na pločici određenog segmenta.

3. Izaberite **Dodaj u** iz padajuće liste radnji i izaberite odredište za izvoz u koje želite da pošaljete podatke.

## <a name="draft-mode-for-segments"></a>Režim radne verzije za segmente

Ako nisu ispunjeni svi zahtevi za obradu segmenta, možete da sačuvate segment kao radnu verziju i pristupite mu sa stranice **Segmenti**.

Biće sačuvan kao neaktivan segment i nećete moći da ga aktivirate dok ne postane važeći.

## <a name="add-more-conditions-to-a-group"></a>Dodajte više uslova grupi

Da biste grupi dodali više uslova, možete da koristite dva logička operatora:

- Operator **I**: Oba uslova moraju da budu ispunjena kao deo procesa segmentacije. Ova opcija je najkorisnija kada definišete uslove u različitim entitetima.

- Operator **ILI**: Bilo koji od uslova mora biti ispunjen kao deo procesa segmentacije. Ova opcija je najkorisnija kada definišete više uslova u istom entitetu.

   > [!div class="mx-imgBorder"]
   > ![Operator ILI gde je potrebno ispuniti bilo koji uslov](media/segmentation-either-condition.png "Operator ILI gde je potrebno ispuniti bilo koji uslov")

Trenutno je moguće ugnezditi operator **ILI** unutar operatora **I**, ali ne i obrnuto.

## <a name="combine-multiple-groups"></a>Kombinovanje više grupa

Svaka grupa proizvodi određeni skup klijenata. Možete kombinovati ove grupe da biste uključili klijente potrebne za vaš predmet poslovanja.

1. U uvidima o klijentima idite na stranicu **Segmenti** i izaberite segment.

2. Izaberite **Dodaj grupu**.

   > [!div class="mx-imgBorder"]
   > ![Grupa klijenata dodaj grupu](media/customer-group-add-group.png "Grupa klijenata dodaj grupu")

3. Izaberite jedan od sledećih skupa operatora: **Unija**, **Presek** ili **Izuzimanje**.

   > [!div class="mx-imgBorder"]
   > ![Grupa klijenata dodaj uniju](media/customer-group-union.png "Grupa klijenata dodaj uniju")

   Izaberite operator skupa da biste definisali novu grupu. Čuvanje različitih grupa radi određivanja koji podaci se zadržavaju:

   - **Unija** objedinjuje dve grupe.

   - **Presek** preklapa dve grupe. Samo podaci koji *su zajednički* za obe grupe zadržavaju se u objedinjenoj grupi.

   - **Osim** kombinuje dve grupe. Samo podaci u grupi A koji *nisu zajednički* sa podacima iz grupe B zadržavaju se.

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

## <a name="quick-segments"></a>Brzi segmenti

Pored alatke za pravljenje segmenata, postoji još jedan put za kreiranje segmenata. Brzi segmenti vam omogućavaju da napravite jednostavne segmente, sa jednim operatorom, brzo i uz trenutne uvide.

1. Na stranici **Segmenti** izaberite **Nova** > **Brzo kreirajte od**.

   - Izaberite opciju **Profili** za izgradnju segmenta koji je zasnovan na objedinjenom entitetu Klijent.
   - Izaberite opciju **Mere** za izgradnju segmenta oko svake vrste mera atributa klijenta koje ste prethodno kreirali na stranici **Mere**.
   - Izaberite opciju **Obaveštavanje** da izgradite segment oko jednog od izlaznih entiteta koje ste generisali koristeći mogućnosti **Predviđanja** ili **Prilagođeni modeli**.

2. U dijalogu **Novi brzi segment** izaberite atribut iz padajuće liste **Polje**.

3. Sistem će vam pružiti neke dodatne uvide koji će vam pomoći da stvorite bolje segmente svojih klijenata.
   - Za kategorijska polja prikazaćemo 10 glavnih brojeva klijenta. Odaberite **Vrednost** i izabrali **Pregled**.

   - Za numerički atribut, sistem će pokazati koja vrednost atributa spada ispod svakog procenta klijenta. Odaberite **Operator** i **Vrednost**, a zatim izaberite **Pregled**.

4. Sistem će vam pružiti **Procenjenu veličinu segmenta**. Možete odabrati da li da generišete segment koji ste definisali ili da ga prvo pregledate kako biste dobili drugu veličinu segmenta.

    > [!div class="mx-imgBorder"]
    > ![Naziv i procena za brzi segment](media/quick-segment-name.png "Naziv i procena za brzi segment")

5. Navedite **Naziv** za segment. Opcionalno, navedite **Ime za prikaz**.

6. Izaberite **Sačuvaj** da biste kreirali segment.

7. Nakon završetka obrade segmenta, možete ga pregledati kao i bilo koji drugi segment koji ste kreirali.

Za sledeće scenarije, savetujemo upotrebu alata za pravljenje segmenata umesto preporučenih mogućnosti segmenata:

- Stvaranje segmenata sa filterima na kategorijskim poljima gde je operator drugačiji od operatora **Da li je**
- Kreiranje segmenata sa filterima na numeričkim poljima gde je operator drugačiji od operatora **Između**, **Veće od** i **Manje od**
- Kreiranje segmenata sa filterima na poljima tipa datuma

## <a name="next-steps"></a>Sledeći koraci

[Izvezite segment](export-destinations.md) i istražite [karticu klijenta](customer-card-add-in.md) i [konektore](export-power-bi.md) da biste dobili uvid na nivou klijenta.
