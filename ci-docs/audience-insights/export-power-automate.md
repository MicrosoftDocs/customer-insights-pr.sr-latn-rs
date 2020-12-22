---
title: Power Automate konektor | Microsoft Docs
description: Kreirajte tokove u usluzi Microsoft Power Automate iz usluge Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406776"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="84483-103">Power Automate konektor (pregled)</span><span class="sxs-lookup"><span data-stu-id="84483-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="84483-104">Pokrenite određene događaje koji se pojavljuju automatski kada se promene podaci i upravljajte složenijim tokovima direktno u usluzi [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="84483-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="84483-105">Power Automate okidači</span><span class="sxs-lookup"><span data-stu-id="84483-105">Power Automate triggers</span></span>

<span data-ttu-id="84483-106">Možete koristiti razne okidače koji vam omogućavaju da kreirate tokove za automatizaciju zadataka koji se ponavljaju, poput obaveštenja ili naprednijih radnji.</span><span class="sxs-lookup"><span data-stu-id="84483-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="84483-107">Pokrenite kada ne uspe osvežavanje izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="84483-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="84483-108">Pokrenite kada uspe osvežavanje izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="84483-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="84483-109">Pokrenite kada se pređe granična vrednost za segment.</span><span class="sxs-lookup"><span data-stu-id="84483-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="84483-110">Okidač je ograničen na prekoračenje granične vrednosti.</span><span class="sxs-lookup"><span data-stu-id="84483-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="84483-111">Pokrenite kada se pređe granična vrednost za poslovnu meru.</span><span class="sxs-lookup"><span data-stu-id="84483-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="84483-112">Okidač je ograničen na prekoračenje granične vrednosti.</span><span class="sxs-lookup"><span data-stu-id="84483-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="84483-113">Aktivira se kada se završi potpuno osvežavanje (izvora podataka, segmenata, mera...).</span><span class="sxs-lookup"><span data-stu-id="84483-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="84483-114">Pokrenite kada se završi osvežavanje procesa objedinjavanja (mapiranje, podudaranje, spajanje).</span><span class="sxs-lookup"><span data-stu-id="84483-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="84483-115">[Konfigurisanje okidača u usluzi Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="84483-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="84483-116">Power Automate radnje</span><span class="sxs-lookup"><span data-stu-id="84483-116">Power Automate actions</span></span>
<span data-ttu-id="84483-117">Power Automate konektor pruža druge radnje osim dostupnih okidača.</span><span class="sxs-lookup"><span data-stu-id="84483-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="84483-118">Za više informacija pogledajte [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="84483-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="84483-119">Kreirajte Power Automate tok u uvidima o korisnicima</span><span class="sxs-lookup"><span data-stu-id="84483-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="84483-120">U uvidima o korisnicima idite na **Administrator** > **Sistem**.</span><span class="sxs-lookup"><span data-stu-id="84483-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="84483-121">Na stranici **Sistem** izaberite karticu **Status**.</span><span class="sxs-lookup"><span data-stu-id="84483-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="84483-122">U odeljku **Izvori podataka** izaberite **Tokovi** i izaberite **Kreiranje toka** iz padajuće liste.</span><span class="sxs-lookup"><span data-stu-id="84483-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="84483-123">![Power Automate konektor koji prikazuje radnju „Kreiraj tok“](media/power-automate-connector-create-flow.png "Power Automate konektor koji prikazuje radnju „Kreiraj tok“")</span><span class="sxs-lookup"><span data-stu-id="84483-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="84483-124">U usluzi Power Automate, izaberite jedan od dostupnih okidača da biste kreirali željeni tok.</span><span class="sxs-lookup"><span data-stu-id="84483-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="84483-125">Ako kreirate prvi tok, prvo ćete morati da potvrdite identitet pomoću Power Automate konektora.</span><span class="sxs-lookup"><span data-stu-id="84483-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
