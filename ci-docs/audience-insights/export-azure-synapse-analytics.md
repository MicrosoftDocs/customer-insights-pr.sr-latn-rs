---
title: Izvoz Customer Insights podataka u uslugu Azure Synapse Analytics
description: Saznajte kako da konfigurišete vezu sa uslugom Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977394"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="d7bd0-103">Izvoz podataka u uslugu Azure Synapse Analytics (pregled)</span><span class="sxs-lookup"><span data-stu-id="d7bd0-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="d7bd0-104">Azure Synapse je analitička usluga koja ubrzava vreme za uvid u skladišta podataka i sisteme velikih podataka.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="d7bd0-105">Možete da unesete i koristite Customer Insights podatke u usluzi [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="d7bd0-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d7bd0-106">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="d7bd0-106">Prerequisites</span></span>

<span data-ttu-id="d7bd0-107">Sledeći preduslovi moraju biti ispunjeni za konfigurisanje veze iz usluge Customer Insights u uslugu Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="d7bd0-108">Obavezno podesite sve **dodele uloga** kao što je opisano.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="d7bd0-109">Preduslovi u usluzi Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d7bd0-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="d7bd0-110">Imate ulogu **administratora** u uvidima u ciljnu grupu.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="d7bd0-111">Saznajte više o [postavljanju korisničkih dozvola u uvidima u ciljnu grupu](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="d7bd0-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="d7bd0-112">U usluzi Azure:</span><span class="sxs-lookup"><span data-stu-id="d7bd0-112">In Azure:</span></span> 

- <span data-ttu-id="d7bd0-113">Aktivna pretplata na uslugu Azure.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-113">An active Azure subscription.</span></span>

- <span data-ttu-id="d7bd0-114">Ako koristite novi Azure Data Lake Storage Gen2 nalog, *principalu usluge za uvide u ciljnu grupu* su potrebne dozvole **saradnika za podatke skladišta blob objekta**.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="d7bd0-115">Saznajte više o [povezivanju sa Azure Data Lake Storage Gen2 nalogom sa Azure principalom usluge za uvide u ciljnu grupu](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="d7bd0-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="d7bd0-116">Data Lake Storage Gen2 **mora da ima** omogućen [hijerarhijski prostor imena](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="d7bd0-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="d7bd0-117">U grupi resursa u kojoj se nalazi Azure Synapse radni prostor, *principalu usluge* i *korisniku za uvide u ciljnu grupu* treba dodeliti barem dozvole **čitaoca**.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="d7bd0-118">Za više informacija, pogledajte [Dodeljivanje Azure uloga pomoću Azure portala](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="d7bd0-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="d7bd0-119">*Korisniku* su potrebne dozvole **saradnika za podatke skladišta blob objekta** na Azure Data Lake Storage Gen2 nalogu na kojem se podaci nalaze i povezani su sa Azure Synapse radnim prostorom.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="d7bd0-120">Saznajte više o [korišćenju Azure portala za dodeljivanje Azure uloge za pristup blob objektu i podacima u redu](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama saradnika za podatke skladišta blob objekta](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="d7bd0-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="d7bd0-121">*[Upravljanom identitetu Azure Synapse radnog prostora](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* su potrebne dozvole **saradnika za podatke skladišta blob objekta** na Azure Data Lake Storage Gen2 nalogu na kojem se podaci nalaze i povezani su sa Azure Synapse radnim prostorom.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="d7bd0-122">Saznajte više o [korišćenju Azure portala za dodeljivanje Azure uloge za pristup blob objektu i podacima u redu](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama saradnika za podatke skladišta blob objekta](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="d7bd0-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="d7bd0-123">U Azure Synapse radnom prostoru, *principalu usluge za uvide u ciljnu grupu* je potrebna dodeljena uloga **Synapse administratora**.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="d7bd0-124">Za više informacija, pogledajte [Kako se postavlja kontrola pristupa za vaš Synapse radni prostor](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="d7bd0-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="d7bd0-125">Podesite vezu i izvoz u Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="d7bd0-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="d7bd0-126">Konfigurisanje veze</span><span class="sxs-lookup"><span data-stu-id="d7bd0-126">Configure a connection</span></span>

1. <span data-ttu-id="d7bd0-127">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d7bd0-128">Izaberite **Dodaj vezu** i birajte **Azure Synapse Analytics** ili izaberite **Podešavanje** na pločici **Azure Synapse Analytics** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="d7bd0-129">Dajte vezi prepoznatljivo ime u polju Ime za prikaz.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="d7bd0-130">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="d7bd0-131">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d7bd0-132">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-132">Choose who can use this connection.</span></span> <span data-ttu-id="d7bd0-133">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d7bd0-134">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d7bd0-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d7bd0-135">Izaberite ili potražite pretplatu u kojoj želite da koristite Customer Insights podatke.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="d7bd0-136">Čim izaberete pretplatu, možete i da izaberete **Radni prostor**, **Nalog skladišta** i **Kontejner**.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="d7bd0-137">Izaberite **Sačuvaj** da biste sačuvali vezu.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="d7bd0-138">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="d7bd0-138">Configure an export</span></span>

<span data-ttu-id="d7bd0-139">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d7bd0-140">Za više informacija, pogledajte [dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d7bd0-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d7bd0-141">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d7bd0-142">Da biste kreirali novi izvoz, izaberite **Dodaj izvoz**.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="d7bd0-143">U polju **Veza za izvoz** odaberite vezu iz odeljka **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="d7bd0-144">Ako ne vidite naziv ovog odeljka, ne postoje [veze](connections.md) ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="d7bd0-145">Obezbedite prepoznatljivo **Ime za prikaz** za vaš izvoz i **Naziv baze podataka**.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="d7bd0-146">Izaberite koje entitete želite da izvezete u uslugu Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="d7bd0-147">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-147">Select **Save**.</span></span>

<span data-ttu-id="d7bd0-148">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d7bd0-149">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d7bd0-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d7bd0-150">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d7bd0-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="d7bd0-151">Ažuriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="d7bd0-151">Update an export</span></span>

1. <span data-ttu-id="d7bd0-152">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d7bd0-153">Izaberite **Uredi** na izvozu koji želite da promenite.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="d7bd0-154">**Dodajte** ili **uklonite** entitete iz izbora.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="d7bd0-155">Ako se entiteti uklone iz izbora, neće se izbrisati iz Synapse Analytics baze podataka.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="d7bd0-156">Međutim, buduća osvežavanja podataka neće ažurirati uklonjene entitete u toj bazi podataka.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="d7bd0-157">**Promena naziva baze podataka** kreira novu Synapse Analytics bazu podataka.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="d7bd0-158">Baza podataka sa imenom koje je prethodno bilo konfigurisano neće dobijati ažuriranja u budućim osvežavanjima.</span><span class="sxs-lookup"><span data-stu-id="d7bd0-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
