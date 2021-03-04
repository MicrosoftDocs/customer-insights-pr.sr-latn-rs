---
title: Predviđanje preporuke proizvoda
description: Predvidite proizvode koje će klijent verovatno kupiti ili stupiti u interakciju sa njima.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270529"
---
# <a name="product-recommendation-prediction-preview"></a>Predviđanje preporuke proizvoda (pregled)

Model preporuke proizvoda kreira skupove prediktivnih preporuka proizvoda. Preporuke se zasnivaju na prethodnom ponašanju kupovine i klijentima sa sličnim obrascima kupovine. Nova predviđanja za preporuke proizvoda možete da kreirate na stranici **Obaveštavanje** > **Predviđanja**. Izaberite **Moja predviđanja** da vidite druga predviđanja koja ste kreirali.

Preporuke proizvoda mogu biti podložne lokalnim zakonima i propisima, kao i očekivanjima klijenata, za šta model nije kreiran da bi posebno uzeo u obzir.  Kao korisnik ove mogućnosti predviđanja, **morate pregledati preporuke pre nego što ih dostavite klijentima** kako biste bili sigurni da se pridržavate svih važećih zakona i propisa, kao i očekivanja klijenata u vezi sa onim što možete preporučiti. 

Pored toga, izlaz ovog modela će vam dati preporuke na osnovu ID-a proizvoda. Mehanizam isporuke moraće uzeti predviđene ID-ove proizvoda i mapirati ih u odgovarajući sadržaj kako bi vaši klijenti uzeli u obzir lokalizaciju, sadržaj slike i drugi sadržaj ili ponašanje specifičan za posao.

## <a name="sample-guide"></a>Primer vodiča

