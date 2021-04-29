---
title: Izvoz Customer Insights podataka u Adobe platformu iskustva
description: Saznajte kako se koriste segmenti uvida o korisnicima u Adobe platformi iskustva.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760118"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="c8d36-103">Korišćenje Customer Insights segmenata u Adobe platformi iskustva (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="c8d36-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="c8d36-104">Kao korisnik uvida o korisnicima za Dynamics 365 Customer Insights, možda ste kreirali segmente da biste marketinške kampanje učinili efikasnijim tako što ćete ciljati relevantne ciljne grupe.</span><span class="sxs-lookup"><span data-stu-id="c8d36-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="c8d36-105">Da biste koristili segment iz uvida o korisnicima u Adobe platformi iskustva i aplikacijama poput Adobe Campaign Standard, potrebno je da sledite nekoliko koraka navedenih u ovom članku.</span><span class="sxs-lookup"><span data-stu-id="c8d36-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a><span data-ttu-id="c8d36-107">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="c8d36-107">Prerequisites</span></span>

-   <span data-ttu-id="c8d36-108">Dynamics 365 Customer Insights licenca</span><span class="sxs-lookup"><span data-stu-id="c8d36-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="c8d36-109">Licenca za Adobe platformu iskustva</span><span class="sxs-lookup"><span data-stu-id="c8d36-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="c8d36-110">Licenca za Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c8d36-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="c8d36-111">Nalog Azure skladišta blob objekta</span><span class="sxs-lookup"><span data-stu-id="c8d36-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="c8d36-112">Pregled kampanje</span><span class="sxs-lookup"><span data-stu-id="c8d36-112">Campaign Overview</span></span>

<span data-ttu-id="c8d36-113">Da biste bolje razumeli kako možete da koristite segmente iz uvida o korisnicima u Adobe platformi iskustva, pogledajmo fiktivni primer kampanje.</span><span class="sxs-lookup"><span data-stu-id="c8d36-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="c8d36-114">Pretpostavimo da vaše preduzeće nudi mesečnu uslugu zasnovanu na pretplati za klijente u Sjedinjenim Državama.</span><span class="sxs-lookup"><span data-stu-id="c8d36-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="c8d36-115">Želite da identifikujete klijente koji treba da obnove pretplate u narednih osam dana, ali još uvek nisu obnovili pretplatu.</span><span class="sxs-lookup"><span data-stu-id="c8d36-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="c8d36-116">Da biste zadržali ove klijente, treba da im pošaljete promotivnu ponudu putem e-pošte, koristeći Adobe platformu iskustva.</span><span class="sxs-lookup"><span data-stu-id="c8d36-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="c8d36-117">U ovom primeru želimo da jednom pokrenemo promotivnu kampanju e-pošte.</span><span class="sxs-lookup"><span data-stu-id="c8d36-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="c8d36-118">Ovaj članak ne pokriva slučaj korišćenja sa više pokretanja kampanje.</span><span class="sxs-lookup"><span data-stu-id="c8d36-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="c8d36-119">Identifikujte svoju ciljnu grupu</span><span class="sxs-lookup"><span data-stu-id="c8d36-119">Identify your target audience</span></span>

<span data-ttu-id="c8d36-120">U našem scenarij,u pretpostavljamo da su adrese e-pošte klijenata dostupne u uvidima o korisnicima i da su analizirane njihove promotivne željene opcije kako bi se identifikovali članovi segmenta.</span><span class="sxs-lookup"><span data-stu-id="c8d36-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="c8d36-121">[Segment koji ste definisali uvidom o korisnicima](segments.md) se zove **ChurnProneCustomers** i planirate da ovim klijentima pošaljete e-poruku sa promocijom.</span><span class="sxs-lookup"><span data-stu-id="c8d36-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimak ekrana stranice segmenata sa kreiranim segmentom ChurnProneCustomers.":::

<span data-ttu-id="c8d36-123">E-poruka sa ponudom koju želite da pošaljete sadrži ime, prezime i datum završetka pretplate klijenta.</span><span class="sxs-lookup"><span data-stu-id="c8d36-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="c8d36-124">Poruka obaveštava klijente o popustu koji će dobiti ako obnove pretplatu pre nego što se završi.</span><span class="sxs-lookup"><span data-stu-id="c8d36-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="c8d36-125">Izvezite svoju ciljnu grupu</span><span class="sxs-lookup"><span data-stu-id="c8d36-125">Export your target audience</span></span>

<span data-ttu-id="c8d36-126">Kada je identifikovana ciljna grupa, možemo da konfigurišemo izvoz iz uvida o korisnicima na nalog Azure skladišta blob objekta.</span><span class="sxs-lookup"><span data-stu-id="c8d36-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="c8d36-127">Konfigurisanje veze</span><span class="sxs-lookup"><span data-stu-id="c8d36-127">Configure a connection</span></span>

1. <span data-ttu-id="c8d36-128">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="c8d36-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c8d36-129">Izaberite **Dodaj vezu** i odaberite **Azure skladište blob objekta** ili izaberite **Podesi** na pločici **Azure skladište blob objekta**:</span><span class="sxs-lookup"><span data-stu-id="c8d36-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Pločica za konfiguraciju za Azure skladište blob objekta."::: <span data-ttu-id="c8d36-131">da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="c8d36-131">to configure the connection.</span></span>

