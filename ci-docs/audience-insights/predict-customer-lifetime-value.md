---
title: Predviđanje trajne vrednosti klijenta (CLV)
description: Predvidite potencijalni prihod za aktivne klijente u budućnosti.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: 07790604b06f21095a9220a6f57727cac80789c5
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355806"
---
# <a name="customer-lifetime-value-clv-prediction"></a>Predviđanje trajne vrednosti klijenta (CLV)

Predvidite potencijalnu vrednost (prihod) koju će pojedinačni aktivni klijenti doneti vašem preduzeću kroz definisan budući vremenski period. Ova funkcija vam može pomoći u postizanju različitih ciljeva: 
- Identifikujte klijente velike vrednosti i obradite ovaj uvid
- Kreirajte strateške segmente klijenata na osnovu njihove potencijalne vrednosti za vođenje personalizovanih kampanja uz ciljanu prodaju, marketing i napore za podršku
- Usmerite razvoj proizvoda fokusirajući se na funkcije koje povećavaju vrednost klijenta
- Optimizujte prodajnu ili marketinšku strategiju i tačnije rasporedite budžet za dosezanje klijenata
- Prepoznajte i nagradite klijente velike vrednosti kroz programe lojalnosti ili nagrađivanja 

## <a name="prerequisites"></a>Preduslovi

Pre nego što započnete, razmislite šta CLV znači za vaše poslovanje. Trenutno podržavamo predviđanje CLV zasnovano na transakcijama. Predviđena vrednost klijenta zasniva se na istoriji poslovnih transakcija. Da biste kreirali predviđanje, trebaju vam dozvole barem na nivou [saradnika](permissions.md).

Budući da konfigurisanje i pokretanje CLV modela ne zahteva mnogo vremena, razmislite o kreiranju nekoliko modela sa različitim željenim opcijama za unos i uporedite rezultate modela da biste videli koji model scenarija najbolje odgovara vašim poslovnim potrebama.

###  <a name="data-requirements"></a>Zahtevi za podacima

Sledeći podaci su obavezni, a tamo gde su označeni kao opcionalni, preporučuju se za veće performanse modela. Što više podataka model može da obradi, to će predviđanje biti tačnije. Stoga vam preporučujemo da unesete više podataka o aktivnostima klijenata, ako su dostupni.

- Identifikator klijenata: Jedinstveni identifikator koji podudara transakcije sa pojedinačnim klijentom

- Istorija transakcija: Dnevnik istorije transakcija sa semantičkom šemom podataka ispod
    - **ID transakcije**: Jedinstveni identifikator svake transakcije
    - **Datum transakcije**: Datum, po mogućnosti vremenski žig svake transakcije
    - **Iznos transakcije**: Monetarna vrednost (na primer, prihod ili marža profita) svake transakcije
    - **Oznaka koja se dodeljuje za povraćaj** (opcionalno): Logička vrednost koja označava da li je transakcija povraćaj 
    - **ID proizvoda** (opcionalno): ID proizvoda koji je uključen u transakciju

- Dodatni podaci (opcionalno), na primer
    - Veb-aktivnosti: istorija poseta veb-lokaciji, istorija e-pošte
    - Aktivnosti lojalnosti: istorija obračuna i otkupa nagradnih poena za lojalnost
    - Evidencija korisničke službe, servisni poziv, žalba ili istorija povraćaja
- Podaci o aktivnostima klijenata (opcionalno):
    - Identifikatori aktivnosti za razlikovanje aktivnosti iste vrste
    - Identifikatori klijenata za mapiranje aktivnosti na klijente
    - Informacije o aktivnostima koje sadrže ime i datum aktivnosti
    - Šema semantičkih podataka za aktivnosti uključuje: 
        - **Primarni ključ**: Jedinstveni identifikator aktivnosti
        - **Vremenska oznaka**: Datum i vreme događaja koje identifikuje primarni ključ
        - **Događaj (naziv aktivnosti)**: Naziv događaja koji želite da koristite
        - **Detalji (iznos ili vrednost)**: Detalji o aktivnosti klijenta

