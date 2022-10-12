---
title: Analiza sentimenta za povratne informacije korisnika (pregled)
description: Saznajte kako da koristite model analize sentimenta za povratne informacije klijenata u Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610483"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analizirajte sentiment u povratnim informacijama klijenata (pregled)

Analiza sentimenta vam omogućava da sintetišete sentiment klijenata i identifikujete poslovne aspekte kao mogućnosti za poboljšanje. Ova funkcija "Uvidi kupaca" vam pomaže da razumete šta dobro funkcioniše i čime treba da se obratite. Može vam pomoći da pokrenete poslovne akcije koje omogućavaju iskustva koja rezultiraju visokim zadovoljstvom i lojalnošću klijenata.

## <a name="overview"></a>+Pregled

Funkcija analize sentimenta generiše dva izvedena uvida po ID-u kupca. Ocena sentimenta (od -5 do 5) i lista primenljivih poslovnih aspekata (oblasti poslovanja) koji vam zajedno pomažu da bolje razumete povratne informacije klijenata.

Ova analiza vam pomaže:
- Pregled osećanja klijenata prema brendu ili organizaciji
- Identifikujte kupce sa negativnim sentimentom da fokusirate svoje kampanje i angažmane i optimizujete za veći povraćaj  
- Identifikovanje poslovnih aspekata sa problemima koje ukazuju klijenti  
- Korisnici segmenta na osnovu svog sentimenta da pokreću personalizovane kampanje sa ciljanom prodajom, marketingom i naporima podrške
- Optimizujte poslovanje tako što ćete se pozabaviti oblastima koje zabrinjavaju ili mogućnostima koje su pomenuli klijenti
- Prepoznajte poslovne aspekte koji dobro rade i nagradite srećne kupce kroz programe lojalnosti i promocije

Model pruža listu reči koje su uticale na odluku modela da dodeli određeni sentimentalni rezultat ili poslovni aspekt komentarima povratnih informacija.  

Koristimo dva modela **obrade prirodnog jezika (NLP).** Drugi model povezuje svaku povratnu informaciju sa svim primenljivim poslovnim aspektima. Modeli su obučeni za javne podatke iz izvora širom društvenih medija, maloprodaje, restorana, proizvoda široke potrošnje i automobilske industrije.
  
Unapred definisani poslovni aspekti za model koji se povezuje sa podacima o povratnim informacijama uključuju:
- Upravljanje poslovnim kontaktima
- Završetak kupovine i plaćanje
- Korisnička podrška
- Preuzimanje u prodavnici
- Isporuka i preuzimanje ambalaže
- Prednaručivanje
- Cena
- Privatnost i bezbednost
- Promocije i nagrade
- Priznanica i garancija
- Povraćaj, zamena i otkazivanje
- Tačnost ispunjenja
- Kvalitet veb-lokacije/aplikacije

> [!NOTE]
> Trenutno podržavamo samo analizu sentimenta na engleskim povratnim informacijama korisnika. Ubuduće će biti podržano više jezika. Ako se otpreme povratne informacije na drugim jezicima, model će ipak dati rezultate. Međutim, ovi rezultati neće biti tačni.

## <a name="prerequisites"></a>Preduslovi

