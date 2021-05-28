---
title: Obogaćivanje profila klijenata podacima kompanije Microsoft
description: Koristite zaštićene podatke kompanije Microsoft da biste obogatili podatke o klijentima afinitetima prema brendu i interesovanjima.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: be042dd139607849b795c903fa58da2edb9ff589
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064908"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="cca25-103">Obogatite profile klijenata afinitetima brenda i interesovanja (pregled)</span><span class="sxs-lookup"><span data-stu-id="cca25-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="cca25-104">Koristite zaštićene podatke kompanije Microsoft da biste obogatili podatke o klijentima afinitetima prema brendu i interesovanjima.</span><span class="sxs-lookup"><span data-stu-id="cca25-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="cca25-105">Ovi afiniteti se određuju na osnovu podataka ljudi sa sličnom demografijom kao i vaši klijenti.</span><span class="sxs-lookup"><span data-stu-id="cca25-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="cca25-106">Ove informacije vam pomažu da bolje razumete i segmentirate svoje klijente na osnovu njihovih afiniteta prema određenim brendovima i interesovanjima.</span><span class="sxs-lookup"><span data-stu-id="cca25-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="cca25-107">U uvidima o korisnicima, idite na **Podaci** > **Obogaćivanje** da biste [konfigurisali i pregledali obogaćivanja](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="cca25-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="cca25-108">Da biste konfigurisali obogaćivanje afiniteta za brendove, idite na karticu **Otkrijte** i izaberite **Obogati moje podatke** na pločici **Brendovi**.</span><span class="sxs-lookup"><span data-stu-id="cca25-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="cca25-109">Da biste konfigurisali obogaćivanje afiniteta interesovanja, idite na karticu **Otkrijte** i izaberite **Obogati moje podatke** na pločici **Interesovanja**.</span><span class="sxs-lookup"><span data-stu-id="cca25-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cca25-110">![Pločice Brendovi i interesovanja](media/BrandsInterest-tile-Hub.png "Pločice Brendovi i interesovanja")</span><span class="sxs-lookup"><span data-stu-id="cca25-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="cca25-111">Kako utvrđujemo afinitete</span><span class="sxs-lookup"><span data-stu-id="cca25-111">How we determine affinities</span></span>

<span data-ttu-id="cca25-112">Koristimo podatke za pretragu na mreži kompanije Microsoft za pronalaženje afiniteta prema brendovima i interesovanjima u različitim demografskim segmentima (definisani uzrastom, polom ili lokacijom).</span><span class="sxs-lookup"><span data-stu-id="cca25-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="cca25-113">Obim pretraživanja brendova ili interesovanja na mreži određuje koliki afinitet demografski segment ima prema tom brendu ili interesovanju, u poređenju s drugim segmentima.</span><span class="sxs-lookup"><span data-stu-id="cca25-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="cca25-114">Nivo afiniteta i rezultat</span><span class="sxs-lookup"><span data-stu-id="cca25-114">Affinity level and score</span></span>

<span data-ttu-id="cca25-115">Na svakom obogaćenom profilu klijenta pružamo dve povezane vrednosti – nivo afiniteta i ocenu afiniteta.</span><span class="sxs-lookup"><span data-stu-id="cca25-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="cca25-116">Ove vrednosti vam pomažu da utvrdite koliko je jak afinitet prema demografskom segmentu tog profila, prema brendu ili interesovanju u poređenju sa drugim demografskim segmentima.</span><span class="sxs-lookup"><span data-stu-id="cca25-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="cca25-117">*Nivo afiniteta* sastoji se od četiri nivoa, a *ocena afiniteta* se izračunava na skali od 100 poena koja se preslikava na nivo afiniteta.</span><span class="sxs-lookup"><span data-stu-id="cca25-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="cca25-118">Nivo afiniteta</span><span class="sxs-lookup"><span data-stu-id="cca25-118">Affinity level</span></span> |<span data-ttu-id="cca25-119">Ocena afiniteta</span><span class="sxs-lookup"><span data-stu-id="cca25-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="cca25-120">Veoma visoko</span><span class="sxs-lookup"><span data-stu-id="cca25-120">Very high</span></span>     | <span data-ttu-id="cca25-121">85-100</span><span class="sxs-lookup"><span data-stu-id="cca25-121">85-100</span></span>       |
|<span data-ttu-id="cca25-122">Visok</span><span class="sxs-lookup"><span data-stu-id="cca25-122">High</span></span>     | <span data-ttu-id="cca25-123">70-84</span><span class="sxs-lookup"><span data-stu-id="cca25-123">70-84</span></span>        |
|<span data-ttu-id="cca25-124">Srednje</span><span class="sxs-lookup"><span data-stu-id="cca25-124">Medium</span></span>     | <span data-ttu-id="cca25-125">35-69</span><span class="sxs-lookup"><span data-stu-id="cca25-125">35-69</span></span>        |
|<span data-ttu-id="cca25-126">Nizak</span><span class="sxs-lookup"><span data-stu-id="cca25-126">Low</span></span>     | <span data-ttu-id="cca25-127">1-34</span><span class="sxs-lookup"><span data-stu-id="cca25-127">1-34</span></span>        |

