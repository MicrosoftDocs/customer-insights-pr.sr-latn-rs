---
title: Power Automate konektor | Microsoft Docs
description: Kreirajte tokove u usluzi Microsoft Power Automate iz usluge Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976105"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="dfcb7-103">Power Automate konektor (pregled)</span><span class="sxs-lookup"><span data-stu-id="dfcb7-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="dfcb7-104">Pokrenite određene događaje koji se pojavljuju automatski kada se promene podaci i upravljajte složenijim tokovima direktno u usluzi [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="dfcb7-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="dfcb7-105">Power Automate okidači</span><span class="sxs-lookup"><span data-stu-id="dfcb7-105">Power Automate triggers</span></span>

<span data-ttu-id="dfcb7-106">Koristite okidače da kreirate tokove u oblaku i automatizujete ponavljajuće zadatke, kao što su obaveštenja ili naprednije radnje.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="dfcb7-107">Pokrenite kada ne uspe osvežavanje izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="dfcb7-108">Pokrenite kada uspe osvežavanje izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="dfcb7-109">Pokrenite kada se pređe granična vrednost za segment.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="dfcb7-110">Okidač je ograničen na prekoračenje granične vrednosti.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="dfcb7-111">Pokrenite kada se pređe granična vrednost za poslovnu meru.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="dfcb7-112">Podržane su samo poslovne mere bez dimenzije.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="dfcb7-113">Okidač je ograničen na prekoračenje granične vrednosti.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="dfcb7-114">Aktivira se kada se završi potpuno osvežavanje (izvora podataka, segmenata, mera...).</span><span class="sxs-lookup"><span data-stu-id="dfcb7-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="dfcb7-115">Pokrenite kada se završi osvežavanje procesa objedinjavanja (mapiranje, podudaranje, spajanje).</span><span class="sxs-lookup"><span data-stu-id="dfcb7-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="dfcb7-116">[Konfigurisanje okidača u usluzi Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="dfcb7-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="dfcb7-117">Power Automate radnje</span><span class="sxs-lookup"><span data-stu-id="dfcb7-117">Power Automate actions</span></span>
<span data-ttu-id="dfcb7-118">Power Automate konektor pruža druge radnje osim dostupnih okidača.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="dfcb7-119">Za više informacija pogledajte [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="dfcb7-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="dfcb7-120">Kreiranje Power Automate toka</span><span class="sxs-lookup"><span data-stu-id="dfcb7-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="dfcb7-121">U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="dfcb7-122">Na pločici **Power Automate** izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="dfcb7-123">Otvara se Customer Insights konektor (pregled) u usluzi Power Automate.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="dfcb7-124">**Prijavite se** u Power Automate.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="dfcb7-125">Izaberite jedan od dostupnih okidača i dodajte još koraka svom novom toku.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="dfcb7-126">Za više informacija pogledajte [Kreiranje toka u oblaku u usluzi Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="dfcb7-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="dfcb7-127">Primeri korišćenja tokova:</span><span class="sxs-lookup"><span data-stu-id="dfcb7-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="dfcb7-128">Pošaljite poruku na Microsoft Teams kanal ako osvežavanje izvora podataka ne uspe.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="dfcb7-129">Pošaljite e-poruku vlasnicima podataka kada se pređe prag na segmentu.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
