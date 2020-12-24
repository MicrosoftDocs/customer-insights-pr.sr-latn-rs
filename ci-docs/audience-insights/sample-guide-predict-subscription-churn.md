---
title: Primer vodiča za predviđanje gubitka pretplata
description: Koristite ovaj primer vodiča da biste isprobali spreman model predviđanja gubitka pretplata.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653997"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="f3a73-103">Primer vodiča za predviđanje gubitka pretplata (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="f3a73-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="f3a73-104">Objasnićemo vam kompletan primer predviđanja gubitka pretplata pomoću primera podataka navedenih u nastavku.</span><span class="sxs-lookup"><span data-stu-id="f3a73-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="f3a73-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="f3a73-105">Scenario</span></span>

<span data-ttu-id="f3a73-106">Contoso je kompanija koja proizvodi visokokvalitetnu kafu i aparate za kafu, koje prodaju putem svog veb-sajta Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="f3a73-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="f3a73-107">Nedavno su pokrenuli uslugu pretplate kako bi njihovi klijenti redovno dobijali kafu.</span><span class="sxs-lookup"><span data-stu-id="f3a73-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="f3a73-108">Cilj im je da razumeju koji pretplaćeni klijenti bi mogli otkazati pretplatu u narednih nekoliko meseci.</span><span class="sxs-lookup"><span data-stu-id="f3a73-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="f3a73-109">Kada znaju koje klijente će **verovatno izgubiti**, mogu da uštede na marketinškim kampanjama i fokusiraju se na njihovo zadržavanje.</span><span class="sxs-lookup"><span data-stu-id="f3a73-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f3a73-110">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="f3a73-110">Prerequisites</span></span>

