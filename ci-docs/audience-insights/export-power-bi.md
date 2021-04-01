---
title: Power BI konektor
description: Saznajte kako da koristite Dynamics 365 Customer Insights konektor u usluzi Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596056"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="a063f-103">Konektor za Power BI (pregled)</span><span class="sxs-lookup"><span data-stu-id="a063f-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="a063f-104">Napravite vizuelizacije za svoje podatke pomoću usluge Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="a063f-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="a063f-105">Generišite dodatne uvide i pravite izveštaje pomoću objedinjenih podataka o klijentima.</span><span class="sxs-lookup"><span data-stu-id="a063f-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a063f-106">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="a063f-106">Prerequisites</span></span>

- <span data-ttu-id="a063f-107">Imate objedinjene profile klijenata.</span><span class="sxs-lookup"><span data-stu-id="a063f-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="a063f-108">Najnovija verzija aplikacije [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je instalirana na vašem računaru.</span><span class="sxs-lookup"><span data-stu-id="a063f-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="a063f-109">[Saznajte više o Power BI Desktop](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="a063f-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="a063f-110">Konfigurišite konektor za Power BI</span><span class="sxs-lookup"><span data-stu-id="a063f-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="a063f-111">U programu Power BI Desktop, izaberite **Datoteka** > **Preuzmi podatke**.</span><span class="sxs-lookup"><span data-stu-id="a063f-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="a063f-112">Izaberite **Prikaži još** i potražite **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="a063f-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="a063f-113">Izaberite **Poveži se**.</span><span class="sxs-lookup"><span data-stu-id="a063f-113">Select **Connect**.</span></span>

1. <span data-ttu-id="a063f-114">**Prijavite se** sa istim organizacionim nalogom koji koristite za Customer Insights i izaberite **Poveži se**.</span><span class="sxs-lookup"><span data-stu-id="a063f-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="a063f-115">Poslovni kontakt koji navedete u ovom koraku koristi se za preuzimanje podataka iz usluge Customer Insights i ne mora biti isti sa kojim ste prijavljeni na Power BI.</span><span class="sxs-lookup"><span data-stu-id="a063f-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="a063f-116">Da biste resetovali nalog koji se koristi za preuzimanje podataka, otvorite Power BI i idite na **Datoteka** > **Opcije** > **Podešavanja** > **Podešavanja izvora podataka**.</span><span class="sxs-lookup"><span data-stu-id="a063f-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="a063f-117">Na listi izvora podataka izaberite **Prijava na Dynamics 365 Customer Insights** i izaberite **Obriši dozvole**.</span><span class="sxs-lookup"><span data-stu-id="a063f-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="a063f-118">U dijalogu **Navigator**.</span><span class="sxs-lookup"><span data-stu-id="a063f-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="a063f-119">vidite listu svih okruženja kojima imate pristup.</span><span class="sxs-lookup"><span data-stu-id="a063f-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="a063f-120">Proširite okruženje i otvorite bilo koju fasciklu (entiteti, mere, segmenti, obogaćivanja).</span><span class="sxs-lookup"><span data-stu-id="a063f-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="a063f-121">Na primer, otvorite fasciklu **Entiteti** da vidite sve entitete koje možete da uvezete.</span><span class="sxs-lookup"><span data-stu-id="a063f-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="a063f-122">![Navigator Power BI konektora](media/power-bi-navigator.png "Navigator Power BI konektora")</span><span class="sxs-lookup"><span data-stu-id="a063f-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="a063f-123">Označite polja za potvrdu pored entiteta koje treba da uključite i **Učitaj**.</span><span class="sxs-lookup"><span data-stu-id="a063f-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="a063f-124">Možete da izaberete više entiteta, čak i iz više okruženja.</span><span class="sxs-lookup"><span data-stu-id="a063f-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="a063f-125">Videćete dijalog za učitavanje dok se entiteti učitavaju.</span><span class="sxs-lookup"><span data-stu-id="a063f-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="a063f-126">Nakon što se učitaju svi izabrani entiteti, možete da koristite mogućnosti usluge Power BI za vizualizaciju podataka.</span><span class="sxs-lookup"><span data-stu-id="a063f-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="a063f-127">Veliki skupovi podataka</span><span class="sxs-lookup"><span data-stu-id="a063f-127">Large data sets</span></span>

<span data-ttu-id="a063f-128">Customer Insights konektor za Power BI je dizajniran da radi za skupove podataka koji sadrže do 1 milion korisničkih profila.</span><span class="sxs-lookup"><span data-stu-id="a063f-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="a063f-129">Uvoz većih skupova podataka može da funkcioniše, ali to traje dugo.</span><span class="sxs-lookup"><span data-stu-id="a063f-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="a063f-130">Pored toga, proces bi mogao naići na vremensko ograničenje zbog Power BI ograničenja.</span><span class="sxs-lookup"><span data-stu-id="a063f-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="a063f-131">Za više informacija, pogledajte [Power BI: Preporuke za velike skupove podataka](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="a063f-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="a063f-132">Rad sa podskupom podataka</span><span class="sxs-lookup"><span data-stu-id="a063f-132">Work with a subset of data</span></span>

<span data-ttu-id="a063f-133">Razmislite o radu sa podskupom podataka.</span><span class="sxs-lookup"><span data-stu-id="a063f-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="a063f-134">Na primer, možete da kreirate[ segmente](segments.md) umesto da izveze sve evidencije klijenata u Power BI.</span><span class="sxs-lookup"><span data-stu-id="a063f-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a063f-135">Rešavanje problema</span><span class="sxs-lookup"><span data-stu-id="a063f-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="a063f-136">Customer Insights okruženje se ne prikazuje u usluzi Power BI</span><span class="sxs-lookup"><span data-stu-id="a063f-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="a063f-137">Okruženja koja imaju više od jedne [relacije](relationships.md) definisane između dva identična entiteta u uvidima o korisnicima neće biti dostupna u Power BI konektoru.</span><span class="sxs-lookup"><span data-stu-id="a063f-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="a063f-138">Možete identifikovati i ukloniti duplikate relacija.</span><span class="sxs-lookup"><span data-stu-id="a063f-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="a063f-139">U uvidima o korisnicima, idite na **Podaci** > **Relacije** na okruženje koje vam nedostaje u usluzi Power BI.</span><span class="sxs-lookup"><span data-stu-id="a063f-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="a063f-140">Identifikujte duplikate relacija:</span><span class="sxs-lookup"><span data-stu-id="a063f-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="a063f-141">Proverite da li postoji više relacija definisanih između ista dva entiteta.</span><span class="sxs-lookup"><span data-stu-id="a063f-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="a063f-142">Proverite da li postoji relacija kreirana između dva entiteta koja su oba uključena u proces objedinjavanja.</span><span class="sxs-lookup"><span data-stu-id="a063f-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="a063f-143">Definisana je implicitna relacija između svih entiteta uključenih u proces ujedinjenja.</span><span class="sxs-lookup"><span data-stu-id="a063f-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="a063f-144">Uklonite sve prepoznate duplikate relacija.</span><span class="sxs-lookup"><span data-stu-id="a063f-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="a063f-145">Kada uklonite duplikate relacija, pokušajte da ponovo konfigurišete Power BI konektor.</span><span class="sxs-lookup"><span data-stu-id="a063f-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="a063f-146">Okruženje bi trebalo da bude dostupno već sada.</span><span class="sxs-lookup"><span data-stu-id="a063f-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]