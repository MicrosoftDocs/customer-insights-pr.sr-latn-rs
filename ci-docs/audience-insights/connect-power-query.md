---
title: Unos podataka putem Power Query konektora
description: Konektori za izvore podataka zasnovane na rešenju Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406800"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="e15d8-103">Povezivanje sa Power Query izvorom podataka</span><span class="sxs-lookup"><span data-stu-id="e15d8-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="e15d8-104">Power Query nudi širok skup konektora za unos podataka.</span><span class="sxs-lookup"><span data-stu-id="e15d8-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="e15d8-105">Većinu ovih konektora podržava Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e15d8-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="e15d8-106">Dodavanje izvora podataka na osnovu Power Query konektora uglavnom sledi korake navedene u sledećem odeljku.</span><span class="sxs-lookup"><span data-stu-id="e15d8-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="e15d8-107">Međutim, u zavisnosti od konektora koji koristite, potrebne su različite informacije.</span><span class="sxs-lookup"><span data-stu-id="e15d8-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="e15d8-108">Za više informacija pogledajte dokumentaciju o pojedinačnim konektorima u [referenci Power Query konektora](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="e15d8-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="e15d8-109">Kreiranje novog izvora podataka</span><span class="sxs-lookup"><span data-stu-id="e15d8-109">Create a new data source</span></span>

