---
title: Kreiranje i uređivanje mera
description: Definišite mere koje se odnose na klijenta kako biste analizirali i odražavali performanse određenih oblasti poslovanja.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406819"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="47a76-103">Definišite i upravljajte merama</span><span class="sxs-lookup"><span data-stu-id="47a76-103">Define and manage measures</span></span>

<span data-ttu-id="47a76-104">**Mere** predstavljaju ključne pokazatelje performansi (KPI) koji odražavaju performanse i ispravnost određenih poslovnih oblasti.</span><span class="sxs-lookup"><span data-stu-id="47a76-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="47a76-105">Uvidi o korisnicima pružaju intuitivno iskustvo za izgradnju različitih vrsta mera, koristeći kreator upita koji ne zahteva ručno kodiranje ili validaciju mera.</span><span class="sxs-lookup"><span data-stu-id="47a76-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="47a76-106">Možete pratiti svoje poslovne mere na stranici **Početak**, pogledajte mere za određene klijente na stranici **Kartica klijenta** i koristite mere za definisanje segmenata korisnika na stranici **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="47a76-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="47a76-107">Kreiranje mere</span><span class="sxs-lookup"><span data-stu-id="47a76-107">Create a measure</span></span>

<span data-ttu-id="47a76-108">Ovaj odeljak vas vodi kroz kreiranje mere ispočetka.</span><span class="sxs-lookup"><span data-stu-id="47a76-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="47a76-109">Možete izgraditi mere pomoću podataka iz više izvora podataka koji su povezani preko entiteta Klijenta.</span><span class="sxs-lookup"><span data-stu-id="47a76-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="47a76-110">Neka [ograničenja usluga](service-limits.md) se primenjuju.</span><span class="sxs-lookup"><span data-stu-id="47a76-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="47a76-111">U uvidima o korisnicima idite na **Mere**.</span><span class="sxs-lookup"><span data-stu-id="47a76-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="47a76-112">Izaberite **Nova mera**.</span><span class="sxs-lookup"><span data-stu-id="47a76-112">Select **New measure**.</span></span>

