---
title: Kreiranje okruženja i upravljanje njima
description: Saznajte kako se registrujete za uslugu i kako da upravljate okruženjima.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598310"
---
# <a name="manage-environments"></a><span data-ttu-id="a6eac-103">Upravljanje okruženjima</span><span class="sxs-lookup"><span data-stu-id="a6eac-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a6eac-104">Ovaj članak objašnjava kako da kreirate novu organizaciju i obezbedite okruženje.</span><span class="sxs-lookup"><span data-stu-id="a6eac-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="a6eac-105">Registrujte se i napravite organizaciju</span><span class="sxs-lookup"><span data-stu-id="a6eac-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="a6eac-106">Idite na veb-lokaciju [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="a6eac-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="a6eac-107">Izaberite **Prvi koraci**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="a6eac-108">Odaberite željeni scenario prijave i izaberite odgovarajuću vezu.</span><span class="sxs-lookup"><span data-stu-id="a6eac-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="a6eac-109">Prihvatite uslove i odredbe i izaberite **Nastavi** da biste započeli kreiranje organizacije.</span><span class="sxs-lookup"><span data-stu-id="a6eac-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="a6eac-110">Nakon kreiranja okruženja, bićete preusmereni na [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="a6eac-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="a6eac-111">Koristite demo okruženje da istražite aplikaciju ili kreirajte novo okruženje prateći korake u sledećem odeljku.</span><span class="sxs-lookup"><span data-stu-id="a6eac-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="a6eac-112">Kada navedete podešavanja okruženja, izaberite **Kreiraj**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="a6eac-113">Bićete prijavljeni nakon što je okruženje uspešno kreirano.</span><span class="sxs-lookup"><span data-stu-id="a6eac-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="a6eac-114">Kreirajte okruženje u postojećoj organizaciji</span><span class="sxs-lookup"><span data-stu-id="a6eac-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="a6eac-115">Postoje dva načina za kreiranje novog okruženja.</span><span class="sxs-lookup"><span data-stu-id="a6eac-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="a6eac-116">Možete da navedete potpuno novu konfiguraciju ili da kopirate neka podešavanja konfiguracije iz postojećeg okruženja.</span><span class="sxs-lookup"><span data-stu-id="a6eac-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="a6eac-117">Da biste kreirali okruženja:</span><span class="sxs-lookup"><span data-stu-id="a6eac-117">To create an environment:</span></span>

