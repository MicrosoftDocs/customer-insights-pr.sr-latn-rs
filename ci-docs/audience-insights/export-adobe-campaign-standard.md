---
title: Izvezite Customer Insights podatke u Adobe Campaign Standard
description: Saznajte kako se koriste segmenti uvida u korisnike u usluzi Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760298"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="325a7-103">Korišćenje Customer Insights segmenata u usluzi Adobe Campaign Standard (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="325a7-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="325a7-104">Kao korisnik uvida o korisnicima za Dynamics 365 Customer Insights, možda ste kreirali segmente da biste marketinške kampanje učinili efikasnijim tako što ćete ciljati relevantne ciljne grupe.</span><span class="sxs-lookup"><span data-stu-id="325a7-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="325a7-105">Da biste koristili segment iz uvida o korisnicima u Adobe platformi iskustva i aplikacijama poput Adobe Campaign Standard, potrebno je da sledite nekoliko koraka navedenih u ovom članku.</span><span class="sxs-lookup"><span data-stu-id="325a7-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a><span data-ttu-id="325a7-107">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="325a7-107">Prerequisites</span></span>

-   <span data-ttu-id="325a7-108">Dynamics 365 Customer Insights licenca</span><span class="sxs-lookup"><span data-stu-id="325a7-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="325a7-109">Licenca za Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="325a7-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="325a7-110">Nalog Azure skladišta blob objekta</span><span class="sxs-lookup"><span data-stu-id="325a7-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="325a7-111">Pregled kampanje</span><span class="sxs-lookup"><span data-stu-id="325a7-111">Campaign Overview</span></span>

<span data-ttu-id="325a7-112">Da biste bolje razumeli kako možete da koristite segmente iz uvida o korisnicima u Adobe platformi iskustva, pogledajmo fiktivni primer kampanje.</span><span class="sxs-lookup"><span data-stu-id="325a7-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="325a7-113">Pretpostavimo da vaše preduzeće nudi mesečnu uslugu zasnovanu na pretplati za klijente u Sjedinjenim Državama.</span><span class="sxs-lookup"><span data-stu-id="325a7-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="325a7-114">Želite da identifikujete klijente koji treba da obnove pretplate u narednih osam dana, ali još uvek nisu obnovili pretplatu.</span><span class="sxs-lookup"><span data-stu-id="325a7-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="325a7-115">Da biste zadržali ove klijente, treba da im pošaljete promotivnu ponudu putem e-pošte, koristeći Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="325a7-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="325a7-116">U ovom primeru želimo da jednom pokrenemo promotivnu kampanju e-pošte.</span><span class="sxs-lookup"><span data-stu-id="325a7-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="325a7-117">Ovaj članak ne pokriva slučaj korišćenja sa više pokretanja kampanje.</span><span class="sxs-lookup"><span data-stu-id="325a7-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="325a7-118">Međutim, uvidi u korisnike i Adobe Campaign Standard mogu se konfigurisati da rade i za ponavljajući scenario kampanje.</span><span class="sxs-lookup"><span data-stu-id="325a7-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="325a7-119">Identifikujte svoju ciljnu grupu</span><span class="sxs-lookup"><span data-stu-id="325a7-119">Identify your target audience</span></span>

<span data-ttu-id="325a7-120">U našem scenarij,u pretpostavljamo da su adrese e-pošte klijenata dostupne u uvidima o korisnicima i da su analizirane njihove promotivne željene opcije kako bi se identifikovali članovi segmenta.</span><span class="sxs-lookup"><span data-stu-id="325a7-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="325a7-121">[Segment koji ste definisali uvidom o korisnicima](segments.md) se zove **ChurnProneCustomers** i planirate da ovim klijentima pošaljete e-poruku sa promocijom.</span><span class="sxs-lookup"><span data-stu-id="325a7-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimak ekrana stranice segmenata sa kreiranim segmentom ChurnProneCustomers.":::

<span data-ttu-id="325a7-123">E-poruka sa ponudom koju želite da pošaljete sadrži ime, prezime i datum završetka pretplate klijenta.</span><span class="sxs-lookup"><span data-stu-id="325a7-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="325a7-124">Poruka obaveštava klijente o popustu koji će dobiti ako obnove pretplatu pre nego što se završi.</span><span class="sxs-lookup"><span data-stu-id="325a7-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="325a7-125">Izvezite svoju ciljnu grupu</span><span class="sxs-lookup"><span data-stu-id="325a7-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="325a7-126">Konfigurisanje veze</span><span class="sxs-lookup"><span data-stu-id="325a7-126">Configure a connection</span></span>

