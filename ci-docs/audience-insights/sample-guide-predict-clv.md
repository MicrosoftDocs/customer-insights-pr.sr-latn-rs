---
title: Vodič kroz primere predviđanja trajne vrednosti klijenta
description: Koristite ovaj vodič kroz primere da isprobate model predviđanja trajne vrednosti klijenta.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: c130e5f699f7eb921b69a20bc6d4ba9eab5b2779
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354848"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Vodič kroz primere predviđanja trajne vrednosti klijenta (CLV)

Ovaj vodič će vam objasniti celokupan primer predviđanja trajne vrednosti klijenta (CLV) u usluzi Customer Insights korišćenjem primera podataka.

## <a name="scenario"></a>Scenario

Contoso je kompanija koja proizvodi visokokvalitetne aparate za kafu i kafu. Proizvode prodaju preko svog sajta Contoso Coffee. Preduzeće želi da razume vrednost (prihod) koju njihovi klijenti mogu da generišu u sledećih 12 meseci. Poznavanje očekivane vrednosti klijenata u sledećih 12 meseci pomoći će im da svoje marketinške napore usmere na klijente visoke vrednosti.

## <a name="prerequisites"></a>Preduslovi

- Najmanje [dozvole saradnika](permissions.md) u uvidima u ciljnu grupu.
- Preporučujemo da primenite sledeće korake [u novom okruženju](manage-environments.md).

## <a name="task-1---ingest-data"></a>1. zadatak – Unos podataka

Pregledajte članke [o unošenju podataka i](data-sources.md) uvozu [izvora podataka pomoću linija Power Query spajanja](connect-power-query.md). Sledeće informacije pretpostavljaju da ste se upoznali sa unošenjem podataka uopšte.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Unesite podatke o klijentima sa platforme eCommerce

1. Napravite izvor podataka pod nazivom **eCommerce**, izaberite opciju uvoza, pa izaberite konektor **Text/CSV**.

