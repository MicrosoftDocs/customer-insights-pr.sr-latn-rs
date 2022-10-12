---
title: Primer vodiča za predviđanje preporuka proizvoda
description: Koristite ovaj primer vodiča da biste isprobali ovaj gotovi model predviđanja preporuka proizvoda.
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610161"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Primer vodiča za predviđanje preporuka proizvoda

Ovaj vodič vas vodi kroz primer preporuke za kraj do kraja proizvoda predviđanje korišćenjem probnih podataka. Preporučujemo da isprobate ovu predviđanje [u novom okruženju](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso je kompanija koja proizvodi visokokvalitetne aparate za kafu i kafu. Proizvode prodaju preko svog sajta Contoso Coffee. Cilj im je da razumeju koje proizvode bi trebalo da preporuče svojim redovnim klijentima. Saznanje šta kupci imaju veću verovatnoću **da kupe može im** pomoći da uštede marketinške napore fokusirajući se na određene artikle.

## <a name="prerequisites"></a>Preduslovi

- Barem [dozvole saradnika](permissions.md) u usluzi Customer Insights.

## <a name="task-1---ingest-data"></a>1. zadatak – Unos podataka

Pregledajte članke [o unošenju podataka](data-sources.md) i [povezivanju sa Power Query izvor podataka](connect-power-query.md). Sledeće informacije pretpostavljaju da ste uopšteno upoznati sa unosećim podacima.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Unesite podatke o klijentima sa platforme eCommerce

1. Kreirajte Power Query izvor podataka ime eCommerce i **izaberite** Text/CSV konektor **.**

1. Unesite URL adresu za eCommerce kontakte:https://aka.ms/ciadclasscontacts.

1. Tokom uređivanja podataka izaberite stavku **Transformiši**, a **zatim koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **Datum rođenja**: Datum
   - **Kreirano**: Datum/vreme/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformacija datuma rođenja u datum.":::

1. U polju **Ime u** desnom oknu preimenujte izvor podataka **eCommerceContacts**.

1. **Sačuvajte** izvor podataka.

### <a name="ingest-online-purchase-data"></a>Unesite podatke o kupovini na mreži

1. Dodajte još jedan skup podatka u isti **eCommerce** izvor podataka. Ponovo izaberite konektor **Tekst/CSV**.

1. Unesite URL adresu za podatke o kupovini na mreži https://aka.ms/ciadclassonline.

1. Tokom uređivanja podataka izaberite stavku **Transformiši**, a **zatim koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **Kupljeno dana**: Datum/vreme
   - **Ukupna cena**: Valuta

1. U polju **Ime u** bočnom oknu preimenujte izvor podataka **eCommercePurchases**.

1. **Sačuvajte** izvor podataka.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Unesite podatke o klijentima iz šeme lojalnosti

1. Kreirajte izvor podataka pod imenom **"LoyaltyScheme**" i izaberite **text/CSV** konektor.

1. Unesite URL adresu za lojalne kupce https://aka.ms/ciadclasscustomerloyalty.

1. Tokom uređivanja podataka izaberite stavku **Transformiši**, a **zatim koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **Datum rođenja**: Datum
   - **Nagradni poeni**: Ceo broj
   - **Kreirano**: Datum/vreme

1. U polju **Ime u** desnom oknu preimenujte izvor podataka **loyCustomers**.

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

## <a name="task-4---configure-product-recommendation-prediction"></a>Zadatak 4 – Konfigurišite predviđanje preporuke proizvoda

Pošto su kreirani objedinjeni profili klijenata i kreirana aktivnost, pokrenite preporuku proizvoda predviđanje.

1. Idite na **obaveštajna** > **predviđanja**.

1. Na kartici **Kreiranje** izaberite stavku **Koristi model** na pločici **"Preporuke proizvoda** (pregled)".

1. Izaberite **Prvi koraci**.

1. Imenujte model **Predviđanje modela preporuke OOB proizvoda** a izlazni entitet **OOBProductRecommendationModelPrediction**.

1. Izaberite **Sledeće**.

1. Definišite željene postavke modela:
   - **Broj proizvoda**: **5 da** biste definisali koliko proizvoda želite da preporučite kupcima.
   - **Ponovite očekivane nabavke**: **Da** da biste uključili prethodno kupljene proizvode u preporuku.
   - **Pogledajte unazad prozor:** **365 dana da** definišete koliko daleko će se model osvrnuti pre nego što ponovo preporučite proizvod.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Željena podešavanja modela za model preporuke proizvoda.":::

1. Izaberite **Sledeće**.

1. U koraku Dodavanje **istorije nabavke** izaberite stavku Dodaj **podatke**.

1. Izaberite **SalesOrderLine** i entitet eCommercePurchases i kliknite na dugme **Dalje**. Potrebni podaci se automatski popunjavaju iz aktivnosti. Izaberite stavku **Sačuvaj**, a zatim **dalje**.

1. Preskočite korake **Dodavanje informacija o** proizvodu **i** filterima proizvoda jer nemamo podatke o proizvodu.

1. U koraku **ažuriranja** podataka izaberite **mesečni** za raspored modela.

1. Izaberite **Sledeće**.

1. Nakon pregleda svih detalja, izaberite **Sačuvaj i pokreni**.

## <a name="task-5---review-model-results-and-explanations"></a>5. zadatak – Pregled rezultata modela i objašnjenja

Neka model završi obuku i ocenjivanje podataka. Pregledajte objašnjenja [modela preporuke proizvoda](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Zadatak 6 – Napravite segment proizvoda koji se često kupuju

Pokretanje modela kreiran novi entitet, koji je naveden na **Podaci** > **Entiteti**. Možete da kreirate novi segment na osnovu entiteta koji je kreirao model.

1. Na stranici rezultata, izaberite **Napravi segment**.

1. Kreirajte pravilo koristeći **entitet OOBProductRecommendationModelPrediction** i definišite segment:
   - **Polje**: ID proizvoda
   - **Vrednost**: Izaberite prva tri ID-a proizvoda

1. Izaberite **sačuvaj** i **pokreni** segment.

Sada imate segment koji se dinamički ažurira i koji identifikuje kupce koji su možda zainteresovani za kupovinu pet najprisutičnijih proizvoda. Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).

> [!TIP]
> Segment za model "Segment" možete kreirati i predviđanje stranici "Segmenti **" tako što** ćete izabrati **stavku "Novo**" i izabrati stavku "Kreiraj **od inteligencije** > **"**. Više informacija potražite u članku [Kreiranje novog segmenta sa brzim segmentima](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
