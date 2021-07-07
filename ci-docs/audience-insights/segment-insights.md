---
title: Uvid u segmente za postojeće segmente
description: Steknite uvid u postojeće segmente da biste videli razlike i zajedničke karakteristike.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2856888d6ac64d5daabcc5a234f13bc6f88bb3df
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306091"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="e59fc-103">Uvidi u segmente (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="e59fc-103">Segment insights (preview)</span></span>

<span data-ttu-id="e59fc-104">Otkrijte dodatne informacije i uvide o vašim postojećim segmentima.</span><span class="sxs-lookup"><span data-stu-id="e59fc-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="e59fc-105">Otkrijte šta razlikuje dva segmenta ili šta imaju zajedničko.</span><span class="sxs-lookup"><span data-stu-id="e59fc-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="e59fc-106">Preklapanje segmenata</span><span class="sxs-lookup"><span data-stu-id="e59fc-106">Segment overlap</span></span>

<span data-ttu-id="e59fc-107">Analiza preklapanja segmenata pokazuje koliko i koji su klijenti zajednički za dva ili više segmenata.</span><span class="sxs-lookup"><span data-stu-id="e59fc-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="e59fc-108">Na primer, kako se segment čestih klijenata preklapa sa segmentom koji sadrži klijente koji su zadovoljni uslugom ili proizvodom.</span><span class="sxs-lookup"><span data-stu-id="e59fc-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="e59fc-109">Takođe možete da analizirate kako se preklapanje menja za određene atribute.</span><span class="sxs-lookup"><span data-stu-id="e59fc-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="e59fc-110">Pokrenite analizu preklapanja</span><span class="sxs-lookup"><span data-stu-id="e59fc-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="e59fc-111">Idite na **Segmenti**, a zatim izaberite karticu **Uvidi (verzija za pregled)**.</span><span class="sxs-lookup"><span data-stu-id="e59fc-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="e59fc-112">Izaberite **Novo**, a zatim odaberite opciju **Preklapanje** u oknu **Izaberite tip uvida**.</span><span class="sxs-lookup"><span data-stu-id="e59fc-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="e59fc-113">Odaberite segmente koji vas zanimaju i izaberite **Sledeći**.</span><span class="sxs-lookup"><span data-stu-id="e59fc-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="e59fc-114">Opcionalno, odaberite jedno ili više polja od interesa da biste analizirali preklapanja za svaku moguću vrednost polja, a zatim izaberite **Sledeći**.</span><span class="sxs-lookup"><span data-stu-id="e59fc-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="e59fc-115">Navedite ime za analizu preklapanja, izborni ime za prikaz i opis.</span><span class="sxs-lookup"><span data-stu-id="e59fc-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="e59fc-116">Izaberite **Sačuvaj** za početak analize.</span><span class="sxs-lookup"><span data-stu-id="e59fc-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="e59fc-117">Analiza preklapanja je spremna kada se status promeni iz Osvežavanje u Uspešno.</span><span class="sxs-lookup"><span data-stu-id="e59fc-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="e59fc-118">Pregled i optimizacija analize preklapanja</span><span class="sxs-lookup"><span data-stu-id="e59fc-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="e59fc-119">Po završetku analize pronađite detalje o ovom uvidu u **Segmenti** > **Uvidi (verzija za pregled)**.</span><span class="sxs-lookup"><span data-stu-id="e59fc-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Detalji uvida u preklapanje segmenata":::

<span data-ttu-id="e59fc-121">Izaberite uvid da biste videli rezultate analize:</span><span class="sxs-lookup"><span data-stu-id="e59fc-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="e59fc-122">Broj članova koji se preklapaju sa segmentima odabranim za analizu.</span><span class="sxs-lookup"><span data-stu-id="e59fc-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="e59fc-123">Broj članova koji su uključeni u jedan od segmenata, ali ne i u ostalim segmentima.</span><span class="sxs-lookup"><span data-stu-id="e59fc-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="e59fc-124">Ako ste tokom konfigurisanja analize preklapanja izabrali polja, naći ćete ih u odgovarajućim karticama.</span><span class="sxs-lookup"><span data-stu-id="e59fc-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="e59fc-125">Pomoću padajućeg menija filtera možete odabrati bilo koji nivo atributa koji vas zanima, a tabela na dnu će prikazati odgovarajuće podatke.</span><span class="sxs-lookup"><span data-stu-id="e59fc-125">You can use the filter dropdown to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="e59fc-126">Diferencijatori segmenta</span><span class="sxs-lookup"><span data-stu-id="e59fc-126">Segment differentiators</span></span>