1. Unesite URL adresu za eCommerce kontakte [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **Datum rođenja**: Datum
   - **Kreirano**: Datum/vreme/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformacija datuma rođenja u datum.":::

1. U polju „Ime“ u desnom oknu preimenujte izvor podataka iz **Upit** u **eCommerce kontakti**

1. **Sačuvajte** izvor podataka.

### <a name="ingest-online-purchase-data"></a>Unesite podatke o kupovini na mreži

1. Dodajte još jedan skup podatka u isti **eCommerce** izvor podataka. Ponovo izaberite konektor **Tekst/CSV**.

1. Unesite URL za podatke o **kupovinama na mreži** https://aka.ms/ciadclassonline.

1. Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **Kupljeno dana**: Datum/vreme
   - **Ukupna cena**: Valuta

1. U polju **Naziv** u bočnom oknu preimenujte izvor podataka iz **Upit** u **eCommerce kupovine**.

1. **Sačuvajte** izvor podataka.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Unesite podatke o klijentima iz šeme lojalnosti

1. Napravite izvor podataka pod imenom **Šema lojalnosti**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.

1. Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadclasscustomerloyalty.

1. Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **Datum rođenja**: Datum
   - **Nagradni poeni**: Ceo broj
   - **Kreirano**: Datum/vreme

1. U polju **Ime** u desnom oknu preimenujte izvor podataka iz **Upit** u **Lojalni klijenti**.

1. **Sačuvajte** izvor podataka.

### <a name="ingest-customer-data-from-website-reviews"></a>Unesite podatke o klijentima iz recenzija na veb-sajtu

1. Napravite izvor podataka pod imenom **Veb-sajt**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.

1. Unesite URL adresu za eCommerce kontakte https://aka.ms/CI-ILT/WebReviews.

1. Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:

   - **ReviewRating**: decimalni broj
   - **Datum recenzije**: Datum

1. U polju „Naziv“ u desnom oknu, preimenujte izvor podataka iz **Upit** u **Pregledi**.

1. **Sačuvajte** izvor podataka.

## <a name="task-2---data-unification"></a>2. zadatak 2 – Objedinjavanje podataka

Nakon unosa podataka, sada započinjemo postupak ujednačavanja podataka kako bismo kreirali jedinstveni profil klijenta. Za više informacija pogledajte [Objedinjavanje podataka](data-unification.md).

### <a name="map"></a>Mapiraj

1. Nakon unosa podataka, mapirajte kontakte sa platforme eCommerce i iz podataka o lojalnosti u uobičajene tipove podataka. Idite na **Podaci** > **Objedini** > **Mapiraj**.

1. Izaberite entitete koji predstavljaju profil klijenta – **eCommerce kontakti** i **Lojalni klijenti**. Zatim izaberite **Primeni**.

   ![objedinite izvore podataka o platform ecommerce i lojalnosti.](media/unify-ecommerce-loyalty.png)

1. Izaberite **ID klijenta** kao primarni ključ za **eCommerce kontakte** i **ID lojalnosti** kao primarni ključ za **Lojalne klijente**.

   ![Objedinite ID lojalnosti kao primarni ključ.](media/unify-loyaltyid.png)

1. Izaberite stavku **Sačuvaj**.

### <a name="match"></a>Podudaranje

1. Idite u na karticu **Podudaranje** i izaberite **Podesi redosled**.

1. U padajućoj listi **Primarno** odaberite **eCommerceContacts : eCommerce** kao primarni izvor i uključite sve zapise.

1. U padajućoj listi **Entitet 2** odaberite **loyCustomers : LoyaltyScheme** i uključite sve zapise.

   ![Objedinite podudaranje platforme eCommerce i lojalnosti.](media/unify-match-order.png)

1. Izaberite **Dodaj pravilo**

1. Dodajte svoj prvi uslov koristeći Ime i prezime.

   - Za eCommerceContacts izaberite **FullName** u padajućoj listi.
   - Za loyCustomers izaberite **FullName** u padajućoj listi.
   - Izaberite padajuću listu **Normalizacija** i odaberite **Tip (telefon, ime, adresa, ...)**.
   - Podesite **Nivo preciznosti**: **Osnovni** i **Vrednost**: **Visoka**.

1. Unesite naziv **Ime i prezime, e-pošta** za novo pravilo.

   - Dodajte drugi uslov za adresu e-pošte izborom stavke **Dodajte uslov**
   - Za entitet eCommerceContacts, odaberite **EMail** u padajućoj listi.
   - Za entitet loyCustomers, odaberite **EMail** u padajućoj listi.
   - Ostavite Normalizacija prazno.
   - Podesite **Nivo preciznosti**: **Osnovni** i **Vrednost**: **Visoka**.

   ![Objedinite pravilo podudaranja za ime i e-poštu.](media/unify-match-rule.png)

1. Izaberite **Gotovo**.

1. Izaberite **Sačuvaj** i **Zatvori**.

### <a name="merge"></a>Objedini

1. Idite na karticu **Objedinjavanje**.

1. Na **ID kontakta** za entitet **Lojalni klijenti** promenite ime za prikaz u **ID kontakta LOJALNOST** da bi se razlikovalo od ostalih unetih ID-ova.

   ![Preimenujte ID kontakta iz ID-a lojalnosti.](media/unify-merge-contactid.png)

1. Izaberite **Sačuvaj** i **Pokreni procese objedinjavanja i posledičnog premeštanja**.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Zadatak 3 – Konfigurisanje predviđanja trajne vrednosti klijenta

Sa uspostavljenim objedinjenim profilima klijenata, sada možemo pokrenuti predviđanje trajne vrednosti klijenta. Detaljne korake pogledajte u članku [Vrednost doživotnog kupca predviđanje](predict-customer-lifetime-value.md).

1. Idite na **Obaveštavanje**  > **Predviđanja** i izaberite **Model trajne vrednosti klijenta**.

1. Pređite kroz informacije u bočnom oknu i izaberite **Započni**.

1. Nazovite model **OOB eCommerce CLV Prediction** a izlazni entitet **OOBeCommerceCLVPrediction**.

1. Definišite željene opcije modela za CLV model:
   - **Vremenski period predviđanja**: **12 meseci ili 1 godina**. Ovo podešavanje definiše koliko u budućnosti treba predviđati trajnu vrednost klijenta.
   - **Aktivni klijenti**: Navedite šta aktivni klijenti znače za vaše poslovanje. Podesite vremenski okvir prethodnog perioda u kojem je klijent morao imati barem jednu transakciju da bi se smatrao aktivnim. Model će predvideti CLV samo za aktivne klijente. Odaberite između dopuštanja modelu da izračuna vremenski period na osnovu istorijskih podataka o transakcijama ili navedite određeni vremenski okvir. U ovom vodiču kroz primer, mi **omogućavamo modelu da izračuna interval kupovine**, što je podrazumevana opcija.
   - **Klijenti velike vrednosti**: Klijente visoke vrednosti definišite kao procenat klijenata koji najviše plaćaju. Model koristi ovaj ulaz za pružanje rezultata koji se uklapaju u vašu poslovnu definiciju klijenata velike vrednosti. Možete odabrati da omogućite modelu da definiše klijente visoke vrednosti. Koristi heurističko pravilo koje izvodi percentil. Klijente visoke vrednosti možete definisati kao procenat klijenata koji će najviše plaćati u budućnosti. U ovom vodiču kroz primere, ručno definišemo klijente velike vrednosti kao **30% aktivnih klijenata koji plaćaju** i izaberite **Sledeći**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Korak željenih opcija u navođenom iskustvu za CLV model.":::

1. U koraku **Potrebni podaci**, izaberite **Dodaj podatke** da biste pružili podatke o transakcijama u prethodnom periodu.

1. Dodajte entitet **eCommercePurchases : eCommerce** i mapirajte atribute koji su potrebni modelu:
   - ID transakcije: eCommerce.eCommercePurchases.PurchaseId
   - Datum transakcije: eCommerce.eCommercePurchases.PurchaseId
   - Iznos transakcije: eCommerce.eCommercePurchases.TotalPrice
   - ID proizvoda: eCommerce.eCommercePurchases.ProductId

1. Izaberite **Sledeće**.

1. Podesite relaciju između entiteta **eCommercePurchases : eCommerce** i **eCommerceContacts : eCommerce**.

1. Korak **Dodatni podaci (opcionalno)** vam omogućava da dodate više podataka o aktivnostima klijenata. Ovi podaci mogu vam pomoći da dobijete više uvida o interakciji klijenata sa vašim preduzećem, što može doprineti modelu CLV. Dodavanje ključnih interakcija sa klijentima poput veb-evidencije, evidencija korisničke službe ili programa nagrađivanja u prethodnom periodu može poboljšati tačnost predviđanja. Izaberite **Dodaj podatke** da biste uključili više podataka o aktivnostima klijenata.

1. Dodajte entitet aktivnosti klijenta i mapirajte nazive njegovih polja u odgovarajuća polja koja zahteva model:
   - Entitet aktivnosti klijenta: Reviews:Website
   - Primarni ključ: Website.Reviews.ReviewId
   - Vremenska oznaka: Website.Reviews.ReviewDate
   - Događaj (naziv aktivnosti): Website.Reviews.ActivityTypeDisplay
   - Detalji (iznos ili vrednost): Website.Reviews.ReviewRating

1. Izaberite **Sledeće** i konfigurišite aktivnost i relaciju između podataka o transakciji i podataka o klijentu:  
   - Tip aktivnosti: Odaberite postojeći
   - Oznaka aktivnosti: Review
   - Odgovarajuća oznaka: Website.Reviews.UserId
   - Entitet klijenta: eCommerceContacts:eCommerce
   - Relacija: WebsiteReviews

1. Izaberite **Dalje** da biste postavili raspored modela.

   Model treba redovno trenirati da bi naučio nove obrasce kada se unose novi podaci. Za ovaj primer, odaberite **Mesečno**.

1. Nakon pregleda svih detalja, izaberite **Sačuvaj i pokreni**.

## <a name="task-4---review-model-results-and-explanations"></a>4. zadatak – Pregled rezultata modela i objašnjenja

Neka model završi obuku i ocenjivanje podataka. Zatim možete pregledati rezultate i objašnjenja CLV modela. Za više informacija pogledajte [Pregledajte status i rezultate predviđanja](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>5. zadatak – Kreiranje segmenta klijenata velike vrednosti

Pokretanje modela kreiran novi entitet, koji je naveden na **Podaci** > **Entiteti**. Možete da kreirate novi segment klijenata na osnovu entiteta koji je kreirao model.

1. Idite na **Segmenti**. 

1. Izaberite **Novo**, pa **Napravi od** > **Obaveštavanje**.

   ![Kreirajte segment sa izlazom modela.](media/segment-intelligence.png)

1. Izaberite entitet **OOBeCommerceCLVPrediction** entitet i definišite segment:
  - Polje: CLVScore
  - Operator: veće je od
  - Vrednost: 1500

1. Izaberite **Pregled** i **sačuvajte** segment.

Sada imate segment koji identifikuje klijente za koje se predviđa da će ostvariti više od 1500 $ prihoda u sledećih 12 meseci. Ovaj segment se dinamički ažurira ako se unese više podataka.

Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).
