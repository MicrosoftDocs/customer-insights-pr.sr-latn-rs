---
title: Izvoz Customer Insights podataka u Adobe platformu iskustva
description: Saznajte kako se koriste segmenti uvida o korisnicima u Adobe platformi iskustva.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596286"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="1a5ec-103">Korišćenje Customer Insights segmenata u Adobe platformi iskustva (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="1a5ec-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="1a5ec-104">Kao korisnik uvida o korisnicima za Dynamics 365 Customer Insights, možda ste kreirali segmente da biste marketinške kampanje učinili efikasnijim tako što ćete ciljati relevantne ciljne grupe.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="1a5ec-105">Da biste koristili segment iz uvida o korisnicima u Adobe platformi iskustva i aplikacijama poput Adobe Campaign Standard, potrebno je da sledite nekoliko koraka navedenih u ovom članku.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a><span data-ttu-id="1a5ec-107">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="1a5ec-107">Prerequisites</span></span>

-   <span data-ttu-id="1a5ec-108">Dynamics 365 Customer Insights licenca</span><span class="sxs-lookup"><span data-stu-id="1a5ec-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="1a5ec-109">Licenca za Adobe platformu iskustva</span><span class="sxs-lookup"><span data-stu-id="1a5ec-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="1a5ec-110">Licenca za Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1a5ec-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="1a5ec-111">Nalog Azure skladišta blob objekta</span><span class="sxs-lookup"><span data-stu-id="1a5ec-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="1a5ec-112">Pregled kampanje</span><span class="sxs-lookup"><span data-stu-id="1a5ec-112">Campaign Overview</span></span>

<span data-ttu-id="1a5ec-113">Da biste bolje razumeli kako možete da koristite segmente iz uvida o korisnicima u Adobe platformi iskustva, pogledajmo fiktivni primer kampanje.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="1a5ec-114">Pretpostavimo da vaše preduzeće nudi mesečnu uslugu zasnovanu na pretplati za klijente u Sjedinjenim Državama.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="1a5ec-115">Želite da identifikujete klijente koji treba da obnove pretplate u narednih osam dana, ali još uvek nisu obnovili pretplatu.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="1a5ec-116">Da biste zadržali ove klijente, treba da im pošaljete promotivnu ponudu putem e-pošte, koristeći Adobe platformu iskustva.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="1a5ec-117">U ovom primeru želimo da jednom pokrenemo promotivnu kampanju e-pošte.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="1a5ec-118">Ovaj članak ne pokriva slučaj korišćenja sa više pokretanja kampanje.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="1a5ec-119">Identifikujte svoju ciljnu grupu</span><span class="sxs-lookup"><span data-stu-id="1a5ec-119">Identify your target audience</span></span>

<span data-ttu-id="1a5ec-120">U našem scenarij,u pretpostavljamo da su adrese e-pošte klijenata dostupne u uvidima o korisnicima i da su analizirane njihove promotivne željene opcije kako bi se identifikovali članovi segmenta.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="1a5ec-121">[Segment koji ste definisali uvidom o korisnicima](segments.md) se zove **ChurnProneCustomers** i planirate da ovim klijentima pošaljete e-poruku sa promocijom.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimak ekrana stranice segmenata sa kreiranim segmentom ChurnProneCustomers.":::

<span data-ttu-id="1a5ec-123">E-poruka sa ponudom koju želite da pošaljete sadrži ime, prezime i datum završetka pretplate klijenta.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="1a5ec-124">Poruka obaveštava klijente o popustu koji će dobiti ako obnove pretplatu pre nego što se završi.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="1a5ec-125">Izvezite svoju ciljnu grupu</span><span class="sxs-lookup"><span data-stu-id="1a5ec-125">Export your target audience</span></span>

<span data-ttu-id="1a5ec-126">Kada je identifikovana ciljna grupa, možemo da konfigurišemo izvoz iz uvida o korisnicima na nalog Azure skladišta blob objekta.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="1a5ec-127">U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1a5ec-128">Na pločici **Azure skladište blob objekta** izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Pločica za konfiguraciju za Azure skladište blob objekta.":::

