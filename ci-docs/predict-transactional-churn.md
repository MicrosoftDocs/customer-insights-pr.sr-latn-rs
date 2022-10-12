---
title: Transaction churn predviđanje (sadrži video)
description: Predvidite da li je klijent ugrožen zbog toga što više ne kupuje vaše proizvode ili usluge.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610529"
---
# <a name="predict-transaction-churn"></a>Predviđanje gubitka transakcija

Predviđanje gubitka transakcija pomaže u predviđanju da li klijent više neće kupovati vaše proizvode ili usluge u datom vremenskom periodu.

Morate imati poslovno znanje da biste razumeli šta churn znači za vaš posao. Podržavamo definicije gubitka zasnovane na vremenu, što znači da se smatra da je klijent izgubljen nakon perioda bez kupovine.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Za okruženja zasnovana na poslovnim kontaktima, možemo predvideti transakcioni gubitak za poslovni nalog, a takođe i poslovnog naloga i drugog nivoa informacija, poput kategorije proizvoda. Na primer, dodavanje dimenzije može pomoći da se utvrdi koliko je verovatno da će nalog "Contoso" prestati da kupuje kategoriju proizvoda "kancelarijska podloga za pisanje". Osim toga, za poslovne naloge, možemo koristiti i veštačku inteligenciju za generisanje liste potencijalnih razloga zbog kojih će poslovni kontakt verovatno otići zbog kategorije informacija sekundarnog nivoa.

