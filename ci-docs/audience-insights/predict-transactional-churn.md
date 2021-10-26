---
title: Predviđanje gubitka transakcija
description: Predvidite da li je klijent ugrožen zbog toga što više ne kupuje vaše proizvode ili usluge.
ms.date: 10/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ac484f74e388aa23422a89e25dabb555f2ad4118
ms.sourcegitcommit: 1565f4f7b4e131ede6ae089c5d21a79b02bba645
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643428"
---
# <a name="transaction-churn-prediction-preview"></a>Predviđanje gubitka transakcija (verzija za pregled)

Predviđanje gubitka transakcija pomaže u predviđanju da li klijent više neće kupovati vaše proizvode ili usluge u datom vremenskom periodu. Možete da kreirate nova predviđanja gubitka u odeljku **Obaveštavanje** > **Predviđanja**. Izaberite **Moja predviđanja** da vidite druga predviđanja koja ste kreirali. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Za okruženja zasnovana na poslovnim kontaktima, možemo predvideti transakcioni gubitak za poslovni nalog, a takođe i poslovnog naloga i drugog nivoa informacija, poput kategorije proizvoda. Dodavanjem dimenzije možete saznati koliko je verovatno da će poslovni kontakt „Contoso“ prestati da kupuje kategoriju proizvoda „kancelarijski materijal“. Osim toga, za poslovne naloge, možemo koristiti i veštačku inteligenciju za generisanje liste potencijalnih razloga zbog kojih će poslovni kontakt verovatno otići zbog kategorije informacija sekundarnog nivoa.

