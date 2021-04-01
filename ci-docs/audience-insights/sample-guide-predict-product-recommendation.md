---
title: Primer vodiča za predviđanje preporuka proizvoda
description: Koristite ovaj primer vodiča da biste isprobali ovaj gotovi model predviđanja preporuka proizvoda.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595290"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="70e08-103">Primer vodiča za predviđanje preporuka proizvoda (pregled)</span><span class="sxs-lookup"><span data-stu-id="70e08-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="70e08-104">Objasnićemo vam kompletan primer predviđanja preporuke proizvoda pomoću primera podataka navedenih u nastavku.</span><span class="sxs-lookup"><span data-stu-id="70e08-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="70e08-105">Scenario</span><span class="sxs-lookup"><span data-stu-id="70e08-105">Scenario</span></span>

<span data-ttu-id="70e08-106">Contoso je kompanija koja proizvodi visokokvalitetnu kafu i aparate za kafu, koje prodaju putem svog veb-sajta Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="70e08-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="70e08-107">Cilj im je da razumeju koje proizvode bi trebalo da preporuče svojim redovnim klijentima.</span><span class="sxs-lookup"><span data-stu-id="70e08-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="70e08-108">Saznanje šta će klijenti **verovatnije kupiti** može im pomoći da uštede marketinške napore fokusiranjem na određene stavke.</span><span class="sxs-lookup"><span data-stu-id="70e08-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="70e08-109">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="70e08-109">Prerequisites</span></span>

- <span data-ttu-id="70e08-110">Barem [dozvole saradnika](permissions.md) u usluzi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="70e08-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="70e08-111">Preporučujemo da primenite sledeće korake [u novom okruženju](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="70e08-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="70e08-112">1. zadatak – Unos podataka</span><span class="sxs-lookup"><span data-stu-id="70e08-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="70e08-113">Pregledajte članke [o unosu podataka](data-sources.md) i [uvozu izvora podataka pomoću Power Query konektora](connect-power-query.md) konkretno.</span><span class="sxs-lookup"><span data-stu-id="70e08-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="70e08-114">Sledeće informacije pretpostavljaju da ste se upoznali sa unošenjem podataka uopšte.</span><span class="sxs-lookup"><span data-stu-id="70e08-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="70e08-115">Unesite podatke o klijentima sa platforme eCommerce</span><span class="sxs-lookup"><span data-stu-id="70e08-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="70e08-116">Napravite izvor podataka pod imenom **eCommerce**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.</span><span class="sxs-lookup"><span data-stu-id="70e08-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="70e08-117">Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="70e08-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="70e08-118">Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="70e08-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="70e08-119">Ažurirajte tip podataka za dolenavedene kolone:</span><span class="sxs-lookup"><span data-stu-id="70e08-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="70e08-120">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="70e08-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="70e08-121">**Kreirano**: Datum/vreme/zona</span><span class="sxs-lookup"><span data-stu-id="70e08-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformacija datuma rođenja u datum.":::

