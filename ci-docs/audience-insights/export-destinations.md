---
title: Odrdišta za izvoz
description: Izvezite podatke i upravljajte odredištima za izvoz.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643880"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="818a2-103">Odredišta za izvoz (pregled)</span><span class="sxs-lookup"><span data-stu-id="818a2-103">Export destinations (preview)</span></span>

<span data-ttu-id="818a2-104">Stranica **Odredišta za izvoz** prikazuje sve lokacije na koje ste postavili izvoz podataka.</span><span class="sxs-lookup"><span data-stu-id="818a2-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="818a2-105">Takođe možete dodati nova odredišta za izvoz.</span><span class="sxs-lookup"><span data-stu-id="818a2-105">You can also add new destinations for export.</span></span> <span data-ttu-id="818a2-106">Pored toga, prikazuje izvoz trenutno dostupnih opcija.</span><span class="sxs-lookup"><span data-stu-id="818a2-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="818a2-107">Preuzmite brzi pregled, opis i saznajte šta možete uraditi sa svakom opcijom proširivosti.</span><span class="sxs-lookup"><span data-stu-id="818a2-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="818a2-108">Izvezite objedinjene profile, mere i segmente u podržane aplikacije relevantne za vaše poslovanje.</span><span class="sxs-lookup"><span data-stu-id="818a2-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="818a2-109">Idite na **Administrator** > **Izvoz odredišta** da biste pronašli sledeće opcije proširenja:</span><span class="sxs-lookup"><span data-stu-id="818a2-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="818a2-110">Dynamics 365 programski dodatak za karticu klijenta</span><span class="sxs-lookup"><span data-stu-id="818a2-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="818a2-111">Facebook Ads Manager konektor</span><span class="sxs-lookup"><span data-stu-id="818a2-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="818a2-112">Power Automate konektor</span><span class="sxs-lookup"><span data-stu-id="818a2-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="818a2-113">Power Apps konektor</span><span class="sxs-lookup"><span data-stu-id="818a2-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="818a2-114">Power BI konektor</span><span class="sxs-lookup"><span data-stu-id="818a2-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="818a2-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="818a2-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="818a2-116">Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="818a2-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="818a2-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="818a2-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="818a2-118">Azure skladište blob objekta</span><span class="sxs-lookup"><span data-stu-id="818a2-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="818a2-119">LiveRamp&reg; konektor</span><span class="sxs-lookup"><span data-stu-id="818a2-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="818a2-120">Robot za Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="818a2-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="818a2-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="818a2-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="818a2-122">Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="818a2-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="818a2-123">Dodavanje novog odredišta za izvoz</span><span class="sxs-lookup"><span data-stu-id="818a2-123">Add a new export destination</span></span>