> [!TIP]
> Isprobajte vodič za predviđanje gubitka transakcija koristeći uzorke podataka: [Vodič sa uzorcima za predviđanje gubitka transakcija (verzija za pregled)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Preduslovi

- Barem [dozvole saradnika](permissions.md) u usluzi Customer Insights.
- Poslovni uvidi da biste razumeli šta znači gubitak za vaše preduzeće. Podržavamo definicije gubitka zasnovane na vremenu, što znači da se smatra da je klijent izgubljen nakon perioda bez kupovine.
- Podaci o vašim transakcijama/kupovinama i njihova istorija:
    - Identifikatori transakcija za razlikovanje kupovina/transakcija.
    - Identifikatori klijenata za podudaranje transakcija sa klijentima.
    - Datumi transakcija, koji definišu datume kada se transakcija dogodila.
    - Šema semantičkih podataka za kupovine/transakcije zahteva sledeće informacije:
        - **ID transakcije**: Jedinstveni identifikator kupovine ili transakcije.
        - **Datum transakcije**: Datum kupovine ili transakcije.
        - **Vrednost transakcije**: Iznos valute/numerička vrednost transakcije/stavke.
        - (Opciono) **Jedinstveni ID proizvoda**: ID proizvoda ili usluge kupljene ako su vaši podaci na nivou stavke porudžbine.
        - (Opciono) **Da li je ova transakcija bila povraćaj**: Polje sa vrednošću „tačno/netačno“ koje identifikuje da li je transakcija bila povraćaj ili ne. Ako je **Vrednost transakcije** negativna, koristićemo i ove podatke za zaključivanje da je u pitanju povraćaj.
- (Opcionalno) Podaci o aktivnostima klijenata:
    - Identifikatori aktivnosti za razlikovanje aktivnosti iste vrste.
    - Identifikatori klijenata za mapiranje aktivnosti na klijente.
    - Informacije o aktivnostima koje sadrže ime i datum aktivnosti.
    - Šema semantičkih podataka za aktivnosti klijenata uključuje:
        - **Primarni ključ:** Jedinstveni identifikator aktivnosti. Na primer, poseta veb lokaciji ili evidencija upotrebe koja pokazuje da je klijent isprobao uzorak vašeg proizvoda.
        - **Vremenska oznaka:** Datum i vreme događaja koje identifikuje primarni ključ.
        - **Događaj:** Naziv događaja koji želite da koristite. Na primer, polje pod nazivom „Radnja korisnika“ u prehrambenoj prodavnici može biti kupon koji klijent koristi.
        - **Detalji:** Detaljne informacije o događaju. Na primer, polje pod nazivom „Vrednost kupona“ u prehrambenoj prodavnici može biti vrednost valute kupona.
- (Opcionalno) Podaci o vašim klijentima:
    - Ovi podaci bi trebalo da budu usklađeni sa statičkijim atributima kako bi se osiguralo da model najbolje funkcioniše.
    - Šema semantičkih podataka za podatke o klijentima uključuje:
        - **CustomerID:** Jedinstveni identifikator klijenta.
        - **Datum kreiranja:** Datum kada je klijent prvobitno dodat.
        - **Država ili provincija:** Država ili provincija lokacije klijenta.
        - **Zemlja:** Zemlja klijenta.
        - **Delatnost:** Tip delatnosti klijenta. Na primer, polje pod nazivom „Delatnost“ u pržionici kafe može ukazivati da li je klijent bio maloprodajni.
        - **Klasifikacija:** Kategorizacija klijenta za vaše poslovanje. Na primer, polje pod nazivom „ValueSegment“ u pržionici za kafu može biti nivo klijenta na osnovu veličine klijenta.
- Predložene karakteristike podataka:
    - Dovoljno istorijskih podataka: Podaci o transakcijama za najmanje udvostručeni izabrani vremenski period. Poželjno je dve do tri godine istorije transakcija. 
    - Više kupovina po klijentu: Idealno najmanje dve transakcije po klijentu.
    - Broj klijenata: Najmanje 10 profila klijenata, po mogućnosti više od 1.000 jedinstvenih klijenata. Model neće uspeti sa manje od 10 klijenata i nedovoljnom količinom istorijskih podataka.
    - Kompletnost podataka: Manje od 20% vrednosti koje nedostaju u polju podataka datog entiteta.

> [!NOTE]
> Za preduzeća sa velikom učestalošću kupovine kupaca (svakih nekoliko nedelja) preporučuje se odabir kraćeg perioda predviđanja i definicija gubitka klijenta. Za nisku učestalost kupovine (svakih nekoliko meseci ili jednom godišnje), odaberite duži period predviđanja i definiciju gubitka klijenta.

## <a name="create-a-transaction-churn-prediction"></a>Kreiranje predviđanja gubitka transakcija

1. U usluzi Customer Insights, idite na **Obaveštavanje** > **Predviđanja**.

1. Izaberite pločicu **Model gubitka klijenata (verzija za pregled)** i **Koristi ovaj model**.

1. U oknu **Model gubitka klijenata**, odaberite **Transakcija** i izaberite **Započnite**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Snimak ekrana sa izabranom opcijom transakcije u oknu modela gubitka klijenata.":::

### <a name="name-model"></a>Davanje naziva modela

1. Navedite naziv modela da biste ga razlikovali od ostalih modela.

1. Navedite ime izlaznog entiteta koje sadrži samo slova i brojeve, bez razmaka. To je naziv koji će entitet modela koristiti. 

1. Izaberite **Sledeće**.

### <a name="define-customer-churn"></a>Definisanje gubitka klijenata

1. Postavite vremenski period u danima za predviđanje gubitaka u polju **Utvrdite koje ćete klijente možda izgubiti u sledećem**. Na primer, predvidite rizik od gubitka klijenata tokom sledećih 90 dana kako biste se uskladili sa vašim marketinškim naporima za zadržavanje. Predviđanje rizika od gubitka na duži ili kraći vremenski period može otežati reagovanje na faktore na vašem profilu rizika od gubitka, ali to zavisi od vaših specifičnih poslovnih zahteva.
   >[!TIP]
   > Možete da izaberete **Sačuvaj i zatvori** u bilo kom trenutku da biste sačuvali predviđanje kao radnu verziju. Da biste nastavili, radnu verziju predviđanja možete da pronađete na kartici **Moja predviđanja**.

1. Unesite broj dana za definisanje gubitka u polje **Klijent je izgubljen ako nije obavio nijednu kupovinu u:**. Na primer, ako klijent nije obavio nijednu kupovinu u poslednjih 30 dana, moglo bi se smatrati da je izgubljen za vaše preduzeće. 

1. Izaberite **Dalje** za nastavak.

### <a name="add-required-data"></a>Dodavanje obaveznih podataka

1. Izaberite **Dodaj podatke** i odaberite vrstu aktivnosti u bočnom oknu koja sadrži potrebne podatke o transakcijama ili istoriji kupovine.

1. U okviru **Odaberite aktivnosti**, odaberite određene aktivnosti iz izabrane aktivnosti na koju želite da se obračun fokusira.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Bočno okno prikazuje odabir određenih aktivnosti prema semantičkom tipu.":::

1. Ako još niste mapirali aktivnost u semantički tip, izaberite **Uredi** da biste to uradili. Otvara se vođeno iskustvo za mapiranje semantičkih aktivnosti. Mapirajte podatke u odgovarajuća polja u izabranom tipu aktivnosti.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Tip aktivnosti podešavanja stranice.":::

1. Nakon mapiranja aktivnosti na odgovarajući semantički tip, izaberite **Sledeći** za nastavak

1. Mapirajte semantičke atribute u polja koja su potrebna za pokretanje modela. Ako polja u nastavku nisu popunjena, konfigurišite odnos između entiteta istorije kupovine i entiteta *Klijent*.

1. Izaberite **Sledeće**.

### <a name="select-prediction-level"></a>Izbor nivoa predviđanja

Većina predviđanja se kreiraju na nivou klijenta. U nekim situacijama to možda nije dovoljno detaljno da odgovori na vaše poslovne potrebe. Ovu funkciju možete koristiti za predviđanje gubitka za granu klijenta, na primer, umesto za klijenta u celini.

1. Da biste kreirali predviđanje na detaljnijem nivou od klijenta, izaberite **Izaberite entitet za sekundarni nivo**. Ako opcija nije dostupna, uverite se da ste dovršili prethodni odeljak.

1. Proširite entitete iz kojih želite da izaberete sekundarni nivo ili koristite okvir za filtriranje pretrage da biste filtrirali izabrane opcije.

1. Odaberite atribut koji želite koristiti kao sekundarni nivo, a zatim izaberite **Dodaj**

1. Izaberite **Sledeće**

> [!NOTE]
> Entiteti dostupni u ovom odeljku prikazani su jer imaju odnos sa entitetom koji ste izabrali u prethodnom odeljku. Ako ne vidite entitet koji želite da dodate, uverite se da u **Odnosima** ima prisutan važeći odnos. Za ovu konfiguraciju važe samo odnosi jedan-prema-jedan i više-prema-jedan.

### <a name="add-additional-data-optional"></a>Dodavanje dodatnih podataka (opcionalno)

Konfigurišite relaciju između vašeg entiteta aktivnosti klijenta i entiteta *Klijent*.

1. Izaberite polje koje identifikuje klijenta na tabeli aktivnosti klijenata. Može biti direktno povezano sa primarnim ID-om klijenta entiteta *Klijent*.

1. Izaberite entitet koji vam je primarni entitet *Klijent*.

1. Unesite ime koje opisuje odnos.

#### <a name="customer-activities"></a>Aktivnosti klijenta

1. Po želji odaberite **Dodajte podatke** za **Aktivnosti klijenata**.

1. Izaberite tip semantičke aktivnosti koja sadrži podatke koje želite koristiti, a zatim izaberite jednu ili više aktivnosti u odeljku **Aktivnosti**.

1. Odaberite vrstu aktivnosti koja odgovara vrsti aktivnosti klijenta koju konfigurišete. Izaberite **Kreiraj novo** i odaberite dostupni tip aktivnosti ili kreirajte novi.

1. Izaberite **Sledeće**, a zatim **Sačuvaj**.

1. Ako imate druge aktivnosti klijenata koje biste želeli da uključite, ponovite gornje korake.

#### <a name="customers-data"></a>Podaci o klijentima

1. Opciono, izaberite **Dodaj podatke** za **Podaci o klijentima**.

1. Mapirajte semantičke atribute na polja u vašim podacima o klijentima kako je identifikovano. Podaci u korišćenim poljima ne bi trebalo da se često menjaju kako biste osigurali najbolje performanse modela. Na primer, izborom polja za „Klasifikaciju“ koje se menja svakog meseca koristila bi se samo poslednja vrednost u predviđaju, iako se istorijski ista vrednost možda ne bi odnosila na klijenta pri pravljenju šablona predviđanja.

1. Izaberite **Sledeće**.

### <a name="provide-an-optional-list-of-benchmark-accounts-business-accounts-only"></a>Navedite opcionu listu referentnih poslovnih naloga (samo poslovni kontakti)

Dodajte listu svojih poslovnih klijenata i poslovnih kontakata koje želite da koristite kao reference. Dobićete [detalje o ovim referentnim poslovnim kontaktima](#review-a-prediction-status-and-results) uključujući njihov rezultat odlaska i najuticajnije karakteristike koje su uticale na njihovo predviđanje odlaska.

1. Izaberite **+Dodaj klijente**.

1. Odaberite klijente koji služe kao referenca.

1. Izaberite **Dalje** za nastavak.

### <a name="set-schedule-and-review-configuration"></a>Podesite raspored i pregledajte konfiguraciju

1. Podesite učestalost kako biste ponovo obučili model. Ovo podešavanje je važno za ažuriranje tačnosti predviđanja kako se unose novi podaci. Većina preduzeća može da obavi ponovnu obuku jednom mesečno i dobije precizna predviđanja.

1. Izaberite **Sledeće**.

1. Pregledajte konfiguraciju predviđanja. Možete se vratiti na prethodne korake ako izaberete **Uredi** ispod prikazane vrednosti. Ili možete da odaberete korak konfiguracije iz indikatora napretka.

1. Ako su sve vrednosti pravilno konfigurisane, izaberite **Sačuvaj i pokreni** da biste započeli proces predviđanja. Na kartici **Moja predviđanja** možete videti status predviđanja. Za završetak procesa može biti potrebno nekoliko sati, u zavisnosti od količine podataka korišćenih u predviđanju.

## <a name="review-a-prediction-status-and-results"></a>Pregled statusa i rezultata predviđanja

1. Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.

1. Izaberite predviđanje koje želite da pregledate.
   - **Naziv predviđanja**: Naziv predviđanja naveden pri njegovom kreiranju.
   - **Tip predviđanja**: Tip modela koji se koristi za predviđanje
   - **Izlazni entitet**: Naziv entiteta za skladištenje izlaza predviđanja. Možete pronaći entitet sa ovim imenom u delu **Podaci** > **Entiteti**.
     U izlaznom entitetu, *ChurnScore* je predviđena verovatnoća gubitka klijenta a *IsChurn* je binarna oznaka zasnovana na graničnoj vrednosti parametra *ChurnScore* od 0,5. Podrazumevana granična vrednost možda neće raditi za vaš scenario. [Napravite novi segment](segments.md#create-a-new-segment) sa željenom graničnom vrednošću.
     Nisu svi klijenti nužno aktivni klijenti. Neki od njih možda već duže vreme nisu imali nikakve aktivnosti i smatraju se već izgubljenim, na osnovu vaše definicije gubitka klijenta. Predviđanje rizika od gubitka za klijente koji su već otišli nije korisno jer nisu interesna ciljna grupa.
   - **Predviđeno polje**: Ovo polje je popunjeno samo za neke tipove predviđanja i ne koristi se za predviđanje gubitka.
   - **Status**: Status pokretanja predviđanja.
        - **U redu**: Predviđanje čeka da se pokrenu drugi procesi.
        - **Osvežavanje**: Predviđanje je trenutno pokrenuto da bi dalo rezultate koji će biti prosleđeni u izlazni entitet.
        - **Nije uspelo**: Pokretanje predviđanja nije uspelo. Detaljnije informacije potražite u [evidenciji](manage-predictions.md#troubleshoot-a-failed-prediction).
        - **Uspelo je**: Predviđanje je uspelo. Izaberite **Pregled** u okviru uspravne tri tačke da biste pregledali predviđanje
   - **Izmenjeno:** Datum promene konfiguracije predviđanja.
   - **Poslednje osvežavanje**: Datum kada je predviđanje osvežilo rezultate u izlaznom entitetu.

1. Odaberite uspravne tri tačke pored predviđanja za koje želite da pregledate rezultate i izaberite **Pregled**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Pogledajte kontrolu da biste videli rezultate predviđanja.":::

1. Postoje tri primarna odeljka podataka na stranici sa rezultatima:
   - **Performanse modela obuke**: A, B ili V su mogući rezultati. Ovaj rezultat pokazuje performanse predviđanja i može vam pomoći da donesete odluku o korišćenju rezultata sačuvanih u izlaznom entitetu. Rezultati se određuju na osnovu sledećih pravila: 
        - **A.** Kada je model tačno predvideo najmanje 50% ukupnih predviđanja i kada je procenat tačnih predviđanja za klijente koji su izgubljeni veći od osnovne stope za najmanje 10%.
            
        - **B.** Kada je model tačno predvideo najmanje 50% ukupnih predviđanja i kada je procenat tačnih predviđanja za klijente koji su izgubljeni veći od osnovne stope za najviše 10%.
            
        - **V.** Kada je model tačno predvideo manje 50% ukupnih predviđanja ili kada je procenat tačnih predviđanja za klijente koji su izgubljeni manji od osnovne stope.
               
        - **Osnovno** uzima unos vremenskog perioda predviđanja za model (na primer, godinu dana) i model stvara različite delove vremena deleći ga sa 2 dok ne dostigne mesec dana ili manje. Koristi ove delove za stvaranje poslovnog pravila za klijente koji nisu kupili ništa u ovom vremenskom okviru. Ovi klijenti se smatraju izgubljenim. Poslovno pravilo zasnovano na vremenu sa najvišom sposobnošću predviđanja ko će verovatno biti izgubljen uzima se kao osnovna linija.
            
    - **Verovatnoća gubitka (broj klijenata)**: Grupe klijenata na osnovu predviđenog rizika od gubitka. Ovi podaci mogu vam kasnije pomoći ako želite da kreirate segment klijenata sa visokim rizikom gubitka. Takvi segmenti vam pomažu da razumete gde treba da bude prekid članstva u segmentu.
       
    - **Najuticajniji faktori**: Mnogo je faktora koji se uzimaju u obzir pri kreiranju predviđanja. Svaki od faktora ima svoj značaj izračunat za agregirana predviđanja koja model kreira. Pomoću ovih faktora možete potvrditi rezultate predviđanja ili ove informacije kasnije možete koristiti za [kreiranje segmenata](segments.md) koji bi mogli da utiču na rizik od gubitka za klijente.


1. Za poslovne naloge, pronaći ćete stranicu sa informacijama **Analiza uticajnih funkcija**. Sadrži četiri odeljka sa podacima:

    - Stavka izabrana u desnom oknu određuje sadržaj ove stranice. Izaberite stavku iz **Glavni klijenti** ili **Referentni klijenti**. Obe liste su poređane prema opadajućoj vrednosti ocene gubitka, bilo da je ocena samo za klijenta ili kombinovana ocena za klijente i sekundarni nivo poput kategorije proizvoda.
        
        - **Glavni klijenti**: Spisak 10 klijenata koji imaju najveći rizik od gubitka i najmanji rizik od gubitka na osnovu njihovih rezultata za gubitak. 
        - **Referentni klijenti**: Lista do 10 klijenata koji su izabrani prilikom konfigurisanja modela.
 
    - **Rezultat gubitka**: Prikazuje rezultat gubitka za izabranu stavku u desnom oknu.
    
    - **Distribucija rizika od gubitka:** Prikazuje raspodelu rizika od gubitka po klijentima i percentil u kom se izabrani klijent nalazi. 
    
    - **Glavne karakteristike koje povećavaju i smanjuju rizik od gubitka:** Za izabranu stavku u desnom oknu, navedenih je glavnih pet karakteristika koje su povećale i smanjile rizik od gubitka. Za svaku uticajnu karakteristiku pronaći ćete vrednost karakteristike za tu stavku i njen uticaj na rezultat gubitka. Prikazana je i prosečna vrednost svake funkcije u segmentima klijenata sa niskim, srednjim i visokim gubitkom. Pomaže u boljoj kontekstualizaciji vrednosti najuticajnijih karakteristika za izabranu stavku i upoređivanju sa segmentima klijenata sa niskim, srednjim i visokim gubitkom.

       - Nisko: poslovni kontakti ili kombinacije poslovnog kontakta i sekundarnog nivoa sa ocenom gubitka između 0 i 0,33
       - Srednje: poslovni kontakti ili kombinacije poslovnih kontakata i sekundarnih nivoa sa ocenom gubitka između 0,33 i 0,66
       - Visoko: poslovni kontakti ili kombinacije poslovnih kontakata i sekundarnih nivoa sa ocenom gubitka većom od 0,66
    
       Kada predviđate gubitak na nivou poslovnog kontakta, svi poslovni kontakti se uzimaju u obzir pri izvođenju prosečnih vrednosti karakteristika za segmente gubitka. Za predviđanja gubitka na sekundarnom nivou za svaki poslovni kontakt, izvođenje segmenata gubitka zavisi od sekundarnog nivoa stavke izabrane u bočnom oknu. Na primer, ako stavka ima sekundarni nivo kategorije proizvoda = kancelarijski materijal, onda se samo artikli koji imaju kancelarijski materijal kao kategoriju proizvoda uzimaju u obzir pri izvlačenju prosečnih vrednosti karakteristika za segmente gubitka. Ova logika se primenjuje kako bi se obezbedilo fer poređenje vrednosti karakteristika stavke sa prosečnim vrednostima u segmentima sa niskim, srednjim i visokim gubitkom.

       U nekim slučajevima, prosečna vrednost segmenata niske, srednje ili visoke stope gubitka je prazna ili nije dostupna jer ne postoje stavke koje pripadaju odgovarajućim segmentima gubitka na osnovu gornje definicije.

## <a name="manage-predictions"></a>Upravljanje predviđanjima

Predviđanja je moguće optimizovati, rešavati, osvežiti ili izbrisati. Pregledajte izveštaj o upotrebljivosti ulaznih podataka da biste saznali kako da predviđanje učinite bržim i pouzdanijim. Više informacija potražite u [upravljanju predviđanjima](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
