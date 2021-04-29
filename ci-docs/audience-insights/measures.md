---
title: Kreiranje mera i upravljanje njima
description: Definišite mere za analizu i odraz učinka vašeg poslovanja.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a94a32a04f2a8beb661c27271fe96f23d998722
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887957"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="b27a7-103">Definišite i upravljajte merama</span><span class="sxs-lookup"><span data-stu-id="b27a7-103">Define and manage measures</span></span>

<span data-ttu-id="b27a7-104">Mere vam pomažu da bolje razumete ponašanje klijenata i poslovne rezultate.</span><span class="sxs-lookup"><span data-stu-id="b27a7-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="b27a7-105">Oni gledaju na relevantne vrednosti iz [objedinjenih profila](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="b27a7-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="b27a7-106">Na primer, preduzeće želi da vidi *ukupnu potrošnju po klijentu* da biste razumeli istoriju kupovine pojedinačnog klijenta ili meru *ukupne prodaje preduzeća* da biste razumeli ukupni prihod u celom poslu.</span><span class="sxs-lookup"><span data-stu-id="b27a7-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="b27a7-107">Mere se kreiraju pomoću kreatora mera, platforme za upite podataka sa različitim operaterima i jednostavnim opcijama mapiranja.</span><span class="sxs-lookup"><span data-stu-id="b27a7-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="b27a7-108">Omogućava vam da filtrirate podatke, grupišete rezultate, otkrivate [putanje relacija između entiteta](relationships.md) i pregledate izlaz.</span><span class="sxs-lookup"><span data-stu-id="b27a7-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="b27a7-109">Koristite kreator mera za planiranje poslovnih aktivnosti tako što ćete potražiti podatke o klijentima i izvući uvide.</span><span class="sxs-lookup"><span data-stu-id="b27a7-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="b27a7-110">Na primer, kreiranje mere *ukupna potrošnja po klijentu* i *ukupan povraćaj po klijentu* pomaže u identifikovanju grupe klijenata sa visokom potrošnjom, ali i visokim povraćajem.</span><span class="sxs-lookup"><span data-stu-id="b27a7-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="b27a7-111">Možete da [kreirate segment](segments.md) da biste pokrenuli sledeće najbolje radnje.</span><span class="sxs-lookup"><span data-stu-id="b27a7-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="b27a7-112">Napravite sopstvenu meru ispočetka</span><span class="sxs-lookup"><span data-stu-id="b27a7-112">Build your own measure from scratch</span></span>

<span data-ttu-id="b27a7-113">Ovaj odeljak vas vodi kroz kreiranje nove mere od početka.</span><span class="sxs-lookup"><span data-stu-id="b27a7-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="b27a7-114">Možete da izradite meru sa atributima podataka od entiteta podataka koji imaju uspostavljenu relaciju za povezivanje sa entitetom Klijent.</span><span class="sxs-lookup"><span data-stu-id="b27a7-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="b27a7-115">U uvidima o korisnicima idite na **Mere**.</span><span class="sxs-lookup"><span data-stu-id="b27a7-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="b27a7-116">Izaberite **Nova** i birajte **Napravite sopstvenu**.</span><span class="sxs-lookup"><span data-stu-id="b27a7-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="b27a7-117">Izaberite **Uređivanje naziva** i navedite **Naziv** za meru.</span><span class="sxs-lookup"><span data-stu-id="b27a7-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="b27a7-118">Ako vaša nova konfiguracija mere ima samo dva polja, za primer, CustomerID i jedan proračun, izlaz će biti dodat kao nova kolona sistemski generisanom entitetu pod nazivom Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="b27a7-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="b27a7-119">I moći ćete da vidite vrednost mere u objedinjenom profilu klijenta.</span><span class="sxs-lookup"><span data-stu-id="b27a7-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="b27a7-120">Druge mere će generisati sopstvene entitete.</span><span class="sxs-lookup"><span data-stu-id="b27a7-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="b27a7-121">U oblasti konfiguracije, odaberite agregatnu funkciju iz padajućeg menija **Izaberite funkciju**.</span><span class="sxs-lookup"><span data-stu-id="b27a7-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="b27a7-122">Agregatne funkcije uključuju:</span><span class="sxs-lookup"><span data-stu-id="b27a7-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="b27a7-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="b27a7-123">**Sum**</span></span>
   - <span data-ttu-id="b27a7-124">**Prosek**</span><span class="sxs-lookup"><span data-stu-id="b27a7-124">**Average**</span></span>
   - <span data-ttu-id="b27a7-125">**Brojanje**</span><span class="sxs-lookup"><span data-stu-id="b27a7-125">**Count**</span></span>
   - <span data-ttu-id="b27a7-126">**Broj jedinstvenih**</span><span class="sxs-lookup"><span data-stu-id="b27a7-126">**Count Unique**</span></span>
   - <span data-ttu-id="b27a7-127">**Maksimalna**</span><span class="sxs-lookup"><span data-stu-id="b27a7-127">**Max**</span></span>
   - <span data-ttu-id="b27a7-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="b27a7-128">**Min**</span></span>
   - <span data-ttu-id="b27a7-129">**Prvi**: uzima prvu vrednost zapisa podataka</span><span class="sxs-lookup"><span data-stu-id="b27a7-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="b27a7-130">**Poslednji**: uzima poslednju vrednost koja je dodata u zapis podataka</span><span class="sxs-lookup"><span data-stu-id="b27a7-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatori za proračun mera.":::

