---
title: Objedinjavanje entiteta kod objedinjavanja podataka
description: Objedinite entitete da biste kreirali objedinjene profile klijenata.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085593"
---
# <a name="merge-entities"></a><span data-ttu-id="d9dda-103">Objedinjavanje entiteta</span><span class="sxs-lookup"><span data-stu-id="d9dda-103">Merge entities</span></span>

<span data-ttu-id="d9dda-104">Faza spajanja je poslednja faza u procesu objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="d9dda-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="d9dda-105">Njegova svrha je usklađivanje neusaglašenih podataka.</span><span class="sxs-lookup"><span data-stu-id="d9dda-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="d9dda-106">Primeri neusaglašenih podataka mogu uključivati korisničko ime koje se nalazi u dva skupa podataka, ali to se prikazuje malo drugačije u svakom („Jovan Dučić“ u odnosu na „Jovo Dučić“) ili telefonski broj koji se razlikuje u formatu (npr. 617-803-091 u odnosu na 617803091).</span><span class="sxs-lookup"><span data-stu-id="d9dda-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="d9dda-107">Spajanje tih neusaglašenih tačaka podataka obavlja se na osnovu poređenja atributa.</span><span class="sxs-lookup"><span data-stu-id="d9dda-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Stranica objedinjavanja u procesu ujednačavanja podataka koja prikazuje tabelu sa objedinjenim poljima koja definišu ujednačeni korisnički profil.":::

<span data-ttu-id="d9dda-109">Kada se dovrši [faza podudaranja](match-entities.md), fazu spajanja započinjete odabirom pločice **Objedini** na stranici **Ujednačavanje**.</span><span class="sxs-lookup"><span data-stu-id="d9dda-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="d9dda-110">Pregled sistemskih preporuka</span><span class="sxs-lookup"><span data-stu-id="d9dda-110">Review system recommendations</span></span>

<span data-ttu-id="d9dda-111">U meniju **Podaci** > **Ujednačavanje** > **Objedinjavanje**, birate i izuzimate atribute za objedinjavanje u okviru vašeg ujednačenog entiteta korisničkog profila.</span><span class="sxs-lookup"><span data-stu-id="d9dda-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="d9dda-112">Ujednačeni korisnički profil je rezultat procesa ujednačavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="d9dda-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="d9dda-113">Sistem automatski spaja neke atribute.</span><span class="sxs-lookup"><span data-stu-id="d9dda-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="d9dda-114">Da biste videli atribute koji su uključeni u jedan od vaših automatski objedinjenih atributa, odaberite taj objedinjeni atribut na kartici **Polja za klijente** tabele.</span><span class="sxs-lookup"><span data-stu-id="d9dda-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="d9dda-115">Atributi koji čine taj objedinjeni atribut prikazaće se u dva nova reda ispod objedinjenog atributa.</span><span class="sxs-lookup"><span data-stu-id="d9dda-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="d9dda-116">Odvojite, preimenujte, izuzmite i uredite objedinjena polja</span><span class="sxs-lookup"><span data-stu-id="d9dda-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="d9dda-117">Možete da promenite način na koji sistem obrađuje objedinjene atribute da generiše ujednačeni korisnički profil.</span><span class="sxs-lookup"><span data-stu-id="d9dda-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="d9dda-118">Izaberite **Prikaži više** i izaberite šta želite da promenite.</span><span class="sxs-lookup"><span data-stu-id="d9dda-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opcije u padajućem meniju „Prikaži više“ za upravljanje objedinjenim atributima.":::

<span data-ttu-id="d9dda-120">Pogledajte sledeće odeljke za više informacija.</span><span class="sxs-lookup"><span data-stu-id="d9dda-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="d9dda-121">Razdvajanje objedinjenih polja</span><span class="sxs-lookup"><span data-stu-id="d9dda-121">Separate merged fields</span></span>

<span data-ttu-id="d9dda-122">Da biste razdvojili objedinjena polja, pronađite atribut u tabeli.</span><span class="sxs-lookup"><span data-stu-id="d9dda-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="d9dda-123">Razdvojena polja se prikazuju kao pojedinačne tačke podataka na objedinjenom korisničkom profilu.</span><span class="sxs-lookup"><span data-stu-id="d9dda-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="d9dda-124">Izaberite objedinjeno polje.</span><span class="sxs-lookup"><span data-stu-id="d9dda-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="d9dda-125">Izaberite **Prikaži više** i birajte **Razdvoji polja**.</span><span class="sxs-lookup"><span data-stu-id="d9dda-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="d9dda-126">Potvrdite razdvajanje.</span><span class="sxs-lookup"><span data-stu-id="d9dda-126">Confirm the separation.</span></span>