- Predložene karakteristike podataka:
    - Dovoljno istorijskih podataka: Najmanje jedna godina transakcionih podataka. Poželjno je dve do tri godine podataka o transakcijama da bi se predvidela trajna vrednost klijenta za jednu godinu.
    - Više kupovina po klijentu: U idealnom slučaju, najmanje dve do tri transakcije po ID-u klijenta, po mogućnosti tokom više datuma.
    - Broj klijenata: Najmanje 100 jedinstvenih klijenata, po mogućnosti više od 10.000 klijenata. Model neće uspeti sa manje od 100 klijenata i nedovoljnom količinom istorijskih podataka
    - Kompletnost podataka: Manje od 20% nedostajućih vrednosti u obaveznim poljima u ulaznim podacima   

> [!NOTE]
> - Model zahteva istoriju transakcija vaših klijenata. Trenutno se može konfigurisati samo jedan entitet istorije transakcija. Ako postoji više entiteta nabavke/transakcije, možete ih uvesti pre Power Query brisanja podataka.
> - Međutim, za dodatne podatke o aktivnostima klijenata (opcionalno) možete dodati onoliko entiteta aktivnosti klijenata koliko želite da ih model uzme u obzir.

## <a name="create-a-customer-lifetime-value-prediction"></a>Kreiranje predviđanja trajne vrednosti klijenta

1. U uvidima o korisnicima idite na **Obaveštavanje** > **Predviđanja**.

1. Izaberite pločicu **Trajna vrednost klijenta** i izaberite **Koristi model**. 

1. U oknu sa **doživotnom vrednošću kupca** izaberite stavku **Prvi koraci**.

1. **Dajte ime ovom modelu** i **Izlazni naziv entiteta** da ih razlikujete od ostalih modela ili entiteta.

1. Izaberite **Sledeće**.

### <a name="define-model-preferences"></a>Definisanje željenih podešavanja modela

1. Podesite **Vremenski period predviđanja** da biste definisali koliko daleko u budućnosti želite da predvidite CLV.    
   Podrazumevano, jedinica je podešena na mesece. Možete je promeniti u godine da biste gledali dalje u budućnost.

   > [!TIP]
   > Da biste tačno predvideli CLV za vremenski period koji ste postavili, potreban vam je uporediv period istorijskih podataka. Na primer, ako želite da predvidite trajnu vrednost klijenta za narednih 12 meseci, preporučuje se da imate najmanje 18–24 meseca istorijskih podataka.

1. Navedite šta **Aktivni klijenti** znače za vaše poslovanje. Podesite vremenski okvir u kojem je klijent morao imati najmanje jednu transakciju da bi se smatrao aktivnim. Model će predvideti CLV samo za aktivne klijente. 
   - **Neka model izračuna interval kupovine (preporučeno)**: Model analizira vaše podatke i određuje vremenski period na osnovu istorijskih kupovina.
   - **Podesite interval podesite ručno**: Ako imate specifičnu poslovnu definiciju aktivnog klijenta, odaberite ovu opciju i u skladu s tim podesite vremenski period.

