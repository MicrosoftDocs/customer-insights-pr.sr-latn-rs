---
title: Predviđanje preporuke proizvoda
description: Predvidite proizvode koje će klijent verovatno kupiti ili stupiti u interakciju sa njima.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 62b829b6ca3074e0ca52fb52584b74572bb05f05
ms.sourcegitcommit: 15b1521041149716f8031cfa6d0dc61a56a5e2ff
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967856"
---
# <a name="product-recommendation-prediction-preview"></a>Predviđanje preporuke proizvoda (pregled)

Model preporuke proizvoda kreira skupove prediktivnih preporuka proizvoda. Preporuke se zasnivaju na prethodnom ponašanju kupovine i klijentima sa sličnim obrascima kupovine. Nova predviđanja za preporuke proizvoda možete da kreirate na stranici **Obaveštavanje** > **Predviđanja**. Izaberite **Moja predviđanja** da vidite druga predviđanja koja ste kreirali.

Preporuke za proizvode mogu da podležu lokalnim zakonima i propisima i očekivanjima klijenata, pri čemu model nije napravljen da bi ih posebno uzeo u obzir.  Kao korisnik ove mogućnosti predviđanja, **morate pregledati preporuke pre nego što ih dostavite svojim klijentima** kako biste bili sigurni da se pridržavate svih važećih zakona i propisa i očekivanja klijenata u vezi sa onim što možete preporučiti. 

Pored toga, izlaz ovog modela će vam dati preporuke na osnovu ID-a proizvoda. Vaš mehanizam isporuke moraće da mapira predviđene ID-ove proizvoda u odgovarajući sadržaj za vaše klijente kako bi uzeo u obzir lokalizaciju, slikovni sadržaj i drugi sadržaj ili ponašanje specifično za preduzeće.

## <a name="sample-guide"></a>Primer vodiča

