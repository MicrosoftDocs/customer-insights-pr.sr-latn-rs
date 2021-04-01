---
title: Koristite izvore podataka radi unosa podataka
description: Naučite kako da uvezete podatke iz različitih izvora.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595964"
---
# <a name="data-sources-overview"></a><span data-ttu-id="7999a-103">Pregled izvora podataka</span><span class="sxs-lookup"><span data-stu-id="7999a-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="7999a-104">Sposobnost uvida o korisnicima u usluzi Dynamics 365 Customer Insights povezuje se sa podacima iz širokog skupa izvora.</span><span class="sxs-lookup"><span data-stu-id="7999a-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="7999a-105">Povezivanje sa izvorom podataka se često naziva procesom *unošenja podataka*.</span><span class="sxs-lookup"><span data-stu-id="7999a-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="7999a-106">Nakon unošenja podataka, možete ih [objediniti](data-unification.md) i preduzeti radnju nad njima.</span><span class="sxs-lookup"><span data-stu-id="7999a-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="7999a-107">Dodavanje izvora podataka</span><span class="sxs-lookup"><span data-stu-id="7999a-107">Add a data source</span></span>

<span data-ttu-id="7999a-108">Pogledajte detaljne članke o tome kako da dodate izvor podataka, u zavisnosti od toga koju opciju ste izabrali.</span><span class="sxs-lookup"><span data-stu-id="7999a-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="7999a-109">Izvor podataka možete dodati na tri glavna načina:</span><span class="sxs-lookup"><span data-stu-id="7999a-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="7999a-110">Kroz desetine Power Query konektora</span><span class="sxs-lookup"><span data-stu-id="7999a-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="7999a-111">Iz Common Data Model fascikle</span><span class="sxs-lookup"><span data-stu-id="7999a-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="7999a-112">Iz vašeg sopstvenog Common Data Service jezera</span><span class="sxs-lookup"><span data-stu-id="7999a-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="7999a-113">Još ne možete da dodate podatke iz lokalnih izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="7999a-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="7999a-114">Pregled unetih podataka</span><span class="sxs-lookup"><span data-stu-id="7999a-114">Review ingested data</span></span>