1. Definišite procentni iznos **klijenta velike vrednosti** kako biste omogućili da model pruži rezultate koji odgovaraju vašoj definiciji preduzeća.
    - **Proračun modela (preporučeno)**: Model analizira vaše podatke i na osnovu istorije transakcija vaših klijenata utvrđuje koliki bi mogao biti klijent velike vrednosti za vaše poslovanje. Model koristi heurističko pravilo (inspirisano pravilom 80/20 ili pareto principom) da bi pronašao udeo klijenata velike vrednosti. Procenat klijenata koji su u istorijskom periodu doprineli sa 80% kumulativnog prihoda za vaše poslovanje smatraju se klijentima velike vrednosti. Manje od 30-40% klijenata obično doprinosi sa 80% kumulativnog prihoda. Međutim, ovaj broj se može razlikovati u zavisnosti od vašeg poslovanja i delatnosti.    
    - **Procenat najboljih aktivnih klijenata**: Definišite klijente velike vrednosti za svoje poslovanje kao procenat najboljih aktivnih klijenata koji plaćaju. Na primer, pomoću ove opcije možete da definišete klijente velike vrednosti kao najboljih 20% budućih kupaca koji plaćaju.

    Ako vaše preduzeće na drugačiji način definiše klijente velike vrednosti, [javite nam ono što bismo voleli da čujemo](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Izaberite **Sledeće** da biste prešli na sledeći korak.

### <a name="add-required-data"></a>Dodavanje obaveznih podataka

1. U koraku **Obavezni podaci** izaberite **Dodaj podatke** za **Istoriju transakcija klijenta** i odaberite entitet koji pruža informacije o istoriji transakcija kao što je opisano u [preduslovima](#prerequisites).

1. Mapirajte semantička polja sa atributima u entitetu istorije kupovine i izaberite **Sledeće**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Slika koraka konfiguracije za mapiranje atributa podataka za potrebne podatke.":::
 
1. Ako polja u nastavku nisu popunjena, konfigurišite relaciju između entiteta istorije kupovine i entiteta *klijenta* i izaberite **Sačuvaj**.
    1. Izaberite entitet istorije transakcije.
    1. Izaberite polje koje identifikuje klijenta u entitetu istorije kupovine. Mora da se odnosi na primarni ID klijenta entiteta „Klijent“.
    1. Izaberite entitet koji se podudara sa entitetom primarnog klijenta.
    1. Unesite ime koje opisuje odnos.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Slika koraka konfiguracije za definisanje relacije sa entitetom klijenta.":::

1. Izaberite **Sledeće**.

### <a name="add-optional-data"></a>Dodavanje opcionih podataka

Podaci koji odražavaju ključne interakcije sa klijentom (poput veba, korisničke službe i evidencije događaja) dodaju kontekst zapisima transakcija. Više obrazaca pronađenih u podacima o aktivnostima klijenata može poboljšati tačnost predviđanja. 

1. U koraku **Dodatni podaci (opcionalno)**, izaberite **Dodaj podatke**. Izaberite entitet aktivnosti klijenta koji pruža informacije o aktivnostima klijenata kako je opisano u [preduslovima](#prerequisites).

1. Mapirajte semantička polja sa atributima u entitetu aktivnosti klijenata i izaberite **Sledeće**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Slika koraka konfiguracije za mapiranje polja podataka za dodatne podatke.":::

1. Izaberite tip aktivnosti koji se podudara sa tipom aktivnosti klijenta koju dodajete. Odaberite jedan od postojećih tipova aktivnosti ili dodajte novi tip aktivnosti.

1. Konfigurišite relaciju između vašeg entiteta aktivnosti klijenta i entiteta *Klijent*.
    
    1. Izaberite polje koje identifikuje klijenta na tabeli aktivnosti klijenata. Može biti direktno povezano sa primarnim ID-om klijenta entiteta *Klijent*.
    1. Izaberite entitet *Klijent* koji odgovara primarnom entitetu *Klijent*.
    1. Unesite ime koje opisuje odnos.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Slika koraka u toku konfiguracije za dodavanje dodatnih podataka i konfigurisanje aktivnosti sa popunjenim primerima.":::

1. Izaberite stavku **Sačuvaj**.    
    Dodajte još podataka ako postoje druge aktivnosti klijenata koje želite da uključite.

1. Izaberite **Sledeće**.

### <a name="set-update-schedule"></a>Podešavanje rasporeda ažuriranja

1. U koraku **Raspored ažuriranja podataka**, odaberite učestalost za ponovnu obuku modela na osnovu najnovijih podataka. Ovo podešavanje je važno za ažuriranje tačnosti predviđanja kako se unose novi podaci u uvide o korisnicima. Većina preduzeća može da obavi ponovnu obuku jednom mesečno i dobije precizna predviđanja.

1. Izaberite **Sledeće**.

### <a name="review-and-run-the-model-configuration"></a>Pregledajte i pokrenite konfiguraciju modela

1. U koraku **Pregled detalja o modelu** potvrdite konfiguraciju predviđanja. Možete se vratiti na bilo koji deo konfiguracije predviđanja ako izaberete **Uredi** ispod prikazane vrednosti. Takođe možete da izaberete korak konfiguracije iz indikatora napretka.

1. Ako su sve vrednosti ispravno konfigurisane, izaberite **Sačuvaj i pokreni** da započnemo pokretanje modela. Na kartici **Moja predviđanja** možete da vidite status procesa predviđanja. Za završetak procesa može biti potrebno nekoliko sati, u zavisnosti od količine podataka korišćenih u predviđanju.

## <a name="review-prediction-status-and-results"></a>Pregledajte status predviđanja i rezultate

### <a name="review-prediction-status"></a>Pregledajte status predviđanja

1.  Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.
2.  Izaberite predviđanje koje želite da pregledate.

- **Naziv predviđanja**: Naziv predviđanja naveden pri njegovom kreiranju.
- **Tip predviđanja**: Tip modela koji se koristi za predviđanje
- **Izlazni entitet**: Naziv entiteta za skladištenje izlaza predviđanja. Idite na **Podaci** > **Entiteti** da pronađete entitet sa ovim nazivom.
- **Predviđeno polje**: Ovo polje je popunjeno samo za neke tipove predviđanja i ne koristi se za predviđanje vrednosti trajne vrednosti klijenta.
- **Status**: Status pokretanja predviđanja.
    - **Stavljeno u red**: Predviđanje čeka da se drugi procesi završe.
    - **Osvežavanje**: Predviđanje je trenutno pokrenuto da bi kreiralo rezultate koji će biti prosleđeni u izlazni entitet.
    - **Nije uspelo**: Pokretanje predviđanja nije uspelo. Detaljnije informacije potražite u [evidenciji](manage-predictions.md#troubleshoot-a-failed-prediction).
    - **Uspelo je**: Predviđanje je uspelo. Izaberite **Prikaz** ispod uspravne tri tačke da biste pregledali rezultate predviđanja.
- **Izmenjeno:** Datum promene konfiguracije predviđanja.
- **Poslednje osvežavanje**: Datum kada je predviđanje osvežilo rezultate u izlaznom entitetu.

### <a name="review-prediction-results"></a>Pregled rezultata predviđanja

1. Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.

1. Izaberite predviđanje za koje želite da pregledate rezultate.

Postoje tri primarna odeljka podataka na stranici sa rezultatima.

- **Obuka performansi modela**: A, B ili C su moguće klase. Ova klasa ukazuje na performanse predviđanja i može vam pomoći da donesete odluku da koristite rezultate uskladištene u izlaznom entitetu. Izaberite **Saznajte više o ovom rezultatu** da biste bolje razumeli osnovne metrike performansi modela i kako je izvedena konačna klasa performansi modela.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Slika informativnog okvira za ocenu modela sa klasom A.":::

  Koristeći definiciju klijenata velike vrednosti navedenu tokom konfigurisanja predviđanja, sistem procenjuje kako se model veštačke inteligencije pokazao u predviđanju klijenata velike vrednosti u poređenju sa osnovnim modelom.    

  Klase se određuju na osnovu sledećih pravila:
  - **A** kada je model tačno predvideo barem 5% više klijenata visoke vrednosti u poređenju sa osnovnim modelom.
  - **B** kada je model tačno predvideo 0–5% više klijenata visoke vrednosti u poređenju sa osnovnim modelom.
  - **V** kada je model tačno predvideo manje klijenata visoke vrednosti u poređenju sa osnovnim modelom.

  Okno **Ocena modela** prikazuje dalje detalje o performansama modela veštačke inteligencije i osnovnog modela. Osnovni model koristi pristup koji nije zasnovan na veštačkoj inteligenciji da bi izračunao trajnu vrednost klijenta na osnovu prevashodno istorijskih kupovina koje su obavili klijenti.     
  Standardna formula koja se koristi za izračunavanje CLV po osnovnom modelu:    

  _**Trajna vrednost za svakog klijenta** = Prosečna mesečna kupovina koju je klijent obavio u aktivnom prozoru klijenta * Broj meseci u periodu predviđanja * Ukupna stopa zadržavanja svih klijenata*_

  Model veštačke inteligencije se upoređuje sa osnovnim modelom na osnovu dva pokazatelja performansi modela.
  
  - **Stopa uspešnosti predviđanja klijenata visoke vrednosti**

    Pogledajte razliku u predviđanju klijenata velike vrednosti koristeći model veštačke inteligencije u poređenju sa osnovnim modelom. Na primer, stopa uspešnosti od 84% znači da je od svih klijenata visoke vrednosti u podacima o obuci, model veštačke inteligencije uspeo da tačno uhvati 84%. Zatim upoređujemo ovu stopu uspešnosti sa stopom uspešnosti osnovnog modela da bismo prijavili relativnu promenu. Ova vrednost se koristi za dodeljivanje klase modelu.

  - **Metrike grešaka**
    
    Drugi pokazatelj vam omogućava da pregledate ukupne performanse modela u smislu greške u predviđanju budućih vrednosti. Za procenu ove greške koristimo opštu metriku osnovnog srednjeg kvadrata (RMSE). RMSE je standardni način merenja greške modela u predviđanju kvantitativnih podataka. RMSE modela veštačke inteligencije se upoređuje sa RMSE osnovnog modela i izveštava se o relativnoj razlici.

  Model veštačke inteligencije daje prioritet tačnom rangiranju klijenata prema vrednosti koju oni donose u vaše poslovanje. Dakle, samo se stopa uspešnosti predviđanja klijenata velike vrednosti koristi za izvođenje konačne klase modela. RMSE metrika je osetljiva na izvanredne vrednosti. U scenarijima gde imate mali procenat klijenata sa izuzetno visokim vrednostima kupovine, ukupna RMSE metrika možda neće dati potpunu sliku performansi modela.   

- **Vrednost klijenata prema procentnom iznosu**: Koristeći vašu definiciju klijenata velike vrednosti, klijenti su grupisani u male vrednosti i velike vrednosti na osnovu njihovih predviđanja CLV-a i prikazani na grafikonu. Prelaskom kursora preko traka u histogramu, možete videti broj klijenata u svakoj grupi i prosečni CLV te grupe. Ovi podaci mogu vam pomoći ako želite [da kreirate segmente klijenata](segments.md) na osnovu njihovih CLV predviđanja.

- **Najuticajniji faktori**: Razni faktori se uzimaju u obzir prilikom kreiranja vašeg CLV predviđanja zasnovanog na ulaznim podacima dostavljenim modelu veštačke inteligencije. Svaki od faktora ima svoju važnost koja se izračunava za objedinjena predviđanja koja model kreira. Možete koristiti ove faktore da biste potvrdili rezultate predviđanja. Ovi faktori takođe pružaju bolji uvid u najuticajnije faktore koji su doprineli predviđanju CLV-a za sve vaše klijente.

## <a name="manage-predictions"></a>Upravljanje predviđanjima

Predviđanja je moguće optimizovati, rešavati, osvežiti ili izbrisati. Pregledajte izveštaj o upotrebljivosti ulaznih podataka da biste saznali kako da predviđanje učinite bržim i pouzdanijim. Još informacija potražite u članku [Upravljanje predviđanjima](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
