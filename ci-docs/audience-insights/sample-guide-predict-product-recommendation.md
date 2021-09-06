---
title: Primer vodiča za predviđanje preporuka proizvoda
description: Koristite ovaj primer vodiča da biste isprobali ovaj gotovi model predviđanja preporuka proizvoda.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b219935dfbd9f7acc1104d83e2ca281801a1a4251ae4c19fc03d4b1ce46f4613
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035202"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Primer vodiča za predviđanje preporuka proizvoda (pregled)

Objasnićemo vam kompletan primer predviđanja preporuke proizvoda pomoću primera podataka navedenih u nastavku.

## <a name="scenario"></a>Scenario

Contoso je kompanija koja proizvodi visokokvalitetnu kafu i aparate za kafu, koje prodaju preko veb-lokacije Contoso Coffee. Cilj im je da razumeju koje proizvode bi trebalo da preporuče svojim redovnim klijentima. Saznanje šta će klijenti **verovatnije kupiti** može im pomoći da uštede marketinške napore fokusiranjem na određene stavke.

## <a name="prerequisites"></a>Preduslovi

- Barem [dozvole saradnika](permissions.md) u usluzi Customer Insights.
- Preporučujemo da primenite sledeće korake [u novom okruženju](manage-environments.md).

## <a name="task-1---ingest-data"></a>1. zadatak – Unos podataka

Pregledajte članke [o unosu podataka](data-sources.md) i [uvozu izvora podataka pomoću Power Query konektora](connect-power-query.md) konkretno. Sledeće informacije pretpostavljaju da ste se upoznali sa unošenjem podataka uopšte.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Unesite podatke o klijentima sa platforme eCommerce

1. Napravite izvor podataka pod imenom **eCommerce**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.

1. Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadclasscontacts.

1. Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **Datum rođenja**: Datum
   - **Kreirano**: Datum/vreme/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformacija datuma rođenja u datum.":::

5. U polju „Ime“ u desnom oknu preimenujte izvor podataka iz **Upit** u **eCommerce kontakti**

6. **Sačuvajte** izvor podataka.

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

## <a name="task-2---data-unification"></a>2. zadatak 2 – Objedinjavanje podataka

Nakon unosa podataka, sada započinjemo postupak ujednačavanja podataka kako bismo kreirali jedinstveni profil klijenta. Za više informacija pogledajte [Objedinjavanje podataka](data-unification.md).

### <a name="map"></a>Mapiraj

1. Nakon unosa podataka, mapirajte kontakte sa platforme eCommerce i iz podataka o lojalnosti u uobičajene tipove podataka. Idite na **Podaci** > **Objedini** > **Mapiraj**.

2. Izaberite entitete koji predstavljaju profil klijenta – **eCommerce kontakti** i **Lojalni klijenti**.

   ![objedinite izvore podataka o platform ecommerce i lojalnosti.](media/unify-ecommerce-loyalty.png)

3. Izaberite **ID klijenta** kao primarni ključ za **eCommerce kontakte** i **ID lojalnosti** kao primarni ključ za **Lojalne klijente**.

   ![Objedinite ID lojalnosti kao primarni ključ.](media/unify-loyaltyid.png)

### <a name="match"></a>Podudaranje

1. Idite u na karticu **Podudaranje** i izaberite **Podesi redosled**.

2. U padajućoj listi **Primarno** odaberite **eCommerceContacts : eCommerce** kao primarni izvor i uključite sve zapise.

3. U padajućoj listi **Entitet 2** odaberite **loyCustomers : LoyaltyScheme** i uključite sve zapise.

   ![Objedinite podudaranje platforme eCommerce i lojalnosti.](media/unify-match-order.png)

4. Izaberite **Kreiraj novo pravilo**

5. Dodajte svoj prvi uslov koristeći Ime i prezime.

   - Za eCommerceContacts izaberite **FullName** u padajućoj listi.
   - Za loyCustomers izaberite **FullName** u padajućoj listi.
   - Izaberite padajuću listu **Normalizacija** i odaberite **Tip (telefon, ime, adresa...)**.
   - Podesite **Nivo preciznosti**: **Osnovni** i **Vrednost**: **Visoka**.

