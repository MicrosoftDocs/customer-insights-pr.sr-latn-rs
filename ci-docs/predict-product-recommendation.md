---
title: Predvidite preporuke za proizvode
description: Predvidite proizvode koje će klijent verovatno kupiti ili stupiti u interakciju sa njima.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610299"
---
# <a name="predict-product-recommendations"></a>Predvidite preporuke za proizvode

Model preporuke proizvoda kreira skupove prediktivnih preporuka proizvoda. Preporuke se zasnivaju na prethodnom ponašanju kupovine i klijentima sa sličnim obrascima kupovine. Ovaj model je za pojedinačne potrošače (B-to-C).

Morate imati poslovno znanje o različitim tipovima proizvoda za vaše poslovanje i načinu na koji vaši klijenti komuniciraju sa njima. Podržavamo preporučivanje proizvoda koje su prethodno kupili vaši klijenti ili preporuke za nove proizvode.

Preporuke za proizvode mogu da podležu lokalnim zakonima i propisima i očekivanjima klijenata, pri čemu model nije napravljen da bi ih posebno uzeo u obzir. Zbog toga morate da **pregledate preporuke pre nego što ih dostavite kupcima** da biste se uverili da se pridržavate važećih zakona ili propisa i očekivanja klijenata u pogledu onoga što možete da preporučite.

Izlaz ovog modela daje preporuke zasnovane na ID-u proizvoda. Vaš mehanizam isporuke mora da mapira predviđene ID-ove proizvoda na odgovarajući sadržaj da bi vaši klijenti odgovarali lokalizaciji, sadržaju slike i drugom sadržaju ili ponašanju specifičnom za poslovanje.

