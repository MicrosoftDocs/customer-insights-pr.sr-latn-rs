---
title: Primer vodiča za predviđanje gubitka transakcija
description: Koristite ovaj primer vodiča da biste isprobali spreman model predviđanja gubitka transakcija.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 055708ed3f9f468cad83ecf976a460814bf05199
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643610"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="9e795-103">Primer vodiča za predviđanje gubitka transakcija (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="9e795-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="9e795-104">Ovaj vodič vam objašnjava vam kompletan primer predviđanja gubitka transakcija u usluzi Customer Insights pomoću podataka navedenih u nastavku.</span><span class="sxs-lookup"><span data-stu-id="9e795-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="9e795-105">Svi podaci korišćeni u ovom vodiču nisu stvarni podaci o klijentima i deo su skupa podataka Contoso koji se nalazi u *Demo* okruženju u okviru pretplate na Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9e795-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="9e795-106">Scenario</span><span class="sxs-lookup"><span data-stu-id="9e795-106">Scenario</span></span>

<span data-ttu-id="9e795-107">Contoso je kompanija koja proizvodi visokokvalitetnu kafu i aparate za kafu, koje prodaju putem svog veb-sajta Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="9e795-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="9e795-108">Cilj im je da saznaju koji će klijenti koji obično redovno kupuju njihove proizvode prestati da budu aktivni klijenti u narednih 60 dana.</span><span class="sxs-lookup"><span data-stu-id="9e795-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="9e795-109">Kada znaju koje klijente će **verovatno izgubiti**, mogu da uštede na marketinškim kampanjama i fokusiraju se na njihovo zadržavanje.</span><span class="sxs-lookup"><span data-stu-id="9e795-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9e795-110">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="9e795-110">Prerequisites</span></span>

