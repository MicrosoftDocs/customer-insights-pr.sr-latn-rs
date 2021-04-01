---
title: Objedinjavanje entiteta kod objedinjavanja podataka
description: Objedinite entitete da biste kreirali objedinjene profile klijenata.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597850"
---
# <a name="merge-entities"></a><span data-ttu-id="14094-103">Objedinjavanje entiteta</span><span class="sxs-lookup"><span data-stu-id="14094-103">Merge entities</span></span>

<span data-ttu-id="14094-104">Faza spajanja je poslednja faza u procesu objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="14094-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="14094-105">Njegova svrha je usklađivanje neusaglašenih podataka.</span><span class="sxs-lookup"><span data-stu-id="14094-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="14094-106">Primeri neusaglašenih podataka mogu uključivati korisničko ime koje se nalazi u dva skupa podataka, ali to se prikazuje malo drugačije u svakom („Jovan Dučić“ u odnosu na „Jovo Dučić“) ili telefonski broj koji se razlikuje u formatu (npr. 617-803-091 u odnosu na 617803091).</span><span class="sxs-lookup"><span data-stu-id="14094-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="14094-107">Spajanje tih neusaglašenih tačaka podataka obavlja se na osnovu poređenja atributa.</span><span class="sxs-lookup"><span data-stu-id="14094-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="14094-108">Kada se dovrši [faza podudaranja](match-entities.md), fazu spajanja započinjete odabirom pločice **Objedini** na stranici **Ujednačavanje**.</span><span class="sxs-lookup"><span data-stu-id="14094-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="14094-109">Pregled sistemskih preporuka</span><span class="sxs-lookup"><span data-stu-id="14094-109">Review system recommendations</span></span>

<span data-ttu-id="14094-110">Na stranici **Spajanje** možete izabrati i isključiti atribute koji će se spajati unutar objedinjenog entiteta profila klijenta (rezultat postupka konfiguracije).</span><span class="sxs-lookup"><span data-stu-id="14094-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="14094-111">Sistem automatski spaja neke atribute.</span><span class="sxs-lookup"><span data-stu-id="14094-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="14094-112">Prikaz spojenih atributa</span><span class="sxs-lookup"><span data-stu-id="14094-112">View merged attributes</span></span>

<span data-ttu-id="14094-113">Da biste videli atribute koji su uključeni u jedan od vaših automatski spojenih atributa, izaberite taj spojeni atribut.</span><span class="sxs-lookup"><span data-stu-id="14094-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="14094-114">Dva atributa koja čine taj spojeni atribut prikazuju se u dva nova reda ispod spojenog atributa.</span><span class="sxs-lookup"><span data-stu-id="14094-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="14094-115">![Izbor spojenog atributa](media/configure-data-merge-profile-attributes.png "Izbor spojenog atributa")</span><span class="sxs-lookup"><span data-stu-id="14094-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="14094-116">Odvajanje spojenih atributa</span><span class="sxs-lookup"><span data-stu-id="14094-116">Separate merged attributes</span></span>

<span data-ttu-id="14094-117">Da biste odvojili ili raskinuli bilo koji od automatski spojenih atributa, pronađite atribut u tabeli **Atributi profila**.</span><span class="sxs-lookup"><span data-stu-id="14094-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="14094-118">Izaberite dugme sa tri tačke (...).</span><span class="sxs-lookup"><span data-stu-id="14094-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="14094-119">U padajućoj listi izaberite **Odvoji polja**.</span><span class="sxs-lookup"><span data-stu-id="14094-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="14094-120">Uklanjanje spojenih atributa</span><span class="sxs-lookup"><span data-stu-id="14094-120">Remove merged attributes</span></span>

<span data-ttu-id="14094-121">Da biste izuzeli atribut iz entiteta krajnjeg profila klijenta, pronađite ga u tabeli **Atributi profila**.</span><span class="sxs-lookup"><span data-stu-id="14094-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="14094-122">Izaberite dugme sa tri tačke (...).</span><span class="sxs-lookup"><span data-stu-id="14094-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="14094-123">U padajućoj listi izaberite **Ne objedinjuj**.</span><span class="sxs-lookup"><span data-stu-id="14094-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="14094-124">Atribut je premešten u odeljak **Uklonjeno iz evidencije korisnika**.</span><span class="sxs-lookup"><span data-stu-id="14094-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="14094-125">Ručno dodajte spojeni atribut</span><span class="sxs-lookup"><span data-stu-id="14094-125">Manually add a merged attribute</span></span>

