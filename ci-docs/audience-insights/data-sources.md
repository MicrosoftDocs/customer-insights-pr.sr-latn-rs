---
title: Koristite izvore podataka radi unosa podataka
description: Naučite kako da uvezete podatke iz različitih izvora.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887911"
---
# <a name="data-sources-overview"></a><span data-ttu-id="6df9b-103">Pregled izvora podataka</span><span class="sxs-lookup"><span data-stu-id="6df9b-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6df9b-104">Sposobnost uvida o korisnicima u usluzi Dynamics 365 Customer Insights povezuje se sa podacima iz širokog skupa izvora.</span><span class="sxs-lookup"><span data-stu-id="6df9b-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="6df9b-105">Povezivanje sa izvorom podataka se često naziva procesom *unošenja podataka*.</span><span class="sxs-lookup"><span data-stu-id="6df9b-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="6df9b-106">Nakon unošenja podataka, možete ih [objediniti](data-unification.md) i preduzeti radnju nad njima.</span><span class="sxs-lookup"><span data-stu-id="6df9b-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="6df9b-107">Dodavanje izvora podataka</span><span class="sxs-lookup"><span data-stu-id="6df9b-107">Add a data source</span></span>

<span data-ttu-id="6df9b-108">Pogledajte detaljne članke o tome kako da dodate izvor podataka, u zavisnosti od toga koju opciju ste izabrali.</span><span class="sxs-lookup"><span data-stu-id="6df9b-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="6df9b-109">Izvor podataka možete dodati na tri glavna načina:</span><span class="sxs-lookup"><span data-stu-id="6df9b-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="6df9b-110">Kroz desetine Power Query konektora</span><span class="sxs-lookup"><span data-stu-id="6df9b-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="6df9b-111">Iz Common Data Model fascikle</span><span class="sxs-lookup"><span data-stu-id="6df9b-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="6df9b-112">Iz vašeg sopstvenog Common Data Service jezera</span><span class="sxs-lookup"><span data-stu-id="6df9b-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="6df9b-113">Dodavanje podataka iz lokalnih izvora podataka</span><span class="sxs-lookup"><span data-stu-id="6df9b-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="6df9b-114">Unošenje podataka iz lokalnih izvora podataka u uslugu Uvidi u korisnike je podržano na osnovu Power Platform tokova podataka.</span><span class="sxs-lookup"><span data-stu-id="6df9b-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="6df9b-115">Tokovi podataka se mogu omogućiti u usluzi Customer Insights [navođenjem URL adrese Microsoft Dataverse okruženja](manage-environments.md#create-an-environment-in-an-existing-organization) prilikom podešavanja okruženja.</span><span class="sxs-lookup"><span data-stu-id="6df9b-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="6df9b-116">Izvori podataka koji se kreiraju nakon povezivanja Dataverse okruženja sa uslugom Customer Insights će podrazumevano koristiti [Power Platform tokove podataka](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="6df9b-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="6df9b-117">Tokovi podataka podržavaju lokalnu povezanost pomoću mrežnih prolaza za podatke.</span><span class="sxs-lookup"><span data-stu-id="6df9b-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="6df9b-118">Uklonite i ponovo kreirajte izvore podataka koji su postojali pre nego što je Dataverse okruženje bilo povezano za upotrebu lokalnih mrežnih prolaza za podatke.</span><span class="sxs-lookup"><span data-stu-id="6df9b-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="6df9b-119">Mrežni prolazi za podatke iz postojećeg Power BI ili Power Apps okruženja će biti vidljivi i možete ponovo da ih koristite u usluzi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6df9b-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="6df9b-120">Stranica sa izvorima podataka prikazuje veze ka Power Platform okruženju u kojem možete da pregledate i konfigurišete lokalne mrežne prolaze za podatke.</span><span class="sxs-lookup"><span data-stu-id="6df9b-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Snimak ekrana stranice sa izvorima podataka koja prikazuje veze koje vode do Power Platform okruženja.":::

## <a name="review-ingested-data"></a><span data-ttu-id="6df9b-122">Pregled unetih podataka</span><span class="sxs-lookup"><span data-stu-id="6df9b-122">Review ingested data</span></span>

<span data-ttu-id="6df9b-123">Videćete naziv svakog unetog izvora podataka, njegov status i poslednji put kada su podaci osveženi za taj izvor.</span><span class="sxs-lookup"><span data-stu-id="6df9b-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="6df9b-124">Spisak izvora podataka možete sortirati po svakoj koloni.</span><span class="sxs-lookup"><span data-stu-id="6df9b-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6df9b-125">![Izvor podataka je dodat](media/configure-data-datasource-added.png "Izvor podataka je dodat")</span><span class="sxs-lookup"><span data-stu-id="6df9b-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="6df9b-126">Status</span><span class="sxs-lookup"><span data-stu-id="6df9b-126">Status</span></span>  |<span data-ttu-id="6df9b-127">Opis</span><span class="sxs-lookup"><span data-stu-id="6df9b-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="6df9b-128">Uspešno</span><span class="sxs-lookup"><span data-stu-id="6df9b-128">Successful</span></span>   |<span data-ttu-id="6df9b-129">Izvor podataka je uspešno unet ako je vreme navedeno u koloni **Osveženo**.</span><span class="sxs-lookup"><span data-stu-id="6df9b-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="6df9b-130">Nije započeto</span><span class="sxs-lookup"><span data-stu-id="6df9b-130">Not started</span></span>   |<span data-ttu-id="6df9b-131">Izvor podataka još nema unetih podataka ili je još uvek u režimu radne verzije.</span><span class="sxs-lookup"><span data-stu-id="6df9b-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="6df9b-132">Osvežavanje</span><span class="sxs-lookup"><span data-stu-id="6df9b-132">Refreshing</span></span>    |<span data-ttu-id="6df9b-133">Unos podataka je u toku.</span><span class="sxs-lookup"><span data-stu-id="6df9b-133">Data ingestion is in progress.</span></span> <span data-ttu-id="6df9b-134">Ovu operaciju možete otkazati ako izaberete **Zaustavi osvežavanje** u koloni **Radnje**.</span><span class="sxs-lookup"><span data-stu-id="6df9b-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="6df9b-135">Zaustavljanje osvežavanja izvora podataka vratiće ga u poslednje stanje osvežavanja.</span><span class="sxs-lookup"><span data-stu-id="6df9b-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="6df9b-136">Neuspeh</span><span class="sxs-lookup"><span data-stu-id="6df9b-136">Failed</span></span>     |<span data-ttu-id="6df9b-137">Unos podataka je naišao na greške.</span><span class="sxs-lookup"><span data-stu-id="6df9b-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="6df9b-138">Izaberite vrednost u koloni **Status** bilo kog izvora podataka da biste pregledali više detalja.</span><span class="sxs-lookup"><span data-stu-id="6df9b-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="6df9b-139">U oknu **Detalji napretka**, proširite stavku **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="6df9b-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="6df9b-140">Izaberite **Pogledaj detalje** da biste dobili više informacija o statusu osvežavanja, uključujući detalje o greškama i nadogradnje procesa.</span><span class="sxs-lookup"><span data-stu-id="6df9b-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="6df9b-141">Učitavanje podataka može da potraje.</span><span class="sxs-lookup"><span data-stu-id="6df9b-141">Loading data can take some time.</span></span> <span data-ttu-id="6df9b-142">Nakon uspešnog osvežavanja, uneseni podaci mogu se pregledati sa stranice **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="6df9b-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="6df9b-143">Za više informacija, pogledajte članak [Entiteti](entities.md).</span><span class="sxs-lookup"><span data-stu-id="6df9b-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="6df9b-144">Osvežite izvor podataka</span><span class="sxs-lookup"><span data-stu-id="6df9b-144">Refresh a data source</span></span>

<span data-ttu-id="6df9b-145">Izvori podataka mogu se osvežavati po automatskom rasporedu ili ručno na zahtev.</span><span class="sxs-lookup"><span data-stu-id="6df9b-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="6df9b-146">Idite na **Administrator** > **Sistem** > [**Raspored**](system.md#schedule-tab) da biste konfigurisali zakazana osvežavanja svih unetih izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="6df9b-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="6df9b-147">Da biste osvežili izvor podataka na zahtev, sledite ove korake:</span><span class="sxs-lookup"><span data-stu-id="6df9b-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="6df9b-148">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**</span><span class="sxs-lookup"><span data-stu-id="6df9b-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="6df9b-149">Izaberite vertikalnu elipsu pored izvora podataka koji želite da osvežite i izaberite **Osveži** sa padajuće liste.</span><span class="sxs-lookup"><span data-stu-id="6df9b-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="6df9b-150">Izvor podataka je sada aktiviran za ručno osvežavanje.</span><span class="sxs-lookup"><span data-stu-id="6df9b-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="6df9b-151">Osvežavanjem izvora podataka ažuriraće se i šema entiteta i podaci za sve entitete navedene u izvoru podataka.</span><span class="sxs-lookup"><span data-stu-id="6df9b-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="6df9b-152">Izaberite **Prestanite sa osvežavanjem** ako želite da otkažete postojeće osvežavanje i izvor podataka će se vratiti na svoj poslednji status osvežavanja.</span><span class="sxs-lookup"><span data-stu-id="6df9b-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="6df9b-153">Izbriši izvor podataka</span><span class="sxs-lookup"><span data-stu-id="6df9b-153">Delete a data source</span></span>

1. <span data-ttu-id="6df9b-154">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="6df9b-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="6df9b-155">Izaberite uspravne tri tačke pored izvora podataka koji želite da uklonite i izaberite **Izbriši** iz padajućeg menija.</span><span class="sxs-lookup"><span data-stu-id="6df9b-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="6df9b-156">Potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="6df9b-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