5. <span data-ttu-id="70e08-123">U polju „Ime“ u desnom oknu preimenujte izvor podataka iz **Upit** u **eCommerce kontakti**</span><span class="sxs-lookup"><span data-stu-id="70e08-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="70e08-124">**Sačuvajte** izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="70e08-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="70e08-125">Unesite podatke o kupovini na mreži</span><span class="sxs-lookup"><span data-stu-id="70e08-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="70e08-126">Dodajte još jedan skup podatka u isti **eCommerce** izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="70e08-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="70e08-127">Ponovo izaberite konektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="70e08-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="70e08-128">Unesite URL za podatke o **kupovinama na mreži** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="70e08-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="70e08-129">Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="70e08-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="70e08-130">Ažurirajte tip podataka za dolenavedene kolone:</span><span class="sxs-lookup"><span data-stu-id="70e08-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="70e08-131">**Kupljeno dana**: Datum/vreme</span><span class="sxs-lookup"><span data-stu-id="70e08-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="70e08-132">**Ukupna cena**: Valuta</span><span class="sxs-lookup"><span data-stu-id="70e08-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="70e08-133">U polju **Naziv** u bočnom oknu preimenujte izvor podataka iz **Upit** u **eCommerce kupovine**.</span><span class="sxs-lookup"><span data-stu-id="70e08-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="70e08-134">Sačuvajte izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="70e08-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="70e08-135">Unesite podatke o klijentima iz šeme lojalnosti</span><span class="sxs-lookup"><span data-stu-id="70e08-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="70e08-136">Napravite izvor podataka pod imenom **Šema lojalnosti**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.</span><span class="sxs-lookup"><span data-stu-id="70e08-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="70e08-137">Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="70e08-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="70e08-138">Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="70e08-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="70e08-139">Ažurirajte tip podataka za dolenavedene kolone:</span><span class="sxs-lookup"><span data-stu-id="70e08-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="70e08-140">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="70e08-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="70e08-141">**Nagradni poeni**: Ceo broj</span><span class="sxs-lookup"><span data-stu-id="70e08-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="70e08-142">**Kreirano**: Datum/vreme</span><span class="sxs-lookup"><span data-stu-id="70e08-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="70e08-143">U polju **Ime** u desnom oknu preimenujte izvor podataka iz **Upit** u **Lojalni klijenti**.</span><span class="sxs-lookup"><span data-stu-id="70e08-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="70e08-144">Sačuvajte izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="70e08-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="70e08-145">2. zadatak 2 – Objedinjavanje podataka</span><span class="sxs-lookup"><span data-stu-id="70e08-145">Task 2 - Data unification</span></span>

<span data-ttu-id="70e08-146">Nakon unosa podataka, sada započinjemo proces **Mapiranja, podudaranja, objedinjavanja** da bismo kreirali objedinjeni profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="70e08-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="70e08-147">Za više informacija pogledajte [Objedinjavanje podataka](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="70e08-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="70e08-148">Mapiraj</span><span class="sxs-lookup"><span data-stu-id="70e08-148">Map</span></span>

1. <span data-ttu-id="70e08-149">Nakon unosa podataka, mapirajte kontakte sa platforme eCommerce i iz podataka o lojalnosti u uobičajene tipove podataka.</span><span class="sxs-lookup"><span data-stu-id="70e08-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="70e08-150">Idite na **Podaci** > **Objedini** > **Mapiraj**.</span><span class="sxs-lookup"><span data-stu-id="70e08-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="70e08-151">Izaberite entitete koji predstavljaju profil klijenta – **eCommerce kontakti** i **Lojalni klijenti**.</span><span class="sxs-lookup"><span data-stu-id="70e08-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![objedinite izvore podataka o platform ecommerce i lojalnosti.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="70e08-153">Izaberite **ID klijenta** kao primarni ključ za **eCommerce kontakte** i **ID lojalnosti** kao primarni ključ za **Lojalne klijente**.</span><span class="sxs-lookup"><span data-stu-id="70e08-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Objedinite ID lojalnosti kao primarni ključ.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="70e08-155">Podudaranje</span><span class="sxs-lookup"><span data-stu-id="70e08-155">Match</span></span>

1. <span data-ttu-id="70e08-156">Idite u na karticu **Podudaranje** i izaberite **Podesi redosled**.</span><span class="sxs-lookup"><span data-stu-id="70e08-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="70e08-157">Na padajućoj listi **Primarno**, odaberite **eCommerce kontakti: eCommerce** kao primarni izvor i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="70e08-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="70e08-158">Na padajućoj listi **Entitet 2**, odaberite **Lojalni klijenti: Šema lojalnosti** i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="70e08-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Objedinite podudaranje platforme eCommerce i lojalnosti.](media/unify-match-order.png)

