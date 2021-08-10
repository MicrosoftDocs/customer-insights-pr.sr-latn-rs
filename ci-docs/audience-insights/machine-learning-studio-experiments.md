---
title: Machine Learning Studio (klasični) eksperimenti
description: Koristite modele Machine Learning Studio (klasični) u usluzi Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2eb44604e72b32292f971754d4f8c4fd1988c697
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555186"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Koristite modele koji se zasnivaju na usluzi Azure Machine Learning Studio (klasični)

Objedinjeni podaci u usluzi Dynamics 365 Customer Insights jesu izvor za izgradnju modela mašinskog učenja koji mogu stvoriti dodatne poslovne uvide. Customer Insights se integriše sa Machine Learning Studio (klasični) da bi koristio vaše prilagođene modele. Da biste videli kako se modeli razvijeni u Azure mašinskom učenju integrišu sa uslugom Customer Insights, pogledajte [Eksperimenti u Azure mašinskom učenju](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Preduslovi

- Pristup u Customer Insights
- Aktivna Azure Enterprise pretplata
- [Objedinjeni profil klijenta](data-unification.md)
- Podešavanje [izvoza entiteta u Azure skladište blob objekata](export-azure-blob-storage.md)

## <a name="set-up-machine-learning-studio-classic"></a>Podesite Machine Learning Studio Classic

U prvom koraku treba da kreiramo radni prostor i otvorimo Machine Learning Studio (klasični).

1. Idite na adresu[https://www.portal.azure.com](https://www.portal.azure.com/) i prijavite se.

1. Izaberite **Kreiraj resurs**.

1. Pretražite **Radni prostor studija za mašinsko učenje** i izaberite **Kreiraj**.

1. Unesite potrebne detalje u [kreiranje radnog prostora](/azure/machine-learning/studio/create-workspace). Izaberite **Nivo cena planova veb-usluga** na osnovu količine podataka koju planirate da uvezete. Za najbolje performanse, izaberite **lokaciju** koja vam je geografski najbliža.

1. Nakon kreiranja resursa, prikazaće se kontrolna tabla radnog prostora studija za mašinsko učenje. Izaberite **Pokrenite studio za mašinsko učenje**.

   ![Korisnički interfejs Azure studija za mašinsko učenje.](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Rad sa Azure studiom za mašinsko učenje

Sada možete da kreirate novi eksperiment ili uvezete postojeći predložak eksperimenta iz galerije uzoraka. Postoje uzorci eksperimenata za tri standardna scenarija:

- [Predviđanje odliva](#churn-analysis)

- [Trajna vrednost klijenta](#customer-lifetime-value-prediction)

- [Preporuka za proizvode ili sledeća najbolja radnja](#productrecommendation-or-next-best-action)

1. Ako kreirate novi eksperiment ili upotrebljavate predložak eksperimenta iz galerije, morate da konfigurišete svojstva za **Uvoz podataka**. Koristite vođeno iskustvo ili direktno navedite detalje za pristup Azure skladištu blob objekata koje sadrži vaše podatke.  

   ![Eksperiment sa Azure studiom za mašinsko učenje.](media/azure-machine-learning-studio-experiment.png)

1. Sada možete izgraditi prilagođeni kanal za obradu da biste obrisali i prethodno obradili podatke, izdvojili funkcije i obučili odgovarajući model.

1. Testirajte i optimizujte performanse modela.

1. Kada budete zadovoljni kvalitetom modela, izaberite **Podesite veb-uslugu** > **Veb-usluga predviđanja**. Ova opcija uvozi obučeni model i karakteristiku kanala od eksperimenta obuke do usluge predviđanja. Usluga predviđanja može uzeti drugi skup ulaznih podataka sa šemom koja se koristi u eksperimentu obuke da bi se napravila predviđanja.

   ![Postavljanje veb-usluge predviđanja.](media/predictive-webservice-control.png)

1. Kada eksperiment veb-usluge predviđanja bude uspešan, možete ga primeniti za automatsko zakazivanje. Da bi veb-usluga radila sa uslugom Customer Insights, izaberite **Primeni veb-uslugu** > **Pregled primene veb-usluge [Novo]**. [Saznajte više o primeni veb-usluge](/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Primena veb-usluge predviđanja.](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Modeli uzoraka iz galerije

Koristićemo fiktivni scenario Contoso hotela za modele u ovom članku. Contoso hotel prikuplja sledeće podatke:

- CRM podaci koji se sastoje od aktivnosti boravka u hotelu. Skup podataka sadrži informacije o datumima boravka za svakog registrovanog klijenta. Takođe sadrži informacije o rezervaciji, tipovima soba, detaljima potrošnje itd. Podaci se protežu kroz četiri godine, od januara 2014. do januara 2018. godine.
- Klijentski profili gostiju hotela. Ovi profili sadrže podatke o svakom klijentu, uključujući njihovo ime, datum rođenja, poštansku adresu, pol i broj telefona.
- Upotreba usluga koje nudi hotel, kao što su bazen, perionica, WiFi ili kurirska služba. Ove informacije se beleže za svakog registrovanog klijenta. Upotreba usluga je obično povezana sa boravkom. U nekim slučajevima, usluge mogu koristiti klijenti bez boravka u hotelu.

## <a name="churn-analysis"></a>Analiza odliva

Analiza odliva se odnosi na različite oblasti poslovanja. U ovom primeru, osvrnućemo se na odliv usluga, posebno u kontekstu hotelskih usluga kao što je gore opisano. Omogućava radni primer kanala celovitog modela koji se može koristiti kao početna tačka za bilo koji drugi model odliva.

### <a name="definition-of-churn"></a>Definicija odliva

Definicija odliva može se razlikovati na osnovu scenarija. U ovom primeru, gost koji nije posetio hotel u poslednjih godinu dana trebalo bi da bude označen kao odliv.  

Predložak eksperimenta se može uvesti iz galerije. Prvo obezbedite da uvezete podatke za **Aktivnost boravka u hotelu**, **Podaci o klijentu** i **Podaci o upotrebi usluge** iz skladišta Azure skladišta blob objekta.

   ![Uvoz podataka za model gubitka klijenata.](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Karakterizacija

Na osnovu definicije gubitka, prvo identifikujemo neobrađene funkcije koje će uticati na oznaku. Zatim obrađujemo ove sirove funkcije u numeričke funkcije koje se mogu koristiti sa modelima mašinskog učenja. Integracija podataka se dešava u usluzi Customer Insights tako da možemo pridružiti ove tabele pomoću *ID-a klijenta*.

   ![Pridružite uvezene podatke.](media/join-imported-data.png)

Karakterizacija za izradu modela za analizu odliva može biti pomalo problematična. Podaci su funkcija vremena sa svakodnevnim novim aktivnostima hotela. Tokom karakterizacije želimo da iz dinamičkih podataka stvorimo statičke funkcije. U ovom slučaju generišemo više funkcija iz hotelskih aktivnosti sa kliznim vremenskim okvirom od jedne godine. Takođe proširujemo funkcije kategorizacije poput vrste sobe ili vrste rezervacije u posebne funkcije koristeći kategorizovano kodiranje.  

Konačni spisak funkcija:

| **Broj**  | **Original_Column**          | **Izvedene funkcije**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Vrsta sobe                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Tip rezervacije                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Kategorija putovanja              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Potrošen novac                | TotalDollarSpent                                                                                                                          |
| 5           | Datumi prijavljivanja i odjavljivanja  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Korišćenje usluga                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Izbor modela

Sada treba da odaberemo optimalan algoritam koji ćemo koristiti. U ovom slučaju, većina funkcija se zasniva na kategoričkim funkcijama. Modeli zasnovani na stablu odluka obično dobro rade. Ako postoje samo numeričke funkcije, neuronske mreže bi mogle biti bolji izbor. Vektorska mašina za podršku (SVM) takođe je dobar kandidat u takvim situacijama; međutim, za izvlačenje najboljih performansi potrebno je prilično podešavanje. Mi biramo **Stablo odlučivanja pojačano sa dve klase** kao prvi model izbora koji je praćen sa **SVM u dve klase** kao drugi model. Azure studio za mašinsko učenje dozvoljava vam da obavite A/B testiranje, tako da je korisno početi sa dva modela, a ne sa jednim.

Sledeća slika prikazuje kanal obuke i ocenjivanja modela iz Azure studija za mašinsko učenje:

![Model gubitka klijenata u usluzi Azure Machine Learning Studio.](media/azure-machine-learning-model.png)

Takođe primenjujemo i tehniku pod nazivom **Značaj funkcije permutacije**, važan aspekt optimizacije modela. Ugrađeni modeli imaju malo ili nimalo uvida u uticaj bilo koje posebne funkcije na konačno predviđanje. Kalkulator važnosti funkcije koristi prilagođeni algoritam za izračunavanje uticaja pojedinih karakteristika na ishod određenog modela. Značaj funkcije je normalizovan između +1 i -1. Negativan uticaj znači da odgovarajuća karakteristika ima kontraintuitivni uticaj na ishod i da je treba ukloniti iz modela. Pozitivan uticaj ukazuje na to da funkcija značajno doprinosi predviđanju. Ove vrednosti nisu koeficijenti korelacije, jer su to različiti pokazatelji. Za više informacija pogledajte [Značaj funkcije permutacije](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Čitav [eksperiment odliva dostupan je u Azure AI Gallery](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Predviđanje vrednosti životnog veka klijenta

Proračun vrednosti životnog veka klijenta (CLTV) jedan je od ključnih pokazatelja koje preduzeće može koristiti za procenu i segmentiranje klijenata. Za hotelski posao, najvažnije je poznavanje klijenata. Na primer, razumevanje faktora koji čine dobre klijente predstavlja ključnu informaciju. To pomaže menadžmentu hotela da proceni na koje funkcije treba da se fokusiraju i poboljšaju ih kako bi zadovoljili svoje klijente sa visokom platežnom moći. Ove odluke mogu imati direktan uticaj na prodaju i zaradu.  

### <a name="definition-of-cltv"></a>Definicija vrednosti životnog veka klijenta

Za ovaj primer, vrednost životnog veka klijenta definišemo kao ukupni novčani iznos koji se očekuje da će klijent potrošiti u narednih 365 dana. Koristićemo podatke u poslednje tri godine za sve klijente da predvidimo ovu vrednost.

### <a name="featurization"></a>Karakterizacija

U ovom slučaju, karakterizacija će biti predstavljena upravo kao scenario odliva. Međutim, oznake i predviđene vrednosti se razlikuju od gore definisanih.

### <a name="model-selection"></a>Izbor modela

Predviđanje vrednosti životnog veka klijenta je regresioni problem, jer je predviđena vrednost je kontinuirana promenljiva pozitivne vrednosti. Na osnovu svojstava funkcije, biramo **Pojačana regresija stabla odlučivanja** kao jedan algoritam i **Regresija neuronske mreže** kao još jedan algoritam za obuku modela.

## <a name="product-recommendation-or-next-best-action"></a>Preporuka za proizvode ili sledeća najbolja radnja

Preporuka za proizvode u hotelskom scenariju tumači se kao preporuka usluga koje hotel nudi klijentima. Cilj je odabrati odgovarajuće usluge za klijente tako da njihova upotreba bude maksimalna. To je slično preporukama za filmove za korisnike usluga video strimovanja.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Definicija preporuke za proizvode ili sledeća najbolja radnja

Cilj definišemo kao maksimizovanje novčanog iznosa korišćenja usluga uz ponudu najboljih odgovarajućih usluga klijentima hotela korisnike u skladu sa njihovim interesovanjima.

### <a name="featurization"></a>Karakterizacija

Poput modela odliva, povezujemo ServiceCustomerID za hotel sa parametrom CustomerID kako bismo izgradili preporuke dosledno po parametru CustomerID.

![Karakterizacija modela preporuka.](media/azure-machine-learning-model-featurization.png)

Podaci se dobijaju iz tri različita entiteta i od njih su izvedene funkcije. Karakteristika za problem preporuke različita je u poređenju sa scenarijima odliva ili vrednosti životnog veka klijenta. Modelu preporuka su potrebni ulazni podaci u obliku tri skupa funkcija.

### <a name="model-selection"></a>Izbor modela

Predviđamo proizvode ili usluge koristeći algoritam koji se zove **Train Matchbox Recommender** za obuku modela preporuka.

![Algoritam preporuka za proizvode.](media/azure-machine-learning-model-recommendation-algorithm.png)

Tri ulaza za model **Train Matchbox Recommender** sadrži podatke o korišćenju usluge obuke, opis klijenta (opcionalno) i opis usluge. Postoje tri različita načina bodovanja modela. Jedan je za evaluaciju modela gde se za rangiranje ocenjenih predmeta izračunava Normalizovani diskontni kumulativni dobitak (NDCG). U ovom eksperimentu imamo NDCG ocenu 0,97. Druge dve opcije su ocenjivanje modela u celom preporučenom katalogu usluga ili samo ocenjivanje predmeta koje korisnici ranije nisu koristili.

Gledajući dalje na distribuciju preporuka u čitavom katalogu usluga, primećujemo da su telefon, WiFi i kurirska služba najbolje usluge koje se preporučuju. To je u skladu sa onim što smo pronašli iz distribucije podataka o potrošnji usluga:

![Izlaz modela preporuke.](media/azure-machine-learning-model-output.png)

Celom [eksperimentu preporuke proizvoda može se pristupiti u Azure AI Gallery.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integracija prilagođenih modela

Da biste koristili ta predviđanja u usluzi Customer Insights, morate da **izvezete** predviđanja zajedno sa ID-ovima klijenata. [Izvezite ih na istu lokaciju Azure skladišta blob objekata](/azure/storage/common/storage-import-export-data-from-blobs) na koju izvozite izvorne podatke. Veb-usluga predviđanja može se redovno prikazivati i ažurirati ocene.

Podaci koje generiše prilagođeni model mogu se koristiti za dodatno obogaćivanje podataka o klijentima. Za više informacija pogledajte [Prilagođeni modeli mašinskog učenja](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]