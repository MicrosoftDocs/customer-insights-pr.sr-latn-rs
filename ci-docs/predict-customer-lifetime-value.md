---
title: Predvidite trajnu vrednost klijenta (CLV)
description: Predvidite potencijalni prihod za aktivne klijente u budućnosti.
ms.date: 09/30/2022
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
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610391"
---
# <a name="predict-customer-lifetime-value-clv"></a>Predvidite trajnu vrednost klijenta (CLV)

Predvidite potencijalnu vrednost (prihod) koju će pojedinačni aktivni klijenti doneti vašem preduzeću kroz definisan budući vremenski period. Ova predviđanje vam pomaže:

- Identifikujte kupce visoke vrednosti i obradite ovaj uvid.
- Kreirajte segmente strateških klijenata na osnovu njihove potencijalne vrednosti za pokretanje personalizovanih kampanja sa ciljanom prodajom, marketingom i naporima podrške.
- Vodite razvoj proizvoda fokusirajući se na funkcije koje povećavaju vrednost klijenta.
- Optimizujte prodajnu ili marketinšku strategiju i preciznije dodelite budžet za izlazak kupaca.
- Prepoznajte i nagradite kupce visoke vrednosti putem programa lojalnosti ili nagrađivanja.

Odredite šta CLV znači za vaše poslovanje. Podržavamo CLV datoteke zasnovane na predviđanje. Predviđena vrednost kupca se zasniva na istoriji poslovnih transakcija. Razmislite o kreiranju nekoliko modela sa različitim željenim opcijama unosa i uporedite rezultate modela da biste videli koji model najbolje odgovara vašim poslovnim potrebama.

