---
title: Primer vodiča za predviđanje gubitka transakcija
description: Koristite ovaj primer vodiča da biste isprobali spreman model predviđanja gubitka transakcija.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741336"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Primer vodiča za predviđanje gubitka transakcija

Ovaj vodič vam objašnjava vam kompletan primer predviđanja gubitka transakcija u usluzi Customer Insights pomoću podataka navedenih u nastavku. Svi podaci korišćeni u ovom vodiču nisu stvarni podaci o klijentima i deo su skupa podataka Contoso koji se nalazi u *Demo* okruženju u okviru pretplate na Customer Insights.

## <a name="scenario"></a>Scenario

Contoso je kompanija koja proizvodi visokokvalitetnu kafu i aparate za kafu, koje prodaju putem svog veb-sajta Contoso Coffee. Cilj im je da saznaju koji će klijenti koji obično redovno kupuju njihove proizvode prestati da budu aktivni klijenti u narednih 60 dana. Kada znaju koje klijente će **verovatno izgubiti**, mogu da uštede na marketinškim kampanjama i fokusiraju se na njihovo zadržavanje.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformišite datum rođenja u datum.":::

1. U polju **Ime** u desnom oknu preimenujte izvor podataka iz **Upit** u **eCommerce kontakti**

1. Sačuvajte izvor podataka.

### <a name="ingest-online-purchase-data"></a>Unesite podatke o kupovini na mreži

1. Dodajte još jedan skup podatka u isti **eCommerce** izvor podataka. Ponovo izaberite konektor **Tekst/CSV**.

1. Unesite URL za podatke o **kupovinama na mreži** https://aka.ms/ciadclassonline.

1. Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:

   - **Kupljeno dana**: Datum/vreme
   - **Ukupna cena**: Valuta
   
1. U polju **Ime** u desnom oknu preimenujte izvor podataka iz **Upit** u **eCommerce kupovine**.

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

## <a name="task-2---data-unification"></a>2. zadatak 2 – Objedinjavanje podataka

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>3. zadatak – Konfigurišite predviđanje gubitka transakcija

Sa objedinjenim profilima klijenata, sada možemo da pokrenemo transakciju churn predviđanje. Detaljne korake pogledajte članak [Transaction churn predviđanje](predict-transactional-churn.md). 

1. Idite na **Obaveštavanje** > **Otkrijte** i izaberite da koristite **Model gubitka klijenata**.

1. Izaberite opciju **Transakcija** i **Započnite**.

1. Nazovite model **OOB predviđanje gubitka eCommerce transakcija** i izlazni entitet **OOBeCommerceChurnPrediction**.

1. Definišite dva uslova za model gubitka:

   * **Prozor predviđanja**: **najmanje 60** dana. Ovo podešavanje definiše koliko u budućnosti želimo da predvidimo gubitak klijenata.

   * **Definicija gubitka**: **najmanje 60** dana. Trajanje bez kupovine nakon kojeg se klijent smatra izgubljenim.

     :::image type="content" source="media/model-levers.PNG" alt-text="Izaberite regulatore modela Vremenski period predviđanja i Definicija gubitka.":::

1. Izaberite **Istorija kupovine (obavezno)** i **Dodajte podatke** za istoriju kupovine.

1. Dodajte entitet **eCommerce kupovine: eCommerce** i mapirajte polja iz platforme eCommerce sa odgovarajućim poljima koje traži model.

1. Pridružite entite **eCommerce kupovine: eCommerce** sa **eCommerce kontakti: eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Pridružite eCommerce entitete.":::

1. Izaberite **Dalje** da biste postavili raspored modela.

   Model treba redovno da se obučava kako bi naučio nove obrasce kada dođe do unosa novih podataka. Za ovaj primer izaberite **Mesečno**.

1. Nakon pregleda svih detalja, izaberite **Sačuvaj i pokreni**.

## <a name="task-4---review-model-results-and-explanations"></a>4. zadatak – Pregled rezultata modela i objašnjenja

Neka model završi obuku i ocenjivanje podataka. Sada možete da pregledate objašnjenja modela Churn. Za više informacija pogledajte [Pregledajte status i rezultate predviđanja](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>5. zadatak – Kreirajte segment klijenata sa visokim rizikom od gubitka

Pokretanje proizvodnog modela stvara novi entitet koji možete da vidite u odeljku **Podaci** > **Entiteti**.   

Možete da kreirate novi segment na osnovu entiteta koji je kreirao model.

1.  Idite na **Segmenti**. Izaberite **Novo** i **Napravi od** > **Obaveštavanje**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Kreirajte segment sa izlazom modela.":::

1. Izaberite **OOBeCommerceChurnPrediction** krajnja tačka i definišite segment: 
   - Polje: Ocena gubitka
   - Operator: veće je od
   - Vrednost: 0,6

Sada imate segment koji se dinamički ažurira i koji identifikuje kupce sa visokim rizikom.

Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
