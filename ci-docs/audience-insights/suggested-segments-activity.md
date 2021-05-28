---
title: Predloženi segmenti zasnovani na aktivnosti.
description: Neka vam mašinsko učenje pomogne da pronađete nove i zanimljive segmente na osnovu aktivnosti klijenata.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034109"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="e26fb-103">Predloženi segmenti zasnovani na podacima o aktivnosti (pregled)</span><span class="sxs-lookup"><span data-stu-id="e26fb-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="e26fb-104">Otkrijte zanimljive segmente svojih klijenata na osnovu podataka o aktivnostima klijenata koji se unose u Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e26fb-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="e26fb-105">Primeri podataka o aktivnostima su transakcije, trajanje poziva za podršku, kupovine ili povraćaji.</span><span class="sxs-lookup"><span data-stu-id="e26fb-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="e26fb-106">Da bi predložili segmente, podaci o aktivnostima se analiziraju na osnovu nedavnosti, učestalosti i novčane vrednosti (ili trajanja).</span><span class="sxs-lookup"><span data-stu-id="e26fb-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="e26fb-107">Možete i da generišete [predložene segmente za poboljšanje mere ili za bolje razumevanje uticaja na atribut](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="e26fb-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Kartica Predloženi segmenti prikazuje predloge segmenata za segmente zasnovane na aktivnostima i segmente zasnovane na atributima.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="e26fb-109">Kategorizacija klijenata prema aktivnostima</span><span class="sxs-lookup"><span data-stu-id="e26fb-109">Categorize customers by activity</span></span>

<span data-ttu-id="e26fb-110">Sa [podacima o aktivnostima](activities.md) dostupnim u usluzi Customer Insights, možemo da generišemo predloge koji predstavljaju grupe klijenata:</span><span class="sxs-lookup"><span data-stu-id="e26fb-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="e26fb-111">najaktivniji klijenti</span><span class="sxs-lookup"><span data-stu-id="e26fb-111">most active customers</span></span> 
- <span data-ttu-id="e26fb-112">klijenti koji su obavili najviše kupovina</span><span class="sxs-lookup"><span data-stu-id="e26fb-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="e26fb-113">klijenti koji su ostvarili najviše prihoda</span><span class="sxs-lookup"><span data-stu-id="e26fb-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="e26fb-114">klijenti koji u poslednje vreme nisu bili aktivni</span><span class="sxs-lookup"><span data-stu-id="e26fb-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="e26fb-115">klijenti koji često komuniciraju sa vašim preduzećem</span><span class="sxs-lookup"><span data-stu-id="e26fb-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="e26fb-116">Ako imate maloprodaju, mogli biste da saznate koji klijenti ostvaruju najviše prihoda i nagradite ih kuponom.</span><span class="sxs-lookup"><span data-stu-id="e26fb-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="e26fb-117">Ili možete da identifikujete povremene klijente i ponudite im da se pridruže programu nagrađivanja kako bi češće posećivali vaše preduzeće.</span><span class="sxs-lookup"><span data-stu-id="e26fb-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="e26fb-118">Ako se bavite zdravstvenom delatnošću koja pruža javnu zdravstvenu zaštitu i vaš cilj je da smanjite troškove za pojedinačne pacijente.</span><span class="sxs-lookup"><span data-stu-id="e26fb-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="e26fb-119">Moguć način za to bi bilo smanjenje ponovljenih poseta pružanjem najbolje moguće nege u što manje poseta.</span><span class="sxs-lookup"><span data-stu-id="e26fb-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="e26fb-120">U ovom slučaju, vaš cilj je da učestalost poseta bude niska i da minimizujete ponovljene troškove za pacijente.</span><span class="sxs-lookup"><span data-stu-id="e26fb-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="e26fb-121">Ili možete identifikovati segmente pacijenata koji imaju česte preglede i visoke troškove koji se ponavljaju, pa analizirati ove slučajeve kako biste poboljšali lečenje pojedinca.</span><span class="sxs-lookup"><span data-stu-id="e26fb-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="e26fb-122">Obavezni podaci</span><span class="sxs-lookup"><span data-stu-id="e26fb-122">Required data</span></span>

<span data-ttu-id="e26fb-123">Predlozi se generišu na osnovu izabranih ulaznih podataka.</span><span class="sxs-lookup"><span data-stu-id="e26fb-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="e26fb-124">Korisnički profili: Svi klijenti ili članovi određenog segmenta.</span><span class="sxs-lookup"><span data-stu-id="e26fb-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="e26fb-125">Vremenski period: Prošli mesec, prošla godina ili bilo koji prilagođeni vremenski okvir.</span><span class="sxs-lookup"><span data-stu-id="e26fb-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="e26fb-126">Tip aktivnosti: kupovine, maloprodajne transakcije, transakcije na mreži, slučajevi korisničke podrške, pretplate itd.</span><span class="sxs-lookup"><span data-stu-id="e26fb-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="e26fb-127">Entitet u usluzi Customer Insights koji sadrži podatke o aktivnosti: entitet ujednačene aktivnosti ili entitet za određenu aktivnost.</span><span class="sxs-lookup"><span data-stu-id="e26fb-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="e26fb-128">Dimenzije koje treba da obuhvate: Nedavna aktivnost, učestalost ili novčana dimenzija, u zavisnosti od vaših poslovnih zahteva.</span><span class="sxs-lookup"><span data-stu-id="e26fb-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="e26fb-129">Generišite predložene segmente</span><span class="sxs-lookup"><span data-stu-id="e26fb-129">Generate suggested segments</span></span>

1. <span data-ttu-id="e26fb-130">Idite na **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="e26fb-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="e26fb-131">Izaberite karticu **Predlozi (pregled)**.</span><span class="sxs-lookup"><span data-stu-id="e26fb-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="e26fb-132">Izaberite **Pronađite nove predloge** i odaberite **Pogledajte ili predvidite ponašanje klijenata**.</span><span class="sxs-lookup"><span data-stu-id="e26fb-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="e26fb-133">Izaberite **Početak** za pokretanje vođenog iskustva.</span><span class="sxs-lookup"><span data-stu-id="e26fb-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Prvi korak čarobnjaka za konfiguraciju za predloženi segment na osnovu aktivnosti.":::

1. <span data-ttu-id="e26fb-135">Navedite potrebne ulazne podatke i izaberite **Sledeće** i nastavite.</span><span class="sxs-lookup"><span data-stu-id="e26fb-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="e26fb-136">Odaberite klijente: Uključite sve klijente ili određeni segment.</span><span class="sxs-lookup"><span data-stu-id="e26fb-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="e26fb-137">Odaberite aktivnost: Izaberite vrstu aktivnosti i entitete koji opisuju aktivnost.</span><span class="sxs-lookup"><span data-stu-id="e26fb-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="e26fb-138">Željene postavke: Postavite vremenski period koji treba uzeti u obzir, faktore za predloge i mapirajte atribute.</span><span class="sxs-lookup"><span data-stu-id="e26fb-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="e26fb-139">Pregledajte svoj unos i izaberite **Pokreni** da biste pokrenuli model i generisali predloge.</span><span class="sxs-lookup"><span data-stu-id="e26fb-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="e26fb-140">U zavisnosti od broja korisničkih profila i izabranih aktivnosti, može potrajati nekoliko minuta.</span><span class="sxs-lookup"><span data-stu-id="e26fb-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="e26fb-141">Nakon generisanja predloga, možete ih filtrirati prema dimenziji ili vrednosti koja vas najviše zanima.</span><span class="sxs-lookup"><span data-stu-id="e26fb-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="e26fb-142">Prikaz detalja predloženog segmenta</span><span class="sxs-lookup"><span data-stu-id="e26fb-142">View details of a suggested segment</span></span>

<span data-ttu-id="e26fb-143">Kada se predlozi generišu, naći ćete ih na spisku **Segmenti** > **Predlozi (pregled)** u odeljku **Predlozi zasnovani na aktivnostima**.</span><span class="sxs-lookup"><span data-stu-id="e26fb-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Prošireno bočno okno koje prikazuje detaljne podatke o predloženom segmentu.":::

<span data-ttu-id="e26fb-145">Izaberite **Pogledajte predlog** na predloženom segmentu da biste videli detalje o tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="e26fb-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="e26fb-146">Bočno okno pruža detalje poput obima svake dimenzije u poređenju sa ciljnom grupom.</span><span class="sxs-lookup"><span data-stu-id="e26fb-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="e26fb-147">Takođe naglašava broj potencijalnih članova u segmentu i odgovarajući procenat od ukupnog broja klijenata.</span><span class="sxs-lookup"><span data-stu-id="e26fb-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="e26fb-148">Ako želite da predlog zadržite kao segment, izaberite **Napravi segment**.</span><span class="sxs-lookup"><span data-stu-id="e26fb-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="e26fb-149">Čuvanje predloga kao segmenta</span><span class="sxs-lookup"><span data-stu-id="e26fb-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="e26fb-150">Idite na **Segmenti** > **Predlozi (pregled)**.</span><span class="sxs-lookup"><span data-stu-id="e26fb-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="e26fb-151">Izaberite segment koji želite da sačuvate.</span><span class="sxs-lookup"><span data-stu-id="e26fb-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="e26fb-152">U bočnom oknu, izaberite **Napravi segment**.</span><span class="sxs-lookup"><span data-stu-id="e26fb-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="e26fb-153">Kada sačuvate segment, prikazaće se na listi segmenata na kartici **Svi segmenti**. Sad može biti [osvežen ili izbrisan kao i bilo koji drugi segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="e26fb-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="e26fb-154">Ne možete da uređujete detalje segmenta.</span><span class="sxs-lookup"><span data-stu-id="e26fb-154">You can't edit the segment details.</span></span> <span data-ttu-id="e26fb-155">Međutim, možete promeniti kriterijume unosa za predloge i generisati različite predloge.</span><span class="sxs-lookup"><span data-stu-id="e26fb-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="e26fb-156">Osvežite ili izmenite skup predloga</span><span class="sxs-lookup"><span data-stu-id="e26fb-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="e26fb-157">Idite na **Segmenti** > **Predlozi (pregled)** i potražite segment u odeljku **Predlozi zasnovani na aktivnostima**.</span><span class="sxs-lookup"><span data-stu-id="e26fb-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="e26fb-158">Izaberite **Osveži predloge** da biste osvežili predloge uz zadržavanje konfigurisanih atributa.</span><span class="sxs-lookup"><span data-stu-id="e26fb-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="e26fb-159">Ili izaberite **Izmeni predloge** da biste izmenili konfigurisane atribute.</span><span class="sxs-lookup"><span data-stu-id="e26fb-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="e26fb-160">Sistem će ponovo pokrenuti postupak, generisati predloge za segmente na osnovu najnovijih podataka i zameniti trenutne predloge.</span><span class="sxs-lookup"><span data-stu-id="e26fb-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