4. <span data-ttu-id="70e08-160">Izaberite **Kreiraj novo pravilo**</span><span class="sxs-lookup"><span data-stu-id="70e08-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="70e08-161">Dodajte svoj prvi uslov koristeći Ime i prezime.</span><span class="sxs-lookup"><span data-stu-id="70e08-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="70e08-162">Za eCommerce kontakte odaberite **Ime i prezime** na padajućoj listi.</span><span class="sxs-lookup"><span data-stu-id="70e08-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="70e08-163">Za Lojalne klijente odaberite **Ime i prezime** na padajućoj listi.</span><span class="sxs-lookup"><span data-stu-id="70e08-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="70e08-164">Izaberite padajuću listu **Normalizacija** i odaberite **Tip (telefon, ime, adresa...)**.</span><span class="sxs-lookup"><span data-stu-id="70e08-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="70e08-165">Podesite **Nivo preciznosti**: **Osnovni** i **Vrednost**: **Visoka**.</span><span class="sxs-lookup"><span data-stu-id="70e08-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="70e08-166">Unesite naziv **Ime i prezime, e-pošta** za novo pravilo.</span><span class="sxs-lookup"><span data-stu-id="70e08-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="70e08-167">Dodajte drugi uslov za adresu e-pošte izborom stavke **Dodajte uslov**</span><span class="sxs-lookup"><span data-stu-id="70e08-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="70e08-168">Za entitet eCommerce kontakti odaberite **E-pošta** u padajućem meniju.</span><span class="sxs-lookup"><span data-stu-id="70e08-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="70e08-169">Za entitet Lojalni klijenti odaberite **E-pošta** u padajućem meniju.</span><span class="sxs-lookup"><span data-stu-id="70e08-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="70e08-170">Ostavite Normalizacija prazno.</span><span class="sxs-lookup"><span data-stu-id="70e08-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="70e08-171">Podesite **Nivo preciznosti**: **Osnovni** i **Vrednost**: **Visoka**.</span><span class="sxs-lookup"><span data-stu-id="70e08-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Objedinite pravilo podudaranja za ime i e-poštu.](media/unify-match-rule.png)

7. <span data-ttu-id="70e08-173">Izaberite **Sačuvaj** i **Zatvori**.</span><span class="sxs-lookup"><span data-stu-id="70e08-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="70e08-174">Objedini</span><span class="sxs-lookup"><span data-stu-id="70e08-174">Merge</span></span>

1. <span data-ttu-id="70e08-175">Idite na karticu **Objedinjavanje**.</span><span class="sxs-lookup"><span data-stu-id="70e08-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="70e08-176">Na **ID kontakta** za entitet **Lojalni klijenti** promenite ime za prikaz u **ID kontakta LOJALNOST** da bi se razlikovalo od ostalih unetih ID-ova.</span><span class="sxs-lookup"><span data-stu-id="70e08-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Preimenujte ID kontakta iz ID-a lojalnosti.](media/unify-merge-contactid.png)

1. <span data-ttu-id="70e08-178">Izaberite **Sačuvaj** i **Pokreni** da biste započeli postupak objedinjavanja.</span><span class="sxs-lookup"><span data-stu-id="70e08-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="70e08-179">Zadatak 3 – Konfigurišite predviđanje preporuke proizvoda</span><span class="sxs-lookup"><span data-stu-id="70e08-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="70e08-180">Kada su objedinjeni profilima klijenata spremni, sada možemo pokrenuti predviđanje gubitka pretplata.</span><span class="sxs-lookup"><span data-stu-id="70e08-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="70e08-181">Idite na **Obaveštavanje** > **Predviđanje** i odaberite **Preporuka proizvoda**.</span><span class="sxs-lookup"><span data-stu-id="70e08-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="70e08-182">Izaberite **Prvi koraci**.</span><span class="sxs-lookup"><span data-stu-id="70e08-182">Select **Get started**.</span></span>

1. <span data-ttu-id="70e08-183">Imenujte model **Predviđanje modela preporuke OOB proizvoda** a izlazni entitet **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="70e08-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="70e08-184">Definišite tri uslova za model:</span><span class="sxs-lookup"><span data-stu-id="70e08-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="70e08-185">**Broj proizvoda**: Podesite ovu vrednost na **5**.</span><span class="sxs-lookup"><span data-stu-id="70e08-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="70e08-186">Ovo podešavanje definiše koliko proizvoda želite da preporučite svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="70e08-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="70e08-187">**Predlažete proizvode koje su klijenti nedavno kupili?**: Izaberite **Da** kako biste naznačili da želite da dodate proizvode u preporuku koju su vaši klijenti ranije kupili.</span><span class="sxs-lookup"><span data-stu-id="70e08-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="70e08-188">**Period za reviziju** Izaberite najmanje **365 dana**.</span><span class="sxs-lookup"><span data-stu-id="70e08-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="70e08-189">Ovo podešavanje definiše koliko daleko unazad će model pratiti aktivnost klijenta da bi ga koristio kao ulaz za preporuke.</span><span class="sxs-lookup"><span data-stu-id="70e08-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Željena podešavanja modela za model preporuke proizvoda.":::