> [!TIP]
> Isprobajte preporuku proizvoda predviđanje probne podatke: preporuka [proizvoda predviđanje probni vodič](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Preduslovi

- [Najmanje saradnik dozvole](permissions.md)
- Najmanje 100 kupaca, po mogućstvu više od 10.000 kupaca.
- Identifikator kupca, jedinstveni identifikator za podudaranje transakcija sa pojedinačnim kupcem
- Najmanje godinu dana transakcionih podataka, po mogućstvu dve do tri godine kako bi se uključila neka sezonalnost. U idealnom uslovima, najmanje tri ili više transakcija po ID-u kupca. Istorija transakcija mora da sadrži:
  - **ID transakcije**: Jedinstveni identifikator nabavke ili transakcije.
  - **Datum transakcije**: Datum nabavke ili transakcije.
  - **Vrednost transakcije**: Numerička vrednost nabavke ili transakcije.
  - **Jedinstveni ID proizvoda**: ID proizvoda ili usluge kupljene ako su podaci na nivou stavke predmeta.
  - **Nabavka ili povraćaj**: Logička vrednost true/false gde *true* identifikuje da je transakcija bila povraćaj. Ako podaci o nabavci ili povraćaju nisu navedeni u modelu **, a vrednost transakcije** je negativna, nalaћemo povraćaj.
- Entitet podataka kataloga proizvoda koji će se koristiti kao filter proizvoda.

> [!NOTE]
> - Model zahteva istoriju transakcija klijenata gde je transakcija bilo koji podatak koji opisuje interakciju korisnika i proizvoda. Na primer, kupovina proizvoda, pohađanje predavanja ili prisustvovanje događaju.
> - Samo jedan entitet istorije transakcija može da se konfiguriše. Ako postoji više entiteta nabavke, kombinujte ih pre Power Query brisanja podataka.
> - Ako su detalji porudžbine i naloga različiti entiteti, pridružite im se pre upotrebe u modelu. Model ne radi samo sa ID-om porudžbine ili ID-om priznanice u entitetu.

## <a name="create-a-product-recommendation-prediction"></a>Kreiranje predviđanja preporuke proizvoda

U **svakom trenutku izaberite** stavku Sačuvaj radnu verziju da biste sačuvali predviđanje kao radnu verziju. Radna verzija predviđanje na kartici "**Moja predviđanja**".

1. Idite na **obaveštajna** > **predviđanja**.

1. Na kartici **Kreiranje** izaberite stavku **Koristi model** na pločici **"Preporuke proizvoda** (pregled)".

1. Izaberite **Prvi koraci**.

1. **Dajte ime ovom modelu** i **Izlazni naziv entiteta** da ih razlikujete od ostalih modela ili entiteta.

1. Izaberite **Sledeće**.

### <a name="define-product-recommendation-preferences"></a>Definisanje željenih opcija preporuke proizvoda

1. Podesite **broj proizvoda koji** ćete preporučiti kupcu. Ova vrednost zavisi od toga kako način isporuke popunjava podatke.

1. Odaberite da li želite da uključite proizvode koje su kupci prethodno kupili u polje Ponavljanje **očekivanih nabavki**.

1. Postavite **prozor "Pogledaj unazad**" sa vremenski okvir model uzme u obzir pre nego što ponovo preporučite proizvod korisniku. Na primer, naznačite da klijent kupuje prenosni računar svake dve godine. Model gleda istoriju kupovine poslednje dve godine, a ako pronađe artikal, artikal se filtrira iz preporuka.

1. Izaberite **Sledeće**

### <a name="add-purchase-history"></a>Dodavanje prethodnih kupovina

1. Izaberite opciju **Dodaj podatke** za istoriju **transakcija kupca**.

1. Izaberite vrstu semantičke aktivnosti **"Linija prodavca"** koja sadrži potrebne informacije o istoriji transakcije ili nabavke. Ako aktivnost nije podešena, izaberite je **ovde i** kreirajte je.

1. U **okviru** Aktivnosti, ako su atributi aktivnosti semantički mapirani prilikom kreiranja aktivnosti, odaberite određene atribute ili entitet na koji želite da se izračunavanje fokusira. Ako nije došlo do semantičkog mapiranja, izaberite opciju Uredi **i** mapiraj svoje podatke.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Bočno okno prikazuje odabir određenih aktivnosti prema semantičkom tipu.":::

1. Kliknite **na** dugme "Dalje" i pregledajte atribute potrebne za ovaj model.

1. Izaberite **Sačuvaj**.

1. Izaberite **Sledeće**.

### <a name="add-product-information-and-filters"></a>Dodavanje informacija o proizvodu i filtera

Ponekad su samo određeni proizvodi korisni ili prikladni za tip predviđanja koji gradite. Koristite filtere proizvoda da biste identifikovali podskup proizvoda sa određenim karakteristikama koje ćete preporučiti kupcima. Model će koristiti sve dostupne proizvode za učenje obrazaca, ali u izlazu koristi samo proizvode koji se podudaraju sa filterom proizvoda.

1. Dodajte entitet kataloga proizvoda koji sadrži informacije za svaki proizvod. Mapiraj potrebne informacije i izaberi dugme **Sačuvaj**.

1. Izaberite **Sledeće**.

1. Izaberite **filtere proizvoda**:

   - **Bez filtera**: Koristite sve proizvode u predviđanju preporuke za proizvod.

   - **Definišite određene filtere proizvoda**: Koristite određene proizvode u preporuci predviđanja za proizvod. U oknu **atributa kataloga** proizvoda izaberite atribute iz entiteta kataloga proizvoda koje želite da uključite u filter.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Bočno okno prikazuje atribute u entitetu kataloga proizvoda da biste ih izabrali za filtere proizvoda.":::

1. Odaberite da li želite da filter proizvoda **koristi** i **ili** da logično kombinujete izbor atributa iz kataloga proizvoda.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Primer konfiguracije filtera proizvoda u kombinaciji sa logičkim I konektorima.":::

1. Izaberite **Sledeće**.

### <a name="set-update-schedule"></a>Podešavanje rasporeda ažuriranja

1. Odaberite frekvenciju za prekvalifikaciju modela. Ova postavka je važna za ažuriranje tačnosti predviđanja jer se novi podaci unose u uvide klijenata. Većina preduzeća može da obavi ponovnu obuku jednom mesečno i dobije precizna predviđanja.

1. Izaberite **Sledeće**.

### <a name="review-and-run-the-model-configuration"></a>Pregledajte i pokrenite konfiguraciju modela

Korak **"Rediguj** i pokreni" prikazuje rezime konfiguracije i pruža šansu za promene pre nego što kreirate predviđanje.

1. Izaberite **stavku Uredi** na bilo kom koraku da biste redigoli i napravili bilo kakve promene.

1. Ako ste zadovoljni izborom, izaberite sačuvaj i pokreni **da biste počeli** da pokrenete model. Izaberite **Gotovo**. Kartica **"Moja predviđanja**" prikazuje se predviđanje se kreira sadržaj. Za završetak procesa može biti potrebno nekoliko sati, u zavisnosti od količine podataka korišćenih u predviđanju.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prikaži predviđanje rezultate

1. Idite na **obaveštajna** > **predviđanja**.

1. Na kartici **Moja predviđanja** izaberite predviđanje želite da prikažete.

Postoji pet primarnih odeljaka podataka unutar stranice sa rezultatima.

- **Performanse modela:** Ocene A, B ili C ukazuju na performanse predviđanje-a i mogu vam pomoći da donesete odluku o korišćenju rezultata uskladištenih u izlaznom entitetu.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Slika rezultata performansi modela sa ocenom A.":::

  Klase se određuju na osnovu sledećih pravila:
  - **A** kada je metrika "Uspeh @ K" najmanje 10% više od osnovne linije.
  - **B** kada je metrika "Uspeh @ K" 0% do 10% više od osnovne linije.
  - **C** kada je metrika "Uspeh @ K" manja od osnovne linije.
  - **Osnovna** linija: Naj preporučeniji proizvodi po broju kupovina u svim kupcima + naučena pravila identifikovana po modelu = skup preporuka za kupce. Zatim se predviđanja upoređuju sa najboljim proizvodima, što se izračunava kao broj klijenata koji su kupili proizvod. Ako klijent ima barem jedan proizvod u preporučenim proizvodima koji se takođe nalazi među najpopularnijim kupljenim proizvodima, smatra se delom osnovne vrednosti. Na primer, ako je 10 ovih kupaca imalo preporučeni proizvod kupljen od ukupno 100 kupaca, osnovna linija je 10%.
  - **Uspeh @ K**: Preporuke se kreiraju za sve kupce i porede sa skupom provera valjanosti vremenskog perioda transakcija. Na primer, u periodu od 12 meseci, mesec 12 se izdvaja kao skup podataka za proveru valjanosti. Ako model predvidi bar jednu stvar koju biste kupili u 12. mesecu na osnovu onoga što je naučio iz prethodnih 11 meseci, klijent bi povećao metriku „Uspeh @ K“.

- **Najviše predlagani proizvodi (sa rezultatom):** Pet najboljih proizvoda koji su predviđeni za vaše klijente.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Grafikon koji prikazuje najboljih 5 preporučenih proizvoda.":::

- **Ključni faktori preporuke:** Model koristi istoriju transakcija klijenata za davanje preporuka za proizvode. Model uči obrasce zasnovane na prošlim kupovinama i pronalazi sličnosti između klijenata i proizvoda. Te sličnosti se zatim koriste za generisanje preporuka za proizvode.
  Sledeći faktori mogli bi da utiču na preporuku proizvoda koju generiše model.
  - **Prethodne transakcije**: Preporučeni proizvod se zasnivao na ranijim obrascima nabavke. Na primer, model može da preporuči *Surface Arc miša* ako je neko nedavno kupio *Surface Book 3* i *Surface olovku*. Model je saznao da su u prošlosti mnogi klijenti kupili *Surface Arc miša* kada su kupili *Surface Book 3* i *Surface olovku*.
  - **Sličnost klijenata**: Preporučeni proizvod u prošlosti su kupovali drugi klijenti koji pokazuju slične obrasce kupovine. Na primer, Jovanu su preporučene *slušalice Surface Headphones 2* jer su Snežana i Branko nedavno kupili *slušalice Surface Headphones 2*. Model veruje da je Jovan sličan sa Snežanom i Brankom, jer su u oni prošlosti imali slične obrasce kupovine.
  - **Sličnost proizvoda**: Preporučeni proizvod je sličan ostalim proizvodima koje je klijent prethodno kupio. Model smatra da su dva proizvoda slična ako su kupljeni zajedno ili su ih kupili slični klijenti. Na primer, neko dobije preporuku za *USB memorijski uređaj* jer je prethodno kupio *adapter USB-C na USB*, a model veruje da je *USB memorijski uređaj* sličan *adapteru USB-C na USB* na osnovu istorijskih obrazaca kupovine.

  Na svaku preporuku proizvoda utiče jedan ili više ovih faktora. Procenat preporuka u kojima je svaki uticajni faktor igrao ulogu prikazan je na grafikonu. U sledećem primeru, na 100% preporuka su uticale prošle transakcije, 60% sličnost klijenata i 22% sličnost proizvoda. Pređite kursorom preko traka na grafikonu da biste videli tačan procenat doprinosa faktora uticaja.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Ključni faktori preporuke koje je model naučio za generisanje preporuka proizvoda.":::

- **Statistika podataka**: Pregled broja transakcija, kupaca i proizvoda koje je model razmotrio. Zasniva se na ulaznim podacima koji su korišćeni za učenje obrazaca i generisanje preporuka za proizvode.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Statistika podataka oko ulaznih podataka koje model koristi za učenje šablona.":::
  
  Model koristi sve dostupne podatke za učenje šablona. Zbog toga, ako filtriranje proizvoda koristite u konfiguraciji modela, ovaj odeljak prikazuje ukupan broj proizvoda koje je model analizirao da bi naučio obrasce, a koji se mogu razlikovati od broja proizvoda koji odgovaraju definisanim kriterijumima filtriranja. Filtriranje se primenjuje na izlaz koji generiše model.

- **Probne preporuke proizvoda:** Uzorak preporuka za koje model veruje da će verovatno biti kupljen od strane kupca. Ako se doda katalog proizvoda, ID-ove proizvoda se zamenjuju imenima proizvoda.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Lista koja prikazuje predloge sa visokom pouzdanošću za izabrani skup pojedinačnih klijenata.":::

> [!NOTE]
> U izlaznom entitetu za ovaj model, *Score prikazuje* kvantitativnu meru preporuke. Model preporučuje proizvode sa višom ocenom u odnosu na proizvode sa nižom ocenom. Da biste prikazali rezultat, idite na **entitete** > **podataka** i prikažite karticu sa podacima za izlazni entitet koji ste definisali za ovaj model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
