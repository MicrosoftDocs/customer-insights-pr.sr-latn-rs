---
title: Analiza sentimenta za povratne informacije korisnika
description: Saznajte kako da koristite model analize sentimenta za povratne informacije klijenata u Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: b06613b00a512a31479f9d30d539a010e17d33ba
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231482"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analiziraj sentiment u povratnim informacijama klijenata (Pregled)

Kupce ovih dana očekuju visokokvalitetni proizvodi, usluge i iskustva. Naročito klijenti koji dele svoje povratne informacije. Veoma je izazovno za organizacije da analiziraju sve veći obim podataka bez smanjenja tačnosti i veće cene rada. Dynamics 365 Customer Insights nudi model analize sentimenta za povratne informacije klijenata koji omogućava organizacijama da preciznije i po nižoj ceni analiziraju svoje podatke.

Analiza sentimenta vam omogućava da sintetišete sentiment klijenata i identifikujete poslovne aspekte kao mogućnosti za poboljšanje. Ova funkcija "Uvidi kupaca" vam pomaže da razumete šta dobro funkcioniše i čime treba da se obratite. Fokusirajte se na najrelevantnije i najproimljivije oblasti poslovanja kako biste poboljšali iskustvo za svoje kupce. Na kraju, to vam može pomoći da pokrenete poslovne akcije koje omogućavaju iskustva koja rezultiraju visokim zadovoljstvom i lojalnošću klijenata.

## <a name="overview"></a>+Pregled

Funkcija analize sentimenta generiše dva izvedena uvida po ID-u kupca. Ocena sentimenta (od -5 do 5) i lista primenljivih poslovnih aspekata (oblasti poslovanja) zajedno vam pomažu da bolje razumete povratne informacije klijenata. 

Ove informacije vam mogu pomoći da postignete sledeće rezultate: 
- Pregled osećanja klijenata prema brendu ili organizaciji
- Identifikujte kupce sa negativnim sentimentom da fokusirate svoje kampanje i angažmane i optimizujete za veći povraćaj  
- Identifikovanje poslovnih aspekata sa problemima koje ukazuju klijenti  
- Korisnici segmenta na osnovu svog sentimenta da pokreću personalizovane kampanje sa ciljanom prodajom, marketingom i naporima podrške
- Optimizujte poslovanje tako što ćete se pozabaviti oblastima koje zabrinjavaju ili mogućnostima koje su pomenuli klijenti
- Prepoznajte poslovne aspekte koji dobro rade i nagradite srećne kupce kroz programe lojalnosti i promocije

Da bismo bili sigurni da možete da verujete rezultatima modela, pružamo transparentne informacije o tome kako modeli donose odluke. Dobićete listu reči koje su uticale na odluku modela da dodele određeni sentimentalni rezultat ili poslovni aspekt komentarima povratnih informacija.  

Koristimo dva modela **obrade prirodnog jezika (NLP).** Drugi model povezuje svaku povratnu informaciju sa svim primenljivim poslovnim aspektima. Modeli su obučeni za javne podatke iz izvora širom društvenih medija, maloprodaje, restorana, proizvoda široke potrošnje i automobilske industrije.    
  
Unapred definisani poslovni aspekti za model koji se povezuje sa podacima o povratnim informacijama uključuju:
-   Upravljanje poslovnim kontaktima
-   Završetak kupovine i plaćanje
-   Korisnička podrška
-   Preuzimanje u prodavnici
-   Isporuka i preuzimanje ambalaže
-   Prednaručivanje
-   Cena
-   Privatnost i bezbednost
-   Promocije i nagrade
-   Priznanica i garancija
-   Povraćaj, zamena i otkazivanje
-   Tačnost ispunjenja
-   Kvalitet veb-lokacije/aplikacije

> [!NOTE]
> Trenutno podržavamo samo analizu sentimenta na engleskim povratnim informacijama korisnika. Ubuduće će biti podržano više jezika. Ako se otpreme povratne informacije na drugim jezicima, model će ipak dati rezultate. Međutim, ovi rezultati neće biti tačni. 

## <a name="prerequisites"></a>Preduslovi