- <span data-ttu-id="9e795-111">Barem [dozvole saradnika](permissions.md) u usluzi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9e795-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="9e795-112">Preporučujemo da primenite sledeće korake [u novom okruženju](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="9e795-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="9e795-113">1. zadatak – Unos podataka</span><span class="sxs-lookup"><span data-stu-id="9e795-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="9e795-114">Pregledajte članke [o unosu podataka](data-sources.md) i [uvozu izvora podataka pomoću Power Query konektora](connect-power-query.md) konkretno.</span><span class="sxs-lookup"><span data-stu-id="9e795-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="9e795-115">Sledeće informacije pretpostavljaju da ste se upoznali sa unošenjem podataka uopšte.</span><span class="sxs-lookup"><span data-stu-id="9e795-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="9e795-116">Unesite podatke o klijentima sa platforme eCommerce</span><span class="sxs-lookup"><span data-stu-id="9e795-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="9e795-117">Napravite izvor podataka pod imenom **eCommerce**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.</span><span class="sxs-lookup"><span data-stu-id="9e795-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9e795-118">Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="9e795-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="9e795-119">Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="9e795-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9e795-120">Ažurirajte tip podataka za dolenavedene kolone:</span><span class="sxs-lookup"><span data-stu-id="9e795-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="9e795-121">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="9e795-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="9e795-122">**Kreirano**: Datum/vreme/zona</span><span class="sxs-lookup"><span data-stu-id="9e795-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="9e795-123">![Transformiši datum rođenja u datum](media/ecommerce-dob-date.PNG "transformacija datuma rođenja u datum")</span><span class="sxs-lookup"><span data-stu-id="9e795-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="9e795-124">U polju „Ime“ u desnom oknu preimenujte izvor podataka iz **Upit** u **eCommerce kontakti**</span><span class="sxs-lookup"><span data-stu-id="9e795-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="9e795-125">Sačuvajte izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="9e795-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="9e795-126">Unesite podatke o kupovini na mreži</span><span class="sxs-lookup"><span data-stu-id="9e795-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="9e795-127">Dodajte još jedan skup podatka u isti **eCommerce** izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="9e795-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="9e795-128">Ponovo izaberite konektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9e795-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="9e795-129">Unesite URL za podatke o **kupovinama na mreži** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="9e795-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="9e795-130">Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="9e795-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9e795-131">Ažurirajte tip podataka za dolenavedene kolone:</span><span class="sxs-lookup"><span data-stu-id="9e795-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="9e795-132">**Kupljeno dana**: Datum/vreme</span><span class="sxs-lookup"><span data-stu-id="9e795-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="9e795-133">**Ukupna cena**: Valuta</span><span class="sxs-lookup"><span data-stu-id="9e795-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="9e795-134">U polju „Ime“ u desnom oknu preimenujte izvor podataka iz **Upit** u **eCommerce kupovine**.</span><span class="sxs-lookup"><span data-stu-id="9e795-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="9e795-135">Sačuvajte izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="9e795-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="9e795-136">Unesite podatke o klijentima iz šeme lojalnosti</span><span class="sxs-lookup"><span data-stu-id="9e795-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="9e795-137">Napravite izvor podataka pod imenom **Šema lojalnosti**, izaberite opciju uvoza i izaberite **Tekst/CSV** konektor.</span><span class="sxs-lookup"><span data-stu-id="9e795-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9e795-138">Unesite URL adresu za eCommerce kontakte https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="9e795-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="9e795-139">Dok uređujete podatke, izaberite **Transformacija**, a zatim **Koristi prvi red kao zaglavlja**.</span><span class="sxs-lookup"><span data-stu-id="9e795-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9e795-140">Ažurirajte tip podataka za dolenavedene kolone:</span><span class="sxs-lookup"><span data-stu-id="9e795-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="9e795-141">**Datum rođenja**: Datum</span><span class="sxs-lookup"><span data-stu-id="9e795-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="9e795-142">**Nagradni poeni**: Ceo broj</span><span class="sxs-lookup"><span data-stu-id="9e795-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="9e795-143">**Kreirano**: Datum/vreme</span><span class="sxs-lookup"><span data-stu-id="9e795-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="9e795-144">U polju „Ime“ u desnom oknu preimenujte izvor podataka iz **Upit** u **Lojalni klijenti**.</span><span class="sxs-lookup"><span data-stu-id="9e795-144">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="9e795-145">Sačuvajte izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="9e795-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="9e795-146">2. zadatak 2 – Objedinjavanje podataka</span><span class="sxs-lookup"><span data-stu-id="9e795-146">Task 2 - Data unification</span></span>

<span data-ttu-id="9e795-147">Nakon unosa podataka, sada započinjemo proces **Mapiranja, podudaranja, objedinjavanja** da bismo kreirali objedinjeni profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="9e795-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="9e795-148">Za više informacija pogledajte [Objedinjavanje podataka](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="9e795-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="9e795-149">Mapiraj</span><span class="sxs-lookup"><span data-stu-id="9e795-149">Map</span></span>

1. <span data-ttu-id="9e795-150">Nakon unosa podataka, mapirajte kontakte sa platforme eCommerce i iz podataka o lojalnosti u uobičajene tipove podataka.</span><span class="sxs-lookup"><span data-stu-id="9e795-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="9e795-151">Idite na **Podaci** > **Objedini** > **Mapiraj**.</span><span class="sxs-lookup"><span data-stu-id="9e795-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="9e795-152">Izaberite entitete koji predstavljaju profil klijenta – **eCommerce kontakti** i **Lojalni klijenti**.</span><span class="sxs-lookup"><span data-stu-id="9e795-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="objedinite izvore podataka o platform ecommerce i lojalnosti.":::

1. <span data-ttu-id="9e795-154">Izaberite **ID klijenta** kao primarni ključ za **eCommerce kontakte** i **ID lojalnosti** kao primarni ključ za **Lojalne klijente**.</span><span class="sxs-lookup"><span data-stu-id="9e795-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Objedinite ID lojalnosti kao primarni ključ.":::

### <a name="match"></a><span data-ttu-id="9e795-156">Podudaranje</span><span class="sxs-lookup"><span data-stu-id="9e795-156">Match</span></span>

1. <span data-ttu-id="9e795-157">Idite u na karticu **Podudaranje** i izaberite **Podesi redosled**.</span><span class="sxs-lookup"><span data-stu-id="9e795-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="9e795-158">Na padajućoj listi **Primarno**, odaberite **eCommerce kontakti: eCommerce** kao primarni izvor i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="9e795-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="9e795-159">Na padajućoj listi **Entitet 2**, odaberite **Lojalni klijenti: Šema lojalnosti** i uključite sve zapise.</span><span class="sxs-lookup"><span data-stu-id="9e795-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Objedinite podudaranje platforme eCommerce i lojalnosti.":::

1. <span data-ttu-id="9e795-161">Izaberite **Kreiraj novo pravilo**</span><span class="sxs-lookup"><span data-stu-id="9e795-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="9e795-162">Dodajte svoj prvi uslov koristeći Ime i prezime.</span><span class="sxs-lookup"><span data-stu-id="9e795-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="9e795-163">Za eCommerce kontakte odaberite **Ime i prezime** na padajućoj listi.</span><span class="sxs-lookup"><span data-stu-id="9e795-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="9e795-164">Za Lojalne klijente odaberite **Ime i prezime** na padajućoj listi.</span><span class="sxs-lookup"><span data-stu-id="9e795-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="9e795-165">Izaberite padajuću listu **Normalizacija** i odaberite **Tip (telefon, ime, adresa...)**.</span><span class="sxs-lookup"><span data-stu-id="9e795-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="9e795-166">Podesite **Nivo preciznosti**: **Osnovni** i **Vrednost**: **Visoka**.</span><span class="sxs-lookup"><span data-stu-id="9e795-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="9e795-167">Unesite naziv **Ime i prezime, e-pošta** za novo pravilo.</span><span class="sxs-lookup"><span data-stu-id="9e795-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="9e795-168">Dodajte drugi uslov za adresu e-pošte izborom stavke **Dodajte uslov**</span><span class="sxs-lookup"><span data-stu-id="9e795-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="9e795-169">Za entitet eCommerce kontakti odaberite **E-pošta** u padajućem meniju.</span><span class="sxs-lookup"><span data-stu-id="9e795-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="9e795-170">Za entitet Lojalni klijenti odaberite **E-pošta** u padajućem meniju.</span><span class="sxs-lookup"><span data-stu-id="9e795-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="9e795-171">Ostavite Normalizacija prazno.</span><span class="sxs-lookup"><span data-stu-id="9e795-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="9e795-172">Podesite **Nivo preciznosti**: **Osnovni** i **Vrednost**: **Visoka**.</span><span class="sxs-lookup"><span data-stu-id="9e795-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Objedinite pravilo podudaranja za ime i e-poštu.":::

7. <span data-ttu-id="9e795-174">Izaberite **Sačuvaj** i **Zatvori**.</span><span class="sxs-lookup"><span data-stu-id="9e795-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="9e795-175">Objedini</span><span class="sxs-lookup"><span data-stu-id="9e795-175">Merge</span></span>

1. <span data-ttu-id="9e795-176">Idite na karticu **Objedinjavanje**.</span><span class="sxs-lookup"><span data-stu-id="9e795-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="9e795-177">Na **ID kontakta** za entitet **Lojalni klijenti** promenite ime za prikaz u **ID kontakta LOJALNOST** da bi se razlikovalo od ostalih unetih ID-ova.</span><span class="sxs-lookup"><span data-stu-id="9e795-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Preimenujte ID kontakta iz ID-a lojalnosti.":::

1. <span data-ttu-id="9e795-179">Izaberite **Sačuvaj** i **Pokreni** da biste započeli postupak objedinjavanja.</span><span class="sxs-lookup"><span data-stu-id="9e795-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="9e795-180">3. zadatak – Konfigurišite predviđanje gubitka transakcija</span><span class="sxs-lookup"><span data-stu-id="9e795-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="9e795-181">Kada su objedinjeni profilima klijenata spremni, sada možemo pokrenuti predviđanje gubitka pretplata.</span><span class="sxs-lookup"><span data-stu-id="9e795-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="9e795-182">Za detaljne korake pogledajte članak [Predviđanje gubitka pretplata (verzija za pregled)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="9e795-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="9e795-183">Idite na **Obaveštavanje** > **Otkrijte** i izaberite da koristite **Model gubitka klijenata**.</span><span class="sxs-lookup"><span data-stu-id="9e795-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="9e795-184">Izaberite opciju **Transakcija** i **Započnite**.</span><span class="sxs-lookup"><span data-stu-id="9e795-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="9e795-185">Nazovite model **OOB predviđanje gubitka eCommerce transakcija** i izlazni entitet **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="9e795-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="9e795-186">Definišite dva uslova za model gubitka:</span><span class="sxs-lookup"><span data-stu-id="9e795-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="9e795-187">**Prozor predviđanja**: **najmanje 60** dana.</span><span class="sxs-lookup"><span data-stu-id="9e795-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="9e795-188">Ovo podešavanje definiše koliko u budućnosti želimo da predvidimo gubitak klijenata.</span><span class="sxs-lookup"><span data-stu-id="9e795-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="9e795-189">**Definicija gubitka**: **najmanje 60** dana.</span><span class="sxs-lookup"><span data-stu-id="9e795-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="9e795-190">Trajanje bez kupovine nakon kojeg se klijent smatra izgubljenim.</span><span class="sxs-lookup"><span data-stu-id="9e795-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Izaberite regulatore modela Vremenski period predviđanja i Definicija gubitka.":::

1. <span data-ttu-id="9e795-192">Izaberite **Istorija kupovine (obavezno)** i **Dodajte podatke** za istoriju pretplata.</span><span class="sxs-lookup"><span data-stu-id="9e795-192">Select **Purchase History (required)** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="9e795-193">Dodajte entitet **eCommerce kupovine: eCommerce** i mapirajte polja iz platforme eCommerce sa odgovarajućim poljima koje traži model.</span><span class="sxs-lookup"><span data-stu-id="9e795-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="9e795-194">Pridružite entite **eCommerce kupovine: eCommerce** sa **eCommerce kontakti: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="9e795-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Pridružite eCommerce entitete.":::

1. <span data-ttu-id="9e795-196">Izaberite **Dalje** da biste postavili raspored modela.</span><span class="sxs-lookup"><span data-stu-id="9e795-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="9e795-197">Model treba redovno da se obučava kako bi naučio nove obrasce kada dođe do unosa novih podataka.</span><span class="sxs-lookup"><span data-stu-id="9e795-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="9e795-198">Za ovaj primer izaberite **Mesečno**.</span><span class="sxs-lookup"><span data-stu-id="9e795-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="9e795-199">Nakon pregleda svih detalja, izaberite **Sačuvaj i pokreni**.</span><span class="sxs-lookup"><span data-stu-id="9e795-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="9e795-200">4. zadatak – Pregled rezultata modela i objašnjenja</span><span class="sxs-lookup"><span data-stu-id="9e795-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="9e795-201">Neka model završi obuku i ocenjivanje podataka.</span><span class="sxs-lookup"><span data-stu-id="9e795-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="9e795-202">Sada možete pregledati objašnjenja modela gubitka pretplata.</span><span class="sxs-lookup"><span data-stu-id="9e795-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="9e795-203">Za više informacija pogledajte [Pregledajte status i rezultate predviđanja](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="9e795-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="9e795-204">5. zadatak – Kreirajte segment klijenata sa visokim rizikom od gubitka</span><span class="sxs-lookup"><span data-stu-id="9e795-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="9e795-205">Pokretanje proizvodnog modela stvara novi entitet koji možete da vidite u odeljku **Podaci** > **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="9e795-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="9e795-206">Možete da kreirate novi segment na osnovu entiteta koji je kreirao model.</span><span class="sxs-lookup"><span data-stu-id="9e795-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="9e795-207">Idite na **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="9e795-207">Go to **Segments**.</span></span> <span data-ttu-id="9e795-208">Izaberite **Novo** i **Napravi od** > **Obaveštavanje**.</span><span class="sxs-lookup"><span data-stu-id="9e795-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Kreirajte segment sa izlazom modela.":::

1. <span data-ttu-id="9e795-210">Izaberite krajnju tačku **OOB predviđanje gubitka klijenata** i definišite segment:</span><span class="sxs-lookup"><span data-stu-id="9e795-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="9e795-211">Polje: Ocena gubitka</span><span class="sxs-lookup"><span data-stu-id="9e795-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="9e795-212">Operator: veće je od</span><span class="sxs-lookup"><span data-stu-id="9e795-212">Operator: greater than</span></span>
   - <span data-ttu-id="9e795-213">Vrednost: 0,6</span><span class="sxs-lookup"><span data-stu-id="9e795-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Podesite segment gubitka pretplate.":::

<span data-ttu-id="9e795-215">Sada imate segment koji se dinamički ažurira i koji identifikuje klijente sa visokim rizikom od gubitka za ovu uslugu pretplate.</span><span class="sxs-lookup"><span data-stu-id="9e795-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="9e795-216">Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9e795-216">For more information, see [Create and manage segments](segments.md).</span></span>