<span data-ttu-id="7999a-115">Videćete naziv svakog unetog izvora podataka, njegov status i poslednji put kada su podaci osveženi za taj izvor.</span><span class="sxs-lookup"><span data-stu-id="7999a-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="7999a-116">Spisak izvora podataka možete sortirati po svakoj koloni.</span><span class="sxs-lookup"><span data-stu-id="7999a-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7999a-117">![Izvor podataka je dodat](media/configure-data-datasource-added.png "Izvor podataka je dodat")</span><span class="sxs-lookup"><span data-stu-id="7999a-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="7999a-118">Status</span><span class="sxs-lookup"><span data-stu-id="7999a-118">Status</span></span>  |<span data-ttu-id="7999a-119">Opis</span><span class="sxs-lookup"><span data-stu-id="7999a-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="7999a-120">Uspešno</span><span class="sxs-lookup"><span data-stu-id="7999a-120">Successful</span></span>   |<span data-ttu-id="7999a-121">Izvor podataka je uspešno unet ako je vreme navedeno u koloni **Osveženo**.</span><span class="sxs-lookup"><span data-stu-id="7999a-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="7999a-122">Nije započeto</span><span class="sxs-lookup"><span data-stu-id="7999a-122">Not started</span></span>   |<span data-ttu-id="7999a-123">Izvor podataka još nema unetih podataka ili je još uvek u režimu radne verzije.</span><span class="sxs-lookup"><span data-stu-id="7999a-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="7999a-124">Osvežavanje</span><span class="sxs-lookup"><span data-stu-id="7999a-124">Refreshing</span></span>    |<span data-ttu-id="7999a-125">Unos podataka je u toku.</span><span class="sxs-lookup"><span data-stu-id="7999a-125">Data ingestion is in progress.</span></span> <span data-ttu-id="7999a-126">Ovu operaciju možete otkazati ako izaberete **Zaustavi osvežavanje** u koloni **Radnje**.</span><span class="sxs-lookup"><span data-stu-id="7999a-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="7999a-127">Zaustavljanje osvežavanja izvora podataka vratiće ga u poslednje stanje osvežavanja.</span><span class="sxs-lookup"><span data-stu-id="7999a-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="7999a-128">Neuspeh</span><span class="sxs-lookup"><span data-stu-id="7999a-128">Failed</span></span>     |<span data-ttu-id="7999a-129">Unos podataka je naišao na greške.</span><span class="sxs-lookup"><span data-stu-id="7999a-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="7999a-130">Izaberite vrednost u koloni **Status** bilo kog izvora podataka da biste pregledali više detalja.</span><span class="sxs-lookup"><span data-stu-id="7999a-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="7999a-131">U oknu **Detalji napretka**, proširite stavku **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="7999a-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="7999a-132">Izaberite **Pogledaj detalje** da biste dobili više informacija o statusu osvežavanja, uključujući detalje o greškama i nadogradnje procesa.</span><span class="sxs-lookup"><span data-stu-id="7999a-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="7999a-133">Učitavanje podataka može da potraje.</span><span class="sxs-lookup"><span data-stu-id="7999a-133">Loading data can take some time.</span></span> <span data-ttu-id="7999a-134">Nakon uspešnog osvežavanja, uneseni podaci mogu se pregledati sa stranice **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="7999a-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="7999a-135">Za više informacija, pogledajte članak [Entiteti](entities.md).</span><span class="sxs-lookup"><span data-stu-id="7999a-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="7999a-136">Osvežite izvor podataka</span><span class="sxs-lookup"><span data-stu-id="7999a-136">Refresh a data source</span></span>

<span data-ttu-id="7999a-137">Izvori podataka mogu se osvežavati po automatskom rasporedu ili ručno na zahtev.</span><span class="sxs-lookup"><span data-stu-id="7999a-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="7999a-138">Idite na **Administrator** > **Sistem** > [**Raspored**](system.md#schedule-tab) da biste konfigurisali zakazana osvežavanja svih unetih izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="7999a-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="7999a-139">Da biste osvežili izvor podataka na zahtev, sledite ove korake:</span><span class="sxs-lookup"><span data-stu-id="7999a-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="7999a-140">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**</span><span class="sxs-lookup"><span data-stu-id="7999a-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="7999a-141">Izaberite vertikalnu elipsu pored izvora podataka koji želite da osvežite i izaberite **Osveži** sa padajuće liste.</span><span class="sxs-lookup"><span data-stu-id="7999a-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="7999a-142">Izvor podataka je sada aktiviran za ručno osvežavanje.</span><span class="sxs-lookup"><span data-stu-id="7999a-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="7999a-143">Osvežavanjem izvora podataka ažuriraće se obe šeme entiteta kao i podaci za sve entitete navedene u izvoru podataka.</span><span class="sxs-lookup"><span data-stu-id="7999a-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="7999a-144">Izaberite **Prestanite sa osvežavanjem** ako želite da otkažete postojeće osvežavanje i izvor podataka će se vratiti na svoj poslednji status osvežavanja.</span><span class="sxs-lookup"><span data-stu-id="7999a-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="7999a-145">Izbriši izvor podataka</span><span class="sxs-lookup"><span data-stu-id="7999a-145">Delete a data source</span></span>

1. <span data-ttu-id="7999a-146">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="7999a-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="7999a-147">Izaberite uspravne tri tačke pored izvora podataka koji želite da uklonite i izaberite **Izbriši** iz padajućeg menija.</span><span class="sxs-lookup"><span data-stu-id="7999a-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="7999a-148">Potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="7999a-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]