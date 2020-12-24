---
title: Power Apps konektor
description: Povežite se sa uslugama Power Apps i Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406778"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="b64f4-103">Microsoft Power Apps konektor (pregled)</span><span class="sxs-lookup"><span data-stu-id="b64f4-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="b64f4-104">Uvedite objedinjene korisničke profile u svoje personalizovane aplikacije pomoću programa Power Apps.</span><span class="sxs-lookup"><span data-stu-id="b64f4-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="b64f4-105">Povežite Power Apps i Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b64f4-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="b64f4-106">Customer Insights je jedan od mnogih [dostupnih izvora za podatke u programu Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="b64f4-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="b64f4-107">Pogledajte Power Apps dokumentaciju da biste saznali kako da [dodate prenos podataka u aplikaciju](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="b64f4-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="b64f4-108">Preporučujemo da takođe pregledate [kako Power Apps koristi delegiranje za obradu velikih skupova podataka u aplikacijama sa podlogom](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="b64f4-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="b64f4-109">Dostupni entiteti</span><span class="sxs-lookup"><span data-stu-id="b64f4-109">Available entities</span></span>

<span data-ttu-id="b64f4-110">Kada dodate uslugu Customer Insights kao vezu za prenos podataka, možete izabrati sledeće entitete u programu Power Apps:</span><span class="sxs-lookup"><span data-stu-id="b64f4-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="b64f4-111">Klijent: da koristite podatke iz [objedinjenog profila klijenta](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b64f4-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="b64f4-112">Aktivnost objedinjenog klijenta: da prikazujete [vremensku osu aktivnosti](activities.md) u aplikaciji.</span><span class="sxs-lookup"><span data-stu-id="b64f4-112">Unified Customer Activity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="b64f4-113">Ograničenja</span><span class="sxs-lookup"><span data-stu-id="b64f4-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="b64f4-114">Povratni entiteti</span><span class="sxs-lookup"><span data-stu-id="b64f4-114">Retrievable entities</span></span>

<span data-ttu-id="b64f4-115">Možete da povratite samo entitete **Klijent**, **Objedinjena aktivnost** i **Segmenti** kroz Power Apps konektor.</span><span class="sxs-lookup"><span data-stu-id="b64f4-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="b64f4-116">Drugi entiteti se prikazuju jer ih osnovni konektor podržava kroz okidače u usluzi Power Automate.</span><span class="sxs-lookup"><span data-stu-id="b64f4-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="b64f4-117">Delegiranje</span><span class="sxs-lookup"><span data-stu-id="b64f4-117">Delegation</span></span>

<span data-ttu-id="b64f4-118">Delegiranje radi za entitet Klijent i entitet Objedinjena aktivnost.</span><span class="sxs-lookup"><span data-stu-id="b64f4-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="b64f4-119">Delegiranje za entitet **Klijent**: Da biste koristili delegiranje za ovaj entitet, polja treba indeksirati u odeljku [Indeks pretrage i filtriranja](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="b64f4-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="b64f4-120">Delegiranje za entitet **Objedinjena aktivnost**: Delegiranje za ovaj entitet radi samo za polja **ActivityId** i **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="b64f4-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="b64f4-121">Za više informacija o delegiranju, pogledajte [Power Apps prenosive funkcije i operacije](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="b64f4-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="b64f4-122">Primer kontrole galerije</span><span class="sxs-lookup"><span data-stu-id="b64f4-122">Example gallery control</span></span>

<span data-ttu-id="b64f4-123">Na primer, dodajete profile klijenata u [kontrolu galerije](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="b64f4-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="b64f4-124">Dodajte kontrolu **Galerija** u aplikaciju koju gradite.</span><span class="sxs-lookup"><span data-stu-id="b64f4-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b64f4-125">![Dodajte element galerije](media/connector-powerapps9.png "Dodajte element galerije")</span><span class="sxs-lookup"><span data-stu-id="b64f4-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="b64f4-126">Izaberite **Klijent** kao izvor podataka za stavke.</span><span class="sxs-lookup"><span data-stu-id="b64f4-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b64f4-127">![Izaberite izvor podataka](media/choose-datasource-powerapps.png "Izaberite izvor podataka")</span><span class="sxs-lookup"><span data-stu-id="b64f4-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="b64f4-128">Možete da promenite tablu sa podacima na desnoj strani da biste izabrali polje koje će entitet Klijent prikazati u galeriji.</span><span class="sxs-lookup"><span data-stu-id="b64f4-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="b64f4-129">Ako želite da u galeriji prikažete bilo koje polje odabranog klijenta, popunite svojstvo Tekst oznake: **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="b64f4-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="b64f4-130">Primer: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="b64f4-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="b64f4-131">Da biste prikazali objedinjenu vremensku osu za klijenta, dodajte element Galerija i dodajte svojstvo Stavke: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="b64f4-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="b64f4-132">Primer: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="b64f4-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>