1. <span data-ttu-id="d9dda-127">Izaberite **Sačuvaj** i **Pokreni** da biste obradili promene.</span><span class="sxs-lookup"><span data-stu-id="d9dda-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="d9dda-128">Preimenovanje objedinjenih polja</span><span class="sxs-lookup"><span data-stu-id="d9dda-128">Rename merged fields</span></span>

<span data-ttu-id="d9dda-129">Promenite ime za prikaz objedinjenih atributa.</span><span class="sxs-lookup"><span data-stu-id="d9dda-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="d9dda-130">Ne možete da promenite naziv izlaznog entiteta.</span><span class="sxs-lookup"><span data-stu-id="d9dda-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="d9dda-131">Izaberite objedinjeno polje.</span><span class="sxs-lookup"><span data-stu-id="d9dda-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="d9dda-132">Izaberite **Prikaži više** i birajte **Preimenuj**.</span><span class="sxs-lookup"><span data-stu-id="d9dda-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="d9dda-133">Potvrdite promenjeno ime za prikaz.</span><span class="sxs-lookup"><span data-stu-id="d9dda-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="d9dda-134">Izaberite **Sačuvaj** i **Pokreni** da biste obradili promene.</span><span class="sxs-lookup"><span data-stu-id="d9dda-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="d9dda-135">Izuzimanje objedinjenih polja</span><span class="sxs-lookup"><span data-stu-id="d9dda-135">Exclude merged fields</span></span>

<span data-ttu-id="d9dda-136">Izuzmite atribut iz ujednačenog korisničkog profila.</span><span class="sxs-lookup"><span data-stu-id="d9dda-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="d9dda-137">Ako se polje koristi u drugim procesima, na primer u segmentu, uklonite ga iz tih procesa pre nego što ga izuzmete iz korisničkog profila.</span><span class="sxs-lookup"><span data-stu-id="d9dda-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="d9dda-138">Izaberite objedinjeno polje.</span><span class="sxs-lookup"><span data-stu-id="d9dda-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="d9dda-139">Izaberite **Prikaži više** i birajte **Izuzmi**.</span><span class="sxs-lookup"><span data-stu-id="d9dda-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="d9dda-140">Potvrdite izuzimanje.</span><span class="sxs-lookup"><span data-stu-id="d9dda-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="d9dda-141">Izaberite **Sačuvaj** i **Pokreni** da biste obradili promene.</span><span class="sxs-lookup"><span data-stu-id="d9dda-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="d9dda-142">Na stranici **Objedinjavanje**, izaberite **Izuzeta polja** da biste videli listu svih izuzetih polja.</span><span class="sxs-lookup"><span data-stu-id="d9dda-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="d9dda-143">Ovo okno vam omogućava da ponovo dodate izuzeta polja.</span><span class="sxs-lookup"><span data-stu-id="d9dda-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="d9dda-144">Ručno kombinovanje polja</span><span class="sxs-lookup"><span data-stu-id="d9dda-144">Manually combine fields</span></span>

<span data-ttu-id="d9dda-145">Ručno navedite objedinjeni atribut.</span><span class="sxs-lookup"><span data-stu-id="d9dda-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="d9dda-146">Na stranici **Objedinjavanje**, izaberite **Kombinuj polja**.</span><span class="sxs-lookup"><span data-stu-id="d9dda-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="d9dda-147">Navedite **Naziv** i jedan **Naziv izlaznog polja**.</span><span class="sxs-lookup"><span data-stu-id="d9dda-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="d9dda-148">Odaberite polje koje želite da dodate.</span><span class="sxs-lookup"><span data-stu-id="d9dda-148">Choose a field to add.</span></span> <span data-ttu-id="d9dda-149">Izaberite **Dodaj polja** da biste kombinovali više polja.</span><span class="sxs-lookup"><span data-stu-id="d9dda-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="d9dda-150">Potvrdite izuzimanje.</span><span class="sxs-lookup"><span data-stu-id="d9dda-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="d9dda-151">Izaberite **Sačuvaj** i **Pokreni** da biste obradili promene.</span><span class="sxs-lookup"><span data-stu-id="d9dda-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="d9dda-152">Promena redosleda polja</span><span class="sxs-lookup"><span data-stu-id="d9dda-152">Change the order of fields</span></span>