<span data-ttu-id="818a2-124">Da biste dodali odredišta za izvoz, imate [administratorske dozvole](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="818a2-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="818a2-125">Ako izvozite u Microsoft usluge, pretpostavljamo da su obe usluge u istoj organizaciji.</span><span class="sxs-lookup"><span data-stu-id="818a2-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="818a2-126">Idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="818a2-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="818a2-127">Prebacite se na karticu **Moja odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="818a2-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="818a2-128">Izaberite **Dodavanje odredišta** da biste kreirali novo odredište za izvoz.</span><span class="sxs-lookup"><span data-stu-id="818a2-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="818a2-129">U oknu **Dodavanje odredišta**, izaberite **Tip** odredišta za izvoz u padajućoj listi.</span><span class="sxs-lookup"><span data-stu-id="818a2-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="818a2-130">Navedite potrebne detalje i izaberite **Sledeće** da kreirate odredište za izvoz.</span><span class="sxs-lookup"><span data-stu-id="818a2-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="818a2-131">Takođe možete da izaberete **Podešavanje** na pločici na kartici **Otkrivanje**.</span><span class="sxs-lookup"><span data-stu-id="818a2-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="818a2-132">Prikaz odredišta za izvoz</span><span class="sxs-lookup"><span data-stu-id="818a2-132">View Export destinations</span></span>

<span data-ttu-id="818a2-133">Kada kreirate odredišta za izvoz, naći ćete ih u tabeli na kartici **Moja odredišta za izvoz**. Ova tabela ima tri kolone:</span><span class="sxs-lookup"><span data-stu-id="818a2-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="818a2-134">**Ime za prikaz**: Ime koje ste uneli prilikom kreiranja odredišta.</span><span class="sxs-lookup"><span data-stu-id="818a2-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="818a2-135">**Tip**: Vrsta odredišta za izvoz koju ste postavili prilikom kreiranja odredišta.</span><span class="sxs-lookup"><span data-stu-id="818a2-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="818a2-136">**Kreirano**: Datum kad ste kreirali odredište.</span><span class="sxs-lookup"><span data-stu-id="818a2-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="818a2-137">Uređivanje odredišta za izvoz</span><span class="sxs-lookup"><span data-stu-id="818a2-137">Edit an export destination</span></span>

1. <span data-ttu-id="818a2-138">Izaberite vertikalne tri tačke za odredište za izvoz koje želite da uređujete.</span><span class="sxs-lookup"><span data-stu-id="818a2-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="818a2-139">![Vertikalne tri tačke](media/export-destinations-page-ellipsis.png "Vertikalne tri tačke")</span><span class="sxs-lookup"><span data-stu-id="818a2-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="818a2-140">Izaberite **Uređuj** iz padajućeg menija.</span><span class="sxs-lookup"><span data-stu-id="818a2-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="818a2-141">Promenite vrednosti za koje je potrebno ažuriranje i izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="818a2-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="818a2-142">Izvoz podataka na zahtev</span><span class="sxs-lookup"><span data-stu-id="818a2-142">Export data on demand</span></span>

<span data-ttu-id="818a2-143">Nakon konfigurisanja konektora za odredište za izvoz, izvozi će se pokrenuti sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="818a2-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="818a2-144">Da biste izvezli podatke bez čekanja na zakazano osvežavanje, idite na karticu **Moja odredišta za izvoz** u dijalogu **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="818a2-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="818a2-145">![Vertikalne tri tačke](media/export-destinations-page-ellipsis.png "Vertikalne tri tačke")</span><span class="sxs-lookup"><span data-stu-id="818a2-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="818a2-146">Izaberite **Izvezi** iznad liste da biste istovremeno pokrenuli izvoz u sva odredišta za izvoz.</span><span class="sxs-lookup"><span data-stu-id="818a2-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="818a2-147">Izaberite tri tačke (...) nakon stavke liste, a zatim odaberite opciju **Izvezi** za pokretanje izvoza za jedno odredište za izvoz.</span><span class="sxs-lookup"><span data-stu-id="818a2-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="818a2-148">Uklanjanje odredište za izvoz</span><span class="sxs-lookup"><span data-stu-id="818a2-148">Remove an Export destination</span></span>

<span data-ttu-id="818a2-149">Da biste uklonili odredište za izvoz, počnite iz glavne stranice **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="818a2-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="818a2-150">Odaberite vertikalne tri tačke za odredište za izvoz koje želite da uklonite.</span><span class="sxs-lookup"><span data-stu-id="818a2-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="818a2-151">![Vertikalne tri tačke](media/export-destinations-page-ellipsis.png "Vertikalne tri tačke")</span><span class="sxs-lookup"><span data-stu-id="818a2-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="818a2-152">Izaberite **Ukloni** iz padajućeg menija.</span><span class="sxs-lookup"><span data-stu-id="818a2-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="818a2-153">Potvrdite uklanjanje odabirom **Ukloni** na ekranu za potvrdu.</span><span class="sxs-lookup"><span data-stu-id="818a2-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