<span data-ttu-id="325a7-127">Kada je identifikovana ciljna grupa, možemo da konfigurišemo izvoz iz uvida o korisnicima na nalog Azure skladišta blob objekta.</span><span class="sxs-lookup"><span data-stu-id="325a7-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="325a7-128">U uvidima u ciljne grupe, idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="325a7-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="325a7-129">Izaberite **Dodaj vezu** i birajte **Adobe Campaign** da biste konfigurisali vezu ili izaberite **Podešavanje** na pločici **Adobe Campaign**</span><span class="sxs-lookup"><span data-stu-id="325a7-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Pločica za konfiguraciju za Adobe Campaign Standard.":::

1. <span data-ttu-id="325a7-131">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="325a7-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="325a7-132">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="325a7-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="325a7-133">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="325a7-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="325a7-134">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="325a7-134">Choose who can use this connection.</span></span> <span data-ttu-id="325a7-135">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="325a7-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="325a7-136">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="325a7-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="325a7-137">Unesite **Naziv naloga**, **Ključ naloga** i **Kontejner** za vaš nalog za Azure skladište blob objekta u koji želite da izvezete segment.</span><span class="sxs-lookup"><span data-stu-id="325a7-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimak ekrana konfiguracije naloga skladišta. "::: 

   - <span data-ttu-id="325a7-139">Da biste saznali više o pronalaženju imena i ključa naloga za Azure skladište blob objekta, pogledajte [Upravljajte podešavanjima naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="325a7-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="325a7-140">Da biste saznali kako da kreirate kontejner, pogledajte članak [Kreiranje kontejnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="325a7-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="325a7-141">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="325a7-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="325a7-142">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="325a7-142">Configure an export</span></span>

<span data-ttu-id="325a7-143">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="325a7-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="325a7-144">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="325a7-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="325a7-145">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="325a7-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="325a7-146">Da biste kreirali novi izvoz, izaberite **Dodaj izvoz**.</span><span class="sxs-lookup"><span data-stu-id="325a7-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="325a7-147">U polju **Veza za izvoz**, odaberite vezu iz odeljka Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="325a7-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="325a7-148">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="325a7-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="325a7-149">Odaberite segment koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="325a7-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="325a7-150">U ovom primeru, to je **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="325a7-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimak ekrana korisničkog interfejsa za odabir segmenta sa izabranim segmentom ChurnProneCustomers.":::

1. <span data-ttu-id="325a7-152">Izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="325a7-152">Select **Next**.</span></span>

1. <span data-ttu-id="325a7-153">Sada mapiramo polja **Izvor** od segmenta uvida u korisnike do imena polja **Cilj** u šemi Adobe Campaign Standard profila.</span><span class="sxs-lookup"><span data-stu-id="325a7-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapiranje polja za Adobe Campaign Standard konektor.":::

   <span data-ttu-id="325a7-155">Ako želite da dodate još atributa, izaberite **Dodaj atribut**.</span><span class="sxs-lookup"><span data-stu-id="325a7-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="325a7-156">Naziv cilja može se razlikovati od imena izvornog polja, tako da i dalje možete mapirati izlaz segmenta iz uvida u korisnike u uslugu Adobe Campaign Standard ako polja nemaju isti naziv u dva sistema.</span><span class="sxs-lookup"><span data-stu-id="325a7-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="325a7-157">Adresa e-pošte se koristi kao polje identiteta, ali možete koristiti bilo koji drugi identifikator iz vašeg korisničkog profila za uvide u korisnike da biste mapirali podatke u Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="325a7-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="325a7-158">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="325a7-158">Select **Save**.</span></span>

<span data-ttu-id="325a7-159">Kada sačuvate odredište za izvoz, pronaći ćete ga u dijalogu **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="325a7-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="325a7-160">Sada možete da [izvozite segment na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="325a7-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="325a7-161">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md).</span><span class="sxs-lookup"><span data-stu-id="325a7-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="325a7-162">Uverite se da je broj zapisa u izvezenom segmentu unutar dozvoljenog ograničenja vaše Adobe Campaign Standard licence.</span><span class="sxs-lookup"><span data-stu-id="325a7-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="325a7-163">Izvezeni podaci se čuvaju u kontejneru Azure skladišta blob objekta koji ste ranije konfigurisali.</span><span class="sxs-lookup"><span data-stu-id="325a7-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="325a7-164">Sledeća putanja do fascikle se automatski kreira u vašem kontejneru:</span><span class="sxs-lookup"><span data-stu-id="325a7-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="325a7-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="325a7-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="325a7-166">Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="325a7-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="325a7-167">Konfigurisanje usluge Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="325a7-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="325a7-168">Kada se izveze segment iz uvida u korisnike, on sadrži kolone koje ste izabrali prilikom definisanja odredišta izvoza u prethodnom koraku.</span><span class="sxs-lookup"><span data-stu-id="325a7-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="325a7-169">Ovi podaci se mogu koristiti za [kreiranje profila u usluzi Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="325a7-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="325a7-170">Da bismo koristili segment u usluzi Adobe Campaign Standard, treba da proširimo šemu profila u usluzi Adobe Campaign Standard tako da uključuje dva dodatna polja.</span><span class="sxs-lookup"><span data-stu-id="325a7-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="325a7-171">Saznajte kako da [produžite resurs profila](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) sa novim poljima u usluzi Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="325a7-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="325a7-172">U našem primeru, ova polja su *Naziv segmenta i Datum segmenta (opcionalno).*</span><span class="sxs-lookup"><span data-stu-id="325a7-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="325a7-173">Ova polja ćemo koristiti za identifikaciju profila u programu Adobe Campaign Standard koje želimo da ciljamo za ovu kampanju.</span><span class="sxs-lookup"><span data-stu-id="325a7-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="325a7-174">Ako u programu Adobe Campaign Standard ne postoje drugi zapisi osim onih koje ćete uvoziti, možete preskočiti ovaj korak.</span><span class="sxs-lookup"><span data-stu-id="325a7-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="325a7-175">Uvoz podataka u Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="325a7-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="325a7-176">Sada kada je sve na svom mestu, moramo pripremiti podatke o korisnicima iz uvida u korisnike u usluzi Adobe Campaign Standard da bismo kreirali profile.</span><span class="sxs-lookup"><span data-stu-id="325a7-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="325a7-177">Saznajte [kako da uvezete profile u Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) koristeći tok posla.</span><span class="sxs-lookup"><span data-stu-id="325a7-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="325a7-178">Tok posla uvoza na donjoj slici konfigurisan je za pokretanje svakih 8 sati i traži izvezene segmente uvida u korisnike (.csv datoteka u Azure skladištu blob objekta).</span><span class="sxs-lookup"><span data-stu-id="325a7-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="325a7-179">Tok posla izdvaja sadržaj .csv datoteke u navedenom redosledu kolona.</span><span class="sxs-lookup"><span data-stu-id="325a7-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="325a7-180">Ovaj tok posla napravljen je da obavi osnovno rukovanje greškama i osigura da svaki zapis ima adresu e-pošte pre popune podacima u usluzi Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="325a7-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="325a7-181">Tok posla takođe izdvaja ime segmenta iz imena datoteke pre dodavanja u podatke ACS profila.</span><span class="sxs-lookup"><span data-stu-id="325a7-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Snimak ekrana toka posla uvoza u korisničkom interfejsu usluge Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="325a7-183">Preuzimanje korisnika u usluzi Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="325a7-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="325a7-184">Kada se podaci uvezu u Adobe Campaign Standard, vi [možete da kreirate tok posla](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [upit](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) da bi klijenti zasnovani na *Nazivu segmenta* i *Datumu segmenta* izabrali profile koji su identifikovani za naš primer kampanje.</span><span class="sxs-lookup"><span data-stu-id="325a7-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="325a7-185">Kreirajte i pošaljite e-poruku koristeći Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="325a7-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="325a7-186">Kreirajte sadržaj e-poruke, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poruku.</span><span class="sxs-lookup"><span data-stu-id="325a7-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Primer e-poruke sa ponudom obnove pretplate iz usluge Adobe Campaign Standard.":::
