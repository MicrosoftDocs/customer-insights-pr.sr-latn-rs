---
title: Povežite Common Data Model podatke sa Azure Data Lake nalogom
description: Radite sa Common Data Model podacima koristeći Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596562"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="2dd46-103">Povežite se sa Common Data Model fasciklom koja koristi Azure Data Lake nalog</span><span class="sxs-lookup"><span data-stu-id="2dd46-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="2dd46-104">Ovaj članak pruža informacije o tome kako unositi podatke iz Common Data Model fascikle pomoću Azure Data Lake Storage Gen2 naloga.</span><span class="sxs-lookup"><span data-stu-id="2dd46-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="2dd46-105">Važna razmatranja</span><span class="sxs-lookup"><span data-stu-id="2dd46-105">Important considerations</span></span>

- <span data-ttu-id="2dd46-106">Podaci u vašem Azure Data Lake treba da prate uobičajeni standard Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="2dd46-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="2dd46-107">Drugi formati trenutno nisu podržani.</span><span class="sxs-lookup"><span data-stu-id="2dd46-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="2dd46-108">Unos podataka podržava samo Azure Data Lake *Gen2* naloge za skladištenje.</span><span class="sxs-lookup"><span data-stu-id="2dd46-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="2dd46-109">Ne možete da koristite Azure Data Lake Gen1 naloge za skladištenje za unos podataka.</span><span class="sxs-lookup"><span data-stu-id="2dd46-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="2dd46-110">Da biste potvrdili identitet pomoću principala usluge Azure, uverite se da je konfigurisan u vašem zakupcu.</span><span class="sxs-lookup"><span data-stu-id="2dd46-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="2dd46-111">Za više informacija pogledajte [Povezivanje uvida o korisnicima sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="2dd46-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="2dd46-112">Azure Data Lake sa kojim želite da se povežete i unesete podatke mora biti u istom Azure regionu kao i Dynamics 365 Customer Insights okruženje.</span><span class="sxs-lookup"><span data-stu-id="2dd46-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="2dd46-113">Ne podržavaju se veze sa Common Data Model fasciklom iz jezera podataka u drugom Azure regionu.</span><span class="sxs-lookup"><span data-stu-id="2dd46-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="2dd46-114">Da biste saznali Azure region okruženja, posetite **Administrator** > **Sistem** > **Osnovni podaci** u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="2dd46-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="2dd46-115">Podaci koji se čuvaju u uslugama na mreži mogu se čuvati na lokaciji koja se razlikuje od one na kojoj se podaci obrađuju ili čuvaju u usluzi Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2dd46-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="2dd46-116"> Uvozom ili povezivanjem podataka uskladištenih u mrežnoj usluzi, slažete se da se podaci mogu preneti i skladištiti u usluzi Dynamics 365 Customer Insights. [Saznajte više u Microsoft centru za pouzdanost.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="2dd46-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="2dd46-117">Povezivanje u fasciklu Common Data Model</span><span class="sxs-lookup"><span data-stu-id="2dd46-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="2dd46-118">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="2dd46-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="2dd46-119">Izaberite **Dodaj izvor podataka**.</span><span class="sxs-lookup"><span data-stu-id="2dd46-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="2dd46-120">Izaberite **Povežite se sa Common Data Model fasciklom**, unesite **Ime** za izvor podataka i izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="2dd46-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="2dd46-121">Smernice za nazive:</span><span class="sxs-lookup"><span data-stu-id="2dd46-121">Name guidelines:</span></span> 
   - <span data-ttu-id="2dd46-122">Započnite slovom.</span><span class="sxs-lookup"><span data-stu-id="2dd46-122">Start with a letter.</span></span>
   - <span data-ttu-id="2dd46-123">Koristite samo slova i brojeve.</span><span class="sxs-lookup"><span data-stu-id="2dd46-123">Use letters and numbers only.</span></span> <span data-ttu-id="2dd46-124">Posebni znakovi i razmaci nisu dozvoljeni.</span><span class="sxs-lookup"><span data-stu-id="2dd46-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="2dd46-125">Koristite između 3 i 64 znaka.</span><span class="sxs-lookup"><span data-stu-id="2dd46-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="2dd46-126">Možete da birate između korišćenja opcije zasnovane na resursima i opcije zasnovane na pretplati za potvrdu identiteta.</span><span class="sxs-lookup"><span data-stu-id="2dd46-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="2dd46-127">Za više informacija pogledajte [Povezivanje uvida o korisnicima sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="2dd46-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="2dd46-128">Unesite informacije o **Kontejneru** i izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="2dd46-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2dd46-129">![Dijalog za unos novih detalja veze za Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="2dd46-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="2dd46-130">Potrebna vam je jedna od sledećih uloga u kontejneru ili nalogu za skladištenje pomenutom gore da biste mogli da se povežete i kreirate izvor podataka:</span><span class="sxs-lookup"><span data-stu-id="2dd46-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="2dd46-131">Čitač podataka skladišta blob objekta</span><span class="sxs-lookup"><span data-stu-id="2dd46-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="2dd46-132">Vlasnik podataka skladišta blob objekta</span><span class="sxs-lookup"><span data-stu-id="2dd46-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="2dd46-133">Saradnik za podatke skladišta blob objekta</span><span class="sxs-lookup"><span data-stu-id="2dd46-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="2dd46-134">U dijalogu **Izaberite Common Data Model fasciklu**, izaberite datoteku model.json ili manifest.json iz koje želite da uvezete podatke, pa izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="2dd46-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="2dd46-135">Nijedna datoteka model.json ili manifest.json povezana sa drugim izvorom podataka u okruženju neće se prikazati na listi.</span><span class="sxs-lookup"><span data-stu-id="2dd46-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="2dd46-136">Listu dostupnih entiteta dobićete u izabranoj datoteci model.json ili manifest.json.</span><span class="sxs-lookup"><span data-stu-id="2dd46-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="2dd46-137">Možete da pregledate entitete i izaberete ih sa liste dostupnih entiteta, pa izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="2dd46-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="2dd46-138">Svi izabrani entiteti biće uneti iz novog izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="2dd46-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2dd46-139">![Dijalog koji prikazuje listu entiteta iz datoteke model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="2dd46-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="2dd46-140">Navedite entitete podataka za koje želite da omogućite profilisanje podataka i izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="2dd46-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="2dd46-141">Profilisanje podataka omogućava analitiku i druge mogućnosti.</span><span class="sxs-lookup"><span data-stu-id="2dd46-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="2dd46-142">Možete odabrati čitav entitet koji bira sve atribute iz entiteta ili odabrati određene atribute po svom izboru.</span><span class="sxs-lookup"><span data-stu-id="2dd46-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="2dd46-143">Podrazumevano nijedan entitet nije omogućen za profilisanje podataka.</span><span class="sxs-lookup"><span data-stu-id="2dd46-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2dd46-144">![Dijalog koji prikazuje profilisanje podataka](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="2dd46-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="2dd46-145">Kada sačuvate izabrane opcije, otvoriće se stranica **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="2dd46-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="2dd46-146">Sada bi trebalo da vidite vezu Common Data Model fascikle kao izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="2dd46-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="2dd46-147">Datoteka model.json ili manifest.json može se povezati samo sa jednim izvorom podataka u istom okruženju.</span><span class="sxs-lookup"><span data-stu-id="2dd46-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="2dd46-148">Međutim, ista datoteka model.json ili manifest.json može se koristiti za izvore podataka u više okruženja.</span><span class="sxs-lookup"><span data-stu-id="2dd46-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="2dd46-149">Uredite izvor podataka Common Data Model fascikle</span><span class="sxs-lookup"><span data-stu-id="2dd46-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="2dd46-150">Možete da ažurirate pristupni ključ za nalog za skladištenje koji sadrži Common Data Model fasciklu.</span><span class="sxs-lookup"><span data-stu-id="2dd46-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="2dd46-151">Takođe možete promeniti datoteku model.json ili manifest.json.</span><span class="sxs-lookup"><span data-stu-id="2dd46-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="2dd46-152">Da biste se povezali na drugi kontejner sa naloga za skladištenje ili da promenite ime naloga, [kreirajte novu vezu sa izvorom podataka](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="2dd46-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="2dd46-153">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="2dd46-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="2dd46-154">Pored izvora podataka koji želite da ažurirate, izaberite tri tačke.</span><span class="sxs-lookup"><span data-stu-id="2dd46-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="2dd46-155">Izaberite opciju **Uredi** sa liste.</span><span class="sxs-lookup"><span data-stu-id="2dd46-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="2dd46-156">Opcionalno, ažurirajte **Ključ za pristup** i izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="2dd46-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dijalog za uređivanje i ažuriranje ključa za pristup za postojeći izvor podataka](media/edit-access-key.png)