1. <span data-ttu-id="b27a7-132">Izaberite **Dodaj atribut** da biste izabrali podatke koji su vam potrebni za kreiranje ove mere.</span><span class="sxs-lookup"><span data-stu-id="b27a7-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="b27a7-133">Izaberite karticu **Atributi**.</span><span class="sxs-lookup"><span data-stu-id="b27a7-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="b27a7-134">Entitet podataka: Izaberite entitet koji uključuje atribut koji želite da merite.</span><span class="sxs-lookup"><span data-stu-id="b27a7-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="b27a7-135">Atribut podataka: Izaberite atribut koji želite da koristite u agregatnoj funkciji za izračunavanje mere.</span><span class="sxs-lookup"><span data-stu-id="b27a7-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="b27a7-136">Istovremeno možete da izaberete samo jedan atribut.</span><span class="sxs-lookup"><span data-stu-id="b27a7-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="b27a7-137">Takođe možete izabrati atribut podataka iz postojeće mere izborom kartice **Mere**. Ili možete da pretražite naziv entiteta ili naziv mere.</span><span class="sxs-lookup"><span data-stu-id="b27a7-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="b27a7-138">Izaberite **Dodaj** da biste meri dodali izabrani atribut.</span><span class="sxs-lookup"><span data-stu-id="b27a7-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Izaberite atribut koji ćete koristiti u proračunima.":::

1. <span data-ttu-id="b27a7-140">Da biste izgradili složenije mere, možete dodati više atributa ili koristiti matematičke operatore na svojoj funkciji mere.</span><span class="sxs-lookup"><span data-stu-id="b27a7-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Kreirajte složenu meru pomoću matematičkih operatora.":::

