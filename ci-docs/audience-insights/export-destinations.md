---
title: Izvoz podataka iz usluge Customer Insights
description: Upravljajte izvozima da biste delili podatke.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305495"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="0d3cb-103">Pregled izvoza (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="0d3cb-103">Exports (preview) overview</span></span>

<span data-ttu-id="0d3cb-104">Stranica **Izvoz** prikazuje sve konfigurisane izvoze.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="0d3cb-105">Izvozi dele određene podatke sa raznim aplikacijama.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="0d3cb-106">Mogu da uključuju profile klijenata ili entitete, šeme i detalje o mapiranju.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="0d3cb-107">Svaki izvoz zahteva [vezu koju je postavio administrator radi upravljanja potvrdom identiteta i pristupom](connections.md).</span><span class="sxs-lookup"><span data-stu-id="0d3cb-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="0d3cb-108">Idite na **Podaci** > **Izvozi** da biste videli stranicu izvoza.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="0d3cb-109">Sve korisničke uloge mogu pregledati konfigurisane izvoze.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-109">All user roles can view configured exports.</span></span> <span data-ttu-id="0d3cb-110">Koristite polje za pretragu na komandnoj traci da biste pronašli izvoze prema njihovom nazivu, nazivu veze ili tipu veze.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="0d3cb-111">Podešavanje novog izvoza</span><span class="sxs-lookup"><span data-stu-id="0d3cb-111">Set up a new export</span></span>

