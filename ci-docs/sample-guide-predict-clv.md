---
title: Vodič kroz primere predviđanja trajne vrednosti klijenta (CLV)
description: Koristite ovaj vodič kroz primere da isprobate model predviđanja trajne vrednosti klijenta.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609655"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Vodič kroz primere predviđanja trajne vrednosti klijenta (CLV)

Ovaj vodič vas vodi kroz primer "Krajnji do krajnji primer vrednosti klijenta" (CLV) koji predviđanje uvidima klijenata koristeći probne podatke. Preporučujemo da isprobate ovu predviđanje [u novom okruženju](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso je kompanija koja proizvodi visokokvalitetne aparate za kafu i kafu. Proizvode prodaju preko svog sajta Contoso Coffee. Preduzeće želi da razume vrednost (prihod) koju njihovi klijenti mogu da generišu u sledećih 12 meseci. Poznavanje očekivane vrednosti klijenata u sledećih 12 meseci pomoći će im da svoje marketinške napore usmere na klijente visoke vrednosti.

## <a name="prerequisites"></a>Preduslovi

- Barem [Dozvole saradnika](permissions.md).

## <a name="task-1---ingest-data"></a>1. zadatak – Unos podataka

Pregledajte članke [o unošenju podataka](data-sources.md) i [povezivanju sa Power Query izvor podataka](connect-power-query.md). Sledeće informacije pretpostavljaju da ste uopšteno upoznati sa unosećim podacima.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Unesite podatke o klijentima sa platforme eCommerce

1. Kreirajte Power Query izvor podataka ime eCommerce i **izaberite** Text/CSV konektor **.**

1. Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadclasscontacts.

1. Tokom uređivanja podataka izaberite stavku **Transformiši**, a **zatim koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **Datum rođenja**: Datum
   - **Kreirano**: Datum/vreme/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformacija datuma rođenja u datum.":::

1. U polju **Ime u** desnom oknu preimenujte izvor podataka **eCommerceContacts**

1. **Sačuvajte** izvor podataka.

### <a name="ingest-online-purchase-data"></a>Unesite podatke o kupovini na mreži

1. Dodajte još jedan skup podatka u isti **eCommerce** izvor podataka. Ponovo izaberite konektor **Tekst/CSV**.

1. Unesite URL za podatke o **kupovinama na mreži** https://aka.ms/ciadclassonline.

1. Tokom uređivanja podataka izaberite stavku **Transformiši**, a **zatim koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **Kupljeno dana**: Datum/vreme
   - **Ukupna cena**: Valuta

1. U polju **Ime u** bočnom oknu preimenujte izvor podataka **eCommercePurchases**.

1. **Sačuvajte** izvor podataka.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Unesite podatke o klijentima iz šeme lojalnosti

1. Kreirajte izvor podataka pod imenom **"LoyaltyScheme**" i izaberite **text/CSV** konektor.

1. Unesite URL adresu za kupce lojalnosti https://aka.ms/ciadclasscustomerloyalty.

1. Tokom uređivanja podataka izaberite stavku **Transformiši**, a **zatim koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **Datum rođenja**: Datum
   - **Nagradni poeni**: Ceo broj
   - **Kreirano**: Datum/vreme

1. U polju **Ime u** desnom oknu preimenujte izvor podataka **loyCustomers**.

1. **Sačuvajte** izvor podataka.

### <a name="ingest-customer-data-from-website-reviews"></a>Unesite podatke o klijentima iz recenzija na veb-sajtu

1. Kreirajte izvor podataka imenovanu **Veb lokaciju** i izaberite **text/CSV konektor**.

1. Unesite URL adresu za preglede Veb lokacija https://aka.ms/CI-ILT/WebReviews.

1. Tokom uređivanja podataka izaberite stavku **Transformiši**, a **zatim koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **ReviewRating**: decimalni broj
   - **Datum recenzije**: Datum

1. U polju Ime **u** desnom oknu preimenujte izvor podataka u **Redigovanje**.

1. **Sačuvajte** izvor podataka.

## <a name="task-2---data-unification"></a>2. zadatak 2 – Objedinjavanje podataka

Pregledajte članak o [ujedinjenju podataka](data-unification.md). Sledeće informacije pretpostavljaju da ste uopšte upoznati sa ujedinjenjem podataka.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Zadatak 3 - Kreiranje aktivnosti istorije transakcija

Pregledajte članak o [aktivnostima klijenata](activities.md). Sledeće informacije pretpostavljaju da ste upoznati sa kreiranjem aktivnosti uopšte.

1. Kreirajte aktivnost pod nazivom eCommercePurchases **sa** entitetom eCommercePurchases:eCommerce *i njegovim primarnim ključem,* ID kupovine **.**

1. Kreirajte relaciju *između eCommercePurchases:eCommerce* i *eCommerceContacts:eCommerce* **sa ContactID-om** kao strani ključ za povezivanje dva entiteta.

1. Izaberite **opciju TotalPrice** za **opciju "Aktiviranje** **događaja" i "Kupoprodaja**" **za vremensku kontrolu**.

1. Izaberite **"Linija prodavca"** za vrstu **aktivnosti** i semantički mapiraj podatke o aktivnostima.

1. Pokrenite aktivnost.

1. Dodajte drugu aktivnost i mapirate njena polja u odgovarajuća polja:
   - **Entitet aktivnosti:** Recenzije:Veb lokacija
   - **Primarni ključ**: ID recenzije
   - **Timestamp**: ReviewDate
   - **Aktivnost događaja**: ActivityTypeDisplay
   - **Dodatni detalj**: ReviewRating
   - **Tip aktivnosti**: pregled

1. Pokrenite aktivnost.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Zadatak 4 – Konfigurisanje predviđanja trajne vrednosti klijenta

Kada su u mestu objedinjeni profili klijenata i kreirana aktivnost, pokrenite vrednost za životni vek kupca (CLV) predviđanje. Detaljne korake pogledajte članak [Vrednost doživotnog kupca predviđanje](predict-customer-lifetime-value.md).

1. Idite na **obaveštajna** > **predviđanja**.

1. Na kartici **Kreiranje** izaberite stavku Korišćenje **modela na pločici** vrednosti **za doživotnu vrednost** kupca.

1. Izaberite **Prvi koraci**.

1. Nazovite model **OOB eCommerce CLV Prediction** a izlazni entitet **OOBeCommerceCLVPrediction**.

1. Definišite željene postavke modela:
   - **predviđanje period:** **12 meseci ili 1 godina da** bi se definisalo koliko daleko u budućnost treba predvideti CLV.
   - **Aktivni kupci**: Dozvolite **modelu da izračuna interval nabavke** koji je vremenski okvir u kojem kupac mora imati najmanje jednu transakciju koja se smatra aktivnom.
   - **Kupac visoke vrednosti**: ručno definišite kupce visoke vrednosti kao **prvih 30% aktivnih kupaca**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Korak željenih opcija u navođenom iskustvu za CLV model.":::

1. Izaberite **Sledeće**.

1. U koraku **Potrebni podaci**, izaberite **Dodaj podatke** da biste pružili podatke o transakcijama u prethodnom periodu.

    :::image type="content" source="media/clv-model-required.png" alt-text="Dodajte zahtevani korak podataka u vođenom iskustvu za CLV model.":::

1. Izaberite **SalesOrderLine** i entitet eCommercePurchases i kliknite na dugme **Dalje**. Potrebni podaci se automatski popunjavaju iz aktivnosti. Izaberite stavku **Sačuvaj**, a zatim **dalje**.

1. Korak dodatnih **podataka (opcionalno)** vam omogućava da dodate više podataka o aktivnostima klijenata da biste dobili više uvida u interakcije sa klijentima. U ovom primeru, izaberite **dodajte podatke** i dodajte aktivnost Web redigovača.

1. Izaberite **Sledeće**.

1. U koraku **ažuriranja** podataka izaberite **mesečni** za raspored modela.

1. Izaberite **Sledeće**.

1. Nakon pregleda svih detalja, izaberite **Sačuvaj i pokreni**.

## <a name="task-5---review-model-results-and-explanations"></a>5. zadatak – Pregled rezultata modela i objašnjenja

Neka model završi obuku i ocenjivanje podataka. Pregledajte rezultate [i objašnjenja CLV modela](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>6. zadatak – Kreiranje segmenta klijenata velike vrednosti

Pokretanje modela kreiran novi entitet, koji je naveden na **Podaci** > **Entiteti**. Možete da kreirate novi segment klijenata na osnovu entiteta koji je kreirao model.

1. Na stranici rezultata, izaberite **Napravi segment**.

1. Kreirajte pravilo koristeći **entitet OOBeCommerceCLVPrediction** i definišite segment:
   - **Polje**: CLVScore
   - **Operator**: veći od
   - **Vrednost**: 1500

1. Izaberite **sačuvaj** i **pokreni** segment.

Sada imate segment koji identifikuje klijente za koje se predviđa da će ostvariti više od 1500 $ prihoda u sledećih 12 meseci. Ovaj segment se dinamički ažurira ako se unese više podataka. Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).

> [!TIP]
> Segment za model "Segment" možete kreirati i predviđanje stranici "Segmenti **" tako što** ćete izabrati **stavku "Novo**" i izabrati stavku "Kreiraj **od inteligencije** > **"**. Više informacija potražite u članku [Kreiranje novog segmenta sa brzim segmentima](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