<span data-ttu-id="cca25-128">U zavisnosti od granularnosti kojom želite da merite afinitet, možete da koristite nivo afiniteta ili rezultat.</span><span class="sxs-lookup"><span data-stu-id="cca25-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="cca25-129">Ocena afiniteta vam daje precizniju kontrolu.</span><span class="sxs-lookup"><span data-stu-id="cca25-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="cca25-130">Podržane zemlje/regioni</span><span class="sxs-lookup"><span data-stu-id="cca25-130">Supported countries/regions</span></span>

<span data-ttu-id="cca25-131">Trenutno podržavamo sledeće opcije zemlje/regiona: Australija, Kanada (engleski), Francuska, Nemačka, Ujedinjeno Kraljevstvo ili Sjedinjene Države (engleski).</span><span class="sxs-lookup"><span data-stu-id="cca25-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="cca25-132">Da biste izabrali zemlju, otvorite **Obogaćivanje brendova** ili **Obogaćivanje kamata** i izaberite **Promeni** pored stavke **Država/region**.</span><span class="sxs-lookup"><span data-stu-id="cca25-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="cca25-133">U oknu **Podešavanja zemlje/regiona** odaberite opciju i izaberite **Primeni**.</span><span class="sxs-lookup"><span data-stu-id="cca25-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="cca25-134">Posledice koje se odnose na izbor zemlje</span><span class="sxs-lookup"><span data-stu-id="cca25-134">Implications related to country selection</span></span>

