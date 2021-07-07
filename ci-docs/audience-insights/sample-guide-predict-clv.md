---
title: Vodič kroz primere predviđanja trajne vrednosti klijenta
description: Koristite ovaj vodič kroz primere da isprobate model predviđanja trajne vrednosti klijenta.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306366"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="fa5c8-103">Vodič kroz primere predviđanja trajne vrednosti klijenta (CLV)</span><span class="sxs-lookup"><span data-stu-id="fa5c8-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="fa5c8-104">Ovaj vodič će vam objasniti celokupan primer predviđanja trajne vrednosti klijenta (CLV) u usluzi Customer Insights korišćenjem primera podataka.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="fa5c8-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="fa5c8-105">Scenario</span></span>

<span data-ttu-id="fa5c8-106">Contoso je preduzeće koje proizvodi visokokvalitetnu kafu i aparate za kafu.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="fa5c8-107">Proizvode prodaju preko svoje veb-lokacije Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="fa5c8-108">Preduzeće želi da razume vrednost (prihod) koju njihovi klijenti mogu da generišu u sledećih 12 meseci.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="fa5c8-109">Poznavanje očekivane vrednosti klijenata u sledećih 12 meseci pomoći će im da svoje marketinške napore usmere na klijente visoke vrednosti.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fa5c8-110">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="fa5c8-110">Prerequisites</span></span>