6. Unesite naziv **Ime i prezime, e-pošta** za novo pravilo.

   - Dodajte drugi uslov za adresu e-pošte izborom stavke **Dodajte uslov**
   - Za entitet eCommerceContacts, odaberite **EMail** u padajućoj listi.
   - Za entitet loyCustomers, odaberite **EMail** u padajućoj listi.
   - Ostavite Normalizacija prazno.
   - Podesite **Nivo preciznosti**: **Osnovni** i **Vrednost**: **Visoka**.

   ![Objedinite pravilo podudaranja za ime i e-poštu.](media/unify-match-rule.png)

7. Izaberite **Sačuvaj** i **Zatvori**.

### <a name="merge"></a>Objedini

1. Idite na karticu **Objedinjavanje**.

1. Na **ID kontakta** za entitet **Lojalni klijenti** promenite ime za prikaz u **ID kontakta LOJALNOST** da bi se razlikovalo od ostalih unetih ID-ova.

   ![Preimenujte ID kontakta iz ID-a lojalnosti.](media/unify-merge-contactid.png)

1. Izaberite **Sačuvaj** i **Pokreni** da biste započeli postupak objedinjavanja.

## <a name="task-3---configure-product-recommendation-prediction"></a>Zadatak 3 – Konfigurišite predviđanje preporuke proizvoda

Kada su objedinjeni profilima klijenata spremni, sada možemo pokrenuti predviđanje gubitka pretplata.

1. Idite na **Obaveštavanje** > **Predviđanje** i odaberite **Preporuka proizvoda**.

1. Izaberite **Prvi koraci**.

1. Imenujte model **Predviđanje modela preporuke OOB proizvoda** a izlazni entitet **OOBProductRecommendationModelPrediction**.

1. Definišite tri uslova za model:

   - **Broj proizvoda**: Podesite ovu vrednost na **5**. Ovo podešavanje definiše koliko proizvoda želite da preporučite svojim klijentima.

   - **Očekuje se ponovljena kupovina**: Izaberite **Da** kako biste naznačili da želite da dodate proizvode u preporuku koju su vaši klijenti ranije kupovali.

   - **Period za reviziju** Izaberite najmanje **365 dana**. Ovo podešavanje definiše koliko daleko unazad će model pratiti aktivnost klijenta da bi ga koristio kao ulaz za preporuke.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Željena podešavanja modela za model preporuke proizvoda.":::

1. Izaberite **Obavezni podaci** i izaberite **Dodaj podatke** za istoriju kupovina.

1. Dodajte entitet **eCommerce kupovine: eCommerce** i mapirajte polja iz platforme eCommerce sa odgovarajućim poljima koje traži model.

1. Pridružite entite **eCommerce kupovine: eCommerce** sa **eCommerce kontakti: eCommerce**.

   ![Pridružite eCommerce entitete.](media/model-purchase-join.png)

1. Izaberite **Dalje** da biste postavili raspored modela.

   Model treba redovno da se obučava kako bi naučio nove obrasce kada dođe do unosa novih podataka. Za ovaj primer izaberite **Mesečno**.

1. Nakon pregleda svih detalja, izaberite **Sačuvaj i pokreni**.


## <a name="task-4---review-model-results-and-explanations"></a>4. zadatak – Pregled rezultata modela i objašnjenja

Neka model završi obuku i ocenjivanje podataka. Sada možete pregledati objašnjenja modela preporuka proizvoda. Za više informacija pogledajte [Pregledajte status i rezultate predviđanja](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Zadatak 5 – Napravite segment proizvoda koji se često kupuju

Pokretanje proizvodnog modela stvara novi entitet koji možete da vidite u odeljku **Podaci** > **Entiteti**.

Možete da kreirate novi segment na osnovu entiteta koji je kreirao model.

1. Idite na **Segmenti**. Izaberite **Novo** i **Napravi od** > **Obaveštavanje**.

   ![Kreirajte segment sa izlazom modela.](media/segment-intelligence.png)

1. Izaberite krajnju tačku **OOBProductRecommendationModelPrediction** i definišite segment:

   - Polje: ProductID
   - Operator: Vrednost
   - Vrednost: Izaberite prva tri ID-a proizvoda

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Kreirajte segment iz rezultata modela.":::

Sada imate segment koji se dinamički ažurira i koji identifikuje klijente koji su spremniji da kupe tri najbolje preporučena proizvoda 

Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