1. <span data-ttu-id="1a5ec-130">Navedite **ime za prikaz** za ovo novo odredište za izvoz, a zatim unesite **Naziv naloga**, **Ključ naloga** i **Kontejner** naloga Azure skladišta blob objekta u koji želite da izvezete segment.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimak ekrana konfiguracije naloga skladišta. "::: 

   - <span data-ttu-id="1a5ec-132">Da biste saznali više o pronalaženju imena i ključa naloga za Azure skladište blob objekta, pogledajte [Upravljajte podešavanjima naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="1a5ec-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="1a5ec-133">Da biste saznali kako da kreirate kontejner, pogledajte članak [Kreiranje kontejnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="1a5ec-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="1a5ec-134">Izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-134">Select **Next**.</span></span>

1. <span data-ttu-id="1a5ec-135">Odaberite segment koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="1a5ec-136">U ovom primeru, to je **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimak ekrana korisničkog interfejsa za odabir segmenta sa izabranim segmentom ChurnProneCustomers.":::

1. <span data-ttu-id="1a5ec-138">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-138">Select **Save**.</span></span>

<span data-ttu-id="1a5ec-139">Kada sačuvate odredište za izvoz, pronaći ćete ga na listi **Administrator** > **Izvozi** > **Moja odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Snimak ekrana sa istaknutom listom izvoza i uzorkom segmenta.":::

<span data-ttu-id="1a5ec-141">Sada možete da [izvozite segment na zahtev](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1a5ec-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="1a5ec-142">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md).</span><span class="sxs-lookup"><span data-stu-id="1a5ec-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1a5ec-143">Uverite se da je broj zapisa u izvezenom segmentu unutar dozvoljenog ograničenja vaše Adobe Campaign Standard licence.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="1a5ec-144">Izvezeni podaci se čuvaju u kontejneru Azure skladišta blob objekta koji ste ranije konfigurisali.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="1a5ec-145">Sledeća putanja do fascikle se automatski kreira u vašem kontejneru:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="1a5ec-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="1a5ec-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="1a5ec-147">Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="1a5ec-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="1a5ec-148">Datoteka *model.json* za izvezene entitete nalazi se na nivou *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="1a5ec-149">Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="1a5ec-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="1a5ec-150">Definišite model podataka o iskustvu (XDM) na Adobe platformi iskustva</span><span class="sxs-lookup"><span data-stu-id="1a5ec-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="1a5ec-151">Pre nego što budemo mogli da koristimo izvezene podatke iz uvida o korisnicima na Adobe platformi iskustva, moramo da definišemo šemu modela podataka iskustva i [konfigurišemo podatke za profil klijenta u realnom vremenu](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="1a5ec-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="1a5ec-152">Saznajte [šta je to XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) i razjasnite [osnove sastavljanja šeme](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="1a5ec-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="1a5ec-153">Uvezite podatke u Adobe platformu iskustva</span><span class="sxs-lookup"><span data-stu-id="1a5ec-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="1a5ec-154">Sada kada je sve na svom mestu, treba da uvezemo podatke o ciljnoj grupi iz uvida o korisnicima u Adobe platformi iskustva.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="1a5ec-155">Prvo [kreirajte izvornu vezu sa Azure skladištem blob objekta](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="1a5ec-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="1a5ec-156">Kada definišete izvornu vezu, [konfigurišite tok podataka](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) za grupno povezivanje sa skladištem u oblaku radi uvoza izlaza segmenta iz uvida o korisnicima u Adobe platformu iskustva.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="1a5ec-157">Kreiranje korisnika u usluzi Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1a5ec-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="1a5ec-158">Da bismo poslali e-poruku za ovu kampanju, koristićemo Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="1a5ec-159">Nakon uvoza podataka u Adobe platformu iskustva, treba da [kreiramo ciljnu grupu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) u usluzi Adobe Campaign Standard koristeći podatke na Adobe platformi iskustva.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="1a5ec-160">Saznajte kako da [koristite alatku za pravljenje segmenata](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) u usluzi Adobe Campaign Standard da biste definisali ciljnu grupu na osnovu podataka u Adobe platformi iskustva.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="1a5ec-161">Kreirajte i pošaljite e-poruku koristeći Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1a5ec-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="1a5ec-162">Kreirajte sadržaj e-poruke, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poruku.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Primer e-poruke sa ponudom obnove pretplate iz usluge Adobe Campaign Standard.":::