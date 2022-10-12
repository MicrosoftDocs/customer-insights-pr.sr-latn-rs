---
title: Primer vodiča za predviđanje gubitka pretplata
description: Koristite ovaj primer vodiča da biste isprobali spreman model predviđanja gubitka pretplata.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610023"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Primer vodiča za predviđanje gubitka pretplata

Ovaj vodič će vam objasniti primer "kraj-na-krajnji" predviđanje korišćenjem probnih podataka. Preporučujemo da isprobate ovu predviđanje [u novom okruženju](manage-environments.md).

## <a name="scenario"></a>Scenario

Contoso je kompanija koja proizvodi visokokvalitetne aparate za kafu i kafu. Proizvode prodaju preko svog sajta Contoso Coffee. Nedavno su pokrenuli uslugu pretplate kako bi njihovi klijenti redovno dobijali kafu. Njihov cilj je da shvate koji pretplatljeni klijenti bi mogli da otkažu pretplatu u narednih nekoliko meseci. Saznanje ko će od njihovih klijenata **verovatno da im** pomogne da uštede marketinške napore fokusirajući se na njihovo zadržavanje.

## <a name="prerequisites"></a>Preduslovi

- Barem [dozvole saradnika](permissions.md) u usluzi Customer Insights.

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

1. Sačuvajte izvor podataka.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Unesite podatke o klijentima iz šeme lojalnosti

1. Kreirajte izvor podataka pod imenom **"LoyaltyScheme**" i izaberite **text/CSV** konektor.

1. Unesite URL adresu za kupce lojalnosti https://aka.ms/ciadclasscustomerloyalty.

1. Tokom uređivanja podataka izaberite stavku **Transformiši**, a **zatim koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **Datum rođenja**: Datum
   - **Nagradni poeni**: Ceo broj
   - **Kreirano**: Datum/vreme

1. U polju **Ime u** desnom oknu preimenujte izvor podataka **loyCustomers**.

1. Sačuvajte izvor podataka.

### <a name="ingest-subscription-information"></a>Unos informacija o pretplati

1. Kreirajte izvor podataka pod imenom **"Pretplata" i** izaberite **tekstualnu/CSV konektor**.

1. Unesite URL adresu za pretplate https://aka.ms/ciadchurnsubscriptionhistory.

1. Tokom uređivanja podataka izaberite stavku **Transformiši**, a **zatim koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **ID pretplate**: Ceo broj
   - **Iznos pretplate**: Valuta
   - **Datum završetka pretplate**: Datum/vreme
   - **Datum početka pretplate**: Datum/vreme
   - **Datum transakcije**: Datum/vreme
   - **Da li se ponavlja**: Tačno/netačno
   - **Da_li_se_automatski_obnavlja**: Tačno/netačno
   - **Učestalost ponavljanja u mesecima**: Ceo broj

1. U polju **Ime u** desnom oknu preimenujte izvor podataka **u SubscriptionHistory**.

1. Sačuvajte izvor podataka.

### <a name="ingest-customer-data-from-website-reviews"></a>Unesite podatke o klijentima iz recenzija na veb-sajtu

1. Kreirajte izvor podataka imenovanu **Veb lokaciju** i izaberite **text/CSV konektor**.

1. Unesite URL adresu za preglede Veb lokacija https://aka.ms/ciadclasswebsite.

1. Tokom uređivanja podataka izaberite stavku **Transformiši**, a **zatim koristi prvi red kao zaglavlja**.

1. Ažurirajte tip podataka za dolenavedene kolone:
   - **Ocena iz recenzija**: Ceo broj
   - **Datum recenzije**: Datum

1. U polju **Ime u** desnom oknu preimenujte izvor podataka **WebReviews**.

## <a name="task-2---data-unification"></a>2. zadatak 2 – Objedinjavanje podataka

Pregledajte članak o [ujedinjenju podataka](data-unification.md). Sledeće informacije pretpostavljaju da ste uopšte upoznati sa ujedinjenjem podataka.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Zadatak 3 - Kreiranje aktivnosti istorije transakcija

Pregledajte članak o [aktivnostima klijenata](activities.md). Sledeće informacije pretpostavljaju da ste upoznati sa kreiranjem aktivnosti uopšte.

1. Kreirajte aktivnost pod nazivom **"Pretplata" sa** entitetom *pretplate* i njegovim primarnim ključem ID **klijenta**.

