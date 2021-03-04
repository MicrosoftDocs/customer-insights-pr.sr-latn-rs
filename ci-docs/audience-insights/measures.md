---
title: Kreiranje mera i upravljanje njima
description: Definišite mere za analizu i odraz učinka vašeg poslovanja.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269945"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="d7a71-103">Definišite i upravljajte merama</span><span class="sxs-lookup"><span data-stu-id="d7a71-103">Define and manage measures</span></span>

<span data-ttu-id="d7a71-104">Mere vam pomažu da bolje razumete ponašanje klijenata i poslovne performanse preuzimanjem relevantnih vrednosti iz [objedinjenih profila](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="d7a71-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="d7a71-105">Na primer, preduzeće želi da vidi *ukupnu potrošnju po klijentu* da bi razumelo istoriju kupovine pojedinačnog klijenta.</span><span class="sxs-lookup"><span data-stu-id="d7a71-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="d7a71-106">Ili meri *ukupnu prodaju preduzeća* da bi razumelo prihod na zbirnom nivou u celom preduzeću.</span><span class="sxs-lookup"><span data-stu-id="d7a71-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="d7a71-107">Mere se kreiraju pomoću kreatora mera, platforme za upite podataka sa različitim operaterima i jednostavnim opcijama mapiranja.</span><span class="sxs-lookup"><span data-stu-id="d7a71-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="d7a71-108">Omogućava vam da filtrirate podatke, grupišete rezultate, otkrivate [putanje relacija između entiteta](relationships.md) i pregledate izlaz.</span><span class="sxs-lookup"><span data-stu-id="d7a71-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="d7a71-109">Koristite kreator mera za planiranje poslovnih aktivnosti tako što ćete potražiti podatke o klijentima i izvući uvide.</span><span class="sxs-lookup"><span data-stu-id="d7a71-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="d7a71-110">Na primer, kreiranje mere *ukupna potrošnja po klijentu* i *ukupan povraćaj po klijentu* pomaže u identifikovanju grupe klijenata sa visokom potrošnjom, ali i visokim povraćajem.</span><span class="sxs-lookup"><span data-stu-id="d7a71-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="d7a71-111">Možete da [kreirate segment](segments.md) da biste pokrenuli sledeće najbolje radnje.</span><span class="sxs-lookup"><span data-stu-id="d7a71-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="d7a71-112">Kreiranje mere</span><span class="sxs-lookup"><span data-stu-id="d7a71-112">Create a measure</span></span>

<span data-ttu-id="d7a71-113">Ovaj odeljak vas vodi kroz kreiranje nove mere od početka.</span><span class="sxs-lookup"><span data-stu-id="d7a71-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="d7a71-114">Možete da izradite meru sa atributima podataka od entiteta podataka koji imaju uspostavljenu relaciju za povezivanje sa entitetom Klijent.</span><span class="sxs-lookup"><span data-stu-id="d7a71-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="d7a71-115">U uvidima o korisnicima idite na **Mere**.</span><span class="sxs-lookup"><span data-stu-id="d7a71-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="d7a71-116">Izaberite **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d7a71-116">Select **New**.</span></span>

1. <span data-ttu-id="d7a71-117">Izaberite **Uređivanje naziva** i navedite **Naziv** za meru.</span><span class="sxs-lookup"><span data-stu-id="d7a71-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="d7a71-118">Ako vaša nova konfiguracija mere ima samo dva polja, za primer, CustomerID i jedan proračun, izlaz će biti dodat kao nova kolona sistemski generisanom entitetu pod nazivom Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="d7a71-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="d7a71-119">I moći ćete da vidite vrednost mere u objedinjenom profilu klijenta.</span><span class="sxs-lookup"><span data-stu-id="d7a71-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="d7a71-120">Druge mere će generisati sopstvene entitete.</span><span class="sxs-lookup"><span data-stu-id="d7a71-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="d7a71-121">U oblasti konfiguracije, odaberite agregatnu funkciju iz padajućeg menija **Izaberite funkciju**.</span><span class="sxs-lookup"><span data-stu-id="d7a71-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="d7a71-122">Agregatne funkcije uključuju:</span><span class="sxs-lookup"><span data-stu-id="d7a71-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="d7a71-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="d7a71-123">**Sum**</span></span>
   - <span data-ttu-id="d7a71-124">**Prosek**</span><span class="sxs-lookup"><span data-stu-id="d7a71-124">**Average**</span></span>
   - <span data-ttu-id="d7a71-125">**Brojanje**</span><span class="sxs-lookup"><span data-stu-id="d7a71-125">**Count**</span></span>
   - <span data-ttu-id="d7a71-126">**Broj jedinstvenih**</span><span class="sxs-lookup"><span data-stu-id="d7a71-126">**Count Unique**</span></span>
   - <span data-ttu-id="d7a71-127">**Maksimalna**</span><span class="sxs-lookup"><span data-stu-id="d7a71-127">**Max**</span></span>
   - <span data-ttu-id="d7a71-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="d7a71-128">**Min**</span></span>
   - <span data-ttu-id="d7a71-129">**Prvi**: uzima prvu vrednost zapisa podataka</span><span class="sxs-lookup"><span data-stu-id="d7a71-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="d7a71-130">**Poslednji**: uzima poslednju vrednost koja je dodata u zapis podataka</span><span class="sxs-lookup"><span data-stu-id="d7a71-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatori za proračun mera.":::

1. <span data-ttu-id="d7a71-132">Izaberite **Dodaj atribut** da biste izabrali podatke koji su vam potrebni za kreiranje ove mere.</span><span class="sxs-lookup"><span data-stu-id="d7a71-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="d7a71-133">Izaberite karticu **Atributi**.</span><span class="sxs-lookup"><span data-stu-id="d7a71-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="d7a71-134">Entitet podataka: Izaberite entitet koji uključuje atribut koji želite da merite.</span><span class="sxs-lookup"><span data-stu-id="d7a71-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="d7a71-135">Atribut podataka: Izaberite atribut koji želite da koristite u agregatnoj funkciji za izračunavanje mere.</span><span class="sxs-lookup"><span data-stu-id="d7a71-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="d7a71-136">Istovremeno možete da izaberete samo jedan atribut.</span><span class="sxs-lookup"><span data-stu-id="d7a71-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="d7a71-137">Takođe možete izabrati atribut podataka iz postojeće mere izborom kartice **Mere**. Ili možete da pretražite naziv entiteta ili naziv mere.</span><span class="sxs-lookup"><span data-stu-id="d7a71-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="d7a71-138">Izaberite **Dodaj** da biste meri dodali izabrani atribut.</span><span class="sxs-lookup"><span data-stu-id="d7a71-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Izaberite atribut koji ćete koristiti u proračunima.":::

1. <span data-ttu-id="d7a71-140">Da biste izgradili složenije mere, možete dodati više atributa ili koristiti matematičke operatore na svojoj funkciji mere.</span><span class="sxs-lookup"><span data-stu-id="d7a71-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Kreirajte složenu meru pomoću matematičkih operatora.":::

1. <span data-ttu-id="d7a71-142">Da biste dodali filtere, izaberite **Filter** u oblasti konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="d7a71-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="d7a71-143">U odeljku **Dodaj atribut** okna **Filteri**, izaberite atribut koji želite da koristite za kreiranje filtera.</span><span class="sxs-lookup"><span data-stu-id="d7a71-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="d7a71-144">Postavite operatore filtera da definišu filter za svaki izabrani atribut.</span><span class="sxs-lookup"><span data-stu-id="d7a71-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="d7a71-145">Izaberite **Primeni** da biste meri dodali filtere.</span><span class="sxs-lookup"><span data-stu-id="d7a71-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="d7a71-146">Da biste dodali dimenzije, izaberite **Dimenzija** u oblasti konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="d7a71-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="d7a71-147">Dimenzije će se prikazati kao kolone u izlaznom entitetu mere.</span><span class="sxs-lookup"><span data-stu-id="d7a71-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="d7a71-148">Izaberite **Uređivanje dimenzija** da biste dodavali atribute podataka po kojima želite da grupišete vrednosti mere.</span><span class="sxs-lookup"><span data-stu-id="d7a71-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="d7a71-149">Na primer, grad ili pol.</span><span class="sxs-lookup"><span data-stu-id="d7a71-149">For example, city or gender.</span></span> <span data-ttu-id="d7a71-150">Podrazumevano, dimenzija *CustomerID* se bira za kreiranje *mera na nivou klijenta*.</span><span class="sxs-lookup"><span data-stu-id="d7a71-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="d7a71-151">Možete da uklonite podrazumevanu dimenziju ako želite da kreirate *mere na nivou preduzeća*.</span><span class="sxs-lookup"><span data-stu-id="d7a71-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="d7a71-152">Izaberite **Gotovo** da biste meri dodali dimenzije.</span><span class="sxs-lookup"><span data-stu-id="d7a71-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="d7a71-153">Ako postoji više putanja između entiteta podataka koji ste mapirali i entiteta klijenta, morate odabrati jednu od identifikovanih [putanja relacija između entiteta](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="d7a71-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="d7a71-154">Rezultati merenja mogu se razlikovati u zavisnosti od izabrane putanje.</span><span class="sxs-lookup"><span data-stu-id="d7a71-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="d7a71-155">Izaberite **Željene opcije podataka** i odaberite putanju entiteta koju treba koristiti za identifikaciju vaše mere.</span><span class="sxs-lookup"><span data-stu-id="d7a71-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="d7a71-156">Izaberite **Gotovo** da primenite svoj izbor.</span><span class="sxs-lookup"><span data-stu-id="d7a71-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Izaberite putanju entiteta za meru.":::

1. <span data-ttu-id="d7a71-158">Da biste dodali još proračuna za meru, izaberite **Novi proračun**.</span><span class="sxs-lookup"><span data-stu-id="d7a71-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="d7a71-159">Entitete na istoj putanji entiteta možete koristiti samo za nove proračune.</span><span class="sxs-lookup"><span data-stu-id="d7a71-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="d7a71-160">Više proračuna će se prikazati kao nove kolone u izlaznom entitetu mere.</span><span class="sxs-lookup"><span data-stu-id="d7a71-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="d7a71-161">Izaberite **...** na proračunu da biste **napravili duplikat**, **preimenovali** ili **uklonili** proračun iz mere.</span><span class="sxs-lookup"><span data-stu-id="d7a71-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="d7a71-162">U oblasti **Pregled** videćete šemu podataka izlaznog entiteta mere, uključujući filtere i dimenzije.</span><span class="sxs-lookup"><span data-stu-id="d7a71-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="d7a71-163">Pregled dinamički reaguje na promene u konfiguraciji.</span><span class="sxs-lookup"><span data-stu-id="d7a71-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="d7a71-164">Izaberite **Pokreni** da biste izračunali rezultate za konfigurisanu meru.</span><span class="sxs-lookup"><span data-stu-id="d7a71-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="d7a71-165">Izaberite **Sačuvaj i zatvori** ako želite da zadržite trenutnu konfiguraciju i pokrenete meru kasnije.</span><span class="sxs-lookup"><span data-stu-id="d7a71-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="d7a71-166">Idite na **Mere** da biste na listi videli novokreiranu meru.</span><span class="sxs-lookup"><span data-stu-id="d7a71-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="d7a71-167">Upravljanje merama</span><span class="sxs-lookup"><span data-stu-id="d7a71-167">Manage your measures</span></span>

<span data-ttu-id="d7a71-168">Kada [kreirate meru](#create-a-measure), videćete listu mera na stranici **Mere**.</span><span class="sxs-lookup"><span data-stu-id="d7a71-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="d7a71-169">Pronaći ćete informacije o tipu mere, autoru, datumu nastanka, statusu i stanju.</span><span class="sxs-lookup"><span data-stu-id="d7a71-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="d7a71-170">Kada izaberete meru sa liste, možete da pregledate izlaz i preuzmete .CSV datoteku.</span><span class="sxs-lookup"><span data-stu-id="d7a71-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="d7a71-171">Da biste istovremeno osvežili sve mere, izaberite **Osvežite sve** bez izbora određene mere.</span><span class="sxs-lookup"><span data-stu-id="d7a71-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d7a71-172">![Radnje za upravljanje jedinstvenim merama](media/measure-actions.png "Radnje za upravljanje jedinstvenim merama")</span><span class="sxs-lookup"><span data-stu-id="d7a71-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="d7a71-173">Izaberite meru sa liste za sledeće opcije:</span><span class="sxs-lookup"><span data-stu-id="d7a71-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="d7a71-174">Izaberite naziv mere da biste videli njene detalje.</span><span class="sxs-lookup"><span data-stu-id="d7a71-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="d7a71-175">**Uredite** konfiguraciju mere.</span><span class="sxs-lookup"><span data-stu-id="d7a71-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="d7a71-176">**Osvežite** meru na osnovu najnovijih podataka.</span><span class="sxs-lookup"><span data-stu-id="d7a71-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="d7a71-177">**Preimenujte** meru.</span><span class="sxs-lookup"><span data-stu-id="d7a71-177">**Rename** the measure.</span></span>
- <span data-ttu-id="d7a71-178">**Izbrišite** meru.</span><span class="sxs-lookup"><span data-stu-id="d7a71-178">**Delete** the measure.</span></span>
- <span data-ttu-id="d7a71-179">**Aktivirajte** ili **Deaktivirajte**.</span><span class="sxs-lookup"><span data-stu-id="d7a71-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="d7a71-180">Neaktivne mere se neće osvežavati tokom [zakazanog osvežavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d7a71-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="d7a71-181">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="d7a71-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d7a71-182">Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d7a71-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d7a71-183">Možete izabrati status procesa da biste videli detalje o toku celog posla.</span><span class="sxs-lookup"><span data-stu-id="d7a71-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d7a71-184">Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="d7a71-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="d7a71-185">Sledeći korak</span><span class="sxs-lookup"><span data-stu-id="d7a71-185">Next step</span></span>

<span data-ttu-id="d7a71-186">Možete koristiti postojeće mere za kreiranje [segmenta klijenata](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d7a71-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]