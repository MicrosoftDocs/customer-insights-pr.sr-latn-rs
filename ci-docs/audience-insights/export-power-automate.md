---
title: Power Automate konektor | Microsoft Docs
description: Kreirajte tokove u usluzi Microsoft Power Automate iz usluge Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305081"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="899c6-103">Power Automate konektor (pregled)</span><span class="sxs-lookup"><span data-stu-id="899c6-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="899c6-104">Pokrenite određene događaje koji se pojavljuju automatski kada se promene podaci i upravljajte složenijim tokovima direktno u usluzi [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="899c6-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="899c6-105">Power Automate okidači</span><span class="sxs-lookup"><span data-stu-id="899c6-105">Power Automate triggers</span></span>

<span data-ttu-id="899c6-106">Koristite okidače da kreirate tokove u oblaku i automatizujete ponavljajuće zadatke, kao što su obaveštenja ili naprednije radnje.</span><span class="sxs-lookup"><span data-stu-id="899c6-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="899c6-107">Pokrenite kada ne uspe osvežavanje izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="899c6-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="899c6-108">Pokrenite kada uspe osvežavanje izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="899c6-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="899c6-109">Pokrenite kada se pređe granična vrednost za segment.</span><span class="sxs-lookup"><span data-stu-id="899c6-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="899c6-110">Okidač je ograničen na prekoračenje granične vrednosti.</span><span class="sxs-lookup"><span data-stu-id="899c6-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="899c6-111">Pokrenite kada se pređe granična vrednost za poslovnu meru.</span><span class="sxs-lookup"><span data-stu-id="899c6-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="899c6-112">Podržane su samo poslovne mere bez dimenzije.</span><span class="sxs-lookup"><span data-stu-id="899c6-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="899c6-113">Okidač je ograničen na prekoračenje granične vrednosti.</span><span class="sxs-lookup"><span data-stu-id="899c6-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="899c6-114">Aktivira se kada se završi potpuno osvežavanje (izvora podataka, segmenata, mera, ...).</span><span class="sxs-lookup"><span data-stu-id="899c6-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="899c6-115">Pokrenite kada se završi osvežavanje procesa objedinjavanja (mapiranje, podudaranje, spajanje).</span><span class="sxs-lookup"><span data-stu-id="899c6-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="899c6-116">Konfigurišite okidače u usluzi Power Automate.</span><span class="sxs-lookup"><span data-stu-id="899c6-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="899c6-117">Power Automate radnje</span><span class="sxs-lookup"><span data-stu-id="899c6-117">Power Automate actions</span></span>

<span data-ttu-id="899c6-118">Power Automate konektor pruža druge radnje osim dostupnih okidača.</span><span class="sxs-lookup"><span data-stu-id="899c6-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="899c6-119">Za više informacija pogledajte [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="899c6-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="899c6-120">Kreiranje Power Automate toka</span><span class="sxs-lookup"><span data-stu-id="899c6-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="899c6-121">U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="899c6-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="899c6-122">Na pločici **Power Automate** izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="899c6-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="899c6-123">Otvara se Customer Insights konektor (pregled) u usluzi Power Automate.</span><span class="sxs-lookup"><span data-stu-id="899c6-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="899c6-124">**Prijavite se** u Power Automate.</span><span class="sxs-lookup"><span data-stu-id="899c6-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="899c6-125">Izaberite jedan od dostupnih okidača i dodajte još koraka svom novom toku.</span><span class="sxs-lookup"><span data-stu-id="899c6-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="899c6-126">Za više informacija pogledajte [Kreiranje toka u oblaku u usluzi Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="899c6-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="899c6-127">Primeri kako se koriste tokovi:</span><span class="sxs-lookup"><span data-stu-id="899c6-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="899c6-128">Pošaljite poruku na Microsoft Teams kanal ako osvežavanje izvora podataka ne uspe.</span><span class="sxs-lookup"><span data-stu-id="899c6-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="899c6-129">Pošaljite e-poruku vlasnicima podataka kada se pređe prag na segmentu.</span><span class="sxs-lookup"><span data-stu-id="899c6-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