1. <span data-ttu-id="b27a7-142">Da biste dodali filtere, izaberite **Filter** u oblasti konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="b27a7-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="b27a7-143">U odeljku **Dodaj atribut** okna **Filteri**, izaberite atribut koji želite da koristite za kreiranje filtera.</span><span class="sxs-lookup"><span data-stu-id="b27a7-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="b27a7-144">Postavite operatore filtera da definišu filter za svaki izabrani atribut.</span><span class="sxs-lookup"><span data-stu-id="b27a7-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="b27a7-145">Izaberite **Primeni** da biste meri dodali filtere.</span><span class="sxs-lookup"><span data-stu-id="b27a7-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="b27a7-146">Da biste dodali dimenzije, izaberite **Dimenzija** u oblasti konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="b27a7-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="b27a7-147">Dimenzije će se prikazati kao kolone u izlaznom entitetu mere.</span><span class="sxs-lookup"><span data-stu-id="b27a7-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="b27a7-148">Izaberite **Uređivanje dimenzija** da biste dodavali atribute podataka po kojima želite da grupišete vrednosti mere.</span><span class="sxs-lookup"><span data-stu-id="b27a7-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="b27a7-149">Na primer, grad ili pol.</span><span class="sxs-lookup"><span data-stu-id="b27a7-149">For example, city or gender.</span></span> <span data-ttu-id="b27a7-150">Podrazumevano, dimenzija *CustomerID* se bira za kreiranje *mera na nivou klijenta*.</span><span class="sxs-lookup"><span data-stu-id="b27a7-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="b27a7-151">Možete da uklonite podrazumevanu dimenziju ako želite da kreirate *mere na nivou preduzeća*.</span><span class="sxs-lookup"><span data-stu-id="b27a7-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="b27a7-152">Izaberite **Gotovo** da biste meri dodali dimenzije.</span><span class="sxs-lookup"><span data-stu-id="b27a7-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="b27a7-153">Ako u vašim podacima postoje vrednosti koje treba da zamenite celim brojem, na primer, zamenite *null* sa *0*, izaberite **Pravila**.</span><span class="sxs-lookup"><span data-stu-id="b27a7-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="b27a7-154">Konfigurišite pravilo i obavezno odaberite samo cele brojeve kao zamenu.</span><span class="sxs-lookup"><span data-stu-id="b27a7-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="b27a7-155">Ako postoji više putanja između entiteta podataka koji ste mapirali i entiteta *Klijent*, morate odabrati jednu od identifikovanih [putanja relacija između entiteta](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="b27a7-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="b27a7-156">Rezultati merenja mogu se razlikovati u zavisnosti od izabrane putanje.</span><span class="sxs-lookup"><span data-stu-id="b27a7-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="b27a7-157">Izaberite **Željene opcije podataka** i odaberite putanju entiteta koju treba koristiti za identifikaciju vaše mere.</span><span class="sxs-lookup"><span data-stu-id="b27a7-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="b27a7-158">Ako postoji samo jedan put do entiteta *Klijent*, ova kontrola se neće prikazati.</span><span class="sxs-lookup"><span data-stu-id="b27a7-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="b27a7-159">Izaberite **Gotovo** da primenite svoj izbor.</span><span class="sxs-lookup"><span data-stu-id="b27a7-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Izaberite putanju entiteta za meru.":::

1. <span data-ttu-id="b27a7-161">Da biste dodali još proračuna za meru, izaberite **Novi proračun**.</span><span class="sxs-lookup"><span data-stu-id="b27a7-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="b27a7-162">Entitete na istoj putanji entiteta možete koristiti samo za nove proračune.</span><span class="sxs-lookup"><span data-stu-id="b27a7-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="b27a7-163">Više proračuna će se prikazati kao nove kolone u izlaznom entitetu mere.</span><span class="sxs-lookup"><span data-stu-id="b27a7-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="b27a7-164">Izaberite **...** na proračunu da biste **napravili duplikat**, **preimenovali** ili **uklonili** proračun iz mere.</span><span class="sxs-lookup"><span data-stu-id="b27a7-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="b27a7-165">U oblasti **Pregled** videćete šemu podataka izlaznog entiteta mere, uključujući filtere i dimenzije.</span><span class="sxs-lookup"><span data-stu-id="b27a7-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="b27a7-166">Pregled dinamički reaguje na promene u konfiguraciji.</span><span class="sxs-lookup"><span data-stu-id="b27a7-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="b27a7-167">Izaberite **Pokreni** da biste izračunali rezultate za konfigurisanu meru.</span><span class="sxs-lookup"><span data-stu-id="b27a7-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="b27a7-168">Izaberite **Sačuvaj i zatvori** ako želite da zadržite trenutnu konfiguraciju i pokrenete meru kasnije.</span><span class="sxs-lookup"><span data-stu-id="b27a7-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="b27a7-169">Idite na **Mere** da biste na listi videli novokreiranu meru.</span><span class="sxs-lookup"><span data-stu-id="b27a7-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="b27a7-170">Korišćenje predloška za izgradnju mere</span><span class="sxs-lookup"><span data-stu-id="b27a7-170">Use a template to build a measure</span></span>

<span data-ttu-id="b27a7-171">Da biste ih kreirali, možete koristiti unapred definisane predloške najčešće korišćenih mera.</span><span class="sxs-lookup"><span data-stu-id="b27a7-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="b27a7-172">Detaljni opisi predložaka i vođeno iskustvo pomažu vam u efikasnom kreiranju mera.</span><span class="sxs-lookup"><span data-stu-id="b27a7-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="b27a7-173">Predlošci se nadovezuju na mapirane podatke iz entiteta *Objedinjena aktivnost*.</span><span class="sxs-lookup"><span data-stu-id="b27a7-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="b27a7-174">Uverite se da ste konfigurisali [aktivnosti klijenata](activities.md) pre nego što kreirate meru iz predloška.</span><span class="sxs-lookup"><span data-stu-id="b27a7-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="b27a7-175">Dostupni predlošci mera:</span><span class="sxs-lookup"><span data-stu-id="b27a7-175">Available measure templates:</span></span> 
- <span data-ttu-id="b27a7-176">Prosečna vrednost transakcije (ATV)</span><span class="sxs-lookup"><span data-stu-id="b27a7-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="b27a7-177">Ukupna vrednost transakcije</span><span class="sxs-lookup"><span data-stu-id="b27a7-177">Total transaction value</span></span>
- <span data-ttu-id="b27a7-178">Prosečan dnevni prihod</span><span class="sxs-lookup"><span data-stu-id="b27a7-178">Average daily revenue</span></span>
- <span data-ttu-id="b27a7-179">Prosečan godišnji prihod</span><span class="sxs-lookup"><span data-stu-id="b27a7-179">Average yearly revenue</span></span>
- <span data-ttu-id="b27a7-180">Broj transakcija</span><span class="sxs-lookup"><span data-stu-id="b27a7-180">Transaction count</span></span>
- <span data-ttu-id="b27a7-181">Osvojeni poeni lojalnosti</span><span class="sxs-lookup"><span data-stu-id="b27a7-181">Loyalty points earned</span></span>
- <span data-ttu-id="b27a7-182">Iskorišćeni poeni lojalnosti</span><span class="sxs-lookup"><span data-stu-id="b27a7-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="b27a7-183">Bilans poena iz programa lojalnosti</span><span class="sxs-lookup"><span data-stu-id="b27a7-183">Loyalty points balance</span></span>
- <span data-ttu-id="b27a7-184">Vremenski opseg aktivnosti klijenta</span><span class="sxs-lookup"><span data-stu-id="b27a7-184">Active customer lifespan</span></span>
- <span data-ttu-id="b27a7-185">Trajanje članstva u programu lojalnosti</span><span class="sxs-lookup"><span data-stu-id="b27a7-185">Loyalty membership duration</span></span>
- <span data-ttu-id="b27a7-186">Vreme od poslednje kupovine</span><span class="sxs-lookup"><span data-stu-id="b27a7-186">Time since last purchase</span></span>

<span data-ttu-id="b27a7-187">Sledeći postupak opisuje korake za izgradnju nove mere pomoću predloška.</span><span class="sxs-lookup"><span data-stu-id="b27a7-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="b27a7-188">U uvidima o korisnicima idite na **Mere**.</span><span class="sxs-lookup"><span data-stu-id="b27a7-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="b27a7-189">Izaberite **Nova** i birajte **Odaberi predložak**.</span><span class="sxs-lookup"><span data-stu-id="b27a7-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Snimak ekrana padajućeg menija prilikom kreiranja nove mere sa isticanjem na predlošku.":::

1. <span data-ttu-id="b27a7-191">Pronađite predložak koji odgovara vašim potrebama i izaberite **Odaberi predložak**.</span><span class="sxs-lookup"><span data-stu-id="b27a7-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="b27a7-192">Pregledajte potrebne podatke i izaberite **Započnite** ako su svi podaci na svom mestu.</span><span class="sxs-lookup"><span data-stu-id="b27a7-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="b27a7-193">U oknu **Uređivanje naziva** postavite naziv mere i izlazni entitet.</span><span class="sxs-lookup"><span data-stu-id="b27a7-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="b27a7-194">Izaberite **Gotovo**.</span><span class="sxs-lookup"><span data-stu-id="b27a7-194">Select **Done**.</span></span>

1. <span data-ttu-id="b27a7-195">U odeljku **Podešavanje vremenskog perioda** definišite vremenski okvir podataka koji će se koristiti.</span><span class="sxs-lookup"><span data-stu-id="b27a7-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="b27a7-196">Odaberite da li želite da nova mera pokrije čitav skup podataka izborom **Sve vreme**.</span><span class="sxs-lookup"><span data-stu-id="b27a7-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="b27a7-197">Ili ako želite da se mera usredsredi na **Određeni vremenski period**.</span><span class="sxs-lookup"><span data-stu-id="b27a7-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Snimak ekrana koji prikazuje odeljak vremenskog perioda prilikom konfigurisanja mere iz predloška.":::

1. <span data-ttu-id="b27a7-199">U sledećem odeljku, izaberite **Dodaj podatke** da biste izabrali aktivnosti i mapirali odgovarajuće podatke iz svog entiteta *Objedinjena aktivnost*.</span><span class="sxs-lookup"><span data-stu-id="b27a7-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="b27a7-200">Korak 1 od 2: Ispod **Tipa aktivnosti** odaberite tip entiteta koji želite da koristite.</span><span class="sxs-lookup"><span data-stu-id="b27a7-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="b27a7-201">Za **Aktivnosti**, izaberite entitete koje želite da mapirate.</span><span class="sxs-lookup"><span data-stu-id="b27a7-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="b27a7-202">Korak 2 od 2: Izaberite atribut iz entiteta *Objedinjena aktivnost* za komponentu koja je obavezna za formulu.</span><span class="sxs-lookup"><span data-stu-id="b27a7-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="b27a7-203">Na primer, za „Prosečna vrednost transakcije“, to je atribut koji predstavlja vrednost transakcije.</span><span class="sxs-lookup"><span data-stu-id="b27a7-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="b27a7-204">Za **Vremensku oznaku aktivnosti**, odaberite atribut iz entiteta objedinjene aktivnosti koji predstavlja datum i vreme aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="b27a7-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="b27a7-205">Kada mapiranje podataka bude uspešno, možete videti da status ima vrednost **Kompletno** i naziv mapiranih aktivnosti i atributa.</span><span class="sxs-lookup"><span data-stu-id="b27a7-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Snimak ekrana dovršene konfiguracije predloška mere.":::

1. <span data-ttu-id="b27a7-207">Sada možete odabrati **Pokreni** da biste izračunali rezultate mere.</span><span class="sxs-lookup"><span data-stu-id="b27a7-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="b27a7-208">Da biste je kasnije precizirali, izaberite **Sačuvaj radnu verziju**.</span><span class="sxs-lookup"><span data-stu-id="b27a7-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="b27a7-209">Upravljanje merama</span><span class="sxs-lookup"><span data-stu-id="b27a7-209">Manage your measures</span></span>

<span data-ttu-id="b27a7-210">Spisak mera možete pronaći na stranici **Mere**.</span><span class="sxs-lookup"><span data-stu-id="b27a7-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="b27a7-211">Pronaći ćete informacije o tipu mere, autoru, datumu nastanka, statusu i stanju.</span><span class="sxs-lookup"><span data-stu-id="b27a7-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="b27a7-212">Kada izaberete meru sa liste, možete da pregledate izlaz i preuzmete .CSV datoteku.</span><span class="sxs-lookup"><span data-stu-id="b27a7-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="b27a7-213">Da biste istovremeno osvežili sve mere, izaberite **Osvežite sve** bez izbora određene mere.</span><span class="sxs-lookup"><span data-stu-id="b27a7-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b27a7-214">![Radnje za upravljanje jedinstvenim merama](media/measure-actions.png "Radnje za upravljanje jedinstvenim merama")</span><span class="sxs-lookup"><span data-stu-id="b27a7-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="b27a7-215">Izaberite meru sa liste za sledeće opcije:</span><span class="sxs-lookup"><span data-stu-id="b27a7-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="b27a7-216">Izaberite naziv mere da biste videli njene detalje.</span><span class="sxs-lookup"><span data-stu-id="b27a7-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="b27a7-217">**Uredite** konfiguraciju mere.</span><span class="sxs-lookup"><span data-stu-id="b27a7-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="b27a7-218">**Osvežite** meru na osnovu najnovijih podataka.</span><span class="sxs-lookup"><span data-stu-id="b27a7-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="b27a7-219">**Preimenujte** meru.</span><span class="sxs-lookup"><span data-stu-id="b27a7-219">**Rename** the measure.</span></span>
- <span data-ttu-id="b27a7-220">**Izbrišite** meru.</span><span class="sxs-lookup"><span data-stu-id="b27a7-220">**Delete** the measure.</span></span>
- <span data-ttu-id="b27a7-221">**Aktivirajte** ili **Deaktivirajte**.</span><span class="sxs-lookup"><span data-stu-id="b27a7-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="b27a7-222">Neaktivne mere se neće osvežavati tokom [zakazanog osvežavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b27a7-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="b27a7-223">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="b27a7-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="b27a7-224">Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="b27a7-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="b27a7-225">Možete izabrati status procesa da biste videli detalje o toku celog posla.</span><span class="sxs-lookup"><span data-stu-id="b27a7-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="b27a7-226">Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="b27a7-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="b27a7-227">Sledeći korak</span><span class="sxs-lookup"><span data-stu-id="b27a7-227">Next step</span></span>

<span data-ttu-id="b27a7-228">Možete koristiti postojeće mere za kreiranje [segmenta klijenata](segments.md).</span><span class="sxs-lookup"><span data-stu-id="b27a7-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]