- [Najmanje saradnik dozvole](permissions.md)
- [Objedinjeni](data-unification.md) podaci za povratne informacije teksta. Preporučujemo da entitete podataka povratnih [informacija konfigurišete kao entitete aktivnosti semantičkog tipa](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (tip povratnih informacija).
- Objedinjeni ID kupca (UCID) iz ujedinjenja podataka da bi se zapisi podataka tekstualnih povratnih informacija podudarali sa pojedinačnim klijentom.
- ID povratnih informacija
- Vreme povratnih informacija
- Tekst povratnih informacija

Uvidi klijenata mogu da obrade do 10 miliona zapisa povratnih informacija za jedan model koji se pokrene. Model može da analizira komentare povratnih informacija do 128 reči. Ako je komentar povratnih informacija duži, analiza smatra samo prvih 128 reči.

> [!NOTE]
> Samo jedan entitet povratnih informacija može da se konfiguriše. Ako postoji više entiteta povratnih informacija, kombinujte ih Power Query pre unošenja podataka.

## <a name="configure-a-sentiment-analysis"></a>Konfigurisanje analize sentimenta

1. Idite na **obaveštajna** > **predviđanja**.

1. Na kartici **Kreiranje** izaberite stavku Korišćenje **modela** na pločici **Analiza sentimenta kupca (pregled**).

1. Izaberite **Prvi koraci**.

1. **Imenuj** analizu i navedi ime **izlaznog entiteta poslovnog aspekta** i ime **izlaznog entiteta rezultata sentimenta**.

1. Izaberite **Sledeće**.

1. Izaberite opciju **Dodaj podatke** za povratne **informacije kupca**.

1. Izaberite tip semantičke aktivnosti Povratne informacije **koje** sadrže podatke o povratnim informacijama. Ako aktivnost nije podešena, izaberite je **ovde i** kreirajte je.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Korak konfiguracije za izbor aktivnosti povratnih informacija za analizu sentimenta.":::

1. Izaberite aktivnosti koje ćete koristiti za ovu analizu sentimenta, a zatim kliknite na dugme **Dalje**.

1. Mapirajte atribute u podacima na atribute modela. 

1. Izaberite **Sačuvaj**.

1. Izaberite **Sledeće**. Korak **"Rediguj** i pokreni" prikazuje rezime konfiguracije i pruža šansu za promene pre kreiranja analize.

1. Izaberite **stavku Uredi** na bilo kom koraku da biste redigoli i napravili bilo kakve promene.

1. Ako ste zadovoljni izborom, izaberite sačuvaj i pokreni **da biste počeli** da pokrenete model. Izaberite **Gotovo**. Kartica **"Moja predviđanja**" prikazuje se predviđanje se kreira sadržaj. Za završetak procesa može biti potrebno nekoliko sati, u zavisnosti od količine podataka korišćenih u predviđanju.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Prikaz rezultata analize

1. Idite na **obaveštajna** > **predviđanja**.

1. Na kartici **Moja predviđanja** izaberite predviđanje želite da prikažete.

Postoje dve kartice rezultata.

### <a name="sumary-tab"></a>Kartica "Šumarstvo"

Unutar stranice sa rezultatima postoje četiri primarna odeljka podataka.

- **Prosečna ocena sentimenta**: Sentimentalne ocene vam pomažu da razumete celokupan osećaj u svim klijentima.
  - **Negativno** (-5 > 2)
  - **Neutralan** (-1 > 1)
  - **Pozitivno** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Vizuelni prikaz celokupnog osećaja klijenta.":::

- **Distribucija kupaca po sentimentalnom rezultatu**: Kupci se kategorišu u negativne, neutralne i pozitivne grupe na osnovu ocena sentimenta. Zadržite pokazivač iznad rešetaka u histogramu da biste videli broj kupaca i prosečnu ocenu sentimenta u svakoj grupi. Ove podatke vam mogu pomoći da [kreirate segmente klijenata na](prediction-based-segment.md) osnovu njihovih ocena sentimenta.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="trakasti grafikon pokazuje osećaj kupca u tri sentimentalne grupe.":::

- **Prosečna ocena sentimenta tokom vremena**: Sentiment kupca se može vremenom promeniti. Obezbeđujemo trendove u osećanjima vaših klijenata za vremenski opseg vaših podataka. Ovaj prikaz vam pomaže da procenite efekat sezonskih promocija, lansiranja proizvoda ili drugih vremenskih intervencija na sentiment kupca. Pogledajte grafikon tako što ćete izabrati godinu interesovanja iz padajućeg menija.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="grafikon istorije sa sentimentalnim rezultatom vremenom predstavljenim kao linija.":::

- **Sentiment u poslovnim aspektima**: Prosečan sentiment u poslovnim aspektima vam pomaže da procenite koji aspekti vašeg poslovanja već zadovoljavaju kupce ili zahtevaju više pažnje. Zapisi sa povratnim informacijama koji se ne poravnavaju ni sa jednom od podržanih poslovnih aspekata kategorisani su u okviru " **Ostalo"**. Sortiraj podatke tako što ćeš izabrati bilo koju kolonu.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lista poslovnih aspekata sa povezanim vrednost raspoloženja i brojem kupaca koji ga pominju.":::

  Izaberite ime poslovnog aspekta da biste videli kako model identifikuje poslovni aspekt:

  - **Uticajne reči**: Vrhunske reči koje su uticale na identifikaciju poslovnog aspekta AI modela u povratnim informacijama klijenata.
    **Prikaži uvredljive reči**: Omogućava vam da uključite uvredljive reči na listu iz originalnih podataka za povratne informacije korisnika. Podrazumevano je isključen.  Uvredljivo maskiranje reči napaja se AI modelom i možda neće otkriti sve uvredljive reči. Ako otkrijete uvredljivu reč koja nije filtrirana kao što se očekivalo, obavestite nas.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Lista uticajnih reči sa preklopnikom za prikazivanje ili skrivanje uvredljivih reči.":::

  - **Uzorci povratnih informacija**: Stvarni zapisi povratnih informacija u podacima. Reči su obojene u skladu sa njihovim uticajem na identifikaciju poslovnog aspekta.

### <a name="influential-words-analysis-tab"></a>Kartica "Analiza uticajnih reči"

Postoje tri odeljka dodatnih informacija koji objašnjavaju kako funkcioniše model sentimenta.
  
- **Vrhunske reči koje doprinose pozitivnom osećanju**: Vrhunske reči koje su uticale na identifikaciju pozitivnog sentimenta AI modela u povratnim informacijama korisnika.  

- **Vrhunske reči koje doprinose negativnom osećanju**: Vrhunske reči koje su uticale na identifikaciju negativnog sentimenta AI modela u povratnim informacijama korisnika.

- **Uzorci povratnih informacija**: stvarni zapisi povratnih informacija, jedan sa negativnim osećanjima i drugi sa pozitivnim osećanjima. Reči u zapisima povratnih informacija su istaknute u skladu sa njihovim doprinosom dodeljenom rezultatu sentimenta. Reči koje doprinose pozitivnom rezultatu sentimenta istaknute su zelenom. Reči koje doprinose negativnom rezultatu istaknute su crvenom bojom.
   Kliknite na **dugme "Pogledaj više** " da biste učitali još uzoraka povratnih informacija.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Primeri analize sentimenta na povratnim informacijama klijenata.":::

**Prikaži uvredljive reči**: Omogućava vam da uključite uvredljive reči na listu iz originalnih podataka za povratne informacije korisnika. Podrazumevano je isključen.  Uvredljivo maskiranje reči napaja se AI modelom i možda neće otkriti sve uvredljive reči. Ako otkrijete uvredljivu reč koja nije filtrirana kao što se očekivalo, obavestite nas.

## <a name="act-on-analysis-results"></a>Akt o rezultatima analize

Da biste kreirali nove segmente kupaca iz rezultata analize sentimenta, izaberite **stavku Kreiraj segmente** na vrhu stranice sa rezultatima modela.

## <a name="potential-bias"></a>Potencijalna pristrasnost

Kao i kod svake funkcije koja koristi prediktivnu veštačku inteligenciju, može doći do potencijalne pristrasnosti u podacima koje koristite za predviđanje sentimenta korisnika. Na primer, ako informacije prikupljate samo digitalno, možda će vam nedostajati povratne informacije od klijenata koji prvenstveno lično posluju sa vama, što utiče na izlaz funkcije.

Kako ova funkcija koristi automatizovana sredstva za procenu podataka i pravljenje predviđanja na osnovu tih podataka, ona stoga ima mogućnost da se koristi kao metod profilisanja, jer je taj pojam definisan Opštom uredbom o zaštiti podataka ("GDPR"). Vaša upotreba ove funkcije za obradu podataka može biti predmet GDPR-a ili drugih zakona ili propisa. Vi ste odgovorni da obezbedite Dynamics 365 Customer Insights da vaša upotreba, uključujući analizu sentimenta, bude u skladu sa svim važećim zakonima i propisima, uključujući zakone vezane za privatnost, lične podatke, biometrijske podatke, zaštitu podataka i poverljivost komunikacija.

[!INCLUDE [footer-include](includes/footer-banner.md)]