Ako ste zainteresovani za isprobavanje ove funkcije, ali nemate podatke kako biste ispunili dolenavedene zahteve, možete da [kreirate primer primene](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Preduslovi

- Barem [dozvole saradnika](permissions.md) u usluzi Customer Insights.
- Poslovno znanje za razumevanje različitih vrsta proizvoda za vaše poslovanje i kako klijenti komuniciraju s njima. Podržavamo preporučivanje proizvoda koje su prethodno kupili vaši klijenti ili preporuke za nove proizvode.
- Podaci o transakcijama, kupovinama i njihova istorija:
    - Identifikatori transakcija za razlikovanje kupovina ili transakcija.
    - Identifikatori klijenata za mapiranje transakcija na klijente.
    - Datumi događaja transakcija koji navode datume kada se transakcija dogodila.
    - (Opcionalno) Informacije o ID-u proizvoda za transakciju.
    - (Opcionalno) Da li je transakcija povraćaj ili ne.
    - Šema semantičkih podataka zahteva sledeće informacije:
        - **ID transakcije:** Jedinstveni identifikator kupovine ili transakcije.
        - **Datum transakcije:** Datum kupovine ili transakcije.
        - **Vrednost transakcije:** Numerička vrednost kupovine ili transakcije.
        - **Jedinstveni ID proizvoda:** ID proizvoda ili usluge kupljene ako su vaši podaci na nivou stavke porudžbine.
        - (Opcionalno) **Kupovina ili povraćaj:** Polje sa vrednošću „tačno/netačno“ koje identifikuje da li je transakcija bila povraćaj ili ne. Ako je **Vrednost transakcije** negativna, koristićemo i ove podatke za zaključivanje da je u pitanju povraćaj.


## <a name="create-a-product-recommendation-prediction"></a>Kreiranje predviđanja preporuke proizvoda

1. U usluzi Customer Insights, idite na **Obaveštavanje** > **Predviđanja**.

1. Izaberite pločicu **Model preporuka proizvoda (pregled)**, a zatim dugme **Koristi ovaj model**.
   > [!div class="mx-imgBorder"]
   > ![Pločica „Model preporuka proizvoda“ sa dugmetom „Koristi ovaj model“](media/product-recommendation-usethismodel.PNG "Pločica „Model preporuka proizvoda“ sa dugmetom „Koristi ovaj model“")

1. Pregledajte informacije o zahtevima modela. Ako imate potrebne podatke, izaberite **Započni**.

### <a name="name-model"></a>Davanje naziva modela

1. Navedite naziv modela da biste ga razlikovali od ostalih modela.

1. Unesite naziv za izlazni entitet koristeći samo slova i brojeve, bez razmaka. To je naziv koji će entitet modela koristiti. Zatim izaberite **Sledeće**.

### <a name="define-product-recommendation-configuration"></a>Definišite konfiguraciju preporuka proizvoda

1. Podesite **Broj proizvoda** koji želite da preporučite klijentu. Ova vrednost zavisi od toga kako način isporuke popunjava podatke. Ako možete da preporučite tri proizvoda, podesite ovu vrednost u skladu sa tim.
   
   >[!TIP]
   > Možete da izaberete **Sačuvaj i zatvori** u bilo kom trenutku da biste sačuvali predviđanje kao radnu verziju. Radnu verziju predviđanja ćete pronaći na kartici **Moja predviđanja**.

1. Odaberite da li želite da **predložite proizvode koje su klijenti nedavno kupili**.

1. Ako ste izabrali da *ne* preporučite nedavno kupljene proizvode, podesite **Period za reviziju**. Ovo podešavanje određuje vremenski okvir koji model uzima u obzir pre nego što ponovo preporuči proizvod korisniku. Na primer, ukažite na to da klijent kupuje laptop svake 2 godine. Ovaj vremenski period će pogledati istoriju kupovine za poslednje 2 godine i ako pronađe stavku, ona će biti filtrirana iz preporuka.

1. Izaberite **Sledeće**

### <a name="add-required-data"></a>Dodavanje obaveznih podataka

1. Izaberite **Dodaj podatke** za **Istoriju transakcija klijenta** i odaberite entitet koji pruža informacije o istoriji transakcija/kupovina kao što je opisano u [preduslovima](#prerequisites).

1. Mapirajte semantička polja sa atributima u entitetu istorije kupovine i izaberite **Sledeće**. Za opis polja pogledajte [preduslove](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definisanje relacije entiteta](media/product-recommendation-purchasehistorymapping.PNG "Stranica istorije kupovine koja prikazuje semantičke atribute koji su mapirani u polja u izabranom entitetu istorije kupovine")

1. Ako polja u nastavku nisu popunjena, konfigurišite relaciju između entiteta istorije kupovine i entiteta *klijenta*.
    1. Izaberite **Entitet istorije kupovine**.
    1. Izaberite **Polje** koje identifikuje klijenta u entitetu istorije kupovine. Mora da se odnosi na primarni ID klijenta entiteta *klijenta*.
    1. Izaberite **Entitet klijenta** koji odgovara primarnom entitetu klijenta.
    1. Unesite ime koje opisuje odnos.
       > [!div class="mx-imgBorder"]
       > ![Stranica istorije kupovine koja prikazuje kreiranje relacije sa klijentom](media/model-purchase-join.png "Stranica istorije kupovine koja prikazuje kreiranje relacije sa klijentom")

1. Izaberite stavku **Sačuvaj**.

1. Izaberite **Sledeće**.

### <a name="set-schedule-and-review-configuration"></a>Podesite raspored i pregledajte konfiguraciju

1. Podesite učestalost kako biste ponovo obučili model. Ovo podešavanje je važno za ažuriranje tačnosti predviđanja jer se novi podaci uvoze u Customer Insights. Većina preduzeća može da obavi ponovnu obuku jednom mesečno i dobije precizna predviđanja.

1. Izaberite **Sledeće**.

1. Pregledajte konfiguraciju. Možete se vratiti na bilo koji deo konfiguracije predviđanja ako izaberete **Uredi** ispod prikazane vrednosti. Ili možete da odaberete korak konfiguracije iz indikatora napretka.

1. Ako su sve vrednosti pravilno konfigurisane, izaberite **Sačuvaj i pokreni** da biste započeli proces predviđanja. Na kartici **Moja predviđanja** možete videti status predviđanja. Za završetak procesa može biti potrebno nekoliko sati, u zavisnosti od količine podataka korišćenih u predviđanju.

## <a name="review-a-prediction-status-and-results"></a>Pregled statusa i rezultata predviđanja

1. Idite na karticu **Moja predviđanja** u delu **Obaveštavanje** > **Predviđanja**.
   > [!div class="mx-imgBorder"]
   > ![Pregled stranice Moja predviđanja](media/product-recommendation-mypredictions.PNG "Pregled stranice Moja predviđanja")

1. Izaberite predviđanje koje želite da pregledate.
   - **Naziv predviđanja:** Naziv predviđanja koji ste naveli prilikom njegovog kreiranja.
   - **Vrsta predviđanja:** Tip modela koji se koristi za predviđanje
   - **Izlazni entitet:** Naziv entiteta za skladištenje izlaza predviđanja. Možete pronaći entitet sa ovim imenom u delu **Podaci** > **Entiteti**.
   - **Predviđeno polje:** Ovo polje je popunjeno samo za neke tipove predviđanja i ne koristi se za predviđanje gubitka.
   - **Status:** Trenutni status pokretanja predviđanja.
        - **U redu:** Predviđanje trenutno čeka da se pokrenu i drugi procesi.
        - **Osvežavanje:** Predviđanje je trenutno u fazi ocenjivanja obrade da bi se dobili rezultati koji će se preneti u izlazni entitet.
        - **Nije uspelo:** Predviđanje nije uspelo. Izaberite **Evidencije** za više detalja.
        - **Uspešno:** Predviđanje je uspelo. Izaberite **Pregled** u okviru uspravne tri tačke da biste pregledali predviđanje
   - **Izmenjeno:** Datum promene konfiguracije predviđanja.
   - **Poslednje osvežavanje:** Datum kada je predviđanje osvežilo rezultate u izlaznom entitetu.

1. Odaberite uspravne tri tačke pored predviđanja za koje želite da pregledate rezultate i izaberite **Pregled**.
   > [!div class="mx-imgBorder"]
   > ![Prikaz opcija u meniju sa uspravne tri tačke za predviđanje koje obuhvataju uređivanje, osvežavanje, pregled, evidenciju i brisanje](media/product-recommendation-verticalellipses.PNG "Prikaz opcija u meniju sa uspravne tri tačke za predviđanje koje obuhvataju uređivanje, osvežavanje, pregled, evidenciju i brisanje")

1. Postoje tri primarna odeljka podataka na stranici sa rezultatima:
    1. **Performanse modela obuke:** A, B ili C su mogući rezultati. Ovaj rezultat pokazuje performanse predviđanja i može vam pomoći da donesete odluku o korišćenju rezultata sačuvanih u izlaznom entitetu.
        - Rezultati se određuju na osnovu sledećih pravila:
            - **A** Model će se smatrati **A** kvalitetom ako je metrika „Uspeh @ K“ bar 10% veća od osnovne vrednosti. 
            - **B** Model će se smatrati **B** kvalitetom ako je metrika „Uspeh @ K“ od 0 do 10% veća od osnovne vrednosti.
            - **V** Model će se smatrati **V** kvalitetom ako je metrika „Uspeh @ K“ od manja od osnovne vrednosti.
               
               > [!div class="mx-imgBorder"]
               > ![Pregled rezultata performansi modela](media/product-recommendation-modelperformance.PNG "Pregled rezultata performansi modela")
            - **Osnovna vrednost**: Model uzima najbolje preporučene proizvode prema broju kupovina kod svih klijenata i koristi naučena pravila identifikovana modelom za kreiranje niza preporuka za klijente. Zatim se predviđanja upoređuju sa najboljim proizvodima, što se izračunava kao broj klijenata koji su kupili proizvod. Ako klijent ima barem jedan proizvod u preporučenim proizvodima koji se takođe nalazi među najpopularnijim kupljenim proizvodima, smatra se delom osnovne vrednosti. Da je 10 od ovih klijenata od ukupno 100 klijenata kupilo preporučeni proizvod, osnovna vrednost bi bila 10%.
            - **Uspeh @ K**: Korišćenjem skupa za validaciju vremenskog perioda transakcija, preporuke se kreiraju za sve klijente i upoređuju se sa skupom za validaciju transakcija. Na primer, u periodu od 12 meseci, 12. mesec može se izdvojiti kao skup podataka za validaciju. Ako model predvidi bar jednu stvar koju biste kupili u 12. mesecu na osnovu onoga što je naučio iz prethodnih 11 meseci, klijent bi povećao metriku „Uspeh @ K“.
    
    1. **Najčešće predlagani proizvodi (sa brojem):** Najboljih 5 proizvoda koji su predviđeni za vaše klijente.
       > [!div class="mx-imgBorder"]
       > ![Grafikon koji prikazuje najboljih 5 preporučenih proizvoda](media/product-recommendation-topproducts.PNG "Grafikon koji prikazuje najboljih 5 preporučenih proizvoda")
    
    1. **Preporuke proizvoda visoke pouzdanosti:** Uzorak preporuka dostavljenih vašim klijentima za koje model veruje da će ih klijenti verovatno kupiti.
       > [!div class="mx-imgBorder"]
       > ![Lista koja prikazuje predloge sa visokom pouzdanošću za izabrani skup pojedinačnih klijenata](media/product-recommendation-highconfidence.PNG "Lista koja prikazuje predloge sa visokom pouzdanošću za izabrani skup pojedinačnih klijenata")

## <a name="fix-a-failed-prediction"></a>Ispravljanje neuspelog predviđanja

1. Idite na karticu **Moja predviđanja** u delu **Obaveštavanje** > **Predviđanja**.

1. Odaberite predviđanje za koje želite da pregledate evidenciju grešaka i izaberite **Evidencije**.

1. Pregledajte sve greške. Može se pojaviti nekoliko vrsta grešaka i one opisuju uslov koji je doveo do greške. Na primer, greška da nema dovoljno podataka za tačno predviđanje obično se rešava učitavanjem dodatnih podataka u Customer Insights.

## <a name="refresh-a-prediction"></a>Osvežavanje predviđanja

Predviđanja se automatski osvežavaju na istom [rasporedu osvežavanja podataka](system.md#schedule-tab), kao što je konfigurisano u podešavanjima.

1. Idite na karticu **Moja predviđanja** u delu **Obaveštavanje** > **Predviđanja**.

1. Odaberite uspravne tri tačke pored predviđanja koje želite da osvežite.

1. Izaberite **Osveži**.

## <a name="delete-a-prediction"></a>Brisanje predviđanja

Brisanjem predviđanja ukloniće se i njegov izlazni entitet.

1. Idite na karticu **Moja predviđanja** u delu **Obaveštavanje** > **Predviđanja**.

1. Odaberite uspravne tri tačke pored predviđanja koje želite da izbrišete.

1. Izaberite **Izbriši**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]