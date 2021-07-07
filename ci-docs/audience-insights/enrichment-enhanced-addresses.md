---
title: Obogaćivanje poboljšavanja adrese
description: Obogatite i normalizujte informacije o adresama korisničkih profila pomoću Microsoft modela.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305449"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="2853c-103">Obogaćivanje korisničkih profila sa poboljšanim adresama</span><span class="sxs-lookup"><span data-stu-id="2853c-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="2853c-104">Adrese u vašim podacima mogu biti nestrukturirane, nepotpune ili netačne.</span><span class="sxs-lookup"><span data-stu-id="2853c-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="2853c-105">Koristite Microsoft modele za normalizaciju i obogaćivanje adresa u [formatu Common Data Model](/common-data-model/schema/core/applicationcommon/address) radi veće tačnosti i uvida.</span><span class="sxs-lookup"><span data-stu-id="2853c-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="2853c-106">Kako poboljšavamo adrese</span><span class="sxs-lookup"><span data-stu-id="2853c-106">How we enhance addresses</span></span>

<span data-ttu-id="2853c-107">Naš model prolazi kroz postupak u dva koraka za poboljšanje adrese.</span><span class="sxs-lookup"><span data-stu-id="2853c-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="2853c-108">Prvo raščlanjuje adresu da bi identifikovao njene komponente i stavlja ih u strukturirani format.</span><span class="sxs-lookup"><span data-stu-id="2853c-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="2853c-109">Zatim koristimo AI za ispravljanje, popunjavanje i standardizaciju vrednosti u adresi.</span><span class="sxs-lookup"><span data-stu-id="2853c-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="2853c-110">Primer</span><span class="sxs-lookup"><span data-stu-id="2853c-110">Example</span></span>

<span data-ttu-id="2853c-111">Informacije o adresi mogu biti u nestandardnom formatu i sadržati pravopisne greške.</span><span class="sxs-lookup"><span data-stu-id="2853c-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="2853c-112">Model može rešiti ove probleme i kreirati dosledne adrese u objedinjenim korisničkim profilima.</span><span class="sxs-lookup"><span data-stu-id="2853c-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="2853c-113">Ograničenja</span><span class="sxs-lookup"><span data-stu-id="2853c-113">Limitations</span></span>

<span data-ttu-id="2853c-114">Poboljšane adrese funkcionišu samo sa vrednostima koje već postoje u podacima unetih adresa.</span><span class="sxs-lookup"><span data-stu-id="2853c-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="2853c-115">Model ne radi sledeće:</span><span class="sxs-lookup"><span data-stu-id="2853c-115">The model doesn't:</span></span> 

1. <span data-ttu-id="2853c-116">Ne proverava da li je adresa važeća.</span><span class="sxs-lookup"><span data-stu-id="2853c-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="2853c-117">Ne proverava da li je neka od vrednosti, poput poštanskih brojeva ili naziva ulica, važeća.</span><span class="sxs-lookup"><span data-stu-id="2853c-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="2853c-118">Ne menja vrednosti koje ne prepoznaje.</span><span class="sxs-lookup"><span data-stu-id="2853c-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="2853c-119">Model za poboljšanje adresa koristi tehnike zasnovane na mašinskom učenju.</span><span class="sxs-lookup"><span data-stu-id="2853c-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="2853c-120">Iako primenjujemo visok prag pouzdanosti kada model menja ulaznu vrednost, kao i kod bilo kog modela zasnovanog na mašinskom učenju, stopostotna tačnost nije zagarantovana.</span><span class="sxs-lookup"><span data-stu-id="2853c-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="2853c-121">Podržane zemlje ili regioni</span><span class="sxs-lookup"><span data-stu-id="2853c-121">Supported countries or regions</span></span>