<span data-ttu-id="0d3cb-112">Da biste podesili ili uredili izvoz, moraju vam biti dostupne veze.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="0d3cb-113">Veze zavise od vaše [korisničke uloge](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="0d3cb-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="0d3cb-114">Administratori imaju pristup svim vezama.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-114">Administrators have access to all connections.</span></span> <span data-ttu-id="0d3cb-115">Oni takođe mogu da kreiraju nove veze prilikom podešavanja izvoza.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="0d3cb-116">Saradnici mogu imati pristup određenim vezama.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="0d3cb-117">Oni zavise od administratora da konfigurišu i dele veze.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="0d3cb-118">Lista izvoza u koloni **Vaše dozvole** pokazuje saradnicima da li mogu da uređuju ili samo prikazuju izvoz.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="0d3cb-119">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0d3cb-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="0d3cb-120">Gledaoci mogu samo da vide postojeće izvoze, ali ne i da ih kreiraju.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="0d3cb-121">Definisanje novog izvoza</span><span class="sxs-lookup"><span data-stu-id="0d3cb-121">Define a new export</span></span>

1. <span data-ttu-id="0d3cb-122">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0d3cb-123">Izaberite **Dodaj izvoz** da biste kreirali novi izvoz.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="0d3cb-124">U oknu **Podešavanje izvoza**, izaberite koju vezu da koristite.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="0d3cb-125">[Vezama](connections.md) upravljaju administratori.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="0d3cb-126">Navedite potrebne detalje i izaberite **Sačuvati** da biste kreirali izvoz.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="0d3cb-127">Definišite novi izvoz na osnovu postojećeg izvoza</span><span class="sxs-lookup"><span data-stu-id="0d3cb-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="0d3cb-128">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0d3cb-129">Na listi izvoza, izaberite izvoz koji želite da duplirate.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="0d3cb-130">Izaberite **Napravi duplikat** u komandnoj traci da biste otvorili okno **Podešavanje izvoza** sa detaljima izabranog izvoza.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="0d3cb-131">Pregledajte i prilagodite izvoz i izaberite **Sačuvaj** da biste kreirali novi izvoz.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="0d3cb-132">Uređivanje izvoza</span><span class="sxs-lookup"><span data-stu-id="0d3cb-132">Edit an export</span></span>

1. <span data-ttu-id="0d3cb-133">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0d3cb-134">Na listi izvoza, izaberite izvoz koji želite da uređujete.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="0d3cb-135">Na komandnoj traci izaberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="0d3cb-136">Promenite vrednosti koje želite da ažurirate i izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="0d3cb-137">Prikaz izvoza i detalji o izvozu</span><span class="sxs-lookup"><span data-stu-id="0d3cb-137">View exports and export details</span></span>

<span data-ttu-id="0d3cb-138">Nakon kreiranja odredišta za izvoz, ona su navedena na stranici **Podaci** > **Izvoz**.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="0d3cb-139">Svi korisnici mogu videti koji se podaci dele i koji je njihov najnoviji status.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="0d3cb-140">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0d3cb-141">Korisnici bez dozvole za uređivanje biraju **Prikaz** umesto **Uređivanje** da videli detalje o izvozu.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="0d3cb-142">Bočno okno prikazuje konfiguraciju izvoza.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="0d3cb-143">Bez dozvola za uređivanje ne možete menjati vrednosti.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="0d3cb-144">Izaberite **Zatvori** da biste se vratili na stranicu izvoza.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="0d3cb-145">Planiranje i pokretanje izvoza</span><span class="sxs-lookup"><span data-stu-id="0d3cb-145">Schedule and run exports</span></span>

<span data-ttu-id="0d3cb-146">Svaki izvoz koji konfigurišete ima raspored osvežavanja.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="0d3cb-147">Tokom osvežavanja, sistem traži nove ili ažurirane podatke koje će uključiti u izvoz.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="0d3cb-148">Podrazumevano se izvozi kao deo svakog [zakazanog osvežavanja sistema](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0d3cb-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0d3cb-149">Možete prilagoditi raspored osvežavanja ili ga isključiti za ručno pokretanje izvoza.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="0d3cb-150">Rasporedi izvoza zavise od statusa vašeg okruženja.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="0d3cb-151">Ako su u toku ažuriranja [zavisnih elemenata](system.md#refresh-policies) kada treba da započne planirani izvoz, sistem će prvo dovršiti ažuriranja, a zatim pokrenuti izvoz.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="0d3cb-152">U koloni **Osveženo** možete videti kada je izvoz poslednji put osvežen.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="0d3cb-153">Raspored izvoza</span><span class="sxs-lookup"><span data-stu-id="0d3cb-153">Schedule exports</span></span>

<span data-ttu-id="0d3cb-154">Možete da definišete prilagođene rasporede osvežavanja za pojedinačne izvoze ili nekoliko izvoza odjednom.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="0d3cb-155">Trenutno definisani raspored naveden je u koloni **Raspored** liste izvoza.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="0d3cb-156">Dozvola za promenu rasporeda je ista kao i za [uređivanje i definisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0d3cb-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="0d3cb-157">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0d3cb-158">Izaberite izvoz koji želite da zakažete.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="0d3cb-159">Na komandnoj traci izaberite **Zakaži**.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="0d3cb-160">U oknu **Zakazivanje izvoza**, podesite **Izvršavanje rasporeda** na **Uključeno** da biste automatski pokretali izvoz.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="0d3cb-161">Podesite na **Isključeno** da biste ga ručno osvežavali.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="0d3cb-162">Da biste automatski osvežavali izvoze, odaberite vrednost **Ponavljanje** i navedite detalje za nju.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="0d3cb-163">Definisano vreme se odnosi na sve slučajeve ponavljanja.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="0d3cb-164">To je vreme kada bi izvoz trebalo da počne da se osvežava.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="0d3cb-165">Primenite i aktivirajte promene izborom **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="0d3cb-166">Kada uređujete raspored za nekoliko izvoza, potrebno je da napravite izbor pod **Zadržite ili izmenite rasporede**:</span><span class="sxs-lookup"><span data-stu-id="0d3cb-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="0d3cb-167">**Zadržite pojedinačne rasporede**: Zadržite prethodno definisani raspored za izabrane izvoze i samo ih onemogućite ili omogućite.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="0d3cb-168">**Definišite novi raspored za sve izabrane izvoze**: Izmenite postojeće rasporede izabranih izvoza.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="0d3cb-169">Pokretanje izvoza na zahtev</span><span class="sxs-lookup"><span data-stu-id="0d3cb-169">Run exports on demand</span></span>

<span data-ttu-id="0d3cb-170">Da biste izvezli podatke bez čekanja na zakazano osvežavanje, idite na stranicu **Podaci** > **Izvoz**.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="0d3cb-171">Da biste pokrenuli sve izvoze, izaberite **Pokreni sve** u komandnoj traci.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="0d3cb-172">Ova radnja će pokretati samo izvoze koji imaju aktivan raspored.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="0d3cb-173">Da biste pokrenuli jedan izvoz, izaberite ga na listi i izaberite **Pokreni** u komandnoj traci.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="0d3cb-174">Tako pokrećete izvoze bez aktivnog rasporeda.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="0d3cb-175">Uklanjanje izvoza</span><span class="sxs-lookup"><span data-stu-id="0d3cb-175">Remove an Export</span></span>

1. <span data-ttu-id="0d3cb-176">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0d3cb-177">Izaberite izvoz koji želite da uklonite.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="0d3cb-178">Izaberite **Ukloni** na komandnoj traci.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="0d3cb-179">Potvrdite uklanjanje odabirom **Ukloni** na ekranu za potvrdu.</span><span class="sxs-lookup"><span data-stu-id="0d3cb-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
