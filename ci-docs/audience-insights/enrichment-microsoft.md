---
title: Obogaćivanje profila klijenata podacima kompanije Microsoft
description: Koristite zaštićene podatke kompanije Microsoft da biste obogatili podatke o klijentima afinitetima prema brendu i interesovanjima.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305173"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="fe7e1-103">Obogatite profile klijenata afinitetima brenda i interesovanja (pregled)</span><span class="sxs-lookup"><span data-stu-id="fe7e1-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="fe7e1-104">Koristite zaštićene podatke kompanije Microsoft da biste obogatili podatke o klijentima afinitetima prema brendu i interesovanjima.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="fe7e1-105">Ovi afiniteti su zasnovani na podacima od osoba sa sličnim demografskim kategorijama kao vaši klijenti.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="fe7e1-106">Ove informacije vam pomažu da bolje razumete i segmentirate svoje klijente na osnovu njihovih afiniteta prema određenim brendovima i interesovanjima.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="fe7e1-107">U uvidima o korisnicima, idite na **Podaci** > **Obogaćivanje** da biste [konfigurisali i pregledali obogaćivanja](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="fe7e1-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="fe7e1-108">Da biste konfigurisali obogaćivanje afiniteta za brendove, idite na karticu **Otkrijte** i izaberite **Obogati moje podatke** na pločici **Brendovi**.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="fe7e1-109">Da biste konfigurisali obogaćivanje afiniteta interesovanja, idite na karticu **Otkrijte** i izaberite **Obogati moje podatke** na pločici **Interesovanja**.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fe7e1-110">![Pločice Brendovi i Interesovanja](media/BrandsInterest-tile-Hub.png "Pločice Brendovi i Interesovanja")</span><span class="sxs-lookup"><span data-stu-id="fe7e1-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="fe7e1-111">Kako utvrđujemo afinitete</span><span class="sxs-lookup"><span data-stu-id="fe7e1-111">How we determine affinities</span></span>

<span data-ttu-id="fe7e1-112">Koristimo podatke za pretragu na mreži kompanije Microsoft za pronalaženje afiniteta prema brendovima i interesovanjima u različitim demografskim segmentima (definisani uzrastom, polom ili lokacijom).</span><span class="sxs-lookup"><span data-stu-id="fe7e1-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="fe7e1-113">Obim pretraživanja brendova ili interesovanja na mreži određuje koliki afinitet demografski segment ima prema tom brendu ili interesovanju, u poređenju s drugim segmentima.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="fe7e1-114">Nivo afiniteta i rezultat</span><span class="sxs-lookup"><span data-stu-id="fe7e1-114">Affinity level and score</span></span>

<span data-ttu-id="fe7e1-115">Na svakom obogaćenom korisničkom profilu pružamo dve povezane vrednosti: nivo afiniteta i ocenu afiniteta.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="fe7e1-116">Ove vrednosti vam pomažu da utvrdite koliko je jak afinitet prema demografskom segmentu tog profila, prema brendu ili interesovanju u poređenju sa drugim demografskim segmentima.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="fe7e1-117">*Nivo afiniteta* sastoji se od četiri nivoa, a *ocena afiniteta* se izračunava na skali od 100 poena koja se preslikava na nivo afiniteta.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="fe7e1-118">Nivo afiniteta</span><span class="sxs-lookup"><span data-stu-id="fe7e1-118">Affinity level</span></span> |<span data-ttu-id="fe7e1-119">Ocena afiniteta</span><span class="sxs-lookup"><span data-stu-id="fe7e1-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="fe7e1-120">Veoma visoko</span><span class="sxs-lookup"><span data-stu-id="fe7e1-120">Very high</span></span>     | <span data-ttu-id="fe7e1-121">85-100</span><span class="sxs-lookup"><span data-stu-id="fe7e1-121">85-100</span></span>       |
|<span data-ttu-id="fe7e1-122">Visok</span><span class="sxs-lookup"><span data-stu-id="fe7e1-122">High</span></span>     | <span data-ttu-id="fe7e1-123">70-84</span><span class="sxs-lookup"><span data-stu-id="fe7e1-123">70-84</span></span>        |
|<span data-ttu-id="fe7e1-124">Srednje</span><span class="sxs-lookup"><span data-stu-id="fe7e1-124">Medium</span></span>     | <span data-ttu-id="fe7e1-125">35-69</span><span class="sxs-lookup"><span data-stu-id="fe7e1-125">35-69</span></span>        |
|<span data-ttu-id="fe7e1-126">Nizak</span><span class="sxs-lookup"><span data-stu-id="fe7e1-126">Low</span></span>     | <span data-ttu-id="fe7e1-127">1-34</span><span class="sxs-lookup"><span data-stu-id="fe7e1-127">1-34</span></span>        |

<span data-ttu-id="fe7e1-128">U zavisnosti od granularnosti kojom želite da merite afinitet, možete da koristite nivo afiniteta ili rezultat.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="fe7e1-129">Ocena afiniteta vam daje precizniju kontrolu.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="fe7e1-130">Podržane zemlje/regioni</span><span class="sxs-lookup"><span data-stu-id="fe7e1-130">Supported countries/regions</span></span>

<span data-ttu-id="fe7e1-131">Trenutno podržavamo sledeće opcije zemlje/regiona: Australija, Kanada (engleski), Francuska, Nemačka, Ujedinjeno Kraljevstvo ili Sjedinjene Države (engleski).</span><span class="sxs-lookup"><span data-stu-id="fe7e1-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="fe7e1-132">Da biste izabrali zemlju ili region, otvorite **Obogaćivanje brendova** ili **Obogaćivanje interesovanja** i izaberite opciju **Promeni** pored **Država / region**.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="fe7e1-133">U oknu **Podešavanja zemlje/regiona** odaberite opciju i izaberite **Primeni**.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="fe7e1-134">Posledice koje se odnose na izbor zemlje</span><span class="sxs-lookup"><span data-stu-id="fe7e1-134">Implications related to country selection</span></span>

- <span data-ttu-id="fe7e1-135">Kada [birate sopstvene brendove](#define-your-brands-or-interests), sistem pruža predloge na osnovu izabrane zemlje ili regiona.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="fe7e1-136">Kada [birate delatnost](#define-your-brands-or-interests), dobićete najrelevantnije brendove ili interesovanja na osnovu izabrane zemlje ili regiona.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="fe7e1-137">Kada [obogaćujete profile](#refresh-enrichment), obogatićemo sve profile klijenata za koje dobijamo podatke za izabrane brendove i interesovanja, uključujući profile koji nisu u izabranoj zemlji ili regionu.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="fe7e1-138">Na primer, ako ste izabrali Nemačku, obogatićemo profile koji se nalaze u Sjedinjenim Državama ako imamo podatke o izabranim brendovima i interesovanjima u SAD.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="fe7e1-139">Konfigurisanje obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="fe7e1-139">Configure enrichment</span></span>

<span data-ttu-id="fe7e1-140">Vođeno iskustvo vam pomaže u konfiguraciji obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="fe7e1-141">Definisanje brendova ili interesovanja</span><span class="sxs-lookup"><span data-stu-id="fe7e1-141">Define your brands or interests</span></span>

<span data-ttu-id="fe7e1-142">Izaberite do pet brendova ili interesovanja pomoću jedne ili obe ove opcije:</span><span class="sxs-lookup"><span data-stu-id="fe7e1-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="fe7e1-143">**Delatnost**: Izaberite svoju delatnost sa padajuće liste, a zatim odaberite najbolje brendove ili interesovanja za tu delatnost.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="fe7e1-144">**Izaberite svoje**: Unesite brend ili interesovanje koji su relevantni za vašu organizaciju, a zatim odaberite među predlozima za podudaranje.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="fe7e1-145">Ako ne navedemo brend ili interesovanje koje tražite, pošaljite nam povratne informacije koristeći vezu **Predloži**.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="fe7e1-146">Pregled željenih podešavanja za obogaćivanje</span><span class="sxs-lookup"><span data-stu-id="fe7e1-146">Review enrichment preferences</span></span>

<span data-ttu-id="fe7e1-147">Pregledajte podrazumevane postavke obogaćivanja i ažurirajte ih po potrebi.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Snimak ekrana prozora za željena podešavanja obogaćivanja.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="fe7e1-149">Izaberite entitet koji želite da obogatite</span><span class="sxs-lookup"><span data-stu-id="fe7e1-149">Select entity to enrich</span></span>

<span data-ttu-id="fe7e1-150">Izaberite **Obogaćeni entitet** i odaberite skup podataka koji želite da obogatite podacima preduzeća iz kompanije Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="fe7e1-151">Možete izabrati entitet Klijent da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="fe7e1-152">Mapiranje polja</span><span class="sxs-lookup"><span data-stu-id="fe7e1-152">Map your fields</span></span>

<span data-ttu-id="fe7e1-153">Mapirajte polja iz vašeg objedinjenog entiteta klijenta da biste definisali demografski segment koji želite da sistem koristi za obogaćivanje podataka o klijentima.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="fe7e1-154">Mapirajte zemlju/region i barem atribute „Datum rođenja“ ili „Pol“.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="fe7e1-155">Pored toga, morate da mapirate najmanje jedan grad (i državu/pokrajinu) ili poštanski broj.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="fe7e1-156">Izaberite **Uredi** da biste definisali mapiranje polja i izaberite **Primeni** kada završite.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="fe7e1-157">Izaberite **Sačuvaj** da biste dovršili mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="fe7e1-158">Sledeći formati i vrednosti su podržani (vrednosti ne razlikuju velika i mala slova):</span><span class="sxs-lookup"><span data-stu-id="fe7e1-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="fe7e1-159">**Datum rođenja**: Preporučujemo da se datum rođenja konvertuje u tip DateTime tokom unosa podataka.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="fe7e1-160">Alternativno, to može biti niska u [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formatu "yyyy-MM-dd" ili "yyyy-MM-ddTHH:mm:ss".</span><span class="sxs-lookup"><span data-stu-id="fe7e1-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="fe7e1-161">**Pol**: Muški, Ženski, Nepoznat.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="fe7e1-162">**Poštanski broj**: Petocifreni poštanski brojevi za Sjedinjene Države, standardni poštanski broj svuda drugde.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="fe7e1-163">**Grad**: Naziv grada na engleskom jeziku.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-163">**City**: City name in English.</span></span>
- <span data-ttu-id="fe7e1-164">**Država/pokrajina**: Skraćenica sa dva slova za SAD i Kanadu.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="fe7e1-165">Skraćenica od dva ili tri slova za Australiju.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="fe7e1-166">Nije primenjivo za Francusku, Nemačku ili Ujedinjeno Kraljevstvo.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="fe7e1-167">**Zemlja/region**:</span><span class="sxs-lookup"><span data-stu-id="fe7e1-167">**Country/Region**:</span></span>

  - <span data-ttu-id="fe7e1-168">SAD: Sjedinjene Američke Države, Sjedinjene Države, SAD, USA, Amerika</span><span class="sxs-lookup"><span data-stu-id="fe7e1-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="fe7e1-169">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="fe7e1-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="fe7e1-170">GB: Ujedinjeno Kraljevstvo, UK, Velika Britanija, GB, Ujedinjeno Kraljevstvo Velike Britanije i Severne Irske, Ujedinjeno Kraljevstvo Velike Britanije</span><span class="sxs-lookup"><span data-stu-id="fe7e1-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="fe7e1-171">AU: Australija, AU, Komonvelt Australije</span><span class="sxs-lookup"><span data-stu-id="fe7e1-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="fe7e1-172">FR: Francuska, FR, Francuska Republika</span><span class="sxs-lookup"><span data-stu-id="fe7e1-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="fe7e1-173">DE: Nemačka, Germany, Deutschland, Allemagne, DE, Savezna Republika Nemačka, Republika Nemačka</span><span class="sxs-lookup"><span data-stu-id="fe7e1-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="fe7e1-174">Pregled i davanje naziva obogaćenju</span><span class="sxs-lookup"><span data-stu-id="fe7e1-174">Review and name the enrichment</span></span>

<span data-ttu-id="fe7e1-175">Na kraju, treba da pregledate informacije i navedete ime za obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stranica za pregled i imenovanje interesa.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="fe7e1-177">Osvežite obogaćivanje</span><span class="sxs-lookup"><span data-stu-id="fe7e1-177">Refresh enrichment</span></span>

<span data-ttu-id="fe7e1-178">Pokrenite obogaćivanje nakon konfigurisanja brendova, interesovanja i mapiranja polja za demografske kategorije.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="fe7e1-179">Da biste pokrenuli postupak, izaberite **Pokreni** na stranici za konfigurisanje brendova ili interesovanja.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="fe7e1-180">Pored toga, možete pustiti sistem da automatski pokrene obogaćivanje kao deo zakazanog osvežavanja.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="fe7e1-181">U zavisnosti od veličine podataka o klijentima, može proći nekoliko minuta da se oplemenjivanje završi.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="fe7e1-182">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="fe7e1-183">Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="fe7e1-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="fe7e1-184">Možete izabrati status procesa da biste videli detalje o toku celog posla.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="fe7e1-185">Nakon izbora **Vidi detalje** za jedan od zadataka posla, pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="fe7e1-186">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="fe7e1-186">Enrichment results</span></span>

<span data-ttu-id="fe7e1-187">Nakon pokretanja postupka obogaćivanja, idite na **Moja obogaćivanja** da biste pregledali ukupan broj obogaćenih klijenata i raspodelu brendova ili interesovanja u obogaćenim profilima klijenata.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Pregled rezultata nakon pokretanja procesa obogaćivanja":::

<span data-ttu-id="fe7e1-189">Pregledajte obogaćene podatke izborom opcije **Prikaz obogaćenih podataka** u grafikonu.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="fe7e1-190">Obogaćeni podaci o brendovima idu u entitet **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="fe7e1-191">Podaci za interesovanja su u entitetu **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="fe7e1-192">Naći ćete i ove entitete navedene u grupi **Obogaćivanje** u odeljku **Podaci** > **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="fe7e1-193">Pogledajte podatke o obogaćivanju na kartici klijenta</span><span class="sxs-lookup"><span data-stu-id="fe7e1-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="fe7e1-194">Afiniteti prema brendu i interesovanju mogu se takođe videti na karticama pojedinačnih klijenata.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="fe7e1-195">Idite na **Klijenti** i izaberite profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="fe7e1-196">Na kartici klijenta ćete pronaći grafikone za brendove ili interesovanja za koje ljudi u demografskom profilu tog klijenta imaju afinitet.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica klijenta sa obogaćenim podacima":::

## <a name="next-steps"></a><span data-ttu-id="fe7e1-198">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="fe7e1-198">Next steps</span></span>

<span data-ttu-id="fe7e1-199">Nadogradite na obogaćenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="fe7e1-200">Kreirajte [segmente](segments.md) i [mere](measures.md), pa čak i [izvoz podataka](export-destinations.md) da pružite personalizovana iskustva svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="fe7e1-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