<span data-ttu-id="e59fc-127">Razlike između segmenata vam pomažu da otkrijete šta razlikuje segment od ostalih klijenata ili nekog drugog segmenta.</span><span class="sxs-lookup"><span data-stu-id="e59fc-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="e59fc-128">Morate samo izabrati segment i sistem će prepoznati atribute profila i mere koje razlikuju izabrani segment.</span><span class="sxs-lookup"><span data-stu-id="e59fc-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="e59fc-129">Pokrenite analizu razlika</span><span class="sxs-lookup"><span data-stu-id="e59fc-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="e59fc-130">Idite na **Segmenti**, a zatim izaberite karticu **Uvidi (verzija za pregled)**.</span><span class="sxs-lookup"><span data-stu-id="e59fc-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="e59fc-131">Izaberite **Novo**, a zatim odaberite opciju **Preklapanje** u oknu **Izaberite tip uvida**.</span><span class="sxs-lookup"><span data-stu-id="e59fc-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="e59fc-132">Odaberite segment koji želite da analizirate kao **Primarni segment**, a zatim izaberite **Sledeći**.</span><span class="sxs-lookup"><span data-stu-id="e59fc-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="e59fc-133">Odaberite **Svi kupci** ili **Sekundarni segment** sa kojim biste uporedili svoj primarni segment, a zatim izaberite **Sledeći**.</span><span class="sxs-lookup"><span data-stu-id="e59fc-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="e59fc-134">Opcionalno, odaberite jedno ili više polja od interesa da biste analizu fokusirali na određene atribute, a zatim izaberite **Sledeći**.</span><span class="sxs-lookup"><span data-stu-id="e59fc-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="e59fc-135">Navedite ime za analizu preklapanja, izborni ime za prikaz i opis.</span><span class="sxs-lookup"><span data-stu-id="e59fc-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="e59fc-136">Izaberite **Sačuvaj** za početak analize.</span><span class="sxs-lookup"><span data-stu-id="e59fc-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="e59fc-137">Analiza preklapanja je spremna kada se status promeni iz Osvežavanje u Uspešno.</span><span class="sxs-lookup"><span data-stu-id="e59fc-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="e59fc-138">Pogledajte i optimizujte analizu razlika</span><span class="sxs-lookup"><span data-stu-id="e59fc-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="e59fc-139">Po završetku analize pronađite detalje o ovom uvidu u **Segmenti** > **Uvidi (verzija za pregled)**.</span><span class="sxs-lookup"><span data-stu-id="e59fc-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Detalji uvida u razlike između segmenata":::

<span data-ttu-id="e59fc-141">Izaberite uvid da biste videli rezultate analize.</span><span class="sxs-lookup"><span data-stu-id="e59fc-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="e59fc-142">Analiza razlika uključuje dve kartice.</span><span class="sxs-lookup"><span data-stu-id="e59fc-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="e59fc-143">Kartica **Atributi** navodi atribute profila koji se smatraju razlikama.</span><span class="sxs-lookup"><span data-stu-id="e59fc-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="e59fc-144">Kartica **Mere** navodi razlike.</span><span class="sxs-lookup"><span data-stu-id="e59fc-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="e59fc-145">Svaka kartica sadrži sledeće detalje:</span><span class="sxs-lookup"><span data-stu-id="e59fc-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="e59fc-146">Rangiranu listu razlika, sortiranu po razlici bodovanja.</span><span class="sxs-lookup"><span data-stu-id="e59fc-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="e59fc-147">**Bodovanje razlike** za svaku razliku.</span><span class="sxs-lookup"><span data-stu-id="e59fc-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="e59fc-148">Rezultat razlike predstavlja stepen razlikovanja atributa u dva segmenta.</span><span class="sxs-lookup"><span data-stu-id="e59fc-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="e59fc-149">Što je veće bodovanje razlike, to se atributi više razlikuju između dva segmenta.</span><span class="sxs-lookup"><span data-stu-id="e59fc-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="e59fc-150">Izaberite bodovanje da biste otvorili okno **Bodovanje razlike** sa raspodelom vrednosti za taj atribut.</span><span class="sxs-lookup"><span data-stu-id="e59fc-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="e59fc-151">Upravljanje uvidima u segmente</span><span class="sxs-lookup"><span data-stu-id="e59fc-151">Manage segment insights</span></span>

<span data-ttu-id="e59fc-152">Možete da koristite sledeće opcije na uvidima iz komandne trake:</span><span class="sxs-lookup"><span data-stu-id="e59fc-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="e59fc-153">**Nazad** da biste vratili listu uvida</span><span class="sxs-lookup"><span data-stu-id="e59fc-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="e59fc-154">**Osveži** da biste ponovo pokrenuli analizu</span><span class="sxs-lookup"><span data-stu-id="e59fc-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="e59fc-155">**Izbriši** da biste uklonili ovaj uvid</span><span class="sxs-lookup"><span data-stu-id="e59fc-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]