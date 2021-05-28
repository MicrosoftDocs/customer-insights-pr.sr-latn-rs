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
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085547"
---
# <a name="data-sources-overview"></a><span data-ttu-id="26965-103">Pregled izvora podataka</span><span class="sxs-lookup"><span data-stu-id="26965-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="26965-104">Sposobnost uvida o korisnicima u usluzi Dynamics 365 Customer Insights povezuje se sa podacima iz širokog skupa izvora.</span><span class="sxs-lookup"><span data-stu-id="26965-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="26965-105">Povezivanje sa izvorom podataka se često naziva procesom *unošenja podataka*.</span><span class="sxs-lookup"><span data-stu-id="26965-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="26965-106">Nakon unošenja podataka, možete ih [objediniti](data-unification.md) i preduzeti radnju nad njima.</span><span class="sxs-lookup"><span data-stu-id="26965-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="26965-107">Dodavanje izvora podataka</span><span class="sxs-lookup"><span data-stu-id="26965-107">Add a data source</span></span>

<span data-ttu-id="26965-108">Pogledajte detaljne članke o tome kako da dodate izvor podataka, u zavisnosti od toga koju opciju ste izabrali.</span><span class="sxs-lookup"><span data-stu-id="26965-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="26965-109">Izvor podataka možete dodati na tri glavna načina:</span><span class="sxs-lookup"><span data-stu-id="26965-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="26965-110">Kroz desetine Power Query konektora</span><span class="sxs-lookup"><span data-stu-id="26965-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="26965-111">Iz Common Data Model fascikle</span><span class="sxs-lookup"><span data-stu-id="26965-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="26965-112">Iz vašeg sopstvenog Common Data Service jezera</span><span class="sxs-lookup"><span data-stu-id="26965-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="26965-113">Dodavanje podataka iz lokalnih izvora podataka</span><span class="sxs-lookup"><span data-stu-id="26965-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="26965-114">Unošenje podataka iz lokalnih izvora podataka u uslugu Uvidi u korisnike je podržano na osnovu Power Platform tokova podataka.</span><span class="sxs-lookup"><span data-stu-id="26965-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="26965-115">Tokovi podataka se mogu omogućiti u usluzi Customer Insights [navođenjem URL adrese Microsoft Dataverse okruženja](manage-environments.md#create-an-environment-in-an-existing-organization) prilikom podešavanja okruženja.</span><span class="sxs-lookup"><span data-stu-id="26965-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="26965-116">Izvori podataka koji se kreiraju nakon povezivanja Dataverse okruženja sa uslugom Customer Insights će podrazumevano koristiti [Power Platform tokove podataka](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="26965-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="26965-117">Tokovi podataka podržavaju lokalnu povezanost pomoću mrežnog prolaza za podatke.</span><span class="sxs-lookup"><span data-stu-id="26965-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="26965-118">Uklonite i ponovo kreirajte izvore podataka koji su postojali pre nego što je Dataverse okruženje bilo povezano za [upotrebu lokalnih mrežnih prolaza za podatke](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="26965-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="26965-119">Mrežni prolazi za podatke iz postojećeg Power BI ili Power Apps okruženja će biti vidljivi i možete ponovo da ih koristite u usluzi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="26965-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="26965-120">Stranica sa izvorima podataka prikazuje veze ka Power Platform okruženju u kojem možete da pregledate i konfigurišete lokalne mrežne prolaze za podatke.</span><span class="sxs-lookup"><span data-stu-id="26965-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="26965-121">Pregled unetih podataka</span><span class="sxs-lookup"><span data-stu-id="26965-121">Review ingested data</span></span>

<span data-ttu-id="26965-122">Videćete naziv svakog unetog izvora podataka, njegov status i poslednji put kada su podaci osveženi za taj izvor.</span><span class="sxs-lookup"><span data-stu-id="26965-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="26965-123">Spisak izvora podataka možete sortirati po svakoj koloni.</span><span class="sxs-lookup"><span data-stu-id="26965-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="26965-124">![Izvor podataka je dodat](media/configure-data-datasource-added.png "Izvor podataka je dodat")</span><span class="sxs-lookup"><span data-stu-id="26965-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="26965-125">Status</span><span class="sxs-lookup"><span data-stu-id="26965-125">Status</span></span>  |<span data-ttu-id="26965-126">Opis</span><span class="sxs-lookup"><span data-stu-id="26965-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="26965-127">Uspešno</span><span class="sxs-lookup"><span data-stu-id="26965-127">Successful</span></span>   |<span data-ttu-id="26965-128">Izvor podataka je uspešno unet ako je vreme navedeno u koloni **Osveženo**.</span><span class="sxs-lookup"><span data-stu-id="26965-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="26965-129">Nije započeto</span><span class="sxs-lookup"><span data-stu-id="26965-129">Not started</span></span>   |<span data-ttu-id="26965-130">Izvor podataka još nema unetih podataka ili je još uvek u režimu radne verzije.</span><span class="sxs-lookup"><span data-stu-id="26965-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="26965-131">Osvežavanje</span><span class="sxs-lookup"><span data-stu-id="26965-131">Refreshing</span></span>    |<span data-ttu-id="26965-132">Unos podataka je u toku.</span><span class="sxs-lookup"><span data-stu-id="26965-132">Data ingestion is in progress.</span></span> <span data-ttu-id="26965-133">Ovu operaciju možete otkazati ako izaberete **Zaustavi osvežavanje** u koloni **Radnje**.</span><span class="sxs-lookup"><span data-stu-id="26965-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="26965-134">Zaustavljanje osvežavanja izvora podataka vratiće ga u poslednje stanje osvežavanja.</span><span class="sxs-lookup"><span data-stu-id="26965-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="26965-135">Neuspeh</span><span class="sxs-lookup"><span data-stu-id="26965-135">Failed</span></span>     |<span data-ttu-id="26965-136">Unos podataka je naišao na greške.</span><span class="sxs-lookup"><span data-stu-id="26965-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="26965-137">Izaberite vrednost u koloni **Status** bilo kog izvora podataka da biste pregledali više detalja.</span><span class="sxs-lookup"><span data-stu-id="26965-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="26965-138">U oknu **Detalji napretka**, proširite stavku **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="26965-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="26965-139">Izaberite **Pogledaj detalje** da biste dobili više informacija o statusu osvežavanja, uključujući detalje o greškama i nadogradnje procesa.</span><span class="sxs-lookup"><span data-stu-id="26965-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="26965-140">Učitavanje podataka može da potraje.</span><span class="sxs-lookup"><span data-stu-id="26965-140">Loading data can take some time.</span></span> <span data-ttu-id="26965-141">Nakon uspešnog osvežavanja, uneseni podaci mogu se pregledati sa stranice **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="26965-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="26965-142">Za više informacija, pogledajte članak [Entiteti](entities.md).</span><span class="sxs-lookup"><span data-stu-id="26965-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="26965-143">Osvežite izvor podataka</span><span class="sxs-lookup"><span data-stu-id="26965-143">Refresh a data source</span></span>

<span data-ttu-id="26965-144">Izvori podataka mogu se osvežavati po automatskom rasporedu ili ručno na zahtev.</span><span class="sxs-lookup"><span data-stu-id="26965-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="26965-145">Idite na **Administrator** > **Sistem** > [**Raspored**](system.md#schedule-tab) da biste konfigurisali zakazana osvežavanja svih unetih izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="26965-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="26965-146">Da biste osvežili izvor podataka na zahtev, sledite ove korake:</span><span class="sxs-lookup"><span data-stu-id="26965-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="26965-147">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**</span><span class="sxs-lookup"><span data-stu-id="26965-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="26965-148">Izaberite vertikalnu elipsu pored izvora podataka koji želite da osvežite i izaberite **Osveži** sa padajuće liste.</span><span class="sxs-lookup"><span data-stu-id="26965-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="26965-149">Izvor podataka je sada aktiviran za ručno osvežavanje.</span><span class="sxs-lookup"><span data-stu-id="26965-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="26965-150">Osvežavanjem izvora podataka ažuriraće se i šema entiteta i podaci za sve entitete navedene u izvoru podataka.</span><span class="sxs-lookup"><span data-stu-id="26965-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="26965-151">Izaberite **Prestanite sa osvežavanjem** ako želite da otkažete postojeće osvežavanje i izvor podataka će se vratiti na svoj poslednji status osvežavanja.</span><span class="sxs-lookup"><span data-stu-id="26965-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="26965-152">Izbriši izvor podataka</span><span class="sxs-lookup"><span data-stu-id="26965-152">Delete a data source</span></span>

1. <span data-ttu-id="26965-153">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="26965-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="26965-154">Izaberite uspravne tri tačke pored izvora podataka koji želite da uklonite i izaberite **Izbriši** iz padajućeg menija.</span><span class="sxs-lookup"><span data-stu-id="26965-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="26965-155">Potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="26965-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