> [!TIP]
> Isprobajte churn transakciju predviđanje probnih podataka: [Transaction churn predviđanje uzorak vodiča](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Preduslovi

- Barem [Dozvole saradnika](permissions.md).
- Najmanje 10 profila kupaca, po mogućstvu više od 1.000 jedinstvenih kupaca.
- Identifikator kupca, jedinstveni identifikator koji odgovara transakcijama sa kupcima.
- Podaci o transakcijama za najmanje dvostruko više od izabranog vremenskog prozora, kao što je dve do tri godine istorije transakcija. Idealno najmanje dve transakcije po kupcu. Istorija transakcija mora da sadrži:
  - **ID transakcije**: Jedinstveni identifikator nabavke ili transakcije.
  - **Datum transakcije**: Datum nabavke ili transakcije.
  - **Vrednost transakcije**: Iznos valute ili numeričke vrednosti transakcije.
  - **Jedinstveni ID proizvoda**: ID proizvoda ili usluge kupljene ako su podaci na nivou stavke predmeta.
  - **Da li je ova transakcija bila** povraćaj: polje tačno/netačno koje identifikuje da li je transakcija bila povraćaj ili ne. Ako je **vrednost transakcije negativna**, nalaћemo povraćaj.
- Podaci o aktivnostima klijenta:
  - Identifikator kupca, jedinstveni identifikator za mapiranje aktivnosti kupcima.
  - **Primarni ključ:** Jedinstveni identifikator za aktivnost. Na primer, poseta veb lokaciji ili evidencija upotrebe koja pokazuje da je klijent isprobao uzorak vašeg proizvoda.
  - **Vremenska osa:** Datum i vreme događaja identifikovani primarnim ključem.
  - **Događaj:** Ime događaja koji želite da koristite. Na primer, polje pod nazivom „Radnja korisnika“ u prehrambenoj prodavnici može biti kupon koji klijent koristi.
  - **Detalji:** Detaljne informacije o događaju. Na primer, polje pod nazivom „Vrednost kupona“ u prehrambenoj prodavnici može biti vrednost valute kupona.
- Manje od 20% vrednosti koje nedostaju u polju podataka entiteta

Za poslovne naloge (B-na-B), dodajte podatke klijenata poravnate prema statičnijim atributima da biste se uverili da model ima najbolje rezultate:
- **ID kupca:** Jedinstveni identifikator za kupca.
- **Datum kreiranja:** Datum kada je kupac prvobitno dodat.
- **Država ili pokrajina:** lokacija državne ili pokrajine kupca.
- **Zemlja:** Zemlja mušterija.
- **Industrija:** Tip delatnosti kupca. Na primer, polje pod nazivom „Delatnost“ u pržionici kafe može ukazivati da li je klijent bio maloprodajni.
- **Klasifikacija:** Kategorizacija kupca za vaše poslovanje. Na primer, polje pod nazivom „ValueSegment“ u pržionici za kafu može biti nivo klijenta na osnovu veličine klijenta.

> [!NOTE]
> Za preduzeća sa velikom učestalošću kupovine kupaca (svakih nekoliko nedelja) preporučuje se odabir kraćeg perioda predviđanja i definicija gubitka klijenta. Za nisku učestalost kupovine (svakih nekoliko meseci ili jednom godišnje), odaberite duži period predviđanja i definiciju gubitka klijenta.

## <a name="create-a-transaction-churn-prediction"></a>Kreiranje predviđanja gubitka transakcija

1. Idite na **obaveštajna** > **predviđanja**.

1. Na kartici **Kreiranje** izaberite stavku **Korišćenje modela** na pločici **modela Customer churn**.

1. Izaberite **transakciju** za vrstu churn-a, a zatim prvi **koraci**.

1. **Dajte ime ovom modelu** i **Izlazni naziv entiteta** da ih razlikujete od ostalih modela ili entiteta.

1. Izaberite **Sledeće**.

### <a name="define-customer-churn"></a>Definisanje gubitka klijenata

U **svakom trenutku izaberite** stavku Sačuvaj radnu verziju da biste sačuvali predviđanje kao radnu verziju. Radna verzija predviđanje na kartici "**Moja predviđanja**".

1. Podesite **predviđanje prozor**. Na primer, predvidite rizik od gubitka klijenata tokom sledećih 90 dana kako biste se uskladili sa vašim marketinškim naporima za zadržavanje. Predviđanje rizika od gubitka na duži ili kraći vremenski period može otežati reagovanje na faktore na vašem profilu rizika od gubitka, ali to zavisi od vaših specifičnih poslovnih zahteva.

1. Unesite broj dana da biste definisali churn u polju **Churn definicija**. Na primer, ako kupac nije napravio kupovinu u poslednjih 30 dana, može se smatrati da je to zahtev za vaše poslovanje.

1. Izaberite **Sledeće**.

### <a name="add-purchase-history"></a>Dodavanje prethodnih kupovina

1. Izaberite opciju **Dodaj podatke** za istoriju **transakcija kupca**.

1. Izaberite vrstu semantičke aktivnosti, **"Prodavac" ili** " **Linija prodavca"** koja sadrži informacije o istoriji transakcije. Ako aktivnost nije podešena, izaberite je **ovde i** kreirajte je.

1. U **okviru** Aktivnosti, ako su atributi aktivnosti semantički mapirani prilikom kreiranja aktivnosti, odaberite određene atribute ili entitet na koji želite da se izračunavanje fokusira. Ako nije došlo do semantičkog mapiranja, izaberite opciju Uredi **i** mapiraj svoje podatke.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Bočno okno prikazuje odabir određenih aktivnosti prema semantičkom tipu.":::

1. Kliknite **na** dugme "Dalje" i pregledajte atribute potrebne za ovaj model.

1. Izaberite **Sačuvaj**.

1. Dodajte još aktivnosti ili kliknite na dugme " **Dalje"**.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Dodavanje dodatnih podataka (opcionalno)

1. Izaberite **opciju Dodaj podatke** za **aktivnosti klijenta**.

1. Izaberite tip semantičke aktivnosti koji sadrži podatke koje želite da koristite. Ako aktivnost nije podešena, izaberite je **ovde i** kreirajte je.

1. U **okviru** Aktivnosti, ako su atributi aktivnosti semantički mapirani prilikom kreiranja aktivnosti, odaberite određene atribute ili entitet na koji želite da se izračunavanje fokusira. Ako nije došlo do semantičkog mapiranja, izaberite opciju Uredi **i** mapiraj svoje podatke.

1. Kliknite **na** dugme "Dalje" i pregledajte atribute potrebne za ovaj model.

1. Izaberite **Sačuvaj**.

1. Izaberite **Sledeće**

# <a name="business-accounts-b-to-b"></a>[Poslovni nalozi (B-to-B)](#tab/b2b)

### <a name="select-prediction-level"></a>Izbor nivoa predviđanja

Većina predviđanja se kreiraju na nivou klijenta. U nekim situacijama to možda nije dovoljno detaljno da odgovori na vaše poslovne potrebe. Koristite ovu funkciju da biste predvideli churn za granu kupca, npr.

1. Izaberite **izaberite entitet za sekundarni nivo**. Ako opcija nije dostupna, uverite se da ste dovršili prethodni odeljak.

1. Proširite entitete iz kojih želite da izaberete sekundarni nivo ili koristite okvir za filtriranje pretrage da biste filtrirali izabrane opcije.

1. Odaberite atribut koji želite koristiti kao sekundarni nivo, a zatim izaberite **Dodaj**.

1. Izaberite **Sledeće**.

> [!NOTE]
> Entiteti dostupni u ovom odeljku prikazani su jer imaju odnos sa entitetom koji ste izabrali u prethodnom odeljku. Ako ne vidite entitet koji želite da dodate, uverite se da u **Odnosima** ima prisutan važeći odnos. Za ovu konfiguraciju važe samo odnosi jedan-prema-jedan i više-prema-jedan.

### <a name="add-additional-data-optional"></a>Dodavanje dodatnih podataka (opcionalno)

1. Izaberite **opciju Dodaj podatke** za **aktivnosti klijenta**.

1. Izaberite tip semantičke aktivnosti koji sadrži podatke koje želite da koristite. Ako aktivnost nije podešena, izaberite je **ovde i** kreirajte je.

1. U **okviru** Aktivnosti, ako su atributi aktivnosti semantički mapirani prilikom kreiranja aktivnosti, odaberite određene atribute ili entitet na koji želite da se izračunavanje fokusira. Ako nije došlo do semantičkog mapiranja, izaberite opciju Uredi **i** mapiraj svoje podatke.

1. Kliknite **na** dugme "Dalje" i pregledajte atribute potrebne za ovaj model.

1. Izaberite **Sačuvaj**.

1. Izaberite **Sledeće**

1. Opciono, izaberite **Dodaj podatke** za **Podaci o klijentima**.

1. Mapirajte semantičke atribute na polja u vašim podacima o klijentima kako je identifikovano. Podaci u korišćenim poljima ne bi trebalo da se često menjaju kako biste osigurali najbolje performanse modela. Na primer, izborom polja za „Klasifikaciju“ koje se menja svakog meseca koristila bi se samo poslednja vrednost u predviđaju, iako se istorijski ista vrednost možda ne bi odnosila na klijenta pri pravljenju šablona predviđanja.

1. Izaberite **Sledeće**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Navedite opcionu listu referentnih poslovnih kontakata

Dodajte listu svojih poslovnih klijenata i poslovnih kontakata koje želite da koristite kao reference. Detalji [za ove referentne račune](#view-prediction-results) uključuju njihov churn rezultat i najuticajnije funkcije koje su uticale na njihove predviđanje.

1. Izaberite **+Dodaj klijente**.

1. Odaberite klijente koji služe kao referenca.

1. Izaberite **Sledeće**.

---

### <a name="set-update-schedule"></a>Podešavanje rasporeda ažuriranja

1. Za korak ažuriranja **podataka** odaberite učestalost prekvalifikacije modela. Ova postavka je važna za ažuriranje tačnosti predviđanja jer se novi podaci unose u uvide klijenata. Većina preduzeća može da obavi ponovnu obuku jednom mesečno i dobije precizna predviđanja.

1. Izaberite **Sledeće**.

### <a name="review-and-run-the-model-configuration"></a>Pregledajte i pokrenite konfiguraciju modela

Korak **"Rediguj** i pokreni" prikazuje rezime konfiguracije i pruža šansu za promene pre nego što kreirate predviđanje.

1. Izaberite **stavku Uredi** na bilo kom koraku da biste redigoli i napravili bilo kakve promene.

1. Ako ste zadovoljni izborom, izaberite sačuvaj i pokreni **da biste počeli** da pokrenete model. Izaberite **Gotovo**. Kartica **"Moja predviđanja**" prikazuje se predviđanje se kreira sadržaj. Za završetak procesa može biti potrebno nekoliko sati, u zavisnosti od količine podataka korišćenih u predviđanju.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prikaži predviđanje rezultate

1. Idite na **obaveštajna** > **predviđanja**.

1. Na kartici **Moja predviđanja** izaberite predviđanje želite da prikažete.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

Postoje tri primarna odeljka podataka na stranici sa rezultatima:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Poslovni nalozi (B-to-B)](#tab/b2b)

Postoje tri primarna odeljka podataka na stranici sa rezultatima:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Stranica sa **informacijama o analizi** uticajnih funkcija sadrži četiri odeljka podataka:

- U desnom oknu izaberite stavku od najboljih kupaca **ili** benchmark **kupaca**. Obe liste su poređane prema opadajućoj vrednosti ocene gubitka, bilo da je ocena samo za klijenta ili kombinovana ocena za klijente i sekundarni nivo poput kategorije proizvoda. Izabrana stavka određuje sadržaj na ovoj stranici.

  - **Glavni klijenti**: Spisak 10 klijenata koji imaju najveći rizik od gubitka i najmanji rizik od gubitka na osnovu njihovih rezultata za gubitak.
  - **Referentni klijenti**: Lista do 10 klijenata koji su izabrani prilikom konfigurisanja modela.

- **Rezultat gubitka**: Prikazuje rezultat gubitka za izabranu stavku u desnom oknu.

- **Churn raspodela rizika:** Prikazuje raspodelu churn rizika po kupcima i procenat u kojem se nalazi izabrani kupac.

- **Glavne funkcije povećavaju i smanjuju rizik od churn-a:** Navodi prvih pet funkcija koje su povećale i smanjile rizik od čurne izabrane stavke u desnom oknu. Prikazuje vrednost funkcije za tu stavku i njen uticaj na churn rezultat za svaku uticajnu funkciju. Prikazana je i prosečna vrednost svake funkcije u segmentima klijenata sa niskim, srednjim i visokim gubitkom. Pomaže u boljoj kontekstualizaciji vrednosti najuticajnijih karakteristika za izabranu stavku i upoređivanju sa segmentima klijenata sa niskim, srednjim i visokim gubitkom.

  - Nizak: konta ili kombinacije računa i sekundarnog nivoa sa churn rezultatom između 0 i 0,33.
  - Srednji: računi ili kombinacije konta i sekundarnih nivoa sa churn rezultatom između 0,33 i 0,66.
  - Visok: računi ili kombinacije konta i sekundarnih nivoa sa churn ocenom većom od 0,66.

  Kada predviđate gubitak na nivou poslovnog kontakta, svi poslovni kontakti se uzimaju u obzir pri izvođenju prosečnih vrednosti karakteristika za segmente gubitka. Za predviđanja gubitka na sekundarnom nivou za svaki poslovni kontakt, izvođenje segmenata gubitka zavisi od sekundarnog nivoa stavke izabrane u bočnom oknu. Na primer, ako stavka ima sekundarni nivo kategorije proizvoda (kancelarijski materijal), prilikom derunja prosečnih vrednosti funkcija za churn segmente nisu uzete u obzir samo artikli koji imaju kancelarijski pribor kao kategoriju proizvoda. Ova logika se primenjuje kako bi se obezbedilo fer poređenje vrednosti karakteristika stavke sa prosečnim vrednostima u segmentima sa niskim, srednjim i visokim gubitkom.

  U nekim slučajevima, prosečna vrednost segmenata niske, srednje ili visoke stope gubitka je prazna ili nije dostupna jer ne postoje stavke koje pripadaju odgovarajućim segmentima gubitka na osnovu gornje definicije.

  Tumačenje vrednosti ispod kolona prosečno niske, srednje i visoke razlikuje se za karakteristike kategorija kao što su zemlja ili delatnost. Budući da se pojam vrednosti „prosečne“ funkcije ne primenjuje na funkcije kategorija, vrednosti u ovim kolonama su proporcija klijenata u segmentima sa niskim, srednjim ili visokim gubitkom koji imaju istu vrednost funkcije kategorije u poređenju sa stavkom izabranom na bočnoj tabli.

---

 > [!NOTE]
 > U izlaznom entitetu za ovaj model, *ChurnScore prikazuje* predviđenu verovatnoću churn-a *, a IsChurn je binarna* oznaka *zasnovana na ChurnScore* sa 0,5 pragom. Ako ovaj podrazumevani prag ne funkcioniše za vaš scenario, kreirajte [novi segment sa](segments.md#create-a-segment) željenim pragom. Nisu svi klijenti nužno aktivni klijenti. Neki od njih možda već duže vreme nisu imali nikakve aktivnosti i smatraju se već izgubljenim, na osnovu vaše definicije gubitka klijenta. Predviđanje rizika od gubitka za klijente koji su već otišli nije korisno jer nisu interesna ciljna grupa.
>
> Da biste prikazali churn rezultat, idite na **entitete** > **podataka** i prikažite karticu sa podacima za izlazni entitet koji ste definisali za ovaj model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