1. Kreirajte relaciju između *SubscriptionHistory:Subscription* i *eCommerceContacts:eCommerce* **sa ID-om** klijenta kao stranog ključa za povezivanje dva entiteta.

1. Izaberite **SubscriptionType** za **događajAktivnost** događaja **i PretplatuEndDate** za **vremenski izbor**.

1. Izaberite **pretplatu** za **tip aktivnosti i** semantički mapirate podatke o aktivnostima.

1. Pokrenite aktivnost.

1. Dodajte drugu aktivnost i mapirate njena polja u odgovarajuća polja:
   - Entitet aktivnosti klijenta: Reviews:Website
   - Primarni ključ: Website.Reviews.ReviewId
   - Vremenska oznaka: Website.Reviews.ReviewDate
   - Događaj (naziv aktivnosti): Website.Reviews.ActivityTypeDisplay
   - Detalji (iznos ili vrednost): Website.Reviews.ReviewRating

1. Pokrenite aktivnost.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>4. zadatak – Konfigurišite predviđanje gubitka pretplata

Pošto su kreirani objedinjeni profili klijenata i kreirana aktivnost, pokrenite nalog za predviđanje. Detaljne korake pogledajte [u članku Pretplata churn predviđanje](predict-subscription-churn.md).

1. Idite na **obaveštajna** > **predviđanja**.

1. Na kartici **Kreiranje** izaberite stavku **Korišćenje modela** na pločici **modela Customer churn**.

1. Izaberite **pretplatu** za tip churn-a, a zatim prvi **koraci**.

1. Nazovite model **OOB predviđanje gubitka klijenata** i izlazni entitet **OOBSubscriptionChurnPrediction**.

1. Definišite željene postavke modela:
   - **Dani od završetka pretplate**: **60** dana da bi se ukazalo na to da se kupac smatra neodobiđenim ako ne obnovi pretplatu u ovom periodu po završetku pretplate.
   - **Dani za istraživanje budućnosti da bi se predvideo churn**: **93** dana, što je trajanje koje model predviđa koji kupci bi mogli da se uzbude. Što dalje gledate u budućnost, to su rezultati manje precizni.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Izaberite željene opcije modela i definiciju churn-a.":::

1. Izaberite **Sledeće**.

1. U koraku Potrebni **podaci izaberite** stavku Dodaj podatke **da biste obezbedili** istoriju pretplate.

1. Izaberite **pretplatu** i entitetHistory pretplate i kliknite na dugme **Dalje**. Potrebni podaci se automatski popunjavaju iz aktivnosti. Izaberite **Sačuvaj**.

1. U okviru Aktivnosti klijenta izaberite Dodaj **podatke**.

1. Na primer, dodajte aktivnost Web redigovača.

1. Izaberite **Sledeće**.

1. U koraku **ažuriranja** podataka izaberite **mesečni** za raspored modela.

1. Nakon pregleda svih detalja, izaberite **Sačuvaj i pokreni**.

## <a name="task-5---review-model-results-and-explanations"></a>5. zadatak – Pregled rezultata modela i objašnjenja

Neka model završi obuku i ocenjivanje podataka. Pregledajte objašnjenja modela pretplate. Više informacija potražite u članku [Prikaz predviđanje rezultata](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>6. zadatak – Kreirajte segment klijenata sa visokim rizikom od gubitka

Pokretanje modela kreiran novi entitet, koji je naveden na **Podaci** > **Entiteti**. Možete da kreirate novi segment na osnovu entiteta koji je kreirao model.

1. Na stranici rezultata, izaberite **Napravi segment**.

1. Kreirajte pravilo koristeći **OOBSubscriptionChurnPrediction** entitet i definišite segment:
   - **Polje**: ChurnScore
   - **Operator**: veći od
   - **Vrednost**: 0.6

1. Izaberite **sačuvaj** i **pokreni** segment.

Sada imate segment koji se dinamički ažurira i koji identifikuje klijente sa visokim rizikom od gubitka za ovu uslugu pretplate. Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).

> [!TIP]
> Segment za model "Segment" možete kreirati i predviđanje stranici "Segmenti **" tako što** ćete izabrati **stavku "Novo**" i izabrati stavku "Kreiraj **od inteligencije** > **"**. Više informacija potražite u članku [Kreiranje novog segmenta sa brzim segmentima](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