5. <span data-ttu-id="2dd46-158">Po želji možete da ažurirate sa veze ključa naloga na vezu zasnovanu na resursima ili pretplati.</span><span class="sxs-lookup"><span data-stu-id="2dd46-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="2dd46-159">Za više informacija pogledajte [Povezivanje uvida o korisnicima sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="2dd46-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="2dd46-160">Ne možete promeniti informacije o **kontejneru** prilikom ažuriranja veze.</span><span class="sxs-lookup"><span data-stu-id="2dd46-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Dijalog za unos detalja veze usluge Azure Data Lake sa postojećim nalogom za skladištenje](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="2dd46-162">Potrebna vam je jedna od sledećih uloga u kontejneru ili nalogu za skladištenje pomenutom gore da biste mogli da se povežete i kreirate izvor podataka:</span><span class="sxs-lookup"><span data-stu-id="2dd46-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="2dd46-163">Čitač podataka skladišta blob objekta</span><span class="sxs-lookup"><span data-stu-id="2dd46-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="2dd46-164">Vlasnik podataka skladišta blob objekta</span><span class="sxs-lookup"><span data-stu-id="2dd46-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="2dd46-165">Saradnik za podatke skladišta blob objekta</span><span class="sxs-lookup"><span data-stu-id="2dd46-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="2dd46-166">Opcionalno, odaberite drugu datoteku model.json ili manifest.json sa različitim skupom entiteta iz kontejnera.</span><span class="sxs-lookup"><span data-stu-id="2dd46-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="2dd46-167">Po želji možete odabrati dodatne entitete za unos.</span><span class="sxs-lookup"><span data-stu-id="2dd46-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="2dd46-168">Takođe možete ukloniti sve već odabrane entitete ako nema zavisnih elemenata.</span><span class="sxs-lookup"><span data-stu-id="2dd46-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="2dd46-169">Ako postoje zavisnosti od postojeće datoteke model.json ili manifest.json i skupa entiteta, videćete poruku o grešci i ne možete da izaberete drugu datoteku model.json ili manifest.json.</span><span class="sxs-lookup"><span data-stu-id="2dd46-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="2dd46-170">Uklonite te zavisnosti pre promene datoteke model.json ili manifest.json ili kreirajte novi izvor podataka sa datotekom model.json ili manifest.json koju želite da koristite da biste izbegli uklanjanje zavisnosti.</span><span class="sxs-lookup"><span data-stu-id="2dd46-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="2dd46-171">Po želji možete odabrati dodatne atribute ili entitete kako biste omogućili profilisanje podataka ili onemogućili već odabrane.</span><span class="sxs-lookup"><span data-stu-id="2dd46-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]