3. <span data-ttu-id="47a76-113">Odaberite **Tip** mere:</span><span class="sxs-lookup"><span data-stu-id="47a76-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="47a76-114">**Atribut klijenta**: Jedno polje po klijentu koje odražava rezultat, vrednost ili stanje za klijenta.</span><span class="sxs-lookup"><span data-stu-id="47a76-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="47a76-115">Atributi korisnika kreiraju se kao atributi u novom sistemski generiranom entitetu koji se zove **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="47a76-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="47a76-116">**Mera klijenta**: Uvid u ponašanje klijenata sa analizom po odabranim dimenzijama.</span><span class="sxs-lookup"><span data-stu-id="47a76-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="47a76-117">Kreira se novi entitet za svaku meru, potencijalno sa više zapisa po korisniku.</span><span class="sxs-lookup"><span data-stu-id="47a76-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="47a76-118">**Poslovna mera**: Prati vaše poslovne rezultate i stanje vašeg poslovanja.</span><span class="sxs-lookup"><span data-stu-id="47a76-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="47a76-119">Poslovne mere mogu imati dva različita izlaza: numerički izlaz koji se prikazuje na stranici **Početak** ili novi entitet koji ćete pronaći na stranici **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="47a76-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="47a76-120">Navedite **Ime** i opcionalno **Ime za prikaz**, a zatim izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="47a76-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="47a76-121">U odeljku **Entitet**, izaberite prvi entitet sa padajuće liste.</span><span class="sxs-lookup"><span data-stu-id="47a76-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="47a76-122">U ovom trenutku, trebalo bi da odlučite da li su potrebni dodatni entiteti kao deo vaše definicije mera.</span><span class="sxs-lookup"><span data-stu-id="47a76-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="47a76-123">![Definicija mere](media/measure-definition.png "Definicija mere")</span><span class="sxs-lookup"><span data-stu-id="47a76-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="47a76-124">Da biste dodali još entiteta, izaberite **Dodajte entitet** i izaberite entitete koje želite da koristite za meru.</span><span class="sxs-lookup"><span data-stu-id="47a76-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="47a76-125">Možete izabrati samo one entitete koji imaju relaciju sa početnim entitetom.</span><span class="sxs-lookup"><span data-stu-id="47a76-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="47a76-126">Više informacija o definisanju relacija potražite u članku [Relacije](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="47a76-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="47a76-127">Opcionalno, možete da konfigurišete promenljive.</span><span class="sxs-lookup"><span data-stu-id="47a76-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="47a76-128">U odeljku **Promenljive**, izaberite **Nova promenljiva**.</span><span class="sxs-lookup"><span data-stu-id="47a76-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="47a76-129">Promenljive su proračuni koji se obavljaju na svim izabranim zapisima.</span><span class="sxs-lookup"><span data-stu-id="47a76-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="47a76-130">Na primer, sabiranje prodajnog mesta (POS) i prodaja putem interneta za sve zapise vaših klijenata.</span><span class="sxs-lookup"><span data-stu-id="47a76-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="47a76-131">Navedite **Naziv** za promenljivu.</span><span class="sxs-lookup"><span data-stu-id="47a76-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="47a76-132">U oblasti **Izraz** odaberite polje za početak izračunavanja.</span><span class="sxs-lookup"><span data-stu-id="47a76-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="47a76-133">Unesite izraz u oblast **Izraz** dok birate više polja koja će se uključiti u vaš proračun.</span><span class="sxs-lookup"><span data-stu-id="47a76-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="47a76-134">Trenutno su podržani samo aritmetički izrazi.</span><span class="sxs-lookup"><span data-stu-id="47a76-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="47a76-135">Pored toga, izračunavanje promenljivih nije podržano za entitete iz različitih [putanja entiteta](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="47a76-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="47a76-136">Izaberite **Gotovo**.</span><span class="sxs-lookup"><span data-stu-id="47a76-136">Select **Done**.</span></span>

11. <span data-ttu-id="47a76-137">U odeljku **Definicija mere**, definisaćete kako se izabrani entiteti i izračunate promenljive agregiraju u novu celinu ili atribut mere.</span><span class="sxs-lookup"><span data-stu-id="47a76-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="47a76-138">Izaberite **Nova dimenzija**.</span><span class="sxs-lookup"><span data-stu-id="47a76-138">Select **New dimension**.</span></span> <span data-ttu-id="47a76-139">O dimenziji možete razmišljati kao o funkciji *grupiši prema*.</span><span class="sxs-lookup"><span data-stu-id="47a76-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="47a76-140">Izlaz podataka vašeg entiteta ili atributa Mera biće grupisan po svim vašim definisanim dimenzijama.</span><span class="sxs-lookup"><span data-stu-id="47a76-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="47a76-141">![Izaberite agregatni ciklus](media/measures-businessreport-measure-definition2.png "Izaberite agregatni ciklus")</span><span class="sxs-lookup"><span data-stu-id="47a76-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="47a76-142">Izaberite ili unesite sledeće informacije kao deo definicije vaše dimenzije:</span><span class="sxs-lookup"><span data-stu-id="47a76-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="47a76-143">**Entitet**: Ako definišete entitet Mera, on treba da sadrži najmanje jedan atribut.</span><span class="sxs-lookup"><span data-stu-id="47a76-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="47a76-144">Ako definišete atribut Mera, on će podrazumevano sadržavati samo jedan atribut.</span><span class="sxs-lookup"><span data-stu-id="47a76-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="47a76-145">Ovaj izbor se odnosi na izbor entiteta koji uključuje taj atribut.</span><span class="sxs-lookup"><span data-stu-id="47a76-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="47a76-146">**Polje**: Izaberite određeni atribut koji će se uključiti u vašu mernu jedinicu ili atribut.</span><span class="sxs-lookup"><span data-stu-id="47a76-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="47a76-147">**Kontejner**: Izaberite da li želite da objedinite podatke na dnevnoj, mesečnoj ili godišnjoj osnovi.</span><span class="sxs-lookup"><span data-stu-id="47a76-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="47a76-148">To je obavezan izbor samo ako ste izabrali atribut tipa Datum.</span><span class="sxs-lookup"><span data-stu-id="47a76-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="47a76-149">**Kao**: Definiše ime vašeg novog polja.</span><span class="sxs-lookup"><span data-stu-id="47a76-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="47a76-150">**Ime za prikaz**: Definiše ime za prikaz vašeg polja.</span><span class="sxs-lookup"><span data-stu-id="47a76-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="47a76-151">Vaša poslovna mera će biti sačuvana kao entitet s jednim brojem i prikazaće se na stranici **Početak** ukoliko u meru ne dodate više dimenzija.</span><span class="sxs-lookup"><span data-stu-id="47a76-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="47a76-152">Nakon dodavanja više dimenzija, mera se *neće* prikazivati na stranici **Početak**.</span><span class="sxs-lookup"><span data-stu-id="47a76-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="47a76-153">Opcionalno, dodajte funkcije agregacije.</span><span class="sxs-lookup"><span data-stu-id="47a76-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="47a76-154">Svako združivanje koje stvorite rezultira novom vrednošću unutar entiteta ili atributa Mere.</span><span class="sxs-lookup"><span data-stu-id="47a76-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="47a76-155">Podržane funkcije agregacije su: **Min**, **Maks**, **Prosek**, **Medijana**, **Zbir**, **Broj jedinstvenih**, **Prvi** (uzima prvi zapis vrednosti dimenzije) i **Poslednji** (uzima poslednji zapis koji je dodat u dimenziju).</span><span class="sxs-lookup"><span data-stu-id="47a76-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="47a76-156">Izaberite **Sačuvaj** da biste primenili promene na meru.</span><span class="sxs-lookup"><span data-stu-id="47a76-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="47a76-157">Upravljanje merama</span><span class="sxs-lookup"><span data-stu-id="47a76-157">Manage your measures</span></span>

<span data-ttu-id="47a76-158">Nakon što napravite bar jednu meru, videćete listu mera na stranici **Mere**.</span><span class="sxs-lookup"><span data-stu-id="47a76-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="47a76-159">Pronaći ćete informacije o vrsti mere, kreatoru, datumu i vremenu kreiranja, datumu i vremenu poslednje izmene, statusu (da li je mera aktivna, neaktivna ili neuspela) i poslednjem datumu i vremenu osvežavanja.</span><span class="sxs-lookup"><span data-stu-id="47a76-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="47a76-160">Kada sa liste izaberete meru, možete videti pregled njenog rezultata.</span><span class="sxs-lookup"><span data-stu-id="47a76-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="47a76-161">Da biste istovremeno osvežili sve mere, izaberite **Osvežite sve** bez izbora određene mere.</span><span class="sxs-lookup"><span data-stu-id="47a76-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="47a76-162">![Radnje za upravljanje jedinstvenim merama](media/measure-actions.png "Radnje za upravljanje jedinstvenim merama")</span><span class="sxs-lookup"><span data-stu-id="47a76-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="47a76-163">Alternativno, izaberite meru sa liste i izvršite jednu od sledećih radnji:</span><span class="sxs-lookup"><span data-stu-id="47a76-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="47a76-164">Izaberite naziv mere da biste videli njene detalje.</span><span class="sxs-lookup"><span data-stu-id="47a76-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="47a76-165">**Uredite** konfiguraciju mere.</span><span class="sxs-lookup"><span data-stu-id="47a76-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="47a76-166">**Preimenujte** meru.</span><span class="sxs-lookup"><span data-stu-id="47a76-166">**Rename** the measure.</span></span>
- <span data-ttu-id="47a76-167">**Izbrišite** meru.</span><span class="sxs-lookup"><span data-stu-id="47a76-167">**Delete** the measure.</span></span>
- <span data-ttu-id="47a76-168">Izaberite tri tačke (...), a zatim **Osveži** da biste započeli postupak osvežavanja mere.</span><span class="sxs-lookup"><span data-stu-id="47a76-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="47a76-169">Izaberite tri tačke (...), a zatim **Preuzmi** da biste preuzeli .CSV datoteku mere.</span><span class="sxs-lookup"><span data-stu-id="47a76-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="47a76-170">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="47a76-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="47a76-171">Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="47a76-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="47a76-172">Možete izabrati status procesa da biste videli detalje o toku celog posla.</span><span class="sxs-lookup"><span data-stu-id="47a76-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="47a76-173">Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="47a76-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="47a76-174">Sledeći korak</span><span class="sxs-lookup"><span data-stu-id="47a76-174">Next step</span></span>

<span data-ttu-id="47a76-175">Možete da koristite postojeće mere da biste kreirali svoj prvi segment korisnika na stranici **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="47a76-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="47a76-176">Za više informacija, pogledajte članak [Segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="47a76-176">For more information, see [Segments](segments.md).</span></span>