Ako ste zainteresovani za isprobavanje ove funkcije, ali nemate podatke kako biste ispunili dolenavedene zahteve, možete da [kreirate primer primene](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Preduslovi

- Barem [dozvole saradnika](permissions.md) u usluzi Customer Insights.

- Poslovno znanje za razumevanje različitih vrsta proizvoda za vaše poslovanje i kako klijenti komuniciraju s njima. Podržavamo preporučivanje proizvoda koje su prethodno kupili vaši klijenti ili preporuke za nove proizvode.

- Podaci o transakcijama, kupovinama i njihova istorija:
    - Identifikatori transakcija za razlikovanje kupovina ili transakcija.
    - Identifikatori klijenata za mapiranje transakcija na klijente.
    - Datumi događaja transakcija koji navode datume kada se transakcija dogodila.
    - Informacije o ID-u proizvoda za transakciju.
    - (Opcionalno) Entitet podataka kataloga proizvoda koji koristi filter proizvoda.
    - (Opcionalno) Da li je transakcija povraćaj ili ne.
    - Šema semantičkih podataka zahteva sledeće informacije:
        - **ID transakcije:** Jedinstveni identifikator kupovine ili transakcije.
        - **Datum transakcije:** Datum kupovine ili transakcije.
        - **Vrednost transakcije:** Numerička vrednost kupovine ili transakcije.
        - **Jedinstveni ID proizvoda:** ID proizvoda ili usluge kupljene ako su vaši podaci na nivou stavke porudžbine.
        - (Opcionalno) **Kupovina ili povraćaj:** Logičko polje gde je vrednost *tačno* identifikuje da je transakcija bila povraćaj. Ako podaci o kupovini ili povraćaju ne navode model, a **Vrednost transakcije** je negativna, koristićemo i ove podatke za zaključivanje povraćaja.
- Predložene karakteristike podataka:
    - Dovoljno istorijskih podataka: Najmanje jedna godina podataka o transakcijama, po mogućnosti dve do tri godine da bi se uključila određena periodičnost.
    - Više kupovina po klijentu: tri ili više transakcija po ID-u klijenta
    - Broj klijenata: Najmanje 100 klijenata, po mogućnosti više od 10.000 klijenata. Model neće uspeti sa manje od 100 klijenata.

> [!NOTE]
> - Model zahteva istoriju transakcija vaših klijenata. Definicija transakcije je prilično fleksibilna. Svi podaci koji opisuju interakciju korisnika i proizvoda mogu da posluže kao ulaz. Na primer, kupovina proizvoda, pohađanje predavanja ili prisustvovanje događaju.
> - Trenutno se može konfigurisati samo jedan entitet istorije transakcija. Ako postoji više entiteta nabavke, sloћite ih Power Query pre unošenja podataka.
> - Ako su detalji porudžbine i naloga različiti entiteti, pridružite im se pre upotrebe u modelu. Model ne radi samo sa ID-om porudžbine ili ID-om priznanice u entitetu.


## <a name="create-a-product-recommendation-prediction"></a>Kreiranje predviđanja preporuke proizvoda

1. U usluzi Customer Insights, idite na **Obaveštavanje** > **Predviđanja**.

1. Izaberite pločicu **Model preporuka proizvoda (pregled)**, a zatim dugme **Koristi ovaj model**.
   > [!div class="mx-imgBorder"]
   > ![Pločica „Model preporuka proizvoda“ sa dugmetom „Koristi ovaj model“.](media/product-recommendation-usethismodel.PNG "Pločica „Model preporuka proizvoda“ sa dugmetom „Koristi ovaj model“")

1. Pregledajte informacije o zahtevima modela. Ako imate potrebne podatke, izaberite **Započni**.

### <a name="name-model"></a>Davanje naziva modela

1. Navedite naziv modela da biste ga razlikovali od ostalih modela.

1. Unesite naziv za izlazni entitet koristeći samo slova i brojeve, bez razmaka. To je naziv koji će entitet modela koristiti. Zatim izaberite **Sledeće**.

### <a name="define-product-recommendation-configuration"></a>Definišite konfiguraciju preporuka proizvoda

1. Podesite **Broj proizvoda** koji želite da preporučite klijentu. Ova vrednost zavisi od toga kako način isporuke popunjava podatke. Ako možete da preporučite tri proizvoda, podesite ovu vrednost u skladu sa tim.
   
   >[!TIP]
   > U svakom trenutku **možete da** izaberete opciju "Sačuvaj radnu verziju" da biste sačuvali predviđanje kao radnu verziju. Radnu verziju predviđanja ćete pronaći na kartici **Moja predviđanja**.

1. Odaberite da li želite da uključite proizvode koje su kupci nedavno kupili u **polje Ponavljanje očekivanih** nabavki.

1. Postavite **prozor "Pogledaj unazad"**. Ovo podešavanje određuje vremenski okvir koji model uzima u obzir pre nego što ponovo preporuči proizvod korisniku. Na primer, naznačite da klijent kupuje prenosni računar svake dve godine. Ovaj prozor će pogledati istoriju kupovine za poslednje dve godine i ako pronađu stavku, stavka će biti filtrirana iz preporuka.

1. Izaberite **Sledeće**

### <a name="add-required-data"></a>Dodavanje obaveznih podataka

1. Izaberite **Dodaj podatke** i odaberite vrstu aktivnosti u bočnom oknu koja sadrži potrebne podatke o transakcijama ili istoriji kupovine.

1. U okviru **Odaberite aktivnosti**, odaberite određene aktivnosti iz izabrane aktivnosti na koju želite da se obračun fokusira.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Bočno okno prikazuje odabir određenih aktivnosti prema semantičkom tipu.":::

1. Ako još niste mapirali aktivnost u semantički tip, izaberite **Uredi** da biste to uradili. Otvara se vođeno iskustvo za mapiranje semantičkih aktivnosti. Mapirajte podatke u odgovarajuća polja u izabranom tipu aktivnosti.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Tip aktivnosti podešavanja stranice.":::

1. Nakon mapiranja aktivnosti na odgovarajući semantički tip, izaberite **Sledeći** za nastavak 
 
1. Mapirajte semantičke atribute u polja koja su potrebna za pokretanje modela.

1. Izaberite stavku **Sačuvaj**.

1. Izaberite **Sledeće**.


### <a name="configure-product-filters"></a>Konfigurisanje filtera za proizvode

Ponekad su samo određeni proizvodi korisni ili prikladni za tip predviđanja koji gradite. Filteri proizvoda omogućavaju vam da identifikujete podskup proizvoda sa određenim karakteristikama koje ćete preporučiti svojim klijentima. Model će koristiti sve dostupne proizvode za učenje obrazaca, ali u izlazu koristi samo proizvode koji se podudaraju sa filterom proizvoda.

1. U koraku **Dodavanje informacija o proizvodu**, dodajte katalog proizvoda sa informacijama za svaki proizvod. Mapirajte potrebne informacije i izaberite **Sledeće**.

3. U koraku **Filteri za proizvode**, odaberite između sledećih opcija.

   * **Bez filtera**: Koristite sve proizvode u predviđanju preporuke za proizvod.

   * **Definišite određene filtere proizvoda**: Koristite određene proizvode u preporuci predviđanja za proizvod.

1. Izaberite **Sledeće**.

1. Ako odlučite da definišete filter proizvoda, morate ga sada definisati. U oknu **Atributi kataloga proizvoda** odaberite atribute iz *entiteta kataloga proizvoda* koje želite da uključite u filter.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Bočno okno prikazuje atribute u entitetu kataloga proizvoda da biste ih izabrali za filtere proizvoda.":::

1. Odaberite da li želite da filter proizvoda koristi konektore **i** ili **ili** za logičko kombinovanje izbora atributa iz kataloga proizvoda.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Primer konfiguracije filtera proizvoda u kombinaciji sa logičkim I konektorima.":::

1. Izaberite **Sledeće**.

### <a name="set-update-schedule-and-review-configuration"></a>Podešavanje rasporeda ažuriranja i pregled konfiguracije

1. Podesite učestalost kako biste ponovo obučili model. Ovo podešavanje je važno za ažuriranje tačnosti predviđanja jer se novi podaci uvoze u Customer Insights. Većina preduzeća može da obavi ponovnu obuku jednom mesečno i dobije precizna predviđanja.

1. Izaberite **Sledeće**.

1. Pregledajte konfiguraciju. Možete se vratiti na bilo koji deo konfiguracije predviđanja ako izaberete **Uredi** ispod prikazane vrednosti. Ili možete da odaberete korak konfiguracije iz indikatora napretka.

1. Ako su sve vrednosti pravilno konfigurisane, izaberite **Sačuvaj i pokreni** da biste započeli proces predviđanja. Na kartici **Moja predviđanja** možete videti status predviđanja. Za završetak procesa može biti potrebno nekoliko sati, u zavisnosti od količine podataka korišćenih u predviđanju.

## <a name="review-a-prediction-status-and-results"></a>Pregled statusa i rezultata predviđanja

1. Idite na karticu **Moja predviđanja** u delu **Obaveštavanje** > **Predviđanja**.
   > [!div class="mx-imgBorder"]
   > ![Pregled stranice Moja predviđanja.](media/product-recommendation-mypredictions.PNG "Pregled stranice Moja predviđanja")

1. Izaberite predviđanje koje želite da pregledate.
   - **Naziv predviđanja:** Naziv predviđanja koji ste naveli prilikom njegovog kreiranja.
   - **Vrsta predviđanja:** Tip modela koji se koristi za predviđanje
   - **Izlazni entitet:** Naziv entiteta za skladištenje izlaza predviđanja. Možete pronaći entitet sa ovim imenom u delu **Podaci** > **Entiteti**.    
      *Ocena* u izlaznom entitetu je kvantitativna mera preporuke. Model preporučuje proizvode sa višom ocenom u odnosu na proizvode sa nižom ocenom.
   - **Predviđeno polje:** Ovo polje se popunjava samo za neke vrste predviđanja i ne koristi se u predviđanju preporuke za proizvod.
   - **Status:** Trenutni status pokretanja predviđanja.
        - **U redu:** Predviđanje trenutno čeka da se pokrenu i drugi procesi.
        - **Osvežavanje:** Predviđanje je trenutno u fazi ocenjivanja obrade da bi se dobili rezultati koji će se preneti u izlazni entitet.
        - **Nije uspelo:** Predviđanje nije uspelo. Izaberite **Evidencije** za više detalja.
        - **Uspešno:** Predviđanje je uspelo. Izaberite **Pregled** u okviru uspravne tri tačke da biste pregledali predviđanje
   - **Izmenjeno:** Datum promene konfiguracije predviđanja.
   - **Poslednje osvežavanje:** Datum kada je predviđanje osvežilo rezultate u izlaznom entitetu.

1. Odaberite uspravne tri tačke pored predviđanja za koje želite da pregledate rezultate i izaberite **Pregled**.
   > [!div class="mx-imgBorder"]
   > ![Prikaz opcija u meniju sa uspravne tri tačke za predviđanje koje obuhvataju uređivanje, osvežavanje, pregled, evidenciju i brisanje.](media/product-recommendation-verticalellipses.PNG "Prikaz opcija u meniju sa uspravne tri tačke za predviđanje koje obuhvataju uređivanje, osvežavanje, pregled, evidenciju i brisanje")

1. Na stranici rezultata nalazi se pet primarnih odeljaka podataka:
    1. **Performanse modela obuke:** A, B ili C su mogući rezultati. Ovaj rezultat pokazuje performanse predviđanja i može vam pomoći da donesete odluku o korišćenju rezultata sačuvanih u izlaznom entitetu.
        - Rezultati se određuju na osnovu sledećih pravila:
            - **A** Model će se smatrati **A** kvalitetom ako je metrika „Uspeh @ K“ bar 10% veća od osnovne vrednosti. 
            - **B** Model će se smatrati **B** kvalitetom ako je metrika „Uspeh @ K“ od 0% do 10% veća od osnovne vrednosti.
            - **C** Model će se smatrati **C** kvalitetom ako je metrika „Uspeh @ K“ manja od osnovne vrednosti.
               
               > [!div class="mx-imgBorder"]
               > ![Pregled rezultata performansi modela.](media/product-recommendation-modelperformance.PNG "Pregled rezultata performansi modela")
            - **Osnovna vrednost**: Model uzima najbolje preporučene proizvode prema broju kupovina kod svih klijenata i koristi naučena pravila identifikovana modelom za kreiranje niza preporuka za klijente. Zatim se predviđanja upoređuju sa najboljim proizvodima, što se izračunava kao broj klijenata koji su kupili proizvod. Ako klijent ima barem jedan proizvod u preporučenim proizvodima koji se takođe nalazi među najpopularnijim kupljenim proizvodima, smatra se delom osnovne vrednosti. Da je 10 od ovih klijenata od ukupno 100 klijenata kupilo preporučeni proizvod, osnovna vrednost bi bila 10%.
            - **Uspeh @ K**: Korišćenjem skupa za validaciju vremenskog perioda transakcija, preporuke se kreiraju za sve klijente i upoređuju se sa skupom za validaciju transakcija. Na primer, u periodu od 12 meseci, 12. mesec može se izdvojiti kao skup podataka za validaciju. Ako model predvidi bar jednu stvar koju biste kupili u 12. mesecu na osnovu onoga što je naučio iz prethodnih 11 meseci, klijent bi povećao metriku „Uspeh @ K“.
    
    1. **Najviše predlagani proizvodi (sa rezultatom):** Pet najboljih proizvoda koji su predviđeni za vaše klijente.
       > [!div class="mx-imgBorder"]
       > ![Grafikon koji prikazuje najboljih 5 preporučenih proizvoda.](media/product-recommendation-topproducts.PNG "Grafikon koji prikazuje najboljih 5 preporučenih proizvoda")
    
    1. **Ključni faktori preporuke:** Model koristi istoriju transakcija klijenata za davanje preporuka za proizvode. Model uči obrasce zasnovane na prošlim kupovinama i pronalazi sličnosti između klijenata i proizvoda. Te sličnosti se zatim koriste za generisanje preporuka za proizvode.
    Slede faktori koji mogu uticati na preporuke proizvoda koje generiše model. 
        - **Prošle transakcije**: Model je u prošlosti koristio obrasce kupovine za generisanje preporuka za proizvode. Na primer, model može da preporuči _Surface Arc miša_ ako je neko nedavno kupio _Surface Book 3_ i _Surface olovku_. Model je saznao da su u prošlosti mnogi klijenti kupili _Surface Arc miša_ kada su kupili _Surface Book 3_ i _Surface olovku_.
        - **Sličnost klijenata**: Preporučeni proizvod u prošlosti su kupovali drugi klijenti koji pokazuju slične obrasce kupovine. Na primer, Jovanu su preporučene _slušalice Surface Headphones 2_ jer su Snežana i Branko nedavno kupili _slušalice Surface Headphones 2_. Model veruje da je Jovan sličan sa Snežanom i Brankom, jer su u oni prošlosti imali slične obrasce kupovine.
        - **Sličnost proizvoda**: Preporučeni proizvod je sličan ostalim proizvodima koje je klijent prethodno kupio. Model smatra da su dva proizvoda slična ako su kupljeni zajedno ili su ih kupili slični klijenti. Na primer, neko dobije preporuku za _USB memorijski uređaj_ jer je prethodno kupio _adapter USB-C na USB_, a model veruje da je _USB memorijski uređaj_ sličan _adapteru USB-C na USB_ na osnovu istorijskih obrazaca kupovine.

        Na svaku preporuku proizvoda utiče jedan ili više ovih faktora. Procenat preporuka u kojima je svaki uticajni faktor igrao ulogu prikazan je na grafikonu. U sledećem primeru, na 100% preporuka su uticale prošle transakcije, 60% sličnost klijenata i 22% sličnost proizvoda. Pređite kursorom preko traka na grafikonu da biste videli tačan procenat doprinosa faktora uticaja.

        > [!div class="mx-imgBorder"]
        > ![Ključni faktori za preporuke.](media/product-recommendation-keyrecommendationfactors.png "Ključni faktori za preporuke koje je model naučio za generisanje preporuka za proizvode")
       
     
   1. **Statistika podataka**: Daje pregled broja transakcija, klijenata i proizvoda koje je model razmatrao. Zasniva se na ulaznim podacima koji su korišćeni za učenje obrazaca i generisanje preporuka za proizvode.

      > [!div class="mx-imgBorder"]
      > ![Statistika podataka.](media/product-recommendation-datastatistics.png "Statistika podataka oko ulaznih podataka koje model koristi za učenje obrazaca")

      Ovaj odeljak prikazuje statistiku oko tačaka podataka koje je model koristio za učenje obrazaca i generisanje preporuka za proizvode. Filtriranje, kao što je konfigurisano u konfiguraciji modela, primeniće se na izlaz koji generiše model. Međutim, model koristi sve dostupne podatke za učenje obrazaca. Stoga, ako koristite filtriranje proizvoda u konfiguraciji modela, ovaj odeljak će prikazati ukupan broj proizvoda koje je model analizirao da bi naučio obrasce, koji se mogu razlikovati od broja proizvoda koji odgovaraju definisanim kriterijumima filtriranja.

   1. **Preporuke proizvoda visoke pouzdanosti:** Uzorak preporuka dostavljenih vašim klijentima za koje model veruje da će ih klijenti verovatno kupiti.    
      Ako se doda katalog proizvoda, ID-ovi proizvoda se zamenjuju nazivima proizvoda. Nazivi proizvoda pružaju korisnije i intuitivnije informacije o predviđanjima.
       > [!div class="mx-imgBorder"]
       > ![Lista koja prikazuje predloge sa visokom pouzdanošću za izabrani skup pojedinačnih klijenata.](media/product-recommendation-highconfidence.PNG "Lista koja prikazuje predloge sa visokom pouzdanošću za izabrani skup pojedinačnih klijenata")

## <a name="manage-predictions"></a>Upravljanje predviđanjima

Predviđanja je moguće optimizovati, rešavati, osvežiti ili izbrisati. Pregledajte izveštaj o upotrebljivosti ulaznih podataka da biste saznali kako da predviđanje učinite bržim i pouzdanijim. Još informacija potražite u članku [Upravljanje predviđanjima](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