1. <span data-ttu-id="a6eac-118">Izaberite birač **Okruženje** u zaglavlju aplikacije.</span><span class="sxs-lookup"><span data-stu-id="a6eac-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="a6eac-119">Izaberite **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a6eac-120">![Podešavanja okruženja](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="a6eac-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="a6eac-121">U dijalogu **Kreirajte novo okruženje**, izaberite **Novo okruženje**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="a6eac-122">Ako želite da [kopirate podatke iz trenutnog okruženja](#additional-considerations-for-copy-configuration-preview), izaberite **Kopiraj iz postojećeg okruženja**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="a6eac-123">Videćete listu svih dostupnih okruženja u vašoj organizaciji, odakle možete kopirati podatke.</span><span class="sxs-lookup"><span data-stu-id="a6eac-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="a6eac-124">Navedite sledeće detalje:</span><span class="sxs-lookup"><span data-stu-id="a6eac-124">Provide the following details:</span></span>
   - <span data-ttu-id="a6eac-125">**Naziv**: Unesite naziv ovog okruženja.</span><span class="sxs-lookup"><span data-stu-id="a6eac-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="a6eac-126">Ovo polje je već popunjeno ako ste kopirali postojeće okruženje, ali možete ga promeniti.</span><span class="sxs-lookup"><span data-stu-id="a6eac-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="a6eac-127">**Region**: Region u kojem je usluga primenjena i hostovana.</span><span class="sxs-lookup"><span data-stu-id="a6eac-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="a6eac-128">**Tip**: Izaberite da li želite da kreirate proizvodno ili Sandbox okruženje.</span><span class="sxs-lookup"><span data-stu-id="a6eac-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="a6eac-129">Po želji možete odabrati **Napredna podešavanja**:</span><span class="sxs-lookup"><span data-stu-id="a6eac-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="a6eac-130">**Sačuvaj sve podatke u**: Određuje gde želite da sačuvate izlazne podatke generisane u usluzi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a6eac-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="a6eac-131">Imaćete dve mogućnosti: **Customer Insights skladište** (Azure Data Lake kojim upravlja Customer Insights tim) i **Azure Data Lake Storage Gen2** (vaš sopstveni Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="a6eac-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="a6eac-132">Podrazumevano je odabrana opcija Customer Insights skladišta.</span><span class="sxs-lookup"><span data-stu-id="a6eac-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a6eac-133">Čuvanjem podataka u usluzi Azure Data Lake Storage, slažete se da će podaci biti preneti i uskladišteni na odgovarajućoj geografskoj lokaciji za taj Azure nalog za skladištenje, koja može da se razlikuje od mesta skladištenja podataka u usluzi Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a6eac-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="a6eac-134">Saznajte više u Microsoft centru za pouzdanost.</span><span class="sxs-lookup"><span data-stu-id="a6eac-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="a6eac-135">Trenutno se uneti entiteti uvek čuvaju u jezeru podataka kojim upravlja Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a6eac-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="a6eac-136">Podržavamo samo Azure Data Lake Gen2 naloge za skladištenje iz iste Azure regije koju ste izabrali prilikom kreiranja okruženja.</span><span class="sxs-lookup"><span data-stu-id="a6eac-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="a6eac-137">Mi podržavamo samo naloge za skladištenje koje omogućuje Azure Data Lake Gen2 hijerarhijski prostoru imena (HNS).</span><span class="sxs-lookup"><span data-stu-id="a6eac-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="a6eac-138">Za opciju Azure Data Lake Storage Gen2, možete da birate između opcije zasnovane na resursima i opcije zasnovane na pretplati za potvrdu identiteta.</span><span class="sxs-lookup"><span data-stu-id="a6eac-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="a6eac-139">Za više informacija pogledajte [Povezivanje uvida o korisnicima sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="a6eac-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="a6eac-140">Naziv **kontejnera** se ne može promeniti i biće „uvidi o korisnicima“.</span><span class="sxs-lookup"><span data-stu-id="a6eac-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="a6eac-141">Ako želite da koristite [predviđanja](predictions.md) ili konfigurišete deljenje podataka sa aplikacijama i rešenjima zasnovano na platformi Microsoft Dataverse, obezbedite URL adresu Microsoft Dataverse okruženja u delu **Konfigurišite deljenje podataka sa platformom Microsoft Dataverse i omogućite dodatne mogućnosti**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="a6eac-142">Izaberite **Omogući deljenje podataka** da biste delili Customer Insights izlazne podatke pomoću usluge Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="a6eac-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="a6eac-143">Deljenje podataka pomoću usluge Microsoft Dataverse Managed Data Lake trenutno nije podržano kada sve podatke čuvate u sopstvenom Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="a6eac-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="a6eac-144">[Predviđanje vrednosti koje nedostaju u entitetu](predictions.md) trenutno nije podržano kada omogućite deljenje podataka sa uslugom Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="a6eac-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="a6eac-145">![Opcije konfiguracije za omogućavanje deljenja podataka sa uslugom Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="a6eac-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="a6eac-146">Kada pokrenete procese, poput unosa podataka ili kreiranja segmenta, na nalogu za skladištenje koji ste gore naveli kreiraće se odgovarajuće mape.</span><span class="sxs-lookup"><span data-stu-id="a6eac-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="a6eac-147">Datoteke podataka i datoteke model.json će biti kreirane i dodate u odgovarajuće potfasikle na osnovu procesa koji pokrećete.</span><span class="sxs-lookup"><span data-stu-id="a6eac-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="a6eac-148">Ako kreirate više okruženja za Customer Insights i odlučite da sačuvate izlazne entitete iz tih okruženja na svom nalogu za skladištenje, kreiraće se zasebne fascikle za svako okruženje sa ci_<environmentid> u kontejneru.</span><span class="sxs-lookup"><span data-stu-id="a6eac-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="a6eac-149">Dodatna razmatranja za konfiguraciju kopija (pregled)</span><span class="sxs-lookup"><span data-stu-id="a6eac-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="a6eac-150">Kopiraju se sledeća podešavanja konfiguracije:</span><span class="sxs-lookup"><span data-stu-id="a6eac-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="a6eac-151">Konfiguracije funkcija</span><span class="sxs-lookup"><span data-stu-id="a6eac-151">Feature configurations</span></span>
- <span data-ttu-id="a6eac-152">Uneseni/uvezeni izvori podataka</span><span class="sxs-lookup"><span data-stu-id="a6eac-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="a6eac-153">Konfiguracija objedinjavanja podataka (mapa, podudaranje, spajanje)</span><span class="sxs-lookup"><span data-stu-id="a6eac-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="a6eac-154">Segmenti</span><span class="sxs-lookup"><span data-stu-id="a6eac-154">Segments</span></span>
- <span data-ttu-id="a6eac-155">Mere</span><span class="sxs-lookup"><span data-stu-id="a6eac-155">Measures</span></span>
- <span data-ttu-id="a6eac-156">Odnosi</span><span class="sxs-lookup"><span data-stu-id="a6eac-156">Relationships</span></span>
- <span data-ttu-id="a6eac-157">Aktivnosti</span><span class="sxs-lookup"><span data-stu-id="a6eac-157">Activities</span></span>
- <span data-ttu-id="a6eac-158">Indeks pretrage i filtriranja</span><span class="sxs-lookup"><span data-stu-id="a6eac-158">Search & filter Index</span></span>
- <span data-ttu-id="a6eac-159">Odredišta za izvoz</span><span class="sxs-lookup"><span data-stu-id="a6eac-159">Export destinations</span></span>
- <span data-ttu-id="a6eac-160">Planirano osvežavanje</span><span class="sxs-lookup"><span data-stu-id="a6eac-160">Scheduled refresh</span></span>
- <span data-ttu-id="a6eac-161">Obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="a6eac-161">Enrichments</span></span>
- <span data-ttu-id="a6eac-162">Upravljanje modelima</span><span class="sxs-lookup"><span data-stu-id="a6eac-162">Model management</span></span>
- <span data-ttu-id="a6eac-163">Dodela uloga</span><span class="sxs-lookup"><span data-stu-id="a6eac-163">Role assignments</span></span>

<span data-ttu-id="a6eac-164">Sledeća podešavanja se *ne* kopiraju:</span><span class="sxs-lookup"><span data-stu-id="a6eac-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="a6eac-165">Profili klijenata.</span><span class="sxs-lookup"><span data-stu-id="a6eac-165">Customer profiles.</span></span>
- <span data-ttu-id="a6eac-166">Akreditivi izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="a6eac-166">Data source credentials.</span></span> <span data-ttu-id="a6eac-167">Moraćete da dostavite akreditive za svaki izvor podataka i ručno osvežite izvore podataka.</span><span class="sxs-lookup"><span data-stu-id="a6eac-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="a6eac-168">Izvori podataka iz fascikle Common Data Model i Common Data Service upravljanog jezera.</span><span class="sxs-lookup"><span data-stu-id="a6eac-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="a6eac-169">Te izvore podataka ćete morati da kreirate ručno, s istim nazivom kao u izvornom okruženju.</span><span class="sxs-lookup"><span data-stu-id="a6eac-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="a6eac-170">Kada kopirate okruženje, videćete poruku potvrde da je kreirano novo okruženje.</span><span class="sxs-lookup"><span data-stu-id="a6eac-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="a6eac-171">Izaberite **Idite na izvore podataka** da biste videli listu izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="a6eac-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="a6eac-172">Svi izvori podataka će pokazati status **Potrebni su akreditivi**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="a6eac-173">Uredite izvore podataka i unesite akreditive da biste ih osvežili.</span><span class="sxs-lookup"><span data-stu-id="a6eac-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a6eac-174">![Kopirani izvori podataka](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="a6eac-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="a6eac-175">Nakon osvežavanja izvora podataka, idite na **Podaci** > **Objedini**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="a6eac-176">Ovde ćete pronaći podešavanja iz izvornog okruženja.</span><span class="sxs-lookup"><span data-stu-id="a6eac-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="a6eac-177">Uredite ih po potrebi ili izaberite **Pokreni** da biste pokrenuli proces objedinjavanja podataka i kreirali objedinjeni entitet klijenta.</span><span class="sxs-lookup"><span data-stu-id="a6eac-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="a6eac-178">Kada objedinjavanje podataka bude dovršeno, idite na **Mere** i **Segmenti** da osvežite i njih.</span><span class="sxs-lookup"><span data-stu-id="a6eac-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="a6eac-179">Uređivanje postojećeg okruženja</span><span class="sxs-lookup"><span data-stu-id="a6eac-179">Edit an existing environment</span></span>

<span data-ttu-id="a6eac-180">Možete da izmenite neke detalje postojećih okruženja.</span><span class="sxs-lookup"><span data-stu-id="a6eac-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="a6eac-181">Izaberite birač **Okruženje** u zaglavlju aplikacije.</span><span class="sxs-lookup"><span data-stu-id="a6eac-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="a6eac-182">Izaberite ikonu **Uređivanje**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="a6eac-183">U okviru **Uredi okruženje** možete ažurirati okruženje **Ime za prikaz** okruženja, ali ne možete da promenite **Region** ili **Tip**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="a6eac-184">Ako je okruženje konfigurisano za čuvanje podataka Azure Data Lake Storage Gen2, možete da ažurirate **Ključ naloga**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="a6eac-185">Međutim, ne možete promeniti **Ime naloga** ni ime **kontejnera**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="a6eac-186">Po želji možete da ažurirate sa veze ključa naloga na vezu zasnovanu na resursima ili pretplati.</span><span class="sxs-lookup"><span data-stu-id="a6eac-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="a6eac-187">Kada ih nadogradite, ne možete se vratiti na ključ naloga nakon ažuriranja.</span><span class="sxs-lookup"><span data-stu-id="a6eac-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="a6eac-188">Za više informacija pogledajte [Povezivanje uvida o korisnicima sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="a6eac-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="a6eac-189">Ne možete promeniti informacije o **kontejneru** prilikom ažuriranja veze.</span><span class="sxs-lookup"><span data-stu-id="a6eac-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="a6eac-190">Uspostavljanje početnih vrednosti postojećeg okruženja</span><span class="sxs-lookup"><span data-stu-id="a6eac-190">Reset an existing environment</span></span>

<span data-ttu-id="a6eac-191">Kao administrator, možete da vratite okruženje na prazno stanje ako želite da izbrišete sve konfiguracije i uklonite unete podatke.</span><span class="sxs-lookup"><span data-stu-id="a6eac-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="a6eac-192">Izaberite birač **Okruženje** u zaglavlju aplikacije.</span><span class="sxs-lookup"><span data-stu-id="a6eac-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="a6eac-193">Izaberite okruženje koje želite da resetujete i izaberite tri tačke **...**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="a6eac-194">Izaberite opciju **Resetuj**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="a6eac-195">Da biste potvrdili brisanje, unesite ime okruženja i izaberite **Resetuj**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="a6eac-196">Izbrišite postojeće okruženje (dostupno samo za administratore)</span><span class="sxs-lookup"><span data-stu-id="a6eac-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="a6eac-197">Kao administrator možete da izbrišete okruženje kojim administrirate.</span><span class="sxs-lookup"><span data-stu-id="a6eac-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="a6eac-198">Izaberite birač **Okruženje** u zaglavlju aplikacije.</span><span class="sxs-lookup"><span data-stu-id="a6eac-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="a6eac-199">Izaberite okruženje koje želite da resetujete i izaberite tri tačke **...**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="a6eac-200">Odaberite opciju **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="a6eac-201">Da biste potvrdili brisanje, unesite naziv okruženja i izaberite **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="a6eac-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]