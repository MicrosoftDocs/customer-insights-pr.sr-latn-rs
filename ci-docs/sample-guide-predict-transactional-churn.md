---
title: Primer vodiča za predviđanje gubitka transakcija
description: Koristite ovaj primer vodiča da biste isprobali spreman model predviđanja gubitka transakcija.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609701"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Primer vodiča za predviđanje gubitka transakcija

Ovaj vodič će vam objasniti primer "kraj-na-kraj" transakcionog churn predviđanje korišćenjem probnih podataka. Preporučujemo da isprobate ovu predviđanje [u novom okruženju](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso je kompanija koja proizvodi visokokvalitetne aparate za kafu i kafu. Proizvode prodaju preko svog sajta Contoso Coffee. Cilj im je da saznaju koji će klijenti koji obično redovno kupuju njihove proizvode prestati da budu aktivni klijenti u narednih 60 dana. Kada znaju koje klijente će **verovatno izgubiti**, mogu da uštede na marketinškim kampanjama i fokusiraju se na njihovo zadržavanje.

## <a name="prerequisites"></a>Preduslovi

- Barem [Dozvole saradnika](permissions.md).

## <a name="task-1---ingest-data"></a>1. zadatak – Unos podataka

Pregledajte članke [o unošenju podataka](data-sources.md) i [povezivanju sa Power Query izvor podataka](connect-power-query.md). Sledeće informacije pretpostavljaju da ste uopšteno upoznati sa unosećim podacima.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Unesite podatke o klijentima sa platforme eCommerce

1. Kreirajte izvor podataka ime **eCommerce** i izaberite **Text/CSV** konektor.

1. Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadclasscontacts.

1. Tokom uređivanja podataka izaberite stavku **Transformiši**, a **zatim koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:

   - **Datum rođenja**: Datum
   - **Kreirano**: Datum/vreme/zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformišite datum rođenja u datum.":::

1. U polju **Ime u** desnom oknu preimenujte izvor podataka **eCommerceContacts**

1. Sačuvajte izvor podataka.

### <a name="ingest-online-purchase-data"></a>Unesite podatke o kupovini na mreži

1. Dodajte još jedan skup podatka u isti **eCommerce** izvor podataka. Ponovo izaberite konektor **Tekst/CSV**.

1. Unesite URL adresu za podatke o kupovini na mreži https://aka.ms/ciadclassonline.

1. Tokom uređivanja podataka izaberite stavku **Transformiši**, a **zatim koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:

   - **Kupljeno dana**: Datum/vreme
   - **Ukupna cena**: Valuta

1. U polju **Ime u** desnom oknu preimenujte izvor podataka **eCommercePurchases**.

1. Sačuvajte izvor podataka.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Unesite podatke o klijentima iz šeme lojalnosti

1. Kreirajte izvor podataka pod imenom **"LoyaltyScheme**" i izaberite **text/CSV** konektor.

1. Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadclasscustomerloyalty.

1. Tokom uređivanja podataka izaberite stavku **Transformiši**, a **zatim koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:

   - **Datum rođenja**: Datum
   - **Nagradni poeni**: Ceo broj
   - **Kreirano**: Datum/vreme

1. U polju **Ime u** desnom oknu preimenujte izvor podataka **loyCustomers**.

1. Sačuvajte izvor podataka.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>4. zadatak – Konfigurišite predviđanje gubitka transakcija

Sa objedinjenim profilima klijenata i aktivnošću, pokrenite karticu za predviđanje.

1. Idite na **obaveštajna** > **predviđanja**.

1. Na kartici **Kreiranje** izaberite stavku **Koristi model** na modelu **Customer** churn.

1. Izaberite **Transactional** za vrstu churn-a, a zatim prvi **koraci**.

1. Nazovite model **OOB predviđanje gubitka eCommerce transakcija** i izlazni entitet **OOBeCommerceChurnPrediction**.

1. Izaberite **Sledeće**.

1. Definišite željene postavke modela:

   - **predviđanje:** **60 dana** da definišemo koliko daleko u budućnost želimo da predvidimo kupca.

   - **Churn definicija**: **60** dana da označite trajanje bez kupovine nakon čega se kupac smatra churned.

     :::image type="content" source="media/model-levers.PNG" alt-text="Izaberite željene postavke modela predviđanje prozora i Čurn definicije.":::

1. Izaberite **Sledeće**.

1. Izaberite **Istorija kupovine (obavezno)** i **Dodajte podatke** za istoriju kupovine.

1. Izaberite **SalesOrderLine** i entitet eCommercePurchases i kliknite na dugme **Dalje**. Potrebni podaci se automatski popunjavaju iz aktivnosti. Izaberite stavku **Sačuvaj**, a zatim **dalje**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Pridružite eCommerce entitete.":::

1. Preskočite korak **Dodatnih podataka (opcionalno**).

1. U koraku **ažuriranja** podataka izaberite **mesečni** za raspored modela.

1. Nakon pregleda svih detalja, izaberite **Sačuvaj i pokreni**.

## <a name="task-5---review-model-results-and-explanations"></a>5. zadatak – Pregled rezultata modela i objašnjenja

Neka model završi obuku i ocenjivanje podataka. Pregledajte objašnjenja modela Churn. Više informacija potražite u članku [Prikaz predviđanje rezultata](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>6. zadatak – Kreirajte segment klijenata sa visokim rizikom od gubitka

Pokretanjem modela proizvodnje kreira se novi entitet koji je naveden u entitetima **podataka** > **·**. Možete da kreirate novi segment na osnovu entiteta koji je kreirao model.

1. Na stranici rezultata, izaberite **Napravi segment**.

1. Kreirajte pravilo koristeći **entitet OOBeCommerceChurnPrediction** i definišite segment:
   - **Polje**: ChurnScore
   - **Operator**: veći od
   - **Vrednost**: 0.6

1. Izaberite **sačuvaj** i **pokreni** segment.

Sada imate segment koji se dinamički ažurira i koji identifikuje kupce sa visokim rizikom. Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).

> [!TIP]
> Segment za model "Segment" možete kreirati i predviđanje stranici "Segmenti **" tako što** ćete izabrati **stavku "Novo**" i izabrati stavku "Kreiraj **od inteligencije** > **"**. Više informacija potražite u članku [Kreiranje novog segmenta sa brzim segmentima](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