> [!TIP]
> Isprobajte CLV predviđanje pomoću probnih podataka: [Vodič za uzorke vrednosti predviđanje (CLV)](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Preduslovi

- [Najmanje saradnik](permissions.md) dozvole
- Najmanje 100 jedinstvenih kupaca, po mogućstvu više od 10.000 kupaca
- Identifikator kupca, jedinstveni identifikator za podudaranje transakcija sa pojedinačnim kupcem
- Najmanje godinu dana istorije transakcija, po mogućstvu dve do tri godine. U idealnim uslovima, najmanje dve do tri transakcije po ID-u kupca, po mogućstvu tokom više datuma. Istorija transakcija mora da sadrži:
  - **ID transakcije**: Jedinstveni identifikator svake transakcije
  - **Datum transakcije**: oznaka datuma ili vremena svake transakcije
  - **Iznos transakcije**: Monetarna vrednost (na primer, prihod ili marža profita) svake transakcije
  - **Oznaka dodeljena za povraćaj**: Logička vrednost true/false označava da li je transakcija povraćaj
  - **ID proizvoda**: ID proizvoda uključen u transakciju
- Podaci o aktivnostima klijenata:
  - **Primarni ključ**: Jedinstveni identifikator za aktivnost
  - **Vremenska osa**: Datum i vreme događaja identifikovani primarnim ključem
  - **Događaj (ime aktivnosti)**: Ime događaja koji želite da koristite
  - **Detalji (iznos ili vrednost)**: Detalji o aktivnosti klijenta
- Dodatni podaci kao što su:
  - Web aktivnosti: Veb lokacija poseta istoriji ili istorija e-pošte
  - Aktivnosti lojalnosti: Nagradne tačke nagrade akumulirane i iskupljene istorije
  - Korisnička služba evidencije: Poziv usluge, žalba ili istorija povraćaja
  - Informacije o profilu klijenta
- Manje od 20% vrednosti u potrebnim poljima

> [!NOTE]
> Samo jedan entitet istorije transakcija može da se konfiguriše. Ako postoji više entiteta nabavke ili transakcija, kombinujte ih pre Power Query brisanja podataka.

## <a name="create-a-customer-lifetime-value-prediction"></a>Kreiranje predviđanja trajne vrednosti klijenta

U **svakom trenutku izaberite** stavku Sačuvaj radnu verziju da biste sačuvali predviđanje kao radnu verziju. Radna verzija predviđanje na kartici "**Moja predviđanja**".

1. Idite na **obaveštajna** > **predviđanja**.

1. Na kartici **Kreiranje** izaberite stavku Korišćenje **modela na pločici** vrednosti **za doživotnu vrednost** kupca.

1. Izaberite **Prvi koraci**.

1. **Dajte ime ovom modelu** i **Izlazni naziv entiteta** da ih razlikujete od ostalih modela ili entiteta.

1. Izaberite **Sledeće**.

### <a name="define-model-preferences"></a>Definisanje željenih podešavanja modela

1. Podesite **Vremenski period predviđanja** da biste definisali koliko daleko u budućnosti želite da predvidite CLV. Podrazumevano, jedinica je podešena na mesece.

   > [!TIP]
   > Da biste precizno predvideli CLV za određeni vremenski period, potreban je uporedivi period istorijskih podataka. Na primer, ako želite da predvidite CLV u narednih 12 meseci, imajte najmanje 18 – 24 meseca istorijskih podataka.

1. Podesite vremenski okvir u kojem je klijent morao imati najmanje jednu transakciju da bi se smatrao aktivnim. Model predviđa SAMO CLV za aktivne **kupce**.
   - **Neka model izračuna interval kupovine (preporučuje se)**: Model analizira vaše podatke i određuje vremenski period zasnovan na istorijskim kupovinama.
   - **Ručno podešavanje intervala**: Vremenski period za definiciju aktivnog kupca.

1. Definišite procenat kupca **visoke vrednosti**.
    - **Izračunavanje modela (preporučuje se)**: Model koristi pravilo 80/20. Procenat klijenata koji su u istorijskom periodu doprineli sa 80% kumulativnog prihoda za vaše poslovanje smatraju se klijentima velike vrednosti. Manje od 30-40% klijenata obično doprinosi sa 80% kumulativnog prihoda. Međutim, ovaj broj se može razlikovati u zavisnosti od vašeg poslovanja i delatnosti.
    - **Procenat aktivnih klijenata**: Specifičan procenat za kupca visoke vrednosti. Na primer, unesite **25 da** biste definisali kupce visoke vrednosti kao prvih 25% budućih kupaca koji plaćaju.

    Ako vaše preduzeće na drugačiji način definiše klijente velike vrednosti, [javite nam ono što bismo voleli da čujemo](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Izaberite **Sledeće**.

### <a name="add-required-data"></a>Dodavanje obaveznih podataka

1. Izaberite opciju **Dodaj podatke** za istoriju **transakcija kupca**.

1. Izaberite vrstu semantičke aktivnosti, **"Prodavac" ili** " **Linija prodavca"** koja sadrži istoriju transakcija. Ako aktivnost nije podešena, izaberite je **ovde i** kreirajte je.

1. U **okviru** Aktivnosti, ako su atributi aktivnosti semantički mapirani prilikom kreiranja aktivnosti, odaberite određene atribute ili entitet na koji želite da se izračunavanje fokusira. Ako nije došlo do semantičkog mapiranja, izaberite opciju Uredi **i** mapiraj svoje podatke.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Dodavanje potrebnih podataka za CLV model":::

1. Kliknite **na** dugme "Dalje" i pregledajte atribute potrebne za ovaj model.

1. Izaberite **Sačuvaj**.

1. Dodajte još aktivnosti ili kliknite na dugme " **Dalje"**.

### <a name="add-optional-activity-data"></a>Dodavanje opcionalnih podataka o aktivnostima

Podaci koji odražavaju ključne interakcije sa klijentom (poput veba, korisničke službe i evidencije događaja) dodaju kontekst zapisima transakcija. Više obrazaca pronađenih u podacima o aktivnostima klijenata može poboljšati tačnost predviđanja.

1. Izaberite **opciju Dodaj podatke** u **okviru Uvid modela Boost sa dodatnim podacima o aktivnostima**.

1. Izaberite tip aktivnosti koji se podudara sa tipom aktivnosti klijenta koju dodajete. Ako aktivnost nije podešena, izaberite je **ovde i** kreirajte je.

1. U **okviru** Aktivnosti, ako su atributi aktivnosti mapirani prilikom kreiranja aktivnosti, odaberite određene atribute ili entitet na koji želite da se izračunavanje fokusira. Ako nije došlo do mapiranja, izaberite uredite **i** mapirajte podatke.

1. Kliknite **na** dugme "Dalje" i pregledajte atribute potrebne za ovaj model.

1. Izaberite **Sačuvaj**.

1. Izaberite **Sledeće**.

1. [Dodaj opcionalne podatke o kupcima](#add-optional-customer-data) ili kliknite na **dugme "Dalje** " i idite [na stavku "Podešavanje rasporeda ažuriranja"](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Dodavanje opcionalnih podataka korisnika

Izaberite jedan od 18 najčešće korišćenih atributa profila kupca koje treba uključiti kao unos u model. Ovi atributi mogu dovesti do personalizovanijih, relevantnijih i akcionih rezultata modela za vaše slučajeve korišćenja preduzeća.

Na primer: Contoso Coffee želi da predvidi vrednost za životni vek kupca kako bi ciljao kupce visoke vrednosti sa personalizovanom ponudom vezanom za pokretanje njihove nove espreso mašine. Contoso koristi CLV model i dodaje svih 18 atributa profila klijenata da bi video koji faktori utiču na njihove kupce sa najvećom vrednošću. Oni smatraju da je lokacija kupca najuticajniji faktor za ove kupce.
Sa ovim informacijama organizuju lokalni događaj za pokretanje aparata za espreso i partnera sa lokalnim prodavcima za personalizovane ponude i poseban doživljaj na događaju. Bez ovih informacija, Contoso su poslali samo generičke marketinške e-poruke i propustili priliku da personalizuju ovaj lokalni segment svojih klijenata visoke vrednosti.

1. Izaberite **opciju Dodaj podatke** **u okviru Boost uvid modela još više sa dodatnim podacima o klijentima**.

1. Za entitet **odaberite** opciju " **Customer: CustomerInsights" da** biste izabrali objedinjeni profil klijenta koji se mapira na podatke atributa klijenta. Za **ID kupca** izaberite stavku ID **kupca sistema.Kupac**..

1. Mapirajte više polja ako su podaci dostupni u objedinjenim profilima kupaca.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Primer mapiranih polja za podatke profila kupca.":::

1. Izaberite **Sačuvaj**.

1. Izaberite **Sledeće**.

### <a name="set-update-schedule"></a>Podešavanje rasporeda ažuriranja

1. Odaberite učestalost prekvalifikacije modela na osnovu najnovijih podataka. Ova postavka je važna za ažuriranje tačnosti predviđanja jer se novi podaci unose u uvide klijenata. Većina preduzeća može da obavi ponovnu obuku jednom mesečno i dobije precizna predviđanja.

1. Izaberite **Sledeće**.

### <a name="review-and-run-the-model-configuration"></a>Pregledajte i pokrenite konfiguraciju modela

Korak **"Rediguj** i pokreni" prikazuje rezime konfiguracije i pruža šansu za promene pre nego što kreirate predviđanje.

1. Izaberite **stavku Uredi** na bilo kom koraku da biste redigoli i napravili bilo kakve promene.

1. Ako ste zadovoljni izborom, izaberite sačuvaj i pokreni **da biste počeli** da pokrenete model. Izaberite **Gotovo**. Kartica **"Moja predviđanja**" prikazuje se predviđanje se kreira sadržaj. Za završetak procesa može biti potrebno nekoliko sati, u zavisnosti od količine podataka korišćenih u predviđanju.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prikaži predviđanje rezultate

1. Idite na **obaveštajna** > **predviđanja**.

1. Na kartici **Moja predviđanja** izaberite predviđanje želite da prikažete.

Postoje tri primarna odeljka podataka na stranici sa rezultatima.

- **Performanse modela** obuke: Ocene A, B ili C ukazuju na performanse predviđanje-a i mogu vam pomoći da donesete odluku o korišćenju rezultata uskladištenih u izlaznom entitetu.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Slika informativnog okvira za ocenu modela sa klasom A.":::

  Customer Insights procenjuje kako je AI model nastupio u predviđanju kupaca visoke vrednosti u poređenju sa osnovnim modelom.

  Klase se određuju na osnovu sledećih pravila:
  - **A** kada je model tačno predvideo barem 5% više klijenata visoke vrednosti u poređenju sa osnovnim modelom.
  - **B** kada je model tačno predvideo 0–5% više klijenata visoke vrednosti u poređenju sa osnovnim modelom.
  - **V** kada je model tačno predvideo manje klijenata visoke vrednosti u poređenju sa osnovnim modelom.
  
  Izaberite [**stavku Saznajte više o ovom**](#learn-about-the-score) rezultatu da biste otvorili **okno** za ocenjivanje modela koje prikazuje dodatne detalje o performansama AI modela i modelu osnovne linije. To će vam pomoći da bolje razumete osnovne metrike performansi modela i kako je izvedena konačna ocena performansi modela. Osnovni model koristi pristup koji nije zasnovan na veštačkoj inteligenciji da bi izračunao trajnu vrednost klijenta na osnovu prevashodno istorijskih kupovina koje su obavili klijenti.

- **Vrednost kupaca po procentima**: kupci male vrednosti i visoke vrednosti prikazuju se na grafikonu. Zadržite pokazivač iznad rešetaka u histogramu da biste videli broj kupaca u svakoj grupi i prosečan CLV te grupe. Opcionalno, [kreirajte segmente kupaca](prediction-based-segment.md) na osnovu njihovih CLV predviđanja.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Vrednost kupaca po procentu za CLV model":::

- **Najuticajniji faktori**: Razni faktori se uzimaju u obzir prilikom kreiranja vašeg CLV predviđanja zasnovanog na ulaznim podacima dostavljenim modelu veštačke inteligencije. Svaki od faktora ima svoju važnost koja se izračunava za objedinjena predviđanja koja model kreira. Koristite ove faktore da biste proverili valjanost predviđanje rezultata. Ovi faktori takođe pružaju bolji uvid u najuticajnije faktore koji su doprineli predviđanju CLV-a za sve vaše klijente.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Najuticajniji faktori za CLV model":::

### <a name="learn-about-the-score"></a>Saznajte više o rezultatu

Standardna formula koja se koristi za izračunavanje CLV po osnovnom modelu:

 _**CLV za svakog kupca** = Prosečna mesečna nabavka koju je kupac napravio u aktivnom prozoru kupca * Broj meseci u periodu CIV predviđanje * Ukupna stopa zadržavanja svih kupaca_

Model veštačke inteligencije se upoređuje sa osnovnim modelom na osnovu dva pokazatelja performansi modela.
  
- **Stopa uspešnosti predviđanja klijenata visoke vrednosti**

  Pogledajte razliku u predviđanju klijenata velike vrednosti koristeći model veštačke inteligencije u poređenju sa osnovnim modelom. Na primer, stopa uspešnosti od 84% znači da je od svih klijenata visoke vrednosti u podacima o obuci, model veštačke inteligencije uspeo da tačno uhvati 84%. Zatim upoređujemo ovu stopu uspešnosti sa stopom uspešnosti osnovnog modela da bismo prijavili relativnu promenu. Ova vrednost se koristi za dodeljivanje klase modelu.

- **Metrike grešaka**

  Pogledajte ukupne performanse modela u smislu greške u predviđanju budućih vrednosti. Za procenu ove greške koristimo opštu metriku osnovnog srednjeg kvadrata (RMSE). RMSE je standardni način merenja greške modela u predviđanju kvantitativnih podataka. RMSE modela veštačke inteligencije se upoređuje sa RMSE osnovnog modela i izveštava se o relativnoj razlici.

Model veštačke inteligencije daje prioritet tačnom rangiranju klijenata prema vrednosti koju oni donose u vaše poslovanje. Dakle, samo se stopa uspešnosti predviđanja klijenata velike vrednosti koristi za izvođenje konačne klase modela. RMSE metrika je osetljiva na izvanredne vrednosti. U scenarijima gde imate mali procenat klijenata sa izuzetno visokim vrednostima kupovine, ukupna RMSE metrika možda neće dati potpunu sliku performansi modela.

[!INCLUDE [footer-include](includes/footer-banner.md)]