<span data-ttu-id="2853c-122">Trenutno podržavamo obogaćivanje adresa u ovim zemljama ili regionima:</span><span class="sxs-lookup"><span data-stu-id="2853c-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="2853c-123">Australija</span><span class="sxs-lookup"><span data-stu-id="2853c-123">Australia</span></span>
- <span data-ttu-id="2853c-124">Kanada</span><span class="sxs-lookup"><span data-stu-id="2853c-124">Canada</span></span>
- <span data-ttu-id="2853c-125">Ujedinjeno Kraljevstvo</span><span class="sxs-lookup"><span data-stu-id="2853c-125">United Kingdom</span></span>
- <span data-ttu-id="2853c-126">Sjedinjene Države</span><span class="sxs-lookup"><span data-stu-id="2853c-126">United States</span></span>

<span data-ttu-id="2853c-127">Adrese moraju da sadrže vrednost zemlje/regiona.</span><span class="sxs-lookup"><span data-stu-id="2853c-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="2853c-128">Ne obrađujemo adrese za zemlje ili regione koji nisu podržani i adrese za koje nije navedena zemlja ili region.</span><span class="sxs-lookup"><span data-stu-id="2853c-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="2853c-129">Konfigurisanje obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="2853c-129">Configure the enrichment</span></span>

1. <span data-ttu-id="2853c-130">Idite na **Podaci** > **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="2853c-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="2853c-131">Izaberite **Obogati moje podatke** na pločici **Poboljšane adrese**.</span><span class="sxs-lookup"><span data-stu-id="2853c-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Snimak ekrana pločice Poboljšane adrese.":::

1. <span data-ttu-id="2853c-133">Izaberite **Skup podataka klijenta** i odaberite entitet koji sadrži adrese koje želite da obogatite.</span><span class="sxs-lookup"><span data-stu-id="2853c-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="2853c-134">Možete izabrati entitet *Klijent* da obogatite adrese u svim vašim korisničkim profilima ili izaberite entitet segmenta za obogaćivanje adresa samo u korisničkim profilima sadržanim u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="2853c-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="2853c-135">Izaberite način oblikovanja adresa u skupu podataka.</span><span class="sxs-lookup"><span data-stu-id="2853c-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="2853c-136">Odaberite **Adresa sa jednim atributom** ako adrese u vašim podacima koriste jedno polje.</span><span class="sxs-lookup"><span data-stu-id="2853c-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="2853c-137">Odaberite **Adresa sa više atributa** ako adrese u vašim podacima koriste više od jednog polja podataka.</span><span class="sxs-lookup"><span data-stu-id="2853c-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2853c-138">Zemlja/region je obavezan podatak za adrese i sa jednim i sa više atributa.</span><span class="sxs-lookup"><span data-stu-id="2853c-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="2853c-139">Adrese koje ne sadrže važeće ili podržane vrednosti zemlje/regiona neće biti obogaćene.</span><span class="sxs-lookup"><span data-stu-id="2853c-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="2853c-140">Mapirajte polja adrese iz vašeg objedinjenog entiteta klijenta.</span><span class="sxs-lookup"><span data-stu-id="2853c-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Poboljšana stranica za mapiranje polja adrese.":::

1. <span data-ttu-id="2853c-142">Izaberite **Sledeće** da biste dovršili mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="2853c-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="2853c-143">Obezbedite naziv za obogaćivanje i izlazni entitet.</span><span class="sxs-lookup"><span data-stu-id="2853c-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="2853c-144">Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.</span><span class="sxs-lookup"><span data-stu-id="2853c-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="2853c-145">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="2853c-145">Enrichment results</span></span>

<span data-ttu-id="2853c-146">Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake.</span><span class="sxs-lookup"><span data-stu-id="2853c-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="2853c-147">Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2853c-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2853c-148">Vreme obrade zavisi od veličine podataka vaših klijenata.</span><span class="sxs-lookup"><span data-stu-id="2853c-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="2853c-149">Nakon završetka procesa obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod opcijom **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="2853c-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="2853c-150">Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="2853c-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="2853c-151">Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.</span><span class="sxs-lookup"><span data-stu-id="2853c-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2853c-152">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="2853c-152">Next steps</span></span>

<span data-ttu-id="2853c-153">Nadogradite na obogaćenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="2853c-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2853c-154">Kreirajte [segmente](segments.md) i [mere](measures.md), pa čak i [izvoz podataka](export-destinations.md) da pružite personalizovana iskustva svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="2853c-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