1. <span data-ttu-id="c8d36-132">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="c8d36-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c8d36-133">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="c8d36-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c8d36-134">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="c8d36-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c8d36-135">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="c8d36-135">Choose who can use this connection.</span></span> <span data-ttu-id="c8d36-136">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="c8d36-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c8d36-137">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c8d36-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c8d36-138">Unesite **Naziv naloga**, **Ključ naloga** i **Kontejner** za vaš nalog za skladište blob objekta u koji želite da izvezete segment.</span><span class="sxs-lookup"><span data-stu-id="c8d36-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimak ekrana konfiguracije naloga skladišta. "::: 
   
    - <span data-ttu-id="c8d36-140">Da biste saznali više o tome kako da pronađete naziv naloga skladišta blob objekta i ključ naloga, pogledajte [Upravljanje podešavanjima naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="c8d36-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="c8d36-141">Da biste saznali kako da kreirate kontejner, pogledajte članak [Kreiranje kontejnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="c8d36-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="c8d36-142">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="c8d36-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="c8d36-143">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="c8d36-143">Configure an export</span></span>

<span data-ttu-id="c8d36-144">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="c8d36-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c8d36-145">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c8d36-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c8d36-146">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="c8d36-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c8d36-147">Da biste kreirali novi izvoz, izaberite **Dodaj izvoz**.</span><span class="sxs-lookup"><span data-stu-id="c8d36-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="c8d36-148">U polju **Veza za izvoz**, odaberite vezu iz odeljka Azure skladišta blob objekta.</span><span class="sxs-lookup"><span data-stu-id="c8d36-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="c8d36-149">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="c8d36-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c8d36-150">Odaberite segment koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="c8d36-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="c8d36-151">U ovom primeru, to je **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c8d36-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimak ekrana korisničkog interfejsa za odabir segmenta sa izabranim segmentom ChurnProneCustomers.":::

1. <span data-ttu-id="c8d36-153">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="c8d36-153">Select **Save**.</span></span>

<span data-ttu-id="c8d36-154">Kada sačuvate odredište za izvoz, pronaći ćete ga u dijalogu **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="c8d36-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="c8d36-155">Sada možete da [izvozite segment na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c8d36-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="c8d36-156">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md).</span><span class="sxs-lookup"><span data-stu-id="c8d36-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c8d36-157">Uverite se da je broj zapisa u izvezenom segmentu unutar dozvoljenog ograničenja vaše Adobe Campaign Standard licence.</span><span class="sxs-lookup"><span data-stu-id="c8d36-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="c8d36-158">Izvezeni podaci se čuvaju u kontejneru Azure skladišta blob objekta koji ste ranije konfigurisali.</span><span class="sxs-lookup"><span data-stu-id="c8d36-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="c8d36-159">Sledeća putanja do fascikle se automatski kreira u vašem kontejneru:</span><span class="sxs-lookup"><span data-stu-id="c8d36-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="c8d36-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="c8d36-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="c8d36-161">Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="c8d36-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="c8d36-162">Datoteka *model.json* za izvezene entitete nalazi se na nivou *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="c8d36-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="c8d36-163">Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="c8d36-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="c8d36-164">Definišite model podataka o iskustvu (XDM) na Adobe platformi iskustva</span><span class="sxs-lookup"><span data-stu-id="c8d36-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="c8d36-165">Pre nego što budemo mogli da koristimo izvezene podatke iz uvida o korisnicima na Adobe platformi iskustva, moramo da definišemo šemu modela podataka iskustva i [konfigurišemo podatke za profil klijenta u realnom vremenu](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="c8d36-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="c8d36-166">Saznajte [šta je to XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) i razjasnite [osnove sastavljanja šeme](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="c8d36-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="c8d36-167">Uvezite podatke u Adobe platformu iskustva</span><span class="sxs-lookup"><span data-stu-id="c8d36-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="c8d36-168">Sada kada je sve na svom mestu, treba da uvezemo podatke o ciljnoj grupi iz uvida o korisnicima u Adobe platformi iskustva.</span><span class="sxs-lookup"><span data-stu-id="c8d36-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="c8d36-169">Prvo [kreirajte izvornu vezu sa Azure skladištem blob objekta](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="c8d36-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="c8d36-170">Kada definišete izvornu vezu, [konfigurišite tok podataka](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) za grupno povezivanje sa skladištem u oblaku radi uvoza izlaza segmenta iz uvida o korisnicima u Adobe platformu iskustva.</span><span class="sxs-lookup"><span data-stu-id="c8d36-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="c8d36-171">Kreiranje korisnika u usluzi Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c8d36-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="c8d36-172">Da bismo poslali e-poruku za ovu kampanju, koristićemo Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c8d36-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="c8d36-173">Nakon uvoza podataka u Adobe platformu iskustva, treba da [kreiramo ciljnu grupu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) u usluzi Adobe Campaign Standard koristeći podatke na Adobe platformi iskustva.</span><span class="sxs-lookup"><span data-stu-id="c8d36-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="c8d36-174">Saznajte kako da [koristite alatku za pravljenje segmenata](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) u usluzi Adobe Campaign Standard da biste definisali ciljnu grupu na osnovu podataka u Adobe platformi iskustva.</span><span class="sxs-lookup"><span data-stu-id="c8d36-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="c8d36-175">Kreirajte i pošaljite e-poruku koristeći Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c8d36-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="c8d36-176">Kreirajte sadržaj e-poruke, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poruku.</span><span class="sxs-lookup"><span data-stu-id="c8d36-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Primer e-poruke sa ponudom obnove pretplate iz usluge Adobe Campaign Standard.":::