1. <span data-ttu-id="e15d8-110">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="e15d8-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="e15d8-111">Izaberite **Dodaj izvor podataka**.</span><span class="sxs-lookup"><span data-stu-id="e15d8-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="e15d8-112">Odaberite metod **Uvoza podataka** i izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="e15d8-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="e15d8-113">Navedite **Naziv** za izvor podataka, pa izaberite **Sledeće** kako biste kreirali izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="e15d8-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="e15d8-114">Odaberite jedan od [dostupnih konektora](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="e15d8-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="e15d8-115">Za ovaj primer biramo **Tekst/CSV** konektor.</span><span class="sxs-lookup"><span data-stu-id="e15d8-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="e15d8-116">Unesite potrebne detalje u **Podešavanja veze** za izabrani konektor i izaberite **Sledeće** da biste videli pregled podataka.</span><span class="sxs-lookup"><span data-stu-id="e15d8-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="e15d8-117">Izaberite **Transformacija podataka**.</span><span class="sxs-lookup"><span data-stu-id="e15d8-117">Select **Transform data**.</span></span> <span data-ttu-id="e15d8-118">U ovom koraku ćete dodati entitete svom izvoru podataka.</span><span class="sxs-lookup"><span data-stu-id="e15d8-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="e15d8-119">Entiteti su skupovi podataka.</span><span class="sxs-lookup"><span data-stu-id="e15d8-119">Entities are datasets.</span></span> <span data-ttu-id="e15d8-120">Ako imate bazu podataka koja uključuje više skupova podataka, svaki skup podataka je svoj sopstveni entitet.</span><span class="sxs-lookup"><span data-stu-id="e15d8-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="e15d8-121">Dijalog **Power Query – Uređivanje profila** vam omogućava da pregledate i precizirate podatke.</span><span class="sxs-lookup"><span data-stu-id="e15d8-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="e15d8-122">Entiteti koje su sistemi identifikovali u vašem izabranom izvoru podataka prikazuju se u levom oknu.</span><span class="sxs-lookup"><span data-stu-id="e15d8-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e15d8-123">![Dijalog za uređivanje upita](media/data-manager-configure-edit-queries.png "Dijalog za uređivanje upita")</span><span class="sxs-lookup"><span data-stu-id="e15d8-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="e15d8-124">Takođe možete da transformišete svoje podatke.</span><span class="sxs-lookup"><span data-stu-id="e15d8-124">You can also transform your data.</span></span> <span data-ttu-id="e15d8-125">Izaberite entitet za uređivanje ili transformisanje.</span><span class="sxs-lookup"><span data-stu-id="e15d8-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="e15d8-126">Koristite opcije u Power Query prozoru kako biste primenili transformacije.</span><span class="sxs-lookup"><span data-stu-id="e15d8-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="e15d8-127">Svaka transformacija se navodi u okviru **Primenjenih koraka**.</span><span class="sxs-lookup"><span data-stu-id="e15d8-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="e15d8-128">Power Query pruža brojne unapred napravljene mogućnosti transformacije.</span><span class="sxs-lookup"><span data-stu-id="e15d8-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="e15d8-129">Za više informacija, pogledajte [Power Query transformacije](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="e15d8-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="e15d8-130">Možete dodati dodatne entitete u izvor podataka ako izaberete **Preuzmi podatke** u dijalogu **Uređivanje upita**.</span><span class="sxs-lookup"><span data-stu-id="e15d8-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="e15d8-131">Ove transformacije se izričito preporučuju:</span><span class="sxs-lookup"><span data-stu-id="e15d8-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="e15d8-132">Ako unosite podatke iz CSV datoteke, prvi red često sadrži zaglavlja.</span><span class="sxs-lookup"><span data-stu-id="e15d8-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="e15d8-133">Idite na **Transformacija tabele** i izaberite **Koristi zaglavlja kao prvi red**.</span><span class="sxs-lookup"><span data-stu-id="e15d8-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="e15d8-134">Uverite se da je tip podataka podešen na odgovarajući način.</span><span class="sxs-lookup"><span data-stu-id="e15d8-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="e15d8-135">Izaberite **Sačuvaj** u donjem uglu Power Query prozora da biste sačuvali transformacije.</span><span class="sxs-lookup"><span data-stu-id="e15d8-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="e15d8-136">Nakon čuvanja, pronaći ćete svoj izvor podataka u okviru **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="e15d8-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="e15d8-137">Na stranici **Izvori podataka**, primetićete da je novi izvor podataka u statusu **Osvežavanje**.</span><span class="sxs-lookup"><span data-stu-id="e15d8-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="e15d8-138">Dostupni Power Query izvori podataka</span><span class="sxs-lookup"><span data-stu-id="e15d8-138">Available Power Query data sources</span></span>

<span data-ttu-id="e15d8-139">Pogledajte [referencu Power Query konektora](https://docs.microsoft.com/power-query/connectors/) za ažuriranu listu konektora koje možete izabrati za uvoz podataka u Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e15d8-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="e15d8-140">Konektori sa znakom potvrde u koloni **Customer Insights (tokovi podataka)** su dostupni za kreiranje novih izvora podataka zasnovanih na rešenju Power Query.</span><span class="sxs-lookup"><span data-stu-id="e15d8-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="e15d8-141">Pregledajte dokumentaciju određenog konektora da biste saznali više o njegovim preduslovima, ograničenjima i ostalim detaljima.</span><span class="sxs-lookup"><span data-stu-id="e15d8-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="e15d8-142">Uređivanje Power Query izvora podataka</span><span class="sxs-lookup"><span data-stu-id="e15d8-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="e15d8-143">Možda neće biti moguće izvršiti promene izvora podataka koji se trenutno koriste u jednom od procesa aplikacije (npr. *segmentacija*, *podudaranje* ili *spajanje*).</span><span class="sxs-lookup"><span data-stu-id="e15d8-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="e15d8-144">Pomoću stranice **Podešavanja**, možete pratiti napredak svakog aktivnog procesa.</span><span class="sxs-lookup"><span data-stu-id="e15d8-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="e15d8-145">Kada se proces dovrši, možete se vratiti na stranicu **Izvori podataka** i uneti izmene.</span><span class="sxs-lookup"><span data-stu-id="e15d8-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="e15d8-146">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="e15d8-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="e15d8-147">Izaberite uspravne tri tačke pored izvora podataka koji želite da promenite i izaberite **Uredi** iz padajućeg menija.</span><span class="sxs-lookup"><span data-stu-id="e15d8-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e15d8-148">![Uređivanje opcije](media/edit-option-data-sources.png "Uređivanje opcije")</span><span class="sxs-lookup"><span data-stu-id="e15d8-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="e15d8-149">Primenite promene i transformacije u dijalogu **Power Query – uređivanje upita** kao što je opisano u odeljku [Kreiranje novog izvora podataka](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="e15d8-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="e15d8-150">Kako biste sačuvali izmene, izaberite **Sačuvaj** u rešenju Power Query nakon što dovršite uređivanja.</span><span class="sxs-lookup"><span data-stu-id="e15d8-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