1. <span data-ttu-id="70e08-191">Izaberite **Obavezni podaci** i izaberite **Dodaj podatke** za istoriju kupovina.</span><span class="sxs-lookup"><span data-stu-id="70e08-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="70e08-192">Dodajte entitet **eCommerce kupovine: eCommerce** i mapirajte polja iz platforme eCommerce sa odgovarajućim poljima koje traži model.</span><span class="sxs-lookup"><span data-stu-id="70e08-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="70e08-193">Pridružite entite **eCommerce kupovine: eCommerce** sa **eCommerce kontakti: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="70e08-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Pridružite eCommerce entitete.](media/model-purchase-join.png)

1. <span data-ttu-id="70e08-195">Izaberite **Dalje** da biste postavili raspored modela.</span><span class="sxs-lookup"><span data-stu-id="70e08-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="70e08-196">Model treba redovno da se obučava kako bi naučio nove obrasce kada dođe do unosa novih podataka.</span><span class="sxs-lookup"><span data-stu-id="70e08-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="70e08-197">Za ovaj primer izaberite **Mesečno**.</span><span class="sxs-lookup"><span data-stu-id="70e08-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="70e08-198">Nakon pregleda svih detalja, izaberite **Sačuvaj i pokreni**.</span><span class="sxs-lookup"><span data-stu-id="70e08-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="70e08-199">4. zadatak – Pregled rezultata modela i objašnjenja</span><span class="sxs-lookup"><span data-stu-id="70e08-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="70e08-200">Neka model završi obuku i ocenjivanje podataka.</span><span class="sxs-lookup"><span data-stu-id="70e08-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="70e08-201">Sada možete pregledati objašnjenja modela preporuka proizvoda.</span><span class="sxs-lookup"><span data-stu-id="70e08-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="70e08-202">Za više informacija pogledajte [Pregledajte status i rezultate predviđanja](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="70e08-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="70e08-203">Zadatak 5 – Napravite segment proizvoda koji se često kupuju</span><span class="sxs-lookup"><span data-stu-id="70e08-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="70e08-204">Pokretanje proizvodnog modela stvara novi entitet koji možete da vidite u odeljku **Podaci** > **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="70e08-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="70e08-205">Možete da kreirate novi segment na osnovu entiteta koji je kreirao model.</span><span class="sxs-lookup"><span data-stu-id="70e08-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="70e08-206">Idite na **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="70e08-206">Go to **Segments**.</span></span> <span data-ttu-id="70e08-207">Izaberite **Novo** i **Napravi od** > **Obaveštavanje**.</span><span class="sxs-lookup"><span data-stu-id="70e08-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Kreirajte segment sa izlazom modela.](media/segment-intelligence.png)

1. <span data-ttu-id="70e08-209">Izaberite krajnju tačku **OOBProductRecommendationModelPrediction** i definišite segment:</span><span class="sxs-lookup"><span data-stu-id="70e08-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="70e08-210">Polje: ProductID</span><span class="sxs-lookup"><span data-stu-id="70e08-210">Field: ProductID</span></span>
   - <span data-ttu-id="70e08-211">Operator: Vrednost</span><span class="sxs-lookup"><span data-stu-id="70e08-211">Operator: Value</span></span>
   - <span data-ttu-id="70e08-212">Vrednost: Izaberite prva tri ID-a proizvoda</span><span class="sxs-lookup"><span data-stu-id="70e08-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Kreirajte segment iz rezultata modela.":::

<span data-ttu-id="70e08-214">Sada imate segment koji se dinamički ažurira i koji identifikuje klijente koji su spremniji da kupe tri najbolje preporučena proizvoda</span><span class="sxs-lookup"><span data-stu-id="70e08-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="70e08-215">Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).</span><span class="sxs-lookup"><span data-stu-id="70e08-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]