- <span data-ttu-id="fa5c8-111">Najmanje [dozvole saradnika](permissions.md) u uvidima u ciljnu grupu.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="fa5c8-112">Preporučujemo da primenite sledeće korake [u novom okruženju](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="fa5c8-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="fa5c8-113">1. zadatak – Unos podataka</span><span class="sxs-lookup"><span data-stu-id="fa5c8-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="fa5c8-114">Pregledajte članke [o unosu podataka](data-sources.md) i [uvozu izvora podataka pomoću Power Query konektora](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="fa5c8-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="fa5c8-115">Sledeće informacije pretpostavljaju da ste se upoznali sa unošenjem podataka uopšte.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="fa5c8-116">Unesite podatke o klijentima sa platforme eCommerce</span><span class="sxs-lookup"><span data-stu-id="fa5c8-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="fa5c8-117">Napravite izvor podataka pod nazivom **eCommerce**, izaberite opciju uvoza, pa izaberite konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="fa5c8-118">Unesite URL adresu za eCommerce kontakte [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="fa5c8-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="fa5c8-119">Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="fa5c8-120">Ažurirajte tip podataka za dolenavedene kolone:</span><span class="sxs-lookup"><span data-stu-id="fa5c8-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="fa5c8-121">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="fa5c8-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="fa5c8-122">**Kreirano**: Datum/vreme/zona</span><span class="sxs-lookup"><span data-stu-id="fa5c8-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformacija datuma rođenja u datum.":::

1. <span data-ttu-id="fa5c8-124">U polju „Ime“ u desnom oknu preimenujte izvor podataka iz **Upit** u **eCommerce kontakti**</span><span class="sxs-lookup"><span data-stu-id="fa5c8-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="fa5c8-125">**Sačuvajte** izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="fa5c8-126">Unesite podatke o kupovini na mreži</span><span class="sxs-lookup"><span data-stu-id="fa5c8-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="fa5c8-127">Dodajte još jedan skup podatka u isti **eCommerce** izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="fa5c8-128">Ponovo izaberite konektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="fa5c8-129">Unesite URL za podatke o **kupovinama na mreži** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="fa5c8-130">Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="fa5c8-131">Ažurirajte tip podataka za dolenavedene kolone:</span><span class="sxs-lookup"><span data-stu-id="fa5c8-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="fa5c8-132">**Kupljeno dana**: Datum/vreme</span><span class="sxs-lookup"><span data-stu-id="fa5c8-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="fa5c8-133">**Ukupna cena**: Valuta</span><span class="sxs-lookup"><span data-stu-id="fa5c8-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="fa5c8-134">U polju **Naziv** u bočnom oknu preimenujte izvor podataka iz **Upit** u **eCommerce kupovine**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="fa5c8-135">**Sačuvajte** izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="fa5c8-136">Unesite podatke o klijentima iz šeme lojalnosti</span><span class="sxs-lookup"><span data-stu-id="fa5c8-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="fa5c8-137">Napravite izvor podataka pod imenom **Šema lojalnosti**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="fa5c8-138">Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="fa5c8-139">Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="fa5c8-140">Ažurirajte tip podataka za dolenavedene kolone:</span><span class="sxs-lookup"><span data-stu-id="fa5c8-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="fa5c8-141">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="fa5c8-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="fa5c8-142">**Nagradni poeni**: Ceo broj</span><span class="sxs-lookup"><span data-stu-id="fa5c8-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="fa5c8-143">**Kreirano**: Datum/vreme</span><span class="sxs-lookup"><span data-stu-id="fa5c8-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="fa5c8-144">U polju **Ime** u desnom oknu preimenujte izvor podataka iz **Upit** u **Lojalni klijenti**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="fa5c8-145">**Sačuvajte** izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="fa5c8-146">Unesite podatke o klijentima iz recenzija na veb-sajtu</span><span class="sxs-lookup"><span data-stu-id="fa5c8-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="fa5c8-147">Napravite izvor podataka pod imenom **Veb-sajt**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="fa5c8-148">Unesite URL adresu za eCommerce kontakte https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="fa5c8-149">Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="fa5c8-150">Ažurirajte tip podataka za dolenavedene kolone:</span><span class="sxs-lookup"><span data-stu-id="fa5c8-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="fa5c8-151">**ReviewRating**: decimalni broj</span><span class="sxs-lookup"><span data-stu-id="fa5c8-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="fa5c8-152">**Datum recenzije**: Datum</span><span class="sxs-lookup"><span data-stu-id="fa5c8-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="fa5c8-153">U polju „Naziv“ u desnom oknu, preimenujte izvor podataka iz **Upit** u **Pregledi**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="fa5c8-154">**Sačuvajte** izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="fa5c8-155">2. zadatak 2 – Objedinjavanje podataka</span><span class="sxs-lookup"><span data-stu-id="fa5c8-155">Task 2 - Data unification</span></span>

<span data-ttu-id="fa5c8-156">Nakon unosa podataka, sada započinjemo postupak ujednačavanja podataka kako bismo kreirali jedinstveni profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="fa5c8-157">Za više informacija pogledajte [Objedinjavanje podataka](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="fa5c8-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="fa5c8-158">Mapiraj</span><span class="sxs-lookup"><span data-stu-id="fa5c8-158">Map</span></span>

1. <span data-ttu-id="fa5c8-159">Nakon unosa podataka, mapirajte kontakte sa platforme eCommerce i iz podataka o lojalnosti u uobičajene tipove podataka.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="fa5c8-160">Idite na **Podaci** > **Objedini** > **Mapiraj**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="fa5c8-161">Izaberite entitete koji predstavljaju profil klijenta – **eCommerce kontakti** i **Lojalni klijenti**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="fa5c8-162">Zatim izaberite **Primeni**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-162">Then, select **Apply**.</span></span>

   ![objedinite izvore podataka o platform ecommerce i lojalnosti.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="fa5c8-164">Izaberite **ID klijenta** kao primarni ključ za **eCommerce kontakte** i **ID lojalnosti** kao primarni ključ za **Lojalne klijente**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Objedinite ID lojalnosti kao primarni ključ.](media/unify-loyaltyid.png)

1. <span data-ttu-id="fa5c8-166">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="fa5c8-167">Podudaranje</span><span class="sxs-lookup"><span data-stu-id="fa5c8-167">Match</span></span>

1. <span data-ttu-id="fa5c8-168">Idite u na karticu **Podudaranje** i izaberite **Podesi redosled**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="fa5c8-169">U padajućoj listi **Primarno** odaberite **eCommerceContacts : eCommerce** kao primarni izvor i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-169">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="fa5c8-170">U padajućoj listi **Entitet 2** odaberite **loyCustomers : LoyaltyScheme** i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-170">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Objedinite podudaranje platforme eCommerce i lojalnosti.](media/unify-match-order.png)

1. <span data-ttu-id="fa5c8-172">Izaberite **Dodaj pravilo**</span><span class="sxs-lookup"><span data-stu-id="fa5c8-172">Select **Add rule**</span></span>

1. <span data-ttu-id="fa5c8-173">Dodajte svoj prvi uslov koristeći Ime i prezime.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="fa5c8-174">Za eCommerceContacts izaberite **FullName** u padajućoj listi.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-174">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="fa5c8-175">Za loyCustomers izaberite **FullName** u padajućoj listi.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-175">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="fa5c8-176">Izaberite padajuću listu **Normalizacija** i odaberite **Tip (telefon, ime, adresa, ...)**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-176">Select the **Normalize** dropdown and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="fa5c8-177">Podesite **Nivo preciznosti**: **Osnovni** i **Vrednost**: **Visoka**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="fa5c8-178">Unesite naziv **Ime i prezime, e-pošta** za novo pravilo.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="fa5c8-179">Dodajte drugi uslov za adresu e-pošte izborom stavke **Dodajte uslov**</span><span class="sxs-lookup"><span data-stu-id="fa5c8-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="fa5c8-180">Za entitet eCommerceContacts, odaberite **EMail** u padajućoj listi.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-180">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="fa5c8-181">Za entitet loyCustomers, odaberite **EMail** u padajućoj listi.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-181">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="fa5c8-182">Ostavite Normalizacija prazno.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="fa5c8-183">Podesite **Nivo preciznosti**: **Osnovni** i **Vrednost**: **Visoka**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Objedinite pravilo podudaranja za ime i e-poštu.](media/unify-match-rule.png)

1. <span data-ttu-id="fa5c8-185">Izaberite **Gotovo**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-185">Select **Done**.</span></span>

1. <span data-ttu-id="fa5c8-186">Izaberite **Sačuvaj** i **Zatvori**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="fa5c8-187">Objedini</span><span class="sxs-lookup"><span data-stu-id="fa5c8-187">Merge</span></span>

1. <span data-ttu-id="fa5c8-188">Idite na karticu **Objedinjavanje**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="fa5c8-189">Na **ID kontakta** za entitet **Lojalni klijenti** promenite ime za prikaz u **ID kontakta LOJALNOST** da bi se razlikovalo od ostalih unetih ID-ova.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Preimenujte ID kontakta iz ID-a lojalnosti.](media/unify-merge-contactid.png)

1. <span data-ttu-id="fa5c8-191">Izaberite **Sačuvaj** i **Pokreni procese objedinjavanja i posledičnog premeštanja**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="fa5c8-192">Zadatak 3 – Konfigurisanje predviđanja trajne vrednosti klijenta</span><span class="sxs-lookup"><span data-stu-id="fa5c8-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="fa5c8-193">Sa uspostavljenim objedinjenim profilima klijenata, sada možemo pokrenuti predviđanje trajne vrednosti klijenta.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="fa5c8-194">Za detaljne korake, pogledajte [Predviđanje trajne vrednosti klijenta (verzija za pregled)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="fa5c8-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="fa5c8-195">Idite na **Obaveštavanje**  > **Predviđanja** i izaberite **Model trajne vrednosti klijenta**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="fa5c8-196">Pređite kroz informacije u bočnom oknu i izaberite **Započni**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="fa5c8-197">Nazovite model **OOB eCommerce CLV Prediction** a izlazni entitet **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="fa5c8-198">Definišite željene opcije modela za CLV model:</span><span class="sxs-lookup"><span data-stu-id="fa5c8-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="fa5c8-199">**Vremenski period predviđanja**: **12 meseci ili 1 godina**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="fa5c8-200">Ovo podešavanje definiše koliko u budućnosti treba predviđati trajnu vrednost klijenta.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="fa5c8-201">**Aktivni klijenti**: Navedite šta aktivni klijenti znače za vaše poslovanje.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="fa5c8-202">Podesite vremenski okvir prethodnog perioda u kojem je klijent morao imati barem jednu transakciju da bi se smatrao aktivnim.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="fa5c8-203">Model će predvideti CLV samo za aktivne klijente.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="fa5c8-204">Odaberite između dopuštanja modelu da izračuna vremenski period na osnovu istorijskih podataka o transakcijama ili navedite određeni vremenski okvir.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="fa5c8-205">U ovom vodiču kroz primer, mi **omogućavamo modelu da izračuna interval kupovine**, što je podrazumevana opcija.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="fa5c8-206">**Klijenti velike vrednosti**: Klijente visoke vrednosti definišite kao procenat klijenata koji najviše plaćaju.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="fa5c8-207">Model koristi ovaj ulaz za pružanje rezultata koji se uklapaju u vašu poslovnu definiciju klijenata velike vrednosti.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="fa5c8-208">Možete odabrati da omogućite modelu da definiše klijente visoke vrednosti.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="fa5c8-209">Koristi heurističko pravilo koje izvodi percentil.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="fa5c8-210">Klijente visoke vrednosti možete definisati kao procenat klijenata koji će najviše plaćati u budućnosti.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="fa5c8-211">U ovom vodiču kroz primere, ručno definišemo klijente velike vrednosti kao **30% aktivnih klijenata koji plaćaju** i izaberite **Sledeći**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Korak željenih opcija u navođenom iskustvu za CLV model.":::

1. <span data-ttu-id="fa5c8-213">U koraku **Potrebni podaci**, izaberite **Dodaj podatke** da biste pružili podatke o transakcijama u prethodnom periodu.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="fa5c8-214">Dodajte entitet **eCommercePurchases : eCommerce** i mapirajte atribute koji su potrebni modelu:</span><span class="sxs-lookup"><span data-stu-id="fa5c8-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="fa5c8-215">ID transakcije: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="fa5c8-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="fa5c8-216">Datum transakcije: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="fa5c8-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="fa5c8-217">Iznos transakcije: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="fa5c8-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="fa5c8-218">ID proizvoda: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="fa5c8-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="fa5c8-219">Izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-219">Select **Next**.</span></span>

1. <span data-ttu-id="fa5c8-220">Podesite relaciju između entiteta **eCommercePurchases : eCommerce** i **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="fa5c8-221">Korak **Dodatni podaci (opcionalno)** vam omogućava da dodate više podataka o aktivnostima klijenata.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="fa5c8-222">Ovi podaci mogu vam pomoći da dobijete više uvida o interakciji klijenata sa vašim preduzećem, što može doprineti modelu CLV.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="fa5c8-223">Dodavanje ključnih interakcija sa klijentima poput veb-evidencije, evidencija korisničke službe ili programa nagrađivanja u prethodnom periodu može poboljšati tačnost predviđanja.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="fa5c8-224">Izaberite **Dodaj podatke** da biste uključili više podataka o aktivnostima klijenata.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="fa5c8-225">Dodajte entitet aktivnosti klijenta i mapirajte nazive njegovih polja u odgovarajuća polja koja zahteva model:</span><span class="sxs-lookup"><span data-stu-id="fa5c8-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="fa5c8-226">Entitet aktivnosti klijenta: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="fa5c8-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="fa5c8-227">Primarni ključ: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="fa5c8-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="fa5c8-228">Vremenska oznaka: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="fa5c8-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="fa5c8-229">Događaj (naziv aktivnosti): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="fa5c8-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="fa5c8-230">Detalji (iznos ili vrednost): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="fa5c8-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="fa5c8-231">Izaberite **Sledeće** i konfigurišite aktivnost i relaciju između podataka o transakciji i podataka o klijentu:</span><span class="sxs-lookup"><span data-stu-id="fa5c8-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="fa5c8-232">Tip aktivnosti: Odaberite postojeći</span><span class="sxs-lookup"><span data-stu-id="fa5c8-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="fa5c8-233">Oznaka aktivnosti: Review</span><span class="sxs-lookup"><span data-stu-id="fa5c8-233">Activity label: Review</span></span>
   - <span data-ttu-id="fa5c8-234">Odgovarajuća oznaka: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="fa5c8-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="fa5c8-235">Entitet klijenta: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="fa5c8-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="fa5c8-236">Relacija: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="fa5c8-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="fa5c8-237">Izaberite **Dalje** da biste postavili raspored modela.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="fa5c8-238">Model treba redovno trenirati da bi naučio nove obrasce kada se unose novi podaci.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="fa5c8-239">Za ovaj primer, odaberite **Mesečno**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="fa5c8-240">Nakon pregleda svih detalja, izaberite **Sačuvaj i pokreni**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="fa5c8-241">4. zadatak – Pregled rezultata modela i objašnjenja</span><span class="sxs-lookup"><span data-stu-id="fa5c8-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="fa5c8-242">Neka model završi obuku i ocenjivanje podataka.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="fa5c8-243">Zatim možete pregledati rezultate i objašnjenja CLV modela.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="fa5c8-244">Za više informacija pogledajte [Pregledajte status i rezultate predviđanja](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="fa5c8-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="fa5c8-245">5. zadatak – Kreiranje segmenta klijenata velike vrednosti</span><span class="sxs-lookup"><span data-stu-id="fa5c8-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="fa5c8-246">Pokretanje modela kreiran novi entitet, koji je naveden na **Podaci** > **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="fa5c8-247">Možete da kreirate novi segment klijenata na osnovu entiteta koji je kreirao model.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="fa5c8-248">Idite na **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="fa5c8-249">Izaberite **Novo**, pa **Napravi od** > **Obaveštavanje**.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Kreirajte segment sa izlazom modela.](media/segment-intelligence.png)

1. <span data-ttu-id="fa5c8-251">Izaberite entitet **OOBeCommerceCLVPrediction** entitet i definišite segment:</span><span class="sxs-lookup"><span data-stu-id="fa5c8-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="fa5c8-252">Polje: CLVScore</span><span class="sxs-lookup"><span data-stu-id="fa5c8-252">Field: CLVScore</span></span>
  - <span data-ttu-id="fa5c8-253">Operator: veće je od</span><span class="sxs-lookup"><span data-stu-id="fa5c8-253">Operator: greater than</span></span>
  - <span data-ttu-id="fa5c8-254">Vrednost: 1500</span><span class="sxs-lookup"><span data-stu-id="fa5c8-254">Value: 1500</span></span>

1. <span data-ttu-id="fa5c8-255">Izaberite **Pregled** i **sačuvajte** segment.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="fa5c8-256">Sada imate segment koji identifikuje klijente za koje se predviđa da će ostvariti više od 1500 $ prihoda u sledećih 12 meseci.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="fa5c8-257">Ovaj segment se dinamički ažurira ako se unese više podataka.</span><span class="sxs-lookup"><span data-stu-id="fa5c8-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="fa5c8-258">Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).</span><span class="sxs-lookup"><span data-stu-id="fa5c8-258">For more information, see [Create and manage segments](segments.md).</span></span>
