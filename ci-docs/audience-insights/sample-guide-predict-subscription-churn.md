---
title: Primer vodiča za predviđanje gubitka pretplata
description: Koristite ovaj primer vodiča da biste isprobali spreman model predviđanja gubitka pretplata.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 324e5c19778230dd978b2f4e9156a2dd82b3d2bd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595535"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>Primer vodiča za predviđanje gubitka pretplata (verzija za pregled)

Objasnićemo vam kompletan primer predviđanja gubitka pretplata pomoću primera podataka navedenih u nastavku. 

## <a name="scenario"></a>Scenario

Contoso je kompanija koja proizvodi visokokvalitetnu kafu i aparate za kafu, koje prodaju putem svog veb-sajta Contoso Coffee. Nedavno su pokrenuli uslugu pretplate kako bi njihovi klijenti redovno dobijali kafu. Cilj im je da razumeju koji pretplaćeni klijenti bi mogli otkazati pretplatu u narednih nekoliko meseci. Kada znaju koje klijente će **verovatno izgubiti**, mogu da uštede na marketinškim kampanjama i fokusiraju se na njihovo zadržavanje.

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

Nakon unosa podataka, sada započinjemo proces **Mapiranja, podudaranja, objedinjavanja** da bismo kreirali objedinjeni profil klijenta. Za više informacija pogledajte [Objedinjavanje podataka](data-unification.md).

### <a name="map"></a>Mapiraj

1. Nakon unosa podataka, mapirajte kontakte sa platforme eCommerce i iz podataka o lojalnosti u uobičajene tipove podataka. Idite na **Podaci** > **Objedini** > **Mapiraj**.

1. Izaberite entitete koji predstavljaju profil klijenta – **eCommerce kontakti** i **Lojalni klijenti**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="objedinite izvore podataka o platform ecommerce i lojalnosti.":::

1. Izaberite **ID klijenta** kao primarni ključ za **eCommerce kontakte** i **ID lojalnosti** kao primarni ključ za **Lojalne klijente**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Objedinite ID lojalnosti kao primarni ključ.":::

### <a name="match"></a>Podudaranje

1. Idite u na karticu **Podudaranje** i izaberite **Podesi redosled**.

1. Na padajućoj listi **Primarno**, odaberite **eCommerce kontakti: eCommerce** kao primarni izvor i uključite sve zapise.

1. Na padajućoj listi **Entitet 2**, odaberite **Lojalni klijenti: Šema lojalnosti** i uključite sve zapise.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Objedinite podudaranje platforme eCommerce i lojalnosti.":::

1. Izaberite **Kreiraj novo pravilo**

1. Dodajte svoj prvi uslov koristeći Ime i prezime.

   * Za eCommerce kontakte odaberite **Ime i prezime** na padajućoj listi.
   * Za Lojalne klijente odaberite **Ime i prezime** na padajućoj listi.
   * Izaberite padajuću listu **Normalizacija** i odaberite **Tip (telefon, ime, adresa...)**.
   * Podesite **Nivo preciznosti**: **Osnovni** i **Vrednost**: **Visoka**.

1. Unesite naziv **Ime i prezime, e-pošta** za novo pravilo.

   * Dodajte drugi uslov za adresu e-pošte izborom stavke **Dodajte uslov**
   * Za entitet eCommerce kontakti odaberite **E-pošta** u padajućem meniju.
   * Za entitet Lojalni klijenti odaberite **E-pošta** u padajućem meniju. 
   * Ostavite Normalizacija prazno. 
   * Podesite **Nivo preciznosti**: **Osnovni** i **Vrednost**: **Visoka**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Objedinite pravilo podudaranja za ime i e-poštu.":::

7. Izaberite **Sačuvaj** i **Zatvori**.

### <a name="merge"></a>Objedini

1. Idite na karticu **Objedinjavanje**.

1. Na **ID kontakta** za entitet **Lojalni klijenti** promenite ime za prikaz u **ID kontakta LOJALNOST** da bi se razlikovalo od ostalih unetih ID-ova.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Preimenujte ID kontakta iz ID-a lojalnosti.":::

1. Izaberite **Sačuvaj** i **Pokreni** da biste započeli postupak objedinjavanja.


## <a name="task-3---configure-the-subscription-churn-prediction"></a>3. zadatak – Konfigurišite predviđanje gubitka pretplata

Kada su objedinjeni profilima klijenata spremni, sada možemo pokrenuti predviđanje gubitka pretplata. Za detaljne korake pogledajte članak [Predviđanje gubitka pretplata (verzija za pregled)](predict-subscription-churn.md). 

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]