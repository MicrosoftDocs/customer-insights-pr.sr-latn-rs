---
title: Primer vodiča za predviđanje gubitka pretplata
description: Koristite ovaj primer vodiča da biste isprobali spreman model predviđanja gubitka pretplata.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741428"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Primer vodiča za predviđanje gubitka pretplata

Objasnićemo vam kompletan primer predviđanja gubitka pretplata pomoću primera podataka navedenih u nastavku. 

## <a name="scenario"></a>Scenario

Contoso je kompanija koja proizvodi visokokvalitetnu kafu i aparate za kafu, koje prodaju putem svog veb-sajta Contoso Coffee. Nedavno su pokrenuli uslugu pretplate kako bi njihovi klijenti redovno dobijali kafu. Cilj im je da razumeju koji pretplaćeni klijenti bi mogli otkazati pretplatu u narednih nekoliko meseci. Kada znaju koje klijente će **verovatno izgubiti**, mogu da uštede na marketinškim kampanjama i fokusiraju se na njihovo zadržavanje.

## <a name="prerequisites"></a>Preduslovi

- Barem [dozvole saradnika](permissions.md) u usluzi Customer Insights.
- Preporučujemo da primenite sledeće korake [u novom okruženju](manage-environments.md).

## <a name="task-1---ingest-data"></a>1. zadatak – Unos podataka

Posebno pregledajte članke [o unošenju podataka](data-sources.md)[i uvozu izvora podataka pomoću Power Query linija spajanja](connect-power-query.md). Sledeće informacije pretpostavljaju da ste se upoznali sa unošenjem podataka uopšte. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Unesite podatke o klijentima sa platforme eCommerce

1. Napravite izvor podataka pod imenom **eCommerce**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.

1. Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadclasscontacts.

1. Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:

   - **Datum rođenja**: Datum
   - **Kreirano**: Datum/vreme/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformacija datuma rođenja u datum.":::

1. U polju **Ime** u desnom oknu preimenujte izvor podataka iz **Upit** u **eCommerce kontakti**

1. Sačuvajte izvor podataka.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Unesite podatke o klijentima iz šeme lojalnosti

1. Napravite izvor podataka pod imenom **Šema lojalnosti**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.

1. Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadclasscustomerloyalty.

1. Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:

   - **Datum rođenja**: Datum
   - **Nagradni poeni**: Ceo broj
   - **Kreirano**: Datum/vreme

1. U polju **Ime** u desnom oknu preimenujte izvor podataka iz **Upit** u **Lojalni klijenti**.

1. Sačuvajte izvor podataka.

### <a name="ingest-subscription-information"></a>Unos informacija o pretplati

1. Napravite izvor podataka pod imenom **Istorija pretplata**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.

1. Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadchurnsubscriptionhistory.

1. Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:

   - **ID pretplate**: Ceo broj
   - **Iznos pretplate**: Valuta
   - **Datum završetka pretplate**: Datum/vreme
   - **Datum početka pretplate**: Datum/vreme
   - **Datum transakcije**: Datum/vreme
   - **Da li se ponavlja**: Tačno/netačno
   - **Da_li_se_automatski_obnavlja**: Tačno/netačno
   - **Učestalost ponavljanja u mesecima**: Ceo broj

1. U polju **Ime** u desnom oknu preimenujte izvor podataka iz **Upit** u **Istorija pretplata**.

1. Sačuvajte izvor podataka.

### <a name="ingest-customer-data-from-website-reviews"></a>Unesite podatke o klijentima iz recenzija na veb-sajtu

1. Napravite izvor podataka pod imenom **Veb-sajt**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.

1. Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadclasswebsite.

1. Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:

   - **Ocena iz recenzija**: Ceo broj
   - **Datum recenzije**: Datum

1. U polju „Ime“ u desnom oknu preimenujte izvor podataka iz **Upit** u **Recenzije na vebu**.

## <a name="task-2---data-unification"></a>2. zadatak 2 – Objedinjavanje podataka

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>3. zadatak – Konfigurišite predviđanje gubitka pretplata

Kada su objedinjeni profilima klijenata spremni, sada možemo pokrenuti predviđanje gubitka pretplata. Detaljne korake pogledajte u članku [Predviđanje](predict-subscription-churn.md) churn. 

1. Idite na **Obaveštavanje** > **Otkrijte** i izaberite da koristite **Model gubitka klijenata**.

1. Izaberite opciju **Pretplata** i **Započnite**.

1. Nazovite model **OOB predviđanje gubitka klijenata** i izlazni entitet **OOBSubscriptionChurnPrediction**.

1. Definišite dva uslova za model gubitka:

   * **Broj dana od završetka pretplate**: **najmanje 60** dana. Ako klijent ne obnovi pretplatu u ovom periodu nakon njenog završetka, smatra se da ste ga izgubili. 

   * **Definicija gubitka**: **najmanje 93** dana. Trajanje tokom kojeg može doći do gubitka klijenata, po predviđanju modela. Što dalje gledate u budućnost, to su rezultati manje precizni.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Izaberite regulatore modela Vremenski period predviđanja i Definicija gubitka.":::

1. Izaberite **Dodajte potrebne podatke** i **Dodajte podatke** za istoriju pretplata.

1. Dodajte entitet **Pretplata: Istorija pretplata** i mapirajte polja iz platforme eCommerce sa odgovarajućim poljima koje traži model.

1. Pridružite entitet **Pretplata: Istorija pretplata** sa **eCommerce kontakti: eCommerce**, imenujte odnos **eCommerce pretplata**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Pridružite eCommerce entitete.":::

1. U okviru Aktivnosti klijenata dodajte entitet **Recenzije na vebu: Veb-sajt** i mapirajte polja iz Recenzija na vebu sa odgovarajućim poljima koja traži model. 
   - Primarni ključ: ID recenzije
   - Vremenska oznaka: Datum recenzije
   - Događaj: Ocena iz recenzija

1. Konfigurišite aktivnost za recenzije sa veb-sajta. Izaberite aktivnost **Recenzija** i pridružite entitet **Recenzije na vebu: Veb-sajt** sa **eCommerce kontakti: eCommerce**.

1. Izaberite **Dalje** da biste postavili raspored modela.

   Model treba redovno da se obučava kako bi naučio nove obrasce kada dođe do unosa novih podataka. Za ovaj primer izaberite **Mesečno**.

1. Nakon pregleda svih detalja, izaberite **Sačuvaj i pokreni**.

## <a name="task-4---review-model-results-and-explanations"></a>4. zadatak – Pregled rezultata modela i objašnjenja

Neka model završi obuku i ocenjivanje podataka. Sada možete pregledati objašnjenja modela gubitka pretplata. Za više informacija pogledajte [Pregledajte status i rezultate predviđanja](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>5. zadatak – Kreirajte segment klijenata sa visokim rizikom od gubitka

Pokretanje proizvodnog modela stvara novi entitet koji možete da vidite u odeljku **Podaci** > **Entiteti**.   

Možete da kreirate novi segment na osnovu entiteta koji je kreirao model.

1.  Idite na **Segmenti**. Izaberite **Novo** i **Napravi od** > **Obaveštavanje**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Kreirajte segment sa izlazom modela.":::

1. Izaberite krajnju tačku **OOB predviđanje gubitka klijenata** i definišite segment: 
   - Polje: Ocena gubitka
   - Operator: veće je od
   - Vrednost: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Podesite segment gubitka pretplate.":::

Sada imate segment koji se dinamički ažurira i koji identifikuje klijente sa visokim rizikom od gubitka za ovu uslugu pretplate.

Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]