---
title: Unos podataka putem Power Query konektora
description: Konektori za izvore podataka zasnovane na rešenju Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 50c231070ff9930c1ea82971bf4f8541a89d5027
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305908"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="78a3d-103">Povezivanje sa Power Query izvorom podataka</span><span class="sxs-lookup"><span data-stu-id="78a3d-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="78a3d-104">Power Query nudi širok skup konektora za unos podataka.</span><span class="sxs-lookup"><span data-stu-id="78a3d-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="78a3d-105">Većinu ovih konektora podržava Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="78a3d-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="78a3d-106">Dodavanje izvora podataka na osnovu Power Query konektora uglavnom sledi korake navedene u sledećem odeljku.</span><span class="sxs-lookup"><span data-stu-id="78a3d-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="78a3d-107">Međutim, u zavisnosti od konektora koji koristite, potrebne su različite informacije.</span><span class="sxs-lookup"><span data-stu-id="78a3d-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="78a3d-108">Za više informacija pogledajte dokumentaciju o pojedinačnim konektorima u [referenci Power Query konektora](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="78a3d-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="78a3d-109">Kreiranje novog izvora podataka</span><span class="sxs-lookup"><span data-stu-id="78a3d-109">Create a new data source</span></span>

1. <span data-ttu-id="78a3d-110">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="78a3d-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="78a3d-111">Izaberite **Dodaj izvor podataka**.</span><span class="sxs-lookup"><span data-stu-id="78a3d-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="78a3d-112">Odaberite metod **Uvoza podataka** i izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="78a3d-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="78a3d-113">Navedite **Naziv** za izvor podataka, pa izaberite **Sledeće** kako biste kreirali izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="78a3d-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="78a3d-114">Smernice za nazive:</span><span class="sxs-lookup"><span data-stu-id="78a3d-114">Name guidelines:</span></span> 
   - <span data-ttu-id="78a3d-115">Započnite slovom.</span><span class="sxs-lookup"><span data-stu-id="78a3d-115">Start with a letter.</span></span>
   - <span data-ttu-id="78a3d-116">Koristite samo slova i brojeve.</span><span class="sxs-lookup"><span data-stu-id="78a3d-116">Use letters and numbers only.</span></span> <span data-ttu-id="78a3d-117">Posebni znakovi i razmaci nisu dozvoljeni.</span><span class="sxs-lookup"><span data-stu-id="78a3d-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="78a3d-118">Koristite između 3 i 64 znaka.</span><span class="sxs-lookup"><span data-stu-id="78a3d-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="78a3d-119">Odaberite jedan od [dostupnih konektora](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="78a3d-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="78a3d-120">Za ovaj primer biramo **Tekst/CSV** konektor.</span><span class="sxs-lookup"><span data-stu-id="78a3d-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="78a3d-121">Unesite potrebne detalje u **Podešavanja veze** za izabrani konektor i izaberite **Sledeće** da biste videli pregled podataka.</span><span class="sxs-lookup"><span data-stu-id="78a3d-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="78a3d-122">Izaberite **Transformacija podataka**.</span><span class="sxs-lookup"><span data-stu-id="78a3d-122">Select **Transform data**.</span></span> <span data-ttu-id="78a3d-123">U ovom koraku ćete dodati entitete svom izvoru podataka.</span><span class="sxs-lookup"><span data-stu-id="78a3d-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="78a3d-124">Entiteti su skupovi podataka.</span><span class="sxs-lookup"><span data-stu-id="78a3d-124">Entities are datasets.</span></span> <span data-ttu-id="78a3d-125">Ako imate bazu podataka koja uključuje više skupova podataka, svaki skup podataka je svoj sopstveni entitet.</span><span class="sxs-lookup"><span data-stu-id="78a3d-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="78a3d-126">Dijalog **Power Query – Uređivanje profila** vam omogućava da pregledate i precizirate podatke.</span><span class="sxs-lookup"><span data-stu-id="78a3d-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="78a3d-127">Entiteti koje su sistemi identifikovali u vašem izabranom izvoru podataka prikazuju se u levom oknu.</span><span class="sxs-lookup"><span data-stu-id="78a3d-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="78a3d-128">![Dijalog za uređivanje upita](media/data-manager-configure-edit-queries.png "Dijalog za uređivanje upita")</span><span class="sxs-lookup"><span data-stu-id="78a3d-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="78a3d-129">Takođe možete da transformišete svoje podatke.</span><span class="sxs-lookup"><span data-stu-id="78a3d-129">You can also transform your data.</span></span> <span data-ttu-id="78a3d-130">Izaberite entitet za uređivanje ili transformisanje.</span><span class="sxs-lookup"><span data-stu-id="78a3d-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="78a3d-131">Koristite opcije u Power Query prozoru kako biste primenili transformacije.</span><span class="sxs-lookup"><span data-stu-id="78a3d-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="78a3d-132">Svaka transformacija se navodi u okviru **Primenjenih koraka**.</span><span class="sxs-lookup"><span data-stu-id="78a3d-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="78a3d-133">Power Query pruža brojne unapred napravljene mogućnosti transformacije.</span><span class="sxs-lookup"><span data-stu-id="78a3d-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="78a3d-134">Za više informacija, pogledajte [Power Query transformacije](/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="78a3d-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="78a3d-135">Možete dodati dodatne entitete u izvor podataka ako izaberete **Preuzmi podatke** u dijalogu **Uređivanje upita**.</span><span class="sxs-lookup"><span data-stu-id="78a3d-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="78a3d-136">Ove transformacije se izričito preporučuju:</span><span class="sxs-lookup"><span data-stu-id="78a3d-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="78a3d-137">Ako unosite podatke iz CSV datoteke, prvi red često sadrži zaglavlja.</span><span class="sxs-lookup"><span data-stu-id="78a3d-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="78a3d-138">Idite na **Transformacija tabele** i izaberite **Koristi zaglavlja kao prvi red**.</span><span class="sxs-lookup"><span data-stu-id="78a3d-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="78a3d-139">Uverite se da je tip podataka podešen na odgovarajući način.</span><span class="sxs-lookup"><span data-stu-id="78a3d-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="78a3d-140">Izaberite **Sačuvaj** u donjem uglu Power Query prozora da biste sačuvali transformacije.</span><span class="sxs-lookup"><span data-stu-id="78a3d-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="78a3d-141">Nakon čuvanja, pronaći ćete svoj izvor podataka u okviru **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="78a3d-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="78a3d-142">Na stranici **Izvori podataka**, primetićete da je novi izvor podataka u statusu **Osvežavanje**.</span><span class="sxs-lookup"><span data-stu-id="78a3d-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="78a3d-143">Dostupni Power Query izvori podataka</span><span class="sxs-lookup"><span data-stu-id="78a3d-143">Available Power Query data sources</span></span>

<span data-ttu-id="78a3d-144">Pogledajte [referencu Power Query konektora](/power-query/connectors/) za ažuriranu listu konektora koje možete izabrati za uvoz podataka u Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="78a3d-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="78a3d-145">Konektori sa znakom potvrde u koloni **Customer Insights (tokovi podataka)** su dostupni za kreiranje novih izvora podataka zasnovanih na rešenju Power Query.</span><span class="sxs-lookup"><span data-stu-id="78a3d-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="78a3d-146">Pregledajte dokumentaciju određenog konektora da biste saznali više o njegovim preduslovima, ograničenjima i ostalim detaljima.</span><span class="sxs-lookup"><span data-stu-id="78a3d-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="78a3d-147">Uređivanje Power Query izvora podataka</span><span class="sxs-lookup"><span data-stu-id="78a3d-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="78a3d-148">Možda neće biti moguće izvršiti promene izvora podataka koji se trenutno koriste u jednom od procesa aplikacije (npr. *segmentacija*, *podudaranje* ili *spajanje*).</span><span class="sxs-lookup"><span data-stu-id="78a3d-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="78a3d-149">Pomoću stranice **Podešavanja**, možete pratiti napredak svakog aktivnog procesa.</span><span class="sxs-lookup"><span data-stu-id="78a3d-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="78a3d-150">Kada se proces dovrši, možete se vratiti na stranicu **Izvori podataka** i uneti izmene.</span><span class="sxs-lookup"><span data-stu-id="78a3d-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="78a3d-151">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="78a3d-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="78a3d-152">Izaberite vertikalne tri tačke pored izvora podataka koje želite da promenite i izaberite **Uredi** iz padajućeg menija.</span><span class="sxs-lookup"><span data-stu-id="78a3d-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the dropdown menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="78a3d-153">![Uređivanje opcije](media/edit-option-data-sources.png "Uređivanje opcije")</span><span class="sxs-lookup"><span data-stu-id="78a3d-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="78a3d-154">Primenite promene i transformacije u dijalogu **Power Query – uređivanje upita** kao što je opisano u odeljku [Kreiranje novog izvora podataka](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="78a3d-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="78a3d-155">Kako biste sačuvali izmene, izaberite **Sačuvaj** u rešenju Power Query nakon što dovršite uređivanja.</span><span class="sxs-lookup"><span data-stu-id="78a3d-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]