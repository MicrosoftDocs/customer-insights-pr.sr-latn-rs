---
title: Pretplata churn predviđanje (sadrži video)
description: Predvidite da li je klijent ugrožen zbog toga što više ne koristi proizvode ili usluge vašeg preduzeća sa pretplatom.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 415cd5d675512b4f434998afaa8265c8e45c562b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643816"
---
# <a name="subscription-churn-prediction"></a>Predviđanje odliva pretplate

Predviđanje gubitka pretplata vam pomaže da predvidite da li je klijent ugrožen zbog toga što više ne koristi proizvode ili usluge vašeg preduzeća sa pretplatom. Možete da kreirate novo predviđanje gubitka pretplata na stranici **Obaveštavanje** > **Predviđanja**. Izaberite **Moja predviđanja** da vidite druga predviđanja koja ste kreirali.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Isprobajte vodič za predviđanje gubitka pretplata koristeći uzorke podataka: [Primer vodiča za predviđanje gubitka pretplata](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Preduslovi

- Barem [Dozvole saradnika](permissions.md).
- Poslovni uvidi da biste razumeli šta znači gubitak za vaše preduzeće. Podržavamo definicije gubitaka zasnovane na vremenu, što znači da se smatra da je klijent izgubljen neko vreme nakon završetka pretplate.
- Podaci o pretplatama i njihovoj istoriji:
    - Identifikatori pretplate za razlikovanje pretplata.
    - Identifikatori klijenata za podudaranje pretplata i klijenata.
    - Datumi događaja pretplate koji definišu datume početka, datume završetka i datume kada je došlo do događaja pretplate.
    - Informacije o pretplati kako bi se definisalo da li se ponavlja i koliko često se obnavlja.
    - Šema semantičkih podataka za pretplate zahteva sledeće informacije:
        - **ID pretplate:** Jedinstveni identifikator pretplate.
        - **Datum završetka pretplate:** Datum isteka pretplate za klijenta.
        - **Datum početka pretplate:** Datum početka pretplate za klijenta.
        - **Datum transakcije:** Datum kada se dogodila promena pretplate. Na primer, klijent kupuje ili otkazuje pretplatu.
        - **Da li se radi o pretplati koja se ponavlja:** Polje za Bulovu vrednost true/false (tačno/netačno) koje određuje da li će se pretplata obnavljati sa istim ID-om pretplate bez intervencije klijenta
        - **Učestalost ponavljanja (u mesecima):** Za ponavljajuće pretplate, to je period na koji se pretplata obnavlja. Predstavlja se u mesecima. Na primer, godišnja pretplata koja se automatski obnavlja kod klijenta svake godine na još godinu dana ima vrednost 12.
        - (Opcionalno) **Iznos pretplate:** Iznos valute koji klijent plaća za obnavljanje pretplate. Može vam pomoći da identifikujete obrasce za različite nivoe pretplate.
- Podaci o aktivnostima klijenata:
    - Identifikatori aktivnosti za razlikovanje aktivnosti iste vrste.
    - Identifikatori klijenata za mapiranje aktivnosti na klijente.
    - Informacije o aktivnostima koje sadrže ime i datum aktivnosti.
    - Šema semantičkih podataka za aktivnosti klijenata uključuje:
        - **Primarni ključ:** Jedinstveni identifikator aktivnosti. Na primjer, poseta veb-lokaciji ili evidencija o upotrebi koja prikazuje da je klijent odgledao epizodu TV emisije.
        - **Vremenska oznaka:** Datum i vreme događaja koje identifikuje primarni ključ.
        - **Događaj:** Naziv događaja koji želite da koristite. Na primer, polje pod nazivom „UserAction“ u striming video usluzi može imati vrednost „Pregledano“.
        - **Detalji:** Detaljne informacije o događaju. Na primer, polje pod nazivom „ShowTitle“ u striming video usluzi može imati vrednost video zapisa koji je klijent odgledao.
- Predložene karakteristike podataka:
    - Dovoljno istorijskih podataka: Podaci o pretplatama za najmanje udvostručeni izabrani vremenski period. Poželjno je dve do tri godine podataka o pretplati.
    - Status pretplate: Podaci uključuju aktivne i neaktivne pretplate za svakog klijenta, tako da postoji više stavki po ID-u klijenta.
    - Broj klijenata: Najmanje 10 profila klijenata, po mogućnosti više od 1.000 jedinstvenih klijenata. Model neće uspeti sa manje od 10 klijenata i nedovoljnom količinom istorijskih podataka.
    - Kompletnost podataka: Manje od 20% vrednosti koje nedostaju u polju podataka datog entiteta.
   
   > [!NOTE]
   > Trebaće vam najmanje dva zapisa aktivnosti za 50% klijenata za koje želite da izračunate odliv.

## <a name="create-a-subscription-churn-prediction"></a>Kreiranje predviđanja gubitka pretplata

1. Idite na **obaveštajne** > **podatke**.
1. Izaberite pločicu **modela "Pretplata"** i izaberite stavku **Koristi ovaj model**.
   > [!div class="mx-imgBorder"]
   > ![Pločica „Model gubitka pretplate“ sa dugmetom „Koristi ovaj model“.](media/subscription-churn-usethismodel.PNG "Pločica „Model gubitka pretplate“ sa dugmetom „Koristi ovaj model“")

### <a name="name-model"></a>Davanje naziva modela

1. Navedite naziv modela da biste ga razlikovali od ostalih modela.
1. Navedite ime izlaznog entiteta koje sadrži samo slova i brojeve, bez razmaka. To je naziv koji će entitet modela koristiti. Zatim izaberite **Sledeće**.

### <a name="define-customer-churn"></a>Definisanje rizika od gubitka klijenta

1. Unesite broj za **Dani od završetka pretplate** i to je period za koji preduzeće smatra da je status klijenta Izgubljen. Ovaj period je obično povezan sa poslovnim aktivnostima poput ponuda ili drugih marketinških napora kojima pokušavate da sprečite gubitak klijenta.
1. Unesite broj **Dani za istraživanje budućnosti za predviđanje odliva** da biste podesili prozor za predviđanje odliva. Na primer, da biste predvideli rizik od odliva klijenata tokom narednih 90 dana kako biste se prilagodili vašim naporima da zadržite marketing. Predviđanje rizika odliva na duži ili kraći vremenski period može otežati adresiranje faktora u vašem profilu rizika od gubitka klijenta, u zavisnosti od vaših specifičnih poslovnih zahteva. Izaberite **Dalje** za nastavak
   >[!TIP]
   > U svakom trenutku možete **da izaberete** opciju "Sačuvaj radnu verziju" da biste sačuvali predviđanje kao radnu verziju. Da biste nastavili, radnu verziju predviđanja možete da pronađete na kartici **Moja predviđanja**.

### <a name="add-required-data"></a>Dodavanje obaveznih podataka

1. Izaberite **Dodaj podatke** za **Istorija pretplate** i odaberite entitet koji pruža informacije o istoriji pretplate kao što je definisano u [preduslovima](#prerequisites).
1. Ako polja ispod nisu popunjena, konfigurišite odnos između entiteta istorije pretplate i entiteta klijenta.
    1. Izaberite **Entitet istorije pretplate**.
    1. Izaberite **Polje** koji identifikuje klijenta u entitetu istorije pretplate. Mora da se odnosi na primarni ID klijenta entiteta „Klijent“.
    1. Izaberite **Entitet klijenta** koji odgovara primarnom entitetu klijenta.
    1. Unesite ime koje opisuje odnos.
       > [!div class="mx-imgBorder"]
       > ![Stranica sa istorijom pretplate na kojoj je prikazano kreiranje odnosa sa klijentom.](media/subscription-churn-subscriptionhistoryrelationship.PNG "Stranica sa istorijom pretplate na kojoj je prikazano kreiranje odnosa sa klijentom")
1. Izaberite **Sledeće**.
1. Mapirajte semantička polja na atribute unutar entiteta istorije pretplate i izaberite **Sačuvaj**. Za opis polja pogledajte [preduslove](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Stranica sa istorijom pretplate na kojoj su prikazani semantički atributi koji su mapirani na polja u izabranom entitetu istorije pretplate.](media/subscription-churn-subscriptionhistorymapping.PNG "Stranica sa istorijom pretplate na kojoj su prikazani semantički atributi koji su mapirani na polja u izabranom entitetu istorije pretplate")
1. Izaberite **Dodaj podatke** za **Aktivnosti klijenta** i odaberite entitet koji pruža informacije o aktivnostima klijenta kao što je definisano u preduslovima.
1. Odaberite vrstu aktivnosti koja odgovara vrsti aktivnosti klijenta koju konfigurišete.  Izaberite **Kreiraj novu** i navedite ime ako ne vidite opciju koja odgovara vrsti aktivnosti koja vam je potrebna.
1. Treba da konfigurišete odnos između entiteta aktivnosti klijenta i entiteta klijenta.
    1. Izaberite polje koje identifikuje klijenta u tabeli sa aktivnostima klijenta, koji može da bude direktno povezan sa primarnim ID-om klijenta entiteta „Klijent“.
    1. Izaberite Entitet klijenta koji odgovara primarnom entitetu klijenta
    1. Unesite ime koje opisuje odnos.
1. Izaberite **Sledeće**.
1. Mapirajte semantička polja na atribute unutar entiteta aktivnosti klijenta i izaberite **Sačuvaj**. Za opis polja pogledajte [preduslove](#prerequisites).
1. (Opcionalno) Ako imate bilo koje druge aktivnosti klijenta koje želite da uključite, ponovite gorenavedene korake.
   > [!div class="mx-imgBorder"]
   > ![Definisanje relacije između entiteta.](media/subscription-churn-customeractivitiesmapping.PNG "Stranica sa aktivnostima klijenta na kojoj su prikazani semantički atributi koji su mapirani na polja u izabranom entitetu aktivnosti klijenta")
1. Izaberite **Sledeće**.

### <a name="set-schedule-and-review-configuration"></a>Podesite raspored i pregledajte konfiguraciju

1. Podesite učestalost kako biste ponovo obučili model. Ova postavka je važna za ažuriranje tačnosti predviđanja jer se novi podaci unose u uvide klijenata. Većina preduzeća može da obavi ponovnu obuku jednom mesečno i dobije precizna predviđanja.
1. Izaberite **Sledeće**.
1. Pregledajte konfiguraciju. Možete se vratiti na bilo koji deo konfiguracije predviđanja ako izaberete **Uredi** ispod prikazane vrednosti. Ili možete da odaberete korak konfiguracije iz indikatora napretka.
1. Ako su sve vrednosti pravilno konfigurisane, izaberite **Sačuvaj i pokreni** da biste započeli proces predviđanja. Na kartici **Moja predviđanja** možete videti status predviđanja. Za završetak procesa može biti potrebno nekoliko sati, u zavisnosti od količine podataka korišćenih u predviđanju.

## <a name="review-a-prediction-status-and-results"></a>Pregled statusa i rezultata predviđanja

1. Idite na karticu **Moja predviđanja** u delu **Obaveštavanje** > **Predviđanja**.
   > [!div class="mx-imgBorder"]
   > ![Pregled stranice Moja predviđanja.](media/subscription-churn-mypredictions.PNG "Pregled stranice Moja predviđanja")
1. Izaberite predviđanje koje želite da pregledate.
   - **Naziv predviđanja:** Naziv predviđanja koji ste naveli prilikom njegovog kreiranja.
   - **Vrsta predviđanja:** Tip modela koji se koristi za predviđanje
   - **Izlazni entitet:** Naziv entiteta za skladištenje izlaza predviđanja. Možete pronaći entitet sa ovim imenom u delu **Podaci** > **Entiteti**.    
     U izlaznom entitetu, *ChurnScore* je predviđena verovatnoća gubitka klijenta a *IsChurn* je binarna oznaka zasnovana na graničnoj vrednosti parametra *ChurnScore* od 0,5. Podrazumevana granična vrednost možda neće raditi za vaš scenario. [Napravite novi segment](segments.md#create-a-new-segment) sa željenom graničnom vrednošću.
   - **Predviđeno polje:** Ovo polje se popunjava samo za neke vrste predviđanja i ne koristi se u predviđanju gubitka pretplata.
   - **Status:** Trenutni status pokretanja predviđanja.
        - **U redu:** Predviđanje trenutno čeka da se pokrenu i drugi procesi.
        - **Osvežavanje:** Predviđanje je trenutno u fazi ocenjivanja obrade da bi se dobili rezultati koji će se preneti u izlazni entitet.
        - **Nije uspelo:** Predviđanje nije uspelo. Izaberite **Evidencije** za više detalja.
        - **Uspešno:** Predviđanje je uspelo. Izaberite **Pregled** u okviru uspravne tri tačke da biste pregledali predviđanje
   - **Izmenjeno:** Datum promene konfiguracije predviđanja.
   - **Poslednje osvežavanje:** Datum kada je predviđanje osvežilo rezultate u izlaznom entitetu.
1. Odaberite uspravne tri tačke pored predviđanja za koje želite da pregledate rezultate i izaberite **Pregled**.
   > [!div class="mx-imgBorder"]
   > ![Prikaz opcija u meniju sa uspravne tri tačke za predviđanje koje obuhvataju uređivanje, osvežavanje, pregled, evidenciju i brisanje.](media/subscription-churn-verticalellipses.PNG "Prikaz opcija u meniju sa uspravne tri tačke za predviđanje koje obuhvataju uređivanje, osvežavanje, pregled, evidenciju i brisanje")
1. Postoje tri primarna odeljka podataka na stranici sa rezultatima:
    1. **Performanse modela obuke:** A, B ili C su mogući rezultati. Ovaj rezultat pokazuje performanse predviđanja i može vam pomoći da donesete odluku o korišćenju rezultata sačuvanih u izlaznom entitetu.
        - Rezultati se određuju na osnovu sledećih pravila:
            - **A** kada je model tačno predvideo najmanje 50% ukupnih predviđanja, a kada je procenat tačnih predviđanja za klijente koji su otišli na drugo mesto veći od proseka odliva na osnovu istorije za najmanje 10% proseka odliva na osnovu istorije.
            - **B** kada je model tačno predvideo najmanje 50% ukupnih predviđanja, a kada je procenat tačnih predviđanja za klijente koji su otišli na drugo mesto veći do 10% proseka odliva na osnovu istorije od proseka odliva na osnovu istorije.
            - **C** kada je model tačno predvideo manje od 50% ukupnih predviđanja ili kada je procenat tačnih predviđanja za kupce koji su otišli na drugo mesto manji od proseka odliva na osnovu istorije.
               > [!div class="mx-imgBorder"]
               > ![Pregled rezultata performansi modela.](media/subscription-churn-modelperformance.PNG "Pregled rezultata performansi modela")
    1. **Verovatnoća gubitka (broj klijenata):** Grupe klijenata na osnovu predviđenog rizika od gubitka. Ovi podaci mogu vam kasnije pomoći ako želite da kreirate segment klijenata sa visokim rizikom gubitka. Takvi segmenti vam pomažu da razumete gde treba da bude prekid članstva u segmentu.
       > [!div class="mx-imgBorder"]
       > ![Grafikon koji prikazuje raspodelu rezultata gubitaka, podeljen u opsege od 0-100%.](media/subscription-churn-resultdistribution.PNG "Grafikon koji prikazuje raspodelu rezultata gubitaka, podeljen u opsege od 0-100%")
    1. **Najuticajniji faktori:** Mnogo je faktora koji se uzimaju u obzir pri kreiranju predviđanja. Svaki od faktora ima svoju važnost koja se izračunava za objedinjena predviđanja koja model kreira. Možete koristiti ove faktore da biste potvrdili rezultate predviđanja. Ili ove podatke možete kasnije koristiti za [kreiranje segmenata](segments.md), što bi moglo da vam pomogne da utičete na rizik od gubitka klijenata.
       > [!div class="mx-imgBorder"]
       > ![Lista koja pokazuje uticajne faktore i njihovu važnost u predviđanju rezultata gubitaka.](media/subscription-churn-influentialfactors.PNG "Lista koja pokazuje uticajne faktore i njihovu važnost u predviđanju rezultata gubitaka")

## <a name="manage-predictions"></a>Upravljanje predviđanjima

Predviđanja je moguće optimizovati, rešavati, osvežiti ili izbrisati. Pregledajte izveštaj o upotrebljivosti ulaznih podataka da biste saznali kako da predviđanje učinite bržim i pouzdanijim. Još informacija potražite u članku [Upravljanje predviđanjima](manage-predictions.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]