<span data-ttu-id="14094-126">Da biste dodali spojeni atribut, idite na stranicu **Spajanje**.</span><span class="sxs-lookup"><span data-stu-id="14094-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="14094-127">Izaberite **Dodavanje spojenog atributa**.</span><span class="sxs-lookup"><span data-stu-id="14094-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="14094-128">Navedite **Ime** da ga kasnije identifikujete na stranici **Spajanje**.</span><span class="sxs-lookup"><span data-stu-id="14094-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="14094-129">Opcionalno, navedite **Ime za prikaz** koje će se prikazati u objedinjenom entitetu Profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="14094-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="14094-130">Konfigurišite **Izaberite atribute duplikata** da biste izabrali atribute koje želite da spojite iz podudarnih entiteta.</span><span class="sxs-lookup"><span data-stu-id="14094-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="14094-131">Takođe možete da pretražujete atribute.</span><span class="sxs-lookup"><span data-stu-id="14094-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="14094-132">Podesite **Poredak po važnosti** da jedan atribut postavite iznad ostalih.</span><span class="sxs-lookup"><span data-stu-id="14094-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="14094-133">Na primer, ako entitet *WebAccountCSV* uključuje najtačnije podatke o atributu *Puna imena*, možete dati prednost tom entitetu u odnosu na *ContactCSV* tako što ćete izabrati *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="14094-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="14094-134">Kao rezultat, *WebAccountCSV* prelazi na prvi prioritet, dok *ContactCSV* prelazi na drugi prioritet pri povlačenju vrednosti za atribut *Puno ime*.</span><span class="sxs-lookup"><span data-stu-id="14094-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="14094-135">Pokrenite svoje spajanje</span><span class="sxs-lookup"><span data-stu-id="14094-135">Run your merge</span></span>

<span data-ttu-id="14094-136">Bez obzira da li ručno spajate atribute ili puštate sistem da ih spaja, uvek možete pokrenuti spajanje.</span><span class="sxs-lookup"><span data-stu-id="14094-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="14094-137">Izaberite **Pokreni** na stranici **Spajanje** da započnete proces.</span><span class="sxs-lookup"><span data-stu-id="14094-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="14094-138">![Spajanje podataka Sačuvaj i Pokreni](media/configure-data-merge-save-run.png "Spajanje podataka Sačuvaj i Pokreni")</span><span class="sxs-lookup"><span data-stu-id="14094-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="14094-139">Da biste uneli dodatne izmene i ponovo pokrenuli korak, možete otkazati objedinjavanje koje je u toku.</span><span class="sxs-lookup"><span data-stu-id="14094-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="14094-140">Izaberite tekst **Osvežavanje u toku...** i izaberite **Otkaži posao** u bočnom oknu koje se prikazuje.</span><span class="sxs-lookup"><span data-stu-id="14094-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="14094-141">Kada se tekst **Osvežavanje u toku...** promeni u **Uspešno**, objedinjavanje je dovršeno i rešilo kontradikcije u vašim podacima u skladu sa smernicama koje ste definisali.</span><span class="sxs-lookup"><span data-stu-id="14094-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="14094-142">Objedinjeni i neobjedinjeni atributi su uključeni u objedinjeni entitet profila.</span><span class="sxs-lookup"><span data-stu-id="14094-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="14094-143">Izuzeti atributi nisu uključeni u objedinjeni entitet profila.</span><span class="sxs-lookup"><span data-stu-id="14094-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="14094-144">Ako to nije prvi put da ste uspešno izveli objedinjavanje, svi procesi na nižem toku, uključujući obogaćivanje, segmentaciju i mere, automatski će se ponovo pokrenuti.</span><span class="sxs-lookup"><span data-stu-id="14094-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="14094-145">Nakon što su svi procesi na nižem toku ponovo pokrenuti, profili klijenata odražavaju sve vaše izmene.</span><span class="sxs-lookup"><span data-stu-id="14094-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="14094-146">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="14094-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="14094-147">Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="14094-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="14094-148">Možete izabrati status procesa da biste videli detalje o toku celog posla.</span><span class="sxs-lookup"><span data-stu-id="14094-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="14094-149">Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="14094-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="14094-150">Sledeći korak</span><span class="sxs-lookup"><span data-stu-id="14094-150">Next Step</span></span>

<span data-ttu-id="14094-151">Konfigurišite [aktivnosti](activities.md), [obogaćivanje](enrichment-microsoft-graph.md) ili [relacije](relationships.md) da biste ostvarili bolji uvid u klijente.</span><span class="sxs-lookup"><span data-stu-id="14094-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="14094-152">Ako ste već konfigurisali aktivnosti, obogaćivanje ili relacije ili ako ste definisali segmente, oni će se automatski obraditi kako bi se koristili najnoviji podaci o klijentima.</span><span class="sxs-lookup"><span data-stu-id="14094-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]