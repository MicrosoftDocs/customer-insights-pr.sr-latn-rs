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
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965595"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="0b228-103">Obogaćivanje korisničkih profila sa poboljšanim adresama</span><span class="sxs-lookup"><span data-stu-id="0b228-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="0b228-104">Adrese u vašim podacima mogu biti nestrukturirane, nepotpune ili netačne.</span><span class="sxs-lookup"><span data-stu-id="0b228-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="0b228-105">Koristite Microsoft modele za normalizaciju i obogaćivanje adresa u [formatu Common Data Model](/common-data-model/schema/core/applicationcommon/address) radi veće tačnosti i uvida.</span><span class="sxs-lookup"><span data-stu-id="0b228-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="0b228-106">Kako poboljšavamo adrese</span><span class="sxs-lookup"><span data-stu-id="0b228-106">How we enhance addresses</span></span>

<span data-ttu-id="0b228-107">Naš model prolazi kroz postupak u dva koraka za poboljšanje adrese.</span><span class="sxs-lookup"><span data-stu-id="0b228-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="0b228-108">Prvo raščlanjuje adresu da bi identifikovao njene komponente i stavlja ih u strukturirani format.</span><span class="sxs-lookup"><span data-stu-id="0b228-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="0b228-109">Zatim koristimo veštačku inteligenciju da bismo ispravili, upotpunili i standardizovali vrednosti u adresi.</span><span class="sxs-lookup"><span data-stu-id="0b228-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="0b228-110">Primer</span><span class="sxs-lookup"><span data-stu-id="0b228-110">Example</span></span>

<span data-ttu-id="0b228-111">Informacije o adresi mogu da budu u nestandardnom formatu i da sadrže pravopisne greške.</span><span class="sxs-lookup"><span data-stu-id="0b228-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="0b228-112">Model može rešiti ove probleme i kreirati dosledne adrese u objedinjenim korisničkim profilima.</span><span class="sxs-lookup"><span data-stu-id="0b228-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

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

### <a name="limitations"></a><span data-ttu-id="0b228-113">Ograničenja</span><span class="sxs-lookup"><span data-stu-id="0b228-113">Limitations</span></span>

<span data-ttu-id="0b228-114">Poboljšane adrese funkcionišu samo sa vrednostima koje već postoje u podacima unetih adresa.</span><span class="sxs-lookup"><span data-stu-id="0b228-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="0b228-115">Model ne radi sledeće:</span><span class="sxs-lookup"><span data-stu-id="0b228-115">The model doesn't:</span></span> 

1. <span data-ttu-id="0b228-116">Ne proverava da li je adresa važeća.</span><span class="sxs-lookup"><span data-stu-id="0b228-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="0b228-117">Ne proverava da li je neka od vrednosti, poput poštanskih brojeva ili naziva ulica, važeća.</span><span class="sxs-lookup"><span data-stu-id="0b228-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="0b228-118">Ne menja vrednosti koje ne prepoznaje.</span><span class="sxs-lookup"><span data-stu-id="0b228-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="0b228-119">Model za poboljšanje adresa koristi tehnike zasnovane na mašinskom učenju.</span><span class="sxs-lookup"><span data-stu-id="0b228-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="0b228-120">Iako primenjujemo visok prag pouzdanosti kada model menja ulaznu vrednost, kao i kod bilo kog modela zasnovanog na mašinskom učenju, 100% tačnost nije garantovana.</span><span class="sxs-lookup"><span data-stu-id="0b228-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="0b228-121">Podržane zemlje ili regioni</span><span class="sxs-lookup"><span data-stu-id="0b228-121">Supported countries or regions</span></span>

<span data-ttu-id="0b228-122">Trenutno podržavamo obogaćivanje adresa u ovim zemljama ili regionima:</span><span class="sxs-lookup"><span data-stu-id="0b228-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="0b228-123">Australija</span><span class="sxs-lookup"><span data-stu-id="0b228-123">Australia</span></span>
- <span data-ttu-id="0b228-124">Kanada</span><span class="sxs-lookup"><span data-stu-id="0b228-124">Canada</span></span>
- <span data-ttu-id="0b228-125">Ujedinjeno Kraljevstvo</span><span class="sxs-lookup"><span data-stu-id="0b228-125">United Kingdom</span></span>
- <span data-ttu-id="0b228-126">Sjedinjene Države</span><span class="sxs-lookup"><span data-stu-id="0b228-126">United States</span></span>

