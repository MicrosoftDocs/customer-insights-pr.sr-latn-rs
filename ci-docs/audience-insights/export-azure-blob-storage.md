---
title: Izvoz Customer Insights podataka u Azure skladište blob objekta
description: Saznajte kako da konfigurišete vezu i izvezete sadržaj u skladište blob objekta.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760252"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="030e4-103">Izvoz liste segmenata i drugih podataka u Azure skladište blob objekta (pregled)</span><span class="sxs-lookup"><span data-stu-id="030e4-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="030e4-104">Skladištite Customer Insights podatke u skladište blob objekta ili ih koristite za prenos podataka u druge aplikacije.</span><span class="sxs-lookup"><span data-stu-id="030e4-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="030e4-105">Podesite vezu sa skladištem blob objekta</span><span class="sxs-lookup"><span data-stu-id="030e4-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="030e4-106">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="030e4-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="030e4-107">Izaberite **Dodaj vezu** i birajte **Azure skladište blob objekta** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="030e4-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="030e4-108">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="030e4-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="030e4-109">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="030e4-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="030e4-110">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="030e4-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="030e4-111">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="030e4-111">Choose who can use this connection.</span></span> <span data-ttu-id="030e4-112">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="030e4-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="030e4-113">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="030e4-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="030e4-114">Unesite **Naziv naloga**, **Ključ naloga** i **Kontejner** za svoj nalog skladišta blob objekta.</span><span class="sxs-lookup"><span data-stu-id="030e4-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="030e4-115">Da biste saznali više o tome kako da pronađete naziv naloga skladišta blob objekta i ključ naloga, pogledajte [Upravljanje podešavanjima naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="030e4-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="030e4-116">Da biste saznali kako da kreirate kontejner, pogledajte članak [Kreiranje kontejnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="030e4-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="030e4-117">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="030e4-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="030e4-118">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="030e4-118">Configure an export</span></span>

<span data-ttu-id="030e4-119">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="030e4-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="030e4-120">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="030e4-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="030e4-121">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="030e4-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="030e4-122">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="030e4-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="030e4-123">U polju **Veza za izvoz**, odaberite vezu iz odeljka Azure skladišta blob objekta.</span><span class="sxs-lookup"><span data-stu-id="030e4-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="030e4-124">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="030e4-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="030e4-125">Izaberite polje pored svakog entiteta koji želite da izvezete na ovo odredište.</span><span class="sxs-lookup"><span data-stu-id="030e4-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="030e4-126">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="030e4-126">Select **Save**.</span></span>

<span data-ttu-id="030e4-127">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="030e4-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="030e4-128">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="030e4-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="030e4-129">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="030e4-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="030e4-130">Izvezeni podaci se čuvaju u kontejneru skladišta blob objekta koji ste konfigurisali.</span><span class="sxs-lookup"><span data-stu-id="030e4-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="030e4-131">Sledeće putanje fasciklu se automatski kreiraju u vašem kontejneru:</span><span class="sxs-lookup"><span data-stu-id="030e4-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="030e4-132">Za izvorne entitete i entitete koje generiše sistem: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="030e4-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="030e4-133">Primer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="030e4-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="030e4-134">Datoteka model.json za izvezene entitete biće na nivou %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="030e4-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="030e4-135">Primer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="030e4-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