- <span data-ttu-id="f3a73-111">Barem [dozvole saradnika](permissions.md) u usluzi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f3a73-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="f3a73-112">Preporučujemo da primenite sledeće korake [u novom okruženju](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="f3a73-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="f3a73-113">1. zadatak – Unos podataka</span><span class="sxs-lookup"><span data-stu-id="f3a73-113">Task 1 - Ingest Data</span></span>

<span data-ttu-id="f3a73-114">Pregledajte članke [o unosu podataka](data-sources.md) i [uvozu izvora podataka pomoću Power Query konektora](connect-power-query.md) konkretno.</span><span class="sxs-lookup"><span data-stu-id="f3a73-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="f3a73-115">Sledeće informacije pretpostavljaju da ste se upoznali sa unošenjem podataka uopšte.</span><span class="sxs-lookup"><span data-stu-id="f3a73-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="f3a73-116">Unesite podatke o klijentima sa platforme eCommerce</span><span class="sxs-lookup"><span data-stu-id="f3a73-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="f3a73-117">Napravite izvor podataka pod imenom **eCommerce**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.</span><span class="sxs-lookup"><span data-stu-id="f3a73-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f3a73-118">Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="f3a73-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="f3a73-119">Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f3a73-120">Ažurirajte tip podataka za dolenavedene kolone:</span><span class="sxs-lookup"><span data-stu-id="f3a73-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f3a73-121">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="f3a73-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="f3a73-122">**Kreirano**: Datum/vreme/zona</span><span class="sxs-lookup"><span data-stu-id="f3a73-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="f3a73-123">![Transformiši datum rođenja u datum](media/ecommerce-dob-date.PNG "transformacija datuma rođenja u datum")</span><span class="sxs-lookup"><span data-stu-id="f3a73-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="f3a73-124">U polju „Ime“ u desnom oknu preimenujte izvor podataka iz **Upit** u **eCommerce kontakti**</span><span class="sxs-lookup"><span data-stu-id="f3a73-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="f3a73-125">Sačuvajte izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="f3a73-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="f3a73-126">Unesite podatke o klijentima iz šeme lojalnosti</span><span class="sxs-lookup"><span data-stu-id="f3a73-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="f3a73-127">Napravite izvor podataka pod imenom **Šema lojalnosti**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.</span><span class="sxs-lookup"><span data-stu-id="f3a73-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f3a73-128">Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="f3a73-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="f3a73-129">Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f3a73-130">Ažurirajte tip podataka za dolenavedene kolone:</span><span class="sxs-lookup"><span data-stu-id="f3a73-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f3a73-131">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="f3a73-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="f3a73-132">**Nagradni poeni**: Ceo broj</span><span class="sxs-lookup"><span data-stu-id="f3a73-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="f3a73-133">**Kreirano**: Datum/vreme</span><span class="sxs-lookup"><span data-stu-id="f3a73-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="f3a73-134">U polju „Ime“ u desnom oknu preimenujte izvor podataka iz **Upit** u **Lojalni klijenti**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="f3a73-135">Sačuvajte izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="f3a73-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="f3a73-136">Unos informacija o pretplati</span><span class="sxs-lookup"><span data-stu-id="f3a73-136">Ingest subscription information</span></span>

1. <span data-ttu-id="f3a73-137">Napravite izvor podataka pod imenom **Istorija pretplata**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.</span><span class="sxs-lookup"><span data-stu-id="f3a73-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f3a73-138">Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="f3a73-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="f3a73-139">Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f3a73-140">Ažurirajte tip podataka za dolenavedene kolone:</span><span class="sxs-lookup"><span data-stu-id="f3a73-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f3a73-141">**ID pretplate**: Ceo broj</span><span class="sxs-lookup"><span data-stu-id="f3a73-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="f3a73-142">**Iznos pretplate**: Valuta</span><span class="sxs-lookup"><span data-stu-id="f3a73-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="f3a73-143">**Datum završetka pretplate**: Datum/vreme</span><span class="sxs-lookup"><span data-stu-id="f3a73-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="f3a73-144">**Datum početka pretplate**: Datum/vreme</span><span class="sxs-lookup"><span data-stu-id="f3a73-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="f3a73-145">**Datum transakcije**: Datum/vreme</span><span class="sxs-lookup"><span data-stu-id="f3a73-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="f3a73-146">**Da li se ponavlja**: Tačno/netačno</span><span class="sxs-lookup"><span data-stu-id="f3a73-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="f3a73-147">**Da_li_se_automatski_obnavlja**: Tačno/netačno</span><span class="sxs-lookup"><span data-stu-id="f3a73-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="f3a73-148">**Učestalost ponavljanja u mesecima**: Ceo broj</span><span class="sxs-lookup"><span data-stu-id="f3a73-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="f3a73-149">U polju „Ime“ u desnom oknu preimenujte izvor podataka iz **Upit** u **Istorija pretplata**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-149">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="f3a73-150">Sačuvajte izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="f3a73-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="f3a73-151">Unesite podatke o klijentima iz recenzija na veb-sajtu</span><span class="sxs-lookup"><span data-stu-id="f3a73-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="f3a73-152">Napravite izvor podataka pod imenom **Veb-sajt**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.</span><span class="sxs-lookup"><span data-stu-id="f3a73-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f3a73-153">Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="f3a73-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="f3a73-154">Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f3a73-155">Ažurirajte tip podataka za dolenavedene kolone:</span><span class="sxs-lookup"><span data-stu-id="f3a73-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f3a73-156">**Ocena iz recenzija**: Ceo broj</span><span class="sxs-lookup"><span data-stu-id="f3a73-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="f3a73-157">**Datum recenzije**: Datum</span><span class="sxs-lookup"><span data-stu-id="f3a73-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="f3a73-158">U polju „Ime“ u desnom oknu preimenujte izvor podataka iz **Upit** u **Recenzije na vebu**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="f3a73-159">2. zadatak 2 – Objedinjavanje podataka</span><span class="sxs-lookup"><span data-stu-id="f3a73-159">Task 2 - Data unification</span></span>

<span data-ttu-id="f3a73-160">Nakon unosa podataka, sada započinjemo proces **Mapiranja, podudaranja, objedinjavanja** da bismo kreirali objedinjeni profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="f3a73-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="f3a73-161">Za više informacija pogledajte [Objedinjavanje podataka](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="f3a73-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="f3a73-162">Mapiraj</span><span class="sxs-lookup"><span data-stu-id="f3a73-162">Map</span></span>

1. <span data-ttu-id="f3a73-163">Nakon unosa podataka, mapirajte kontakte sa platforme eCommerce i iz podataka o lojalnosti u uobičajene tipove podataka.</span><span class="sxs-lookup"><span data-stu-id="f3a73-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="f3a73-164">Idite na **Podaci** > **Objedini** > **Mapiraj**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="f3a73-165">Izaberite entitete koji predstavljaju profil klijenta – **eCommerce kontakti** i **Lojalni klijenti**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="objedinite izvore podataka o platform ecommerce i lojalnosti.":::

1. <span data-ttu-id="f3a73-167">Izaberite **ID klijenta** kao primarni ključ za **eCommerce kontakte** i **ID lojalnosti** kao primarni ključ za **Lojalne klijente**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Objedinite ID lojalnosti kao primarni ključ.":::

### <a name="match"></a><span data-ttu-id="f3a73-169">Podudaranje</span><span class="sxs-lookup"><span data-stu-id="f3a73-169">Match</span></span>

1. <span data-ttu-id="f3a73-170">Idite u na karticu **Podudaranje** i izaberite **Podesi redosled**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="f3a73-171">Na padajućoj listi **Primarno**, odaberite **eCommerce kontakti: eCommerce** kao primarni izvor i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="f3a73-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="f3a73-172">Na padajućoj listi **Entitet 2**, odaberite **Lojalni klijenti: Šema lojalnosti** i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="f3a73-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Objedinite podudaranje platforme eCommerce i lojalnosti.":::

1. <span data-ttu-id="f3a73-174">Izaberite **Kreiraj novo pravilo**</span><span class="sxs-lookup"><span data-stu-id="f3a73-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="f3a73-175">Dodajte svoj prvi uslov koristeći Ime i prezime.</span><span class="sxs-lookup"><span data-stu-id="f3a73-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="f3a73-176">Za eCommerce kontakte odaberite **Ime i prezime** na padajućoj listi.</span><span class="sxs-lookup"><span data-stu-id="f3a73-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="f3a73-177">Za Lojalne klijente odaberite **Ime i prezime** na padajućoj listi.</span><span class="sxs-lookup"><span data-stu-id="f3a73-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="f3a73-178">Izaberite padajuću listu **Normalizacija** i odaberite **Tip (telefon, ime, adresa...)**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="f3a73-179">Podesite **Nivo preciznosti**: **Osnovni** i **Vrednost**: **Visoka**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="f3a73-180">Unesite naziv **Ime i prezime, e-pošta** za novo pravilo.</span><span class="sxs-lookup"><span data-stu-id="f3a73-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="f3a73-181">Dodajte drugi uslov za adresu e-pošte izborom stavke **Dodajte uslov**</span><span class="sxs-lookup"><span data-stu-id="f3a73-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="f3a73-182">Za entitet eCommerce kontakti odaberite **E-pošta** u padajućem meniju.</span><span class="sxs-lookup"><span data-stu-id="f3a73-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="f3a73-183">Za entitet Lojalni klijenti odaberite **E-pošta** u padajućem meniju.</span><span class="sxs-lookup"><span data-stu-id="f3a73-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="f3a73-184">Ostavite Normalizacija prazno.</span><span class="sxs-lookup"><span data-stu-id="f3a73-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="f3a73-185">Podesite **Nivo preciznosti**: **Osnovni** i **Vrednost**: **Visoka**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Objedinite pravilo podudaranja za ime i e-poštu.":::

7. <span data-ttu-id="f3a73-187">Izaberite **Sačuvaj** i **Zatvori**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="f3a73-188">Objedini</span><span class="sxs-lookup"><span data-stu-id="f3a73-188">Merge</span></span>

1. <span data-ttu-id="f3a73-189">Idite na karticu **Objedinjavanje**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="f3a73-190">Na **ID kontakta** za entitet **Lojalni klijenti** promenite ime za prikaz u **ID kontakta LOJALNOST** da bi se razlikovalo od ostalih unetih ID-ova.</span><span class="sxs-lookup"><span data-stu-id="f3a73-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Preimenujte ID kontakta iz ID-a lojalnosti.":::

1. <span data-ttu-id="f3a73-192">Izaberite **Sačuvaj** i **Pokreni** da biste započeli postupak objedinjavanja.</span><span class="sxs-lookup"><span data-stu-id="f3a73-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="f3a73-193">3. zadatak – Konfigurišite predviđanje gubitka pretplata</span><span class="sxs-lookup"><span data-stu-id="f3a73-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="f3a73-194">Kada su objedinjeni profilima klijenata spremni, sada možemo pokrenuti predviđanje gubitka pretplata.</span><span class="sxs-lookup"><span data-stu-id="f3a73-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="f3a73-195">Za detaljne korake pogledajte članak [Predviđanje gubitka pretplata (verzija za pregled)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="f3a73-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="f3a73-196">Idite na **Obaveštavanje** > **Otkrijte** i izaberite da koristite **Model gubitka klijenata**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="f3a73-197">Izaberite opciju **Pretplata** i **Započnite**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="f3a73-198">Nazovite model **OOB predviđanje gubitka klijenata** i izlazni entitet **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="f3a73-199">Definišite dva uslova za model gubitka:</span><span class="sxs-lookup"><span data-stu-id="f3a73-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="f3a73-200">**Broj dana od završetka pretplate**: **najmanje 60** dana.</span><span class="sxs-lookup"><span data-stu-id="f3a73-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="f3a73-201">Ako klijent ne obnovi pretplatu u ovom periodu nakon njenog završetka, smatra se da ste ga izgubili.</span><span class="sxs-lookup"><span data-stu-id="f3a73-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="f3a73-202">**Definicija gubitka**: **najmanje 93** dana.</span><span class="sxs-lookup"><span data-stu-id="f3a73-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="f3a73-203">Trajanje tokom kojeg može doći do gubitka klijenata, po predviđanju modela.</span><span class="sxs-lookup"><span data-stu-id="f3a73-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="f3a73-204">Što dalje gledate u budućnost, to su rezultati manje precizni.</span><span class="sxs-lookup"><span data-stu-id="f3a73-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Izaberite regulatore modela Vremenski period predviđanja i Definicija gubitka.":::

1. <span data-ttu-id="f3a73-206">Izaberite **Dodajte potrebne podatke** i **Dodajte podatke** za istoriju pretplata.</span><span class="sxs-lookup"><span data-stu-id="f3a73-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="f3a73-207">Dodajte entitet **Pretplata: Istorija pretplata** i mapirajte polja iz platforme eCommerce sa odgovarajućim poljima koje traži model.</span><span class="sxs-lookup"><span data-stu-id="f3a73-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="f3a73-208">Pridružite entitet **Pretplata: Istorija pretplata** sa **eCommerce kontakti: eCommerce**, imenujte odnos **eCommerce pretplata**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Pridružite eCommerce entitete.":::

1. <span data-ttu-id="f3a73-210">U okviru Aktivnosti klijenata dodajte entitet **Recenzije na vebu: Veb-sajt** i mapirajte polja iz Recenzija na vebu sa odgovarajućim poljima koja traži model.</span><span class="sxs-lookup"><span data-stu-id="f3a73-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="f3a73-211">Primarni ključ: ID recenzije</span><span class="sxs-lookup"><span data-stu-id="f3a73-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="f3a73-212">Vremenska oznaka: Datum recenzije</span><span class="sxs-lookup"><span data-stu-id="f3a73-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="f3a73-213">Događaj: Ocena iz recenzija</span><span class="sxs-lookup"><span data-stu-id="f3a73-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="f3a73-214">Konfigurišite aktivnost za recenzije sa veb-sajta.</span><span class="sxs-lookup"><span data-stu-id="f3a73-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="f3a73-215">Izaberite aktivnost **Recenzija** i pridružite entitet **Recenzije na vebu: Veb-sajt** sa **eCommerce kontakti: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="f3a73-216">Izaberite **Dalje** da biste postavili raspored modela.</span><span class="sxs-lookup"><span data-stu-id="f3a73-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="f3a73-217">Model treba redovno da se obučava kako bi naučio nove obrasce kada dođe do unosa novih podataka.</span><span class="sxs-lookup"><span data-stu-id="f3a73-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="f3a73-218">Za ovaj primer izaberite **Mesečno**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="f3a73-219">Nakon pregleda svih detalja, izaberite **Sačuvaj i pokreni**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="f3a73-220">4. zadatak – Pregled rezultata modela i objašnjenja</span><span class="sxs-lookup"><span data-stu-id="f3a73-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="f3a73-221">Neka model završi obuku i ocenjivanje podataka.</span><span class="sxs-lookup"><span data-stu-id="f3a73-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="f3a73-222">Sada možete pregledati objašnjenja modela gubitka pretplata.</span><span class="sxs-lookup"><span data-stu-id="f3a73-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="f3a73-223">Za više informacija pogledajte [Pregledajte status i rezultate predviđanja](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="f3a73-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="f3a73-224">5. zadatak – Kreirajte segment klijenata sa visokim rizikom od gubitka</span><span class="sxs-lookup"><span data-stu-id="f3a73-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="f3a73-225">Pokretanje proizvodnog modela stvara novi entitet koji možete da vidite u odeljku **Podaci** > **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="f3a73-226">Možete da kreirate novi segment na osnovu entiteta koji je kreirao model.</span><span class="sxs-lookup"><span data-stu-id="f3a73-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="f3a73-227">Idite na **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-227">Go to **Segments**.</span></span> <span data-ttu-id="f3a73-228">Izaberite **Novo** i **Napravi od** > **Obaveštavanje**.</span><span class="sxs-lookup"><span data-stu-id="f3a73-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Kreirajte segment sa izlazom modela.":::

1. <span data-ttu-id="f3a73-230">Izaberite krajnju tačku **OOB predviđanje gubitka klijenata** i definišite segment:</span><span class="sxs-lookup"><span data-stu-id="f3a73-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="f3a73-231">Polje: Ocena gubitka</span><span class="sxs-lookup"><span data-stu-id="f3a73-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="f3a73-232">Operator: veće je od</span><span class="sxs-lookup"><span data-stu-id="f3a73-232">Operator: greater than</span></span>
   - <span data-ttu-id="f3a73-233">Vrednost: 0,6</span><span class="sxs-lookup"><span data-stu-id="f3a73-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Podesite segment gubitka pretplate.":::

<span data-ttu-id="f3a73-235">Sada imate segment koji se dinamički ažurira i koji identifikuje klijente sa visokim rizikom od gubitka za ovu uslugu pretplate.</span><span class="sxs-lookup"><span data-stu-id="f3a73-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="f3a73-236">Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f3a73-236">For more information, see [Create and manage segments](segments.md).</span></span>