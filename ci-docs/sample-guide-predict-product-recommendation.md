---
title: Primer vodiča za predviđanje preporuka proizvoda
description: Koristite ovaj primer vodiča da biste isprobali ovaj gotovi model predviđanja preporuka proizvoda.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762703"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Primer vodiča za predviđanje preporuka proizvoda

Objasnićemo vam kompletan primer predviđanja preporuke proizvoda pomoću primera podataka navedenih u nastavku.

## <a name="scenario"></a>Scenario

Contoso je kompanija koja proizvodi visokokvalitetnu kafu i aparate za kafu, koje prodaju putem svog veb-sajta Contoso Coffee. Cilj im je da razumeju koje proizvode bi trebalo da preporuče svojim redovnim klijentima. Saznanje šta će klijenti **verovatnije kupiti** može im pomoći da uštede marketinške napore fokusiranjem na određene stavke.

## <a name="prerequisites"></a>Preduslovi

- Barem [dozvole saradnika](permissions.md) u usluzi Customer Insights.
- Preporučujemo da primenite sledeće korake [u novom okruženju](manage-environments.md).

## <a name="task-1---ingest-data"></a>1. zadatak – Unos podataka

Posebno pregledajte članke [o unošenju podataka](data-sources.md)[i uvozu izvora podataka pomoću Power Query linija spajanja](connect-power-query.md). Sledeće informacije pretpostavljaju da ste se upoznali sa unošenjem podataka uopšte.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Unesite podatke o klijentima sa platforme eCommerce

1. Napravite izvor podataka pod imenom **eCommerce**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.

1. Unesite URL adresu za eCommerce kontakte: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **Datum rođenja**: Datum
   - **Kreirano**: Datum/vreme/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformacija datuma rođenja u datum.":::

1. U polju „Ime“ u desnom oknu preimenujte izvor podataka iz **Upit** u **eCommerce kontakti**

1. **Sačuvajte** izvor podataka.

### <a name="ingest-online-purchase-data"></a>Unesite podatke o kupovini na mreži

1. Dodajte još jedan skup podatka u isti **eCommerce** izvor podataka. Ponovo izaberite konektor **Tekst/CSV**.

1. Unesite URL adresu za podatke **o kupovini na** mreži [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **Kupljeno dana**: Datum/vreme
   - **Ukupna cena**: Valuta

1. U polju **Naziv** u bočnom oknu preimenujte izvor podataka iz **Upit** u **eCommerce kupovine**.

1. **Sačuvajte** izvor podataka.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Unesite podatke o klijentima iz šeme lojalnosti

1. Napravite izvor podataka pod imenom **Šema lojalnosti**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.

1. Unesite URL adresu za eCommerce kontakte [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **Datum rođenja**: Datum
   - **Nagradni poeni**: Ceo broj
   - **Kreirano**: Datum/vreme

1. U polju **Ime** u desnom oknu preimenujte izvor podataka iz **Upit** u **Lojalni klijenti**.

1. **Sačuvajte** izvor podataka.

## <a name="task-2---data-unification"></a>2. zadatak 2 – Objedinjavanje podataka

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Zadatak 3 – Konfigurišite predviđanje preporuke proizvoda

Sa objedinjenim profilima klijenata, sada možemo da pokrenemo preporuku proizvoda predviđanje.

1. Idite na **Obaveštavanje** > **Predviđanje** i odaberite **Preporuka proizvoda**.

1. Izaberite **Prvi koraci**.

1. Imenujte model **Predviđanje modela preporuke OOB proizvoda** a izlazni entitet **OOBProductRecommendationModelPrediction**.

1. Definišite tri uslova za model:

   - **Broj proizvoda**: Podesite ovu vrednost na **5**. Ovo podešavanje definiše koliko proizvoda želite da preporučite svojim klijentima.

   - **Očekuje se ponovljena kupovina**: Izaberite **Da** kako biste naznačili da želite da dodate proizvode u preporuku koju su vaši klijenti ranije kupovali.

   - **Period za reviziju** Izaberite najmanje **365 dana**. Ovo podešavanje definiše koliko daleko unazad će model pratiti aktivnost klijenta da bi ga koristio kao ulaz za preporuke.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Željena podešavanja modela za model preporuke proizvoda.":::

1. U koraku **"Dodavanje potrebnih podataka** " izaberite stavku **Dodaj podatke**.

1. U oknu **sa podacima** odaberite liniju **"Prodavac"** kao entitet istorije nabavke. U ovom trenutku, verovatno još uvek nije konfigurisan. Otvorite vezu u oknu da biste kreirali aktivnost sledećim koracima:
   1. Unesite **ime aktivnosti i** odaberite *eCommercePurchases:eCommerce* kao **entitet aktivnosti**. Primarni **ključ je ID** *nabavke*.
   1. Definišite i imenujte relaciju *sa entitetom eCommerceContacts:eCommerce i* **odaberite ID kontakta** kao strani ključ.
   1. Za ujedinjenje aktivnosti postavite aktivnost **događaja kao** *TotalPrice i* Timestamp na *"PurchasedOn"*. Možete navesti više polja kao što je navedeno u aktivnostima [kupca](activities.md).
   1. Za vrstu **aktivnosti izaberite** stavku *Red prodaje*. Mapiraj sledeća polja aktivnosti:
      - ID reda porudžbine: ID nabavke
      - ID porudžbine: ID nabavke
      - Podaci o porudžbini: PurchasedOn
      - ID proizvoda: ID proizvoda
      - Iznos: ukupna faktura
   1. Pregledajte i završite aktivnost pre nego što se vratite na konfiguraciju modela.

1. U koraku Izbor **aktivnosti** odaberite novokreiranu aktivnost u odeljku **Aktivnosti**. Kliknite **na** dugme "Dalje" i mapiranje atributa je već popunjeno. Izaberite **sačuvaj**.

1. U ovom probnom vodiču preskačemo skup **Dodavanje informacija o** **proizvodu i filtera** proizvoda jer nemamo podatke o proizvodu.

1. U koraku **ažuriranja** podataka podesite raspored modela.

   Model treba redovno da se obučava kako bi naučio nove obrasce kada dođe do unosa novih podataka. Za ovaj primer izaberite **Mesečno**.

1. Nakon pregleda svih detalja, izaberite **Sačuvaj i pokreni**. Biće potrebno nekoliko minuta da se model pokrene prvi put.

## <a name="task-4---review-model-results-and-explanations"></a>4. zadatak – Pregled rezultata modela i objašnjenja

Neka model završi obuku i ocenjivanje podataka. Sada možete pregledati objašnjenja modela preporuka proizvoda. Za više informacija pogledajte [Pregledajte status i rezultate predviđanja](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Zadatak 5 – Napravite segment proizvoda koji se često kupuju

Pokretanje proizvodnog modela stvara novi entitet koji možete da vidite u odeljku **Podaci** > **Entiteti**.

Možete da kreirate novi segment na osnovu entiteta koji je kreirao model.

1. Idite na **Segmenti**. Izaberite opciju **Novo** i odaberite **stavku Kreiraj iz inteligencije**.

   ![Kreirajte segment sa izlazom modela.](media/segment-intelligence.png)

1. Izaberite krajnju tačku **OOBProductRecommendationModelPrediction** i definišite segment:

   - Polje: ProductID
   - Vrednost: Izaberite prva tri ID-a proizvoda

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Kreirajte segment iz rezultata modela.":::

Sada imate segment koji se dinamički ažurira i koji identifikuje kupce koji bi mogli biti zainteresovani da kupe tri najprisutičnija proizvoda.

Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