- <span data-ttu-id="cca25-135">Kada [birate sopstvene brendove](#define-your-brands-or-interests), sistem pruža predloge na osnovu izabrane zemlje ili regiona.</span><span class="sxs-lookup"><span data-stu-id="cca25-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="cca25-136">Kada [birate delatnost](#define-your-brands-or-interests), dobićete najrelevantnije brendove ili interesovanja na osnovu izabrane zemlje ili regiona.</span><span class="sxs-lookup"><span data-stu-id="cca25-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="cca25-137">Kada [obogaćujemo profile](#refresh-enrichment), obogatićemo sve profile klijente za koje dobijamo podatke za izabrane brendove i interesovanja.</span><span class="sxs-lookup"><span data-stu-id="cca25-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="cca25-138">To uključuje profile koji nisu u izabranoj zemlji ili regionu.</span><span class="sxs-lookup"><span data-stu-id="cca25-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="cca25-139">Na primer, ako ste izabrali Nemačku, obogatićemo profile koji se nalaze u Sjedinjenim Državama ako imamo podatke o izabranim brendovima i interesovanjima u SAD.</span><span class="sxs-lookup"><span data-stu-id="cca25-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="cca25-140">Konfigurisanje obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="cca25-140">Configure Enrichment</span></span>

<span data-ttu-id="cca25-141">Vođeno iskustvo vam pomaže u konfiguraciji obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="cca25-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="cca25-142">Definisanje brendova ili interesovanja</span><span class="sxs-lookup"><span data-stu-id="cca25-142">Define your brands or interests</span></span>

<span data-ttu-id="cca25-143">Izaberite neku od sledećih opcija:</span><span class="sxs-lookup"><span data-stu-id="cca25-143">Select one of the following options:</span></span>

- <span data-ttu-id="cca25-144">**Delatnost**: Sistem identifikuje najbolje brendove ili interesovanja koja su relevantna za vašu delatnost i obogaćuje vaše podatke o klijentima.</span><span class="sxs-lookup"><span data-stu-id="cca25-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="cca25-145">**Odaberite sopstveno**: Izaberite do pet stavki sa liste brendova ili interesovanja koja su najrelevantnija za vašu organizaciju.</span><span class="sxs-lookup"><span data-stu-id="cca25-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="cca25-146">Da biste dodali brend ili interesovanje, unesite ga u polje za unos da biste dobili predloge na osnovu termina koji se podudaraju.</span><span class="sxs-lookup"><span data-stu-id="cca25-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="cca25-147">Ako ne navedemo brend ili interesovanje koje tražite, pošaljite nam povratne informacije koristeći vezu **Predloži**.</span><span class="sxs-lookup"><span data-stu-id="cca25-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="cca25-148">Pregled željenih podešavanja za obogaćivanje</span><span class="sxs-lookup"><span data-stu-id="cca25-148">Review enrichment preferences</span></span>

<span data-ttu-id="cca25-149">Pregledajte podrazumevane postavke obogaćivanja i ažurirajte ih po potrebi.</span><span class="sxs-lookup"><span data-stu-id="cca25-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Snimak ekrana prozora za željena podešavanja obogaćivanja.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="cca25-151">Izaberite entitet koji želite da obogatite</span><span class="sxs-lookup"><span data-stu-id="cca25-151">Select entity to enrich</span></span>

<span data-ttu-id="cca25-152">Izaberite **Obogaćeni entitet** i odaberite skup podataka koji želite da obogatite podacima preduzeća iz kompanije Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cca25-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="cca25-153">Možete izabrati entitet Klijent da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="cca25-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="cca25-154">Mapiranje polja</span><span class="sxs-lookup"><span data-stu-id="cca25-154">Map your fields</span></span>

<span data-ttu-id="cca25-155">Mapirajte polja iz vašeg objedinjenog entiteta klijenta da biste definisali demografski segment koji želite da sistem koristi za obogaćivanje podataka o klijentima.</span><span class="sxs-lookup"><span data-stu-id="cca25-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="cca25-156">Mapirajte zemlju/region i barem atribute „Datum rođenja“ ili „Pol“.</span><span class="sxs-lookup"><span data-stu-id="cca25-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="cca25-157">Pored toga, morate da mapirate najmanje jedan grad (i državu/pokrajinu) ili poštanski broj.</span><span class="sxs-lookup"><span data-stu-id="cca25-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="cca25-158">Izaberite **Uredi** da biste definisali mapiranje polja i izaberite **Primeni** kada završite.</span><span class="sxs-lookup"><span data-stu-id="cca25-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="cca25-159">Izaberite **Sačuvaj** da biste dovršili mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="cca25-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="cca25-160">Sledeći formati i vrednosti su podržani, vrednosti ne razlikuju velika i mala slova:</span><span class="sxs-lookup"><span data-stu-id="cca25-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="cca25-161">**Datum rođenja**: Preporučujemo da se datum rođenja konvertuje u tip DateTime tokom unosa podataka.</span><span class="sxs-lookup"><span data-stu-id="cca25-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="cca25-162">Alternativno, to može biti niz u [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formatu „yyyy-MM-dd“ ili „yyyy-MM-ddTHH:mm:ssZ“.</span><span class="sxs-lookup"><span data-stu-id="cca25-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="cca25-163">**Pol**: Muško, Žensko, Nepoznato</span><span class="sxs-lookup"><span data-stu-id="cca25-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="cca25-164">**Poštanski broj**: Petocifreni poštanski brojevi za SAD, standardni poštanski broj na svim drugim mestima</span><span class="sxs-lookup"><span data-stu-id="cca25-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="cca25-165">**Grad**: Naziv grada na engleskom jeziku</span><span class="sxs-lookup"><span data-stu-id="cca25-165">**City**: City name in English</span></span>
- <span data-ttu-id="cca25-166">**Država/pokrajina**: Skraćenica sa dva slova za SAD i Kanadu.</span><span class="sxs-lookup"><span data-stu-id="cca25-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="cca25-167">Skraćenica od dva ili tri slova za Australiju.</span><span class="sxs-lookup"><span data-stu-id="cca25-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="cca25-168">Nije primenjivo za Francusku, Nemačku ili Ujedinjeno Kraljevstvo.</span><span class="sxs-lookup"><span data-stu-id="cca25-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="cca25-169">**Zemlja/region**:</span><span class="sxs-lookup"><span data-stu-id="cca25-169">**Country/Region**:</span></span>

  - <span data-ttu-id="cca25-170">SAD: Sjedinjene Američke Države, Sjedinjene Države, SAD, USA, Amerika</span><span class="sxs-lookup"><span data-stu-id="cca25-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="cca25-171">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="cca25-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="cca25-172">GB: Ujedinjeno Kraljevstvo, UK, Velika Britanija, GB, Ujedinjeno Kraljevstvo Velike Britanije i Severne Irske, Ujedinjeno Kraljevstvo Velike Britanije</span><span class="sxs-lookup"><span data-stu-id="cca25-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="cca25-173">AU: Australija, AU, Komonvelt Australije</span><span class="sxs-lookup"><span data-stu-id="cca25-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="cca25-174">FR: Francuska, FR, Francuska Republika</span><span class="sxs-lookup"><span data-stu-id="cca25-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="cca25-175">DE: Nemačka, Germany, Deutschland, Allemagne, DE, Savezna Republika Nemačka, Republika Nemačka</span><span class="sxs-lookup"><span data-stu-id="cca25-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="cca25-176">Pregled i davanje naziva obogaćenju</span><span class="sxs-lookup"><span data-stu-id="cca25-176">Review and name the enrichment</span></span>

<span data-ttu-id="cca25-177">Na kraju, treba da pregledate informacije i navedete ime za obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="cca25-177">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stranica za pregled i imenovanje interesa.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="cca25-179">Osvežite obogaćivanje</span><span class="sxs-lookup"><span data-stu-id="cca25-179">Refresh enrichment</span></span>

<span data-ttu-id="cca25-180">Pokrenite obogaćivanje nakon konfigurisanja brendova, interesovanja i mapiranja polja za demografske kategorije.</span><span class="sxs-lookup"><span data-stu-id="cca25-180">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="cca25-181">Da biste pokrenuli postupak, izaberite **Pokreni** na stranici za konfigurisanje brendova ili interesovanja.</span><span class="sxs-lookup"><span data-stu-id="cca25-181">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="cca25-182">Pored toga, možete pustiti sistem da automatski pokrene obogaćivanje kao deo zakazanog osvežavanja.</span><span class="sxs-lookup"><span data-stu-id="cca25-182">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="cca25-183">U zavisnosti od veličine podataka o klijentima, može proći nekoliko minuta da se oplemenjivanje završi.</span><span class="sxs-lookup"><span data-stu-id="cca25-183">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="cca25-184">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="cca25-184">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="cca25-185">Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="cca25-185">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="cca25-186">Možete izabrati status procesa da biste videli detalje o toku celog posla.</span><span class="sxs-lookup"><span data-stu-id="cca25-186">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="cca25-187">Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="cca25-187">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="cca25-188">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="cca25-188">Enrichment results</span></span>

<span data-ttu-id="cca25-189">Nakon pokretanja postupka obogaćivanja, idite na **Moja obogaćivanja** da biste pregledali ukupan broj obogaćenih klijenata i raspodelu brendova ili interesovanja u obogaćenim profilima klijenata.</span><span class="sxs-lookup"><span data-stu-id="cca25-189">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Pregled rezultata nakon pokretanja procesa obogaćivanja":::

<span data-ttu-id="cca25-191">Pregledajte obogaćene podatke izborom opcije **Prikaz obogaćenih podataka** u grafikonu.</span><span class="sxs-lookup"><span data-stu-id="cca25-191">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="cca25-192">Obogaćeni podaci o brendovima idu u entitet **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="cca25-192">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="cca25-193">Podaci za interesovanja su u entitetu **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="cca25-193">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="cca25-194">Naći ćete i ove entitete navedene u grupi **Obogaćivanje** u odeljku **Podaci** > **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="cca25-194">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="cca25-195">Pogledajte podatke o obogaćivanju na kartici klijenta</span><span class="sxs-lookup"><span data-stu-id="cca25-195">See enrichment data on the customer card</span></span>

<span data-ttu-id="cca25-196">Afiniteti prema brendu i interesovanju mogu se takođe videti na karticama pojedinačnih klijenata.</span><span class="sxs-lookup"><span data-stu-id="cca25-196">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="cca25-197">Idite na **Klijenti** i izaberite profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="cca25-197">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="cca25-198">Na kartici klijenta ćete pronaći grafikone za brendove ili interesovanja za koje ljudi u demografskom profilu tog klijenta imaju afinitet.</span><span class="sxs-lookup"><span data-stu-id="cca25-198">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica klijenta sa obogaćenim podacima":::

## <a name="next-steps"></a><span data-ttu-id="cca25-200">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="cca25-200">Next steps</span></span>

<span data-ttu-id="cca25-201">Nadogradite na obogaćenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="cca25-201">Build on top of your enriched customer data.</span></span> <span data-ttu-id="cca25-202">Kreirajte [segmente](segments.md), [mere](measures.md), pa čak i [izvoz podataka](export-destinations.md) da biste pružili personalizovana iskustva svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="cca25-202">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