<span data-ttu-id="d9dda-153">Neki entiteti sadrže više detalja od drugih.</span><span class="sxs-lookup"><span data-stu-id="d9dda-153">Some entities contain more details than others.</span></span> <span data-ttu-id="d9dda-154">Ako entitet uključuje najnovije podatke o polju, možete mu dati prioritet nad ostalim entitetima pri objedinjavanju vrednosti.</span><span class="sxs-lookup"><span data-stu-id="d9dda-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="d9dda-155">Izaberite objedinjeno polje.</span><span class="sxs-lookup"><span data-stu-id="d9dda-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="d9dda-156">Izaberite **Prikaži više** i birajte **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="d9dda-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="d9dda-157">U oknu **Kombinuj polja**, izaberite **Pomeri nagore/nadole** da biste postavili redosled ili ih prevucite i ispustite u željeni položaj.</span><span class="sxs-lookup"><span data-stu-id="d9dda-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="d9dda-158">Potvrdite promenu.</span><span class="sxs-lookup"><span data-stu-id="d9dda-158">Confirm the change.</span></span>

1. <span data-ttu-id="d9dda-159">Izaberite **Sačuvaj** i **Pokreni** da biste obradili promene.</span><span class="sxs-lookup"><span data-stu-id="d9dda-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="d9dda-160">Pokrenite svoje spajanje</span><span class="sxs-lookup"><span data-stu-id="d9dda-160">Run your merge</span></span>

<span data-ttu-id="d9dda-161">Bez obzira da li ručno spajate atribute ili puštate sistem da ih spaja, uvek možete pokrenuti spajanje.</span><span class="sxs-lookup"><span data-stu-id="d9dda-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="d9dda-162">Izaberite **Pokreni** na stranici **Spajanje** da započnete proces.</span><span class="sxs-lookup"><span data-stu-id="d9dda-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d9dda-163">![Spajanje podataka Sačuvaj i Pokreni](media/configure-data-merge-save-run.png "Spajanje podataka Sačuvaj i Pokreni")</span><span class="sxs-lookup"><span data-stu-id="d9dda-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="d9dda-164">Odaberite **Pokreni samo objedinjavanje** ako želite da se izlaz odrazi samo u ujednačenom entitetu klijenta.</span><span class="sxs-lookup"><span data-stu-id="d9dda-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="d9dda-165">Posledični procesi će se osvežiti kao [definisani u rasporedu osvežavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d9dda-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="d9dda-166">Odaberite **Pokreni objedinjavanje i posledične procese** da osvežite sistem sa vašim promenama.</span><span class="sxs-lookup"><span data-stu-id="d9dda-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="d9dda-167">Svi procesi, uključujući obogaćivanje, segmente i mere automatski će se ponovo pokrenuti.</span><span class="sxs-lookup"><span data-stu-id="d9dda-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="d9dda-168">Po završetku svih posledičnih procesa, korisnički profili odražavaju sve promene koje ste napravili.</span><span class="sxs-lookup"><span data-stu-id="d9dda-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="d9dda-169">Da biste uneli više promena i ponovo pokrenuli korak, možete da otkažete objedinjavanje u toku.</span><span class="sxs-lookup"><span data-stu-id="d9dda-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="d9dda-170">Izaberite tekst **Osvežavanje u toku...** i izaberite **Otkaži posao** u bočnom oknu koje se prikazuje.</span><span class="sxs-lookup"><span data-stu-id="d9dda-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="d9dda-171">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="d9dda-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d9dda-172">Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d9dda-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d9dda-173">Možete izabrati status procesa da biste videli detalje o toku celog posla.</span><span class="sxs-lookup"><span data-stu-id="d9dda-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d9dda-174">Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="d9dda-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="d9dda-175">Sledeći korak</span><span class="sxs-lookup"><span data-stu-id="d9dda-175">Next Step</span></span>

<span data-ttu-id="d9dda-176">Konfigurišite [aktivnosti](activities.md), [obogaćivanje](enrichment-hub.md) ili [relacije](relationships.md) da biste ostvarili bolji uvid u klijente.</span><span class="sxs-lookup"><span data-stu-id="d9dda-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="d9dda-177">Ako ste već konfigurisali aktivnosti, obogaćivanje ili segmente, oni će se automatski obraditi kako bi se koristili najnoviji podaci o klijentima.</span><span class="sxs-lookup"><span data-stu-id="d9dda-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
