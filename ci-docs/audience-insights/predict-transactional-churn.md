---
title: Predviđanje gubitka transakcija
description: Predvidite da li je klijent ugrožen zbog toga što više ne kupuje vaše proizvode ili usluge.
ms.date: 11/12/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af461d290c69687fb47bacfcff446a0c62978383
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268335"
---
# <a name="transactional-churn-prediction-preview"></a>Predviđanje gubitka transakcija (verzija za pregled)

Predviđanje gubitka transakcija pomaže u predviđanju da li klijent više neće kupovati vaše proizvode ili usluge u datom vremenskom periodu. Možete da kreirate nova predviđanja gubitka u odeljku **Obaveštavanje** > **Predviđanja**. Izaberite **Moja predviđanja** da vidite druga predviđanja koja ste kreirali.

> [!TIP]
> Isprobajte vodič za predviđanje gubitka transakcija koristeći uzorke podataka: [Primer vodiča za predviđanje gubitka transakcija (verzija za pregled)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Preduslovi

- Barem [dozvole saradnika](permissions.md) u usluzi Customer Insights.
- Poslovni uvidi da biste razumeli šta znači gubitak za vaše preduzeće. Podržavamo definicije gubitka zasnovane na vremenu, što znači da se smatra da je klijent izgubljen nakon perioda bez kupovine.
- Podaci o vašim transakcijama/kupovinama i njihova istorija:
    - Identifikatori transakcija za razlikovanje kupovina/transakcija.
    - Identifikatori klijenata za podudaranje transakcija sa klijentima.
    - Datumi transakcija, koji definišu datume kada se transakcija dogodila.
    - Šema semantičkih podataka za kupovine/transakcije zahteva sledeće informacije:
        - **ID transakcije:** Jedinstveni identifikator kupovine ili transakcije.
        - **Datum transakcije:** Datum kupovine ili transakcije.
        - **Vrednost transakcije:** Iznos valute/numeričke vrednosti transakcije/stavke.
        - (Opciono) **Jedinstveni ID proizvoda:** ID proizvoda ili usluge kupljene ako su vaši podaci na nivou stavke porudžbine.
        - (Opciono) **Da li je ova transakcija bila povraćaj:** Polje sa vrednošću „tačno/netačno“ koje identifikuje da li je transakcija bila povraćaj ili ne. Ako je **Vrednost transakcije** negativna, koristićemo i ove podatke za zaključivanje da je u pitanju povraćaj.
- (Opcionalno) Podaci o aktivnostima klijenata:
    - Identifikatori aktivnosti za razlikovanje aktivnosti iste vrste.
    - Identifikatori klijenata za mapiranje aktivnosti na klijente.
    - Informacije o aktivnostima koje sadrže ime i datum aktivnosti.
    - Šema semantičkih podataka za aktivnosti klijenata uključuje:
        - **Primarni ključ:** Jedinstveni identifikator aktivnosti. Na primer, poseta veb lokaciji ili evidencija upotrebe koja pokazuje da je klijent isprobao uzorak vašeg proizvoda.
        - **Vremenska oznaka:** Datum i vreme događaja koje identifikuje primarni ključ.
        - **Događaj:** Naziv događaja koji želite da koristite. Na primer, polje pod nazivom „Radnja korisnika“ u prehrambenoj prodavnici može biti kupon koji klijent koristi.
        - **Detalji:** Detaljne informacije o događaju. Na primer, polje pod nazivom „Vrednost kupona“ u prehrambenoj prodavnici može biti vrednost valute kupona.

## <a name="create-a-transactional-churn-prediction"></a>Kreiranje predviđanja gubitka transakcija

1. U usluzi Customer Insights, idite na **Obaveštavanje** > **Predviđanja**.

1. Izaberite pločicu **Model gubitka klijenata (verzija za pregled)** i **Koristi ovaj model**.
   
1. U oknu **Model gubitka klijenata** izaberite **Transakcijski** i izaberite **Započnite**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Snimak ekrana sa odabranom opcijom transakcije u oknu modela za gubitak klijenata.":::

### <a name="name-model"></a>Davanje naziva modela

1. Navedite naziv modela da biste ga razlikovali od ostalih modela.

1. Navedite ime izlaznog entiteta koje sadrži samo slova i brojeve, bez razmaka. To je naziv koji će entitet modela koristiti. 

1. Izaberite **Sledeće**.

### <a name="define-customer-churn"></a>Definisanje gubitka klijenata

1. Postavite vremenski period u danima za predviđanje gubitaka u polju **Utvrdite koje ćete klijente možda izgubiti u sledećem**. Na primer, predvidite rizik od gubitka klijenata tokom sledećih 90 dana kako biste se uskladili sa vašim marketinškim naporima za zadržavanje. Predviđanje rizika od gubitka na duži ili kraći vremenski period može otežati reagovanje na faktore na vašem profilu rizika od gubitka, ali to zavisi od vaših specifičnih poslovnih zahteva. 
   >[!TIP]
   > Možete da izaberete **Sačuvaj i zatvori** u bilo kom trenutku da biste sačuvali predviđanje kao radnu verziju. Da biste nastavili, radnu verziju predviđanja možete da pronađete na kartici **Moja predviđanja**.

1. Unesite broj dana za definisanje gubitka u polje **Klijent je izgubljen ako nije obavio nijednu kupovinu u:**. Na primer, ako klijent nije obavio nijednu kupovinu u poslednjih 30 dana, moglo bi se smatrati da je izgubljen za vaše preduzeće. 

1. Izaberite **Dalje** za nastavak

### <a name="add-required-data"></a>Dodavanje obaveznih podataka

1. Izaberite **Dodajte podatke** za **Istoriju kupovine** i odaberite entitet koji pruža informacije o istoriji transakcija/kupovina kako je opisano u [preduslovima](#prerequisites).

1. Mapirajte semantička polja sa atributima u entitetu istorije kupovine i izaberite **Sledeće**. Za opis polja pogledajte [preduslove](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Mapirajte semantička polja entiteta kupovine.":::

1. Ako polja u nastavku nisu popunjena, konfigurišite odnos između entiteta istorije kupovine i entiteta klijenta.
    1. Izaberite **Entitet istorije kupovine**.
    1. Izaberite **Polje** koje identifikuje klijenta u entitetu istorije kupovine. Mora da se odnosi na primarni ID klijenta entiteta „Klijent“.
    1. Izaberite **Entitet klijenta** koji odgovara primarnom entitetu klijenta.
    1. Unesite ime koje opisuje odnos.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Stranica istorije kupovine koja prikazuje kreiranje odnosa sa klijentom.":::
   
1. Izaberite **Sledeće**.

1. Po želji odaberite **Dodajte podatke** za **Aktivnosti klijenata**. Izaberite entitet koji pruža informacije o aktivnostima klijenata kako je opisano u preduslovima.

1. Mapirajte semantička polja sa atributima u entitetu aktivnosti klijenata i izaberite **Sledeće**. Za opis polja pogledajte [preduslove](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Mapirajte polja klijenata za podatke o transakcijama.":::

1. Odaberite vrstu aktivnosti koja odgovara vrsti aktivnosti klijenta koju konfigurišete. Izaberite **Kreiraj novo** i odaberite dostupni tip aktivnosti ili kreirajte novi.

1. Treba da konfigurišete odnos između entiteta aktivnosti klijenta i entiteta klijenta.
    1. Izaberite polje koje identifikuje klijenta na tabeli aktivnosti klijenata. Može biti direktno povezano sa primarnim ID-om klijenta entiteta „Klijent“.
    1. Izaberite Entitet klijenta koji odgovara primarnom entitetu klijenta
    1. Unesite ime koje opisuje odnos.

1. Izaberite stavku **Sačuvaj**.

1. Ako imate druge aktivnosti klijenata koje biste želeli da uključite, ponovite gornje korake.

1. Izaberite **Sledeće**.

### <a name="set-schedule-and-review-configuration"></a>Podesite raspored i pregledajte konfiguraciju

1. Podesite učestalost kako biste ponovo obučili model. Ovo podešavanje je važno za ažuriranje tačnosti predviđanja kako se unose novi podaci. Većina preduzeća može da obavi ponovnu obuku jednom mesečno i dobije precizna predviđanja.

1. Izaberite **Sledeće**.

1. Pregledajte konfiguraciju predviđanja. Možete se vratiti na prethodne korake ako izaberete **Uredi** ispod prikazane vrednosti. Ili možete da odaberete korak konfiguracije iz indikatora napretka.

1. Ako su sve vrednosti pravilno konfigurisane, izaberite **Sačuvaj i pokreni** da biste započeli proces predviđanja. Na kartici **Moja predviđanja** možete videti status predviđanja. Za završetak procesa može biti potrebno nekoliko sati, u zavisnosti od količine podataka korišćenih u predviđanju.

## <a name="review-a-prediction-status-and-results"></a>Pregled statusa i rezultata predviđanja

1. Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.

1. Izaberite predviđanje koje želite da pregledate.
   - **Naziv predviđanja:** Naziv predviđanja naveden pri njegovom kreiranju.
   - **Tip predviđanja:** Tip modela koji se koristi za predviđanje
   - **Izlazni entitet:** Naziv entiteta za skladištenje izlaza predviđanja. Možete pronaći entitet sa ovim imenom u delu **Podaci** > **Entiteti**.
   - **Predviđeno polje:** Ovo polje je popunjeno samo za neke tipove predviđanja i ne koristi se za predviđanje gubitka.
   - **Status:** Status pokretanja predviđanja.
        - **U redu:** Predviđanje čeka da se pokrenu drugi procesi.
        - **Osvežavanje:** Predviđanje je trenutno pokrenuto da bi dalo rezultate koji će biti prosleđeni u izlazni entitet.
        - **Nije uspelo:** Pokretanje predviđanja nije uspelo. Detaljnije informacije potražite u [evidenciji](#troubleshoot-a-failed-prediction).
        - **Uspelo je:** Predviđanje je uspelo. Izaberite **Pregled** u okviru uspravne tri tačke da biste pregledali predviđanje
   - **Izmenjeno:** Datum promene konfiguracije predviđanja.
   - **Poslednje osvežavanje:** Datum kada je predviđanje osvežilo rezultate u izlaznom entitetu.

1. Odaberite uspravne tri tačke pored predviđanja za koje želite da pregledate rezultate i izaberite **Pregled**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Pogledajte kontrolu da biste videli rezultate predviđanja.":::   

1. Postoje tri primarna odeljka podataka na stranici sa rezultatima:
    1. **Performanse modela obuke:** A, B ili C su mogući rezultati. Ovaj rezultat pokazuje performanse predviđanja i može vam pomoći da donesete odluku o korišćenju rezultata sačuvanih u izlaznom entitetu. Rezultati se određuju na osnovu sledećih pravila:
         
         - **A.** Kada je model tačno predvideo najmanje 50% ukupnih predviđanja i kada je procenat tačnih predviđanja za klijente koji su izgubljeni veći od osnovne stope za najmanje 10%.
            
         - **B.** Kada je model tačno predvideo najmanje 50% ukupnih predviđanja i kada je procenat tačnih predviđanja za klijente koji su izgubljeni veći od osnovne stope za najviše 10%.
            
         - **V.** Kada je model tačno predvideo manje 50% ukupnih predviđanja ili kada je procenat tačnih predviđanja za klijente koji su izgubljeni manji od osnovne stope.
               
         - **Osnovna linija** uzima unos vremenskog perioda predviđanja za model (na primer, godinu dana) i model stvara različite delove vremena deleći ga sa 2 dok ne dostigne mesec dana ili manje. Koristi ove delove za stvaranje poslovnog pravila za klijente koji nisu kupili ništa u ovom vremenskom okviru. Ovi klijenti se smatraju izgubljenim. Poslovno pravilo zasnovano na vremenu sa najvišom sposobnošću predviđanja ko će verovatno biti izgubljen uzima se kao osnovna linija.
            
    1. **Verovatnoća gubitka (broj klijenata):** Grupe klijenata na osnovu predviđenog rizika od gubitka. Ovi podaci mogu vam kasnije pomoći ako želite da kreirate segment klijenata sa visokim rizikom gubitka. Takvi segmenti vam pomažu da razumete gde treba da bude prekid članstva u segmentu.
       
    1. **Najuticajniji faktori:** Mnogo je faktora koji se uzimaju u obzir pri kreiranju predviđanja. Svaki od faktora ima svoj značaj izračunat za agregirana predviđanja koja model kreira. Možete koristiti ove faktore da biste potvrdili rezultate predviđanja. Ili ove podatke možete kasnije koristiti za [kreiranje segmenata](segments.md), što bi moglo da vam pomogne da utičete na rizik od gubitka klijenata.

## <a name="troubleshoot-a-failed-prediction"></a>Rešite problem sa neuspelim predviđanjem

1. Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.

1. Izaberite vertikalne tri tačke pored predviđanja za koji želite da pregledate evidencije grešaka.

1. Izaberite **Evidencije**.

1. Pregledajte sve greške. Može se pojaviti nekoliko vrsta grešaka i one opisuju uslov koji je doveo do greške. Na primer, greška da nema dovoljno podataka za tačno predviđanje obično se rešava učitavanjem dodatnih podataka u Customer Insights.

## <a name="refresh-a-prediction"></a>Osvežavanje predviđanja

Predviđanja se automatski osvežavaju prema istom [rasporedu za osvežavanje podataka](system.md#schedule-tab), kao što je konfigurisano u podešavanjima. Možete ih osvežiti i ručno.

1. Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.

1. Odaberite uspravne tri tačke pored predviđanja koje želite da osvežite.

1. Izaberite **Osveži**.

## <a name="delete-a-prediction"></a>Brisanje predviđanja

Brisanjem predviđanja uklanja se i njegov izlazni entitet.

1. Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.

1. Odaberite uspravne tri tačke pored predviđanja koje želite da izbrišete.

1. Izaberite **Izbriši**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]