<span data-ttu-id="0b228-127">Adrese moraju da sadrže vrednost zemlje/regiona.</span><span class="sxs-lookup"><span data-stu-id="0b228-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="0b228-128">Ne obrađujemo adrese za zemlje ili regione koji nisu podržani i adrese za koje nije navedena zemlja ili region.</span><span class="sxs-lookup"><span data-stu-id="0b228-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="0b228-129">Konfigurisanje obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="0b228-129">Configure the enrichment</span></span>

1. <span data-ttu-id="0b228-130">Idite na **Podaci** > **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="0b228-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="0b228-131">Izaberite **Obogati moje podatke** na pločici **Poboljšane adrese**.</span><span class="sxs-lookup"><span data-stu-id="0b228-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Snimak ekrana pločice Poboljšane adrese.":::

1. <span data-ttu-id="0b228-133">Izaberite **Skup podataka klijenta** i odaberite entitet koji sadrži adrese koje želite da obogatite.</span><span class="sxs-lookup"><span data-stu-id="0b228-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="0b228-134">Možete izabrati entitet *Klijent* da obogatite adrese u svim vašim korisničkim profilima ili izaberite entitet segmenta za obogaćivanje adresa samo u korisničkim profilima sadržanim u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="0b228-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="0b228-135">Izaberite način oblikovanja adresa u skupu podataka.</span><span class="sxs-lookup"><span data-stu-id="0b228-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="0b228-136">Odaberite **Adresa sa jednim atributom** ako adrese u vašim podacima koriste jedno polje.</span><span class="sxs-lookup"><span data-stu-id="0b228-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="0b228-137">Odaberite **Adresa sa više atributa** ako adrese u vašim podacima koriste više od jednog polja podataka.</span><span class="sxs-lookup"><span data-stu-id="0b228-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0b228-138">Država/region je obavezna i za adresu sa jednim atributom i za onu sa više atributa.</span><span class="sxs-lookup"><span data-stu-id="0b228-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="0b228-139">Adrese koje ne sadrže važeće ili podržane vrednosti zemlje/regiona neće biti obogaćene</span><span class="sxs-lookup"><span data-stu-id="0b228-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="0b228-140">Mapirajte polja adrese iz vašeg objedinjenog entiteta klijenta.</span><span class="sxs-lookup"><span data-stu-id="0b228-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Poboljšana stranica za mapiranje polja adrese.":::

1. <span data-ttu-id="0b228-142">Izaberite **Sledeće** da biste dovršili mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="0b228-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="0b228-143">Obezbedite naziv za obogaćivanje i izlazni entitet.</span><span class="sxs-lookup"><span data-stu-id="0b228-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="0b228-144">Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.</span><span class="sxs-lookup"><span data-stu-id="0b228-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="0b228-145">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="0b228-145">Enrichment results</span></span>

<span data-ttu-id="0b228-146">Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake.</span><span class="sxs-lookup"><span data-stu-id="0b228-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="0b228-147">Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0b228-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0b228-148">Vreme obrade zavisi od veličine podataka vaših klijenata.</span><span class="sxs-lookup"><span data-stu-id="0b228-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="0b228-149">Nakon završetka procesa obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod opcijom **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="0b228-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="0b228-150">Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="0b228-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="0b228-151">Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.</span><span class="sxs-lookup"><span data-stu-id="0b228-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0b228-152">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="0b228-152">Next steps</span></span>

<span data-ttu-id="0b228-153">Nadogradite na obogaćenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="0b228-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="0b228-154">Kreirajte [segmente](segments.md), [mere](measures.md), pa čak i [izvezite podatke](export-destinations.md) da biste pružili personalizovana iskustva svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="0b228-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