Analiza sentimenta se zasniva na podacima tekstualnih povratnih informacija koje su prošle kroz [proces ujedinjenja podataka](data-unification.md). Preporučujemo da unapred konfigurišete [entitete podataka povratnih informacija kao entitete aktivnosti semantičkog](map-entities.md#select-primary-key-and-semantic-type-for-attributes) tipa (tip povratnih informacija). 

Da biste konfigurisali model analize sentimenta, potrebno vam je [najmanje saradnik dozvole](permissions.md).

Uvidi klijenata mogu da obrade do 10 miliona zapisa povratnih informacija za jedan model koji se pokrene. Model može da analizira komentare povratnih informacija do 128 reči. Ako je komentar povratnih informacija duži, analiza smatra samo prvih 128 reči.

### <a name="data-requirements"></a>Zahtevi za podacima
  
Potrebni su sledeći atributi podataka:
- Objedinjeni ID kupca (UCID) da bi se zapisi podataka tekstualnih povratnih informacija podudarali sa pojedinačnim klijentom. Ovaj ID je rezultat procesa ujedinjenja [podataka](data-unification.md).
- ID povratnih informacija
- Vreme povratnih informacija
- Tekst povratnih informacija   

> [!TIP]
> Analiza sentimenta zahteva tekstualne povratne informacije vaših klijenata. Trenutno se može konfigurisati samo jedan entitet povratnih informacija. Ako postoji više entiteta povratnih informacija, možete ih uvesti pre Power Query nego što počne unos podataka.

## <a name="configure-a-sentiment-analysis"></a>Konfigurisanje analize sentimenta 

1. U usluzi Customer Insights, idite na **Obaveštavanje** > **Predviđanja**.

1. Na pločici **Analiza sentimenta kupca** izaberite stavku **Koristi model**.

1. U oknu **Analiza sentimenta kupca (pregled)** izaberite stavku Prvi **koraci**.

1. U koraku **imena** modela navedite ime **za** analizu. 

1. Navedite ime **izlaznog entiteta poslovnog aspekta i** ime izlaznog **entiteta rezultata sentimenta, a zatim** kliknite na dugme **Dalje**.

1. U koraku **Potrebni podaci izaberite** stavku Dodaj **podatke**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Dodajte protok podataka u model analize sentimenta.":::

1. U oknu **za dodavanje** podataka odaberite semantički tip Povratne **informacije** sa liste.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Korak konfiguracije za izbor aktivnosti povratnih informacija za analizu sentimenta.":::

1. Izaberite aktivnosti koje ćete koristiti za ovu analizu sentimenta, a zatim kliknite na dugme **Dalje**.
 
1. Mapirajte atribute u podacima na atribute modela. Kliknite **na dugme** "Sačuvaj" da biste primenili izbore. 

1. Videćete status mapiranja podataka. Izaberite **Dalje** za nastavak. 

1. U koraku **Pregledajte detalje modela**, proverite valjanost konfiguracije analize sentimenta. Možete da se vratite na bilo koji deo predviđanje konfiguracije. Izaberite **stavku Sačuvaj i pokreni** da biste započeli analizu. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Redigujte korak za model sentimenta koji prikazuje sve konfigurisane stavke.":::

1. Kliknite na **dugme "** Gotovo" da biste ostavili iskustvo konfigurisanja. Dovršavanje procesa može potrajati nekoliko sati u zavisnosti od količine korišćenih podataka. 

## <a name="review-analysis-status"></a>Pregled statusa analize

1.  Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.
2.  Izaberite predviđanje koje želite da pregledate.
- **Naziv predviđanja**: Naziv predviđanja naveden pri njegovom kreiranju.
- **predviđanje:** Tip modela koji se koristi za predviđanje.
- **Izlazni entitet**: Naziv entiteta za skladištenje izlaza predviđanja. Idite na **Podaci** > **Entiteti** da pronađete entitet sa ovim nazivom.
- **Predviđeno polje**: Ovo polje je popunjeno samo za neke tipove predviđanja i ne koristi se za predviđanje vrednosti trajne vrednosti klijenta.
- **Status**: Status pokretanja predviđanja.
  - **Stavljeno u red**: Predviđanje čeka da se drugi procesi završe.
  - **Osvežavanje**: Predviđanje je trenutno pokrenuto da bi kreiralo rezultate koji će biti prosleđeni u izlazni entitet.
  - **Nije uspelo**: Pokretanje predviđanja nije uspelo. Detaljnije informacije potražite u evidenciji.
  - **Uspelo je**: Predviđanje je uspelo. Izaberite Prikaz ispod uspravne tri tačke da biste pregledali rezultate predviđanja.
- **Izmenjeno:** Datum promene konfiguracije predviđanja.
- **Poslednji put osvežen**: Datum kada predviđanje je osvežio rezultate u izlaznom entitetu.

## <a name="manage-sentiment-analysis"></a>Upravljanje analizom sentimenta

Možete da optimizujete, rešite probleme, osvežite ili izbrišete predviđanja. Pregledajte izveštaj o upotrebljivosti ulaznih podataka da biste saznali kako da predviđanje učinite bržim i pouzdanijim. Još informacija potražite u članku [Upravljanje predviđanjima](manage-predictions.md).

## <a name="review-analysis-results"></a>Pregled rezultata analize
 
1. Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**. 
1. Izaberite ime stavke predviđanje želite da pregledate rezultate. U ovom slučaju izaberite analizu sentimenta koju želite da pregledate. 

### <a name="summary-tab"></a>Kartica rezimea

Unutar stranice sa rezultatima postoje četiri primarna odeljka podataka. 

- **Prosečan rezultat sentimenta**: Pomaže vam da razumete celokupan sentiment u svim kupcima. Rezultati sentimenta su grupisani u tri kategorije: 
  1.    Negativno (-5 > 2)
  2.    Neutralan (-1 > 1)
  3.    Pozitivno (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Vizuelni prikaz celokupnog osećaja klijenta.":::

- **Distribucija kupaca po sentimentalnom rezultatu**: Kupci se kategorišu u negativne, neutralne i pozitivne grupe na osnovu ocena sentimenta. Zadržite pokazivač iznad rešetaka u histogramu da biste videli broj kupaca i prosečnu ocenu sentimenta u svakoj grupi. Ove podatke vam mogu pomoći da [kreirate segmente klijenata na](segments.md) osnovu njihovih ocena sentimenta.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="trakasti grafikon pokazuje osećaj kupca u tri sentimentalne grupe.":::

- **Prosečna ocena sentimenta tokom vremena**: Sentiment kupca se može vremenom promeniti. Obezbeđujemo trendove u osećanjima vaših klijenata za vremenski opseg vaših podataka. Ovaj prikaz vam može pomoći da procenite efekat sezonskih promocija, lansiranja proizvoda ili drugih vremenskih intervencija na sentiment kupca. Pogledajte grafikon tako što ćete izabrati godinu interesovanja iz padajućeg menija. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="grafikon istorije sa sentimentalnim rezultatom vremenom predstavljenim kao linija.":::
 
- **Sentiment u poslovnim aspektima**: Ova tabela navodi prosečan sentiment u poslovnim aspektima. To vam može pomoći da procenite koji aspekti vašeg poslovanja već zadovoljavaju kupce ili aspekte koji zahtevaju više pažnje. Zapisi sa povratnim informacijama koji se ne poravnavaju ni sa jednom od podržanih poslovnih aspekata kategorisani su u okviru " **Ostalo"**. Tabela je podrazumevano sortirana po abecednom redu. Sortiranje možete izmeniti izborom zaglavlja tabele.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lista poslovnih aspekata sa povezanim vrednost raspoloženja i brojem kupaca koji ga pominju.":::
 
  Izaberite ime poslovnog aspekta da biste videli dodatne informacije o tome kako je model identifikovao poslovni aspekt. U ovom oknu postoje dva dela: 

  - **Uticajne reči**: Prikazuje glavne reči koje su uticale na identifikaciju poslovnog aspekta AI modela u povratnim informacijama klijenata. 
    **Prikaži uvredljive reči**: Omogućava vam da uključite uvredljive reči na listu iz originalnih podataka za povratne informacije korisnika. Podrazumevano je isključen.  Uvredljivo maskiranje reči napaja se AI modelom i možda neće otkriti sve uvredljive reči. Nastavljamo iteriranje i obuku klasifikatora za optimalne performanse. Ako otkrijete uvredljivu reč koja nije filtrirana kao što se očekivalo, obavestite nas. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Lista uticajnih reči sa preklopnikom za prikazivanje ili skrivanje uvredljivih reči.":::
 
  - **Uzorci povratnih informacija**: Prikazuje stvarne zapise povratnih informacija u podacima. Reči su obojene u skladu sa njihovim uticajem na identifikaciju poslovnog aspekta. 


### <a name="influential-words-analysis-tab"></a>Kartica "Analiza uticajnih reči"

Postoje tri odeljka dodatnih informacija koji objašnjavaju kako funkcioniše model sentimenta.
  
1. **Vrhunske reči koje doprinose pozitivnom sentimentu**: Prikazuje vrhunske reči koje su uticale na identifikaciju pozitivnog sentimenta AI modela u povratnim informacijama korisnika.  
2. **Vrhunske reči koje doprinose negativnom sentimentu**: Prikazuje vrhunske reči koje su uticale na identifikaciju negativnog sentimenta AI modela u povratnim informacijama korisnika.  
3. **Uzorci povratnih informacija**: Prikazuje stvarne zapise povratnih informacija, jedan sa negativnim osećajem i drugi sa pozitivnim osećanjima. Reči u zapisima povratnih informacija su istaknute u skladu sa njihovim doprinosom dodeljenom rezultatu sentimenta. Reči koje doprinose pozitivnom rezultatu sentimenta istaknute su zelenom. Reči koje doprinose negativnom rezultatu istaknute su crvenom bojom.
   Izaberite **pogledajte više** da biste učitali više uzoraka povratnih informacija koji pružaju više informacija i konteksta načina na koji funkcioniše model sentimenta.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Primeri analize sentimenta na povratnim informacijama klijenata.":::
 
**Prikaži uvredljive reči**: Omogućava vam da uključite uvredljive reči na listu iz originalnih podataka za povratne informacije korisnika. Podrazumevano je isključen.  Uvredljivo maskiranje reči napaja se AI modelom i možda neće otkriti sve uvredljive reči. Nastavljamo iteriranje i obuku klasifikatora za optimalne performanse. Ako otkrijete uvredljivu reč koja nije filtrirana kao što se očekivalo, obavestite nas. 

## <a name="act-on-analysis-results"></a>Akt o rezultatima analize

Možete lako početi da kreirate nove segmente kupaca sa stranice sa rezultatima analize sentimenta tako što ćete **izabrati stavku Kreiraj segmente** na vrhu stranice sa rezultatima modela.

:::image type="content" source="media/create-segment-model.png" alt-text="Komandna traka sa opcijama na predviđanje modelima.":::
 
## <a name="potential-bias"></a>Potencijalna pristrasnost

Kao i kod svake funkcije koja koristi prediktivnu veštačku inteligenciju, trebalo bi da budete svesni potencijalne pristrasnosti u podacima koje koristite za predviđanje sentimenta korisnika. Na primer, ako samo digitalno prikupljate povratne informacije, možete da propustite povratne informacije klijenata koji prvenstveno lično posluju sa vama, što može da utiče na izlaz funkcije.

Kako ova funkcija koristi automatizovana sredstva za procenu podataka i pravljenje predviđanja na osnovu tih podataka, ona stoga ima mogućnost da se koristi kao metod profilisanja, jer je taj pojam definisan Opštom uredbom o zaštiti podataka ("GDPR"). Vaša upotreba ove funkcije za obradu podataka može biti predmet GDPR-a ili drugih zakona ili propisa. Vi ste odgovorni da obezbedite Dynamics 365 Customer Insights da vaša upotreba, uključujući analizu sentimenta, bude u skladu sa svim važećim zakonima i propisima, uključujući zakone vezane za privatnost, lične podatke, biometrijske podatke, zaštitu podataka i poverljivost komunikacija.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

