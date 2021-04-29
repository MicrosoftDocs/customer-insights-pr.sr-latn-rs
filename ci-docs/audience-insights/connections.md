---
title: Veze sa ostalim uslugama iz usluge Customer Insights.
description: Podelite podatke sa drugim uslugama.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896114"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="705bd-103">Pregled veza (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="705bd-103">Connections (preview) overview</span></span>

<span data-ttu-id="705bd-104">Veze su ključ za omogućavanje deljenja podataka u uslugu Customer Insights i iz nje.</span><span class="sxs-lookup"><span data-stu-id="705bd-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="705bd-105">Svaka veza uspostavlja deljenje podataka sa određenom uslugom.</span><span class="sxs-lookup"><span data-stu-id="705bd-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="705bd-106">Veze su temelj da [konfigurišete obogaćivanja trećih strana](enrichment-hub.md) i [konfigurisanje izvoza](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="705bd-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="705bd-107">Ista veza se može koristiti više puta.</span><span class="sxs-lookup"><span data-stu-id="705bd-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="705bd-108">Na primer, jedna veza sa uslugom Dynamics 365 Marketing funkcioniše za više izvoza, a jedna Leadspace veza može se koristiti za nekoliko obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="705bd-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="705bd-109">Idite na **Administrator** > **Veze** da biste kreirali i prikazali veze.</span><span class="sxs-lookup"><span data-stu-id="705bd-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="705bd-110">Na kartici **Veze** prikazuju se sve aktivne veze.</span><span class="sxs-lookup"><span data-stu-id="705bd-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="705bd-111">Lista prikazuje red za svaku vezu.</span><span class="sxs-lookup"><span data-stu-id="705bd-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="705bd-112">Preuzmite brzi pregled, opis i saznajte šta možete učiniti sa svakom opcijom proširivosti na kartici **Otkrivanje**.</span><span class="sxs-lookup"><span data-stu-id="705bd-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="705bd-113">Izvozi</span><span class="sxs-lookup"><span data-stu-id="705bd-113">Exports</span></span>

<span data-ttu-id="705bd-114">Samo administratori mogu da konfigurišu nove veze, ali mogu da daju pristup saradnicima da koriste postojeće veze.</span><span class="sxs-lookup"><span data-stu-id="705bd-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="705bd-115">Administratori kontrolišu kuda podaci mogu da idu, saradnici definišu korisne podatke i učestalost u skladu sa svojim potrebama.</span><span class="sxs-lookup"><span data-stu-id="705bd-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="705bd-116">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="705bd-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="705bd-117">Obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="705bd-117">Enrichments</span></span>

<span data-ttu-id="705bd-118">Samo administratori mogu da konfigurišu nove veze, ali kreirane veze su uvek dostupne i administratorima i saradnicima.</span><span class="sxs-lookup"><span data-stu-id="705bd-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="705bd-119">Administratori upravljaju akreditivima i daju saglasnost za prenos podataka.</span><span class="sxs-lookup"><span data-stu-id="705bd-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="705bd-120">Veze tada mogu da koriste administratori i saradnici za obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="705bd-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="705bd-121">Dodavanje nove veze</span><span class="sxs-lookup"><span data-stu-id="705bd-121">Add a new connection</span></span>

<span data-ttu-id="705bd-122">Da biste dodali veze, morate da imate [administratorske dozvole](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="705bd-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="705bd-123">Ako se povežete sa drugim Microsoft uslugama, pretpostavljamo da su obe usluge u istoj organizaciji.</span><span class="sxs-lookup"><span data-stu-id="705bd-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="705bd-124">Idite na **Administrator** > **Veze (pregled)**.</span><span class="sxs-lookup"><span data-stu-id="705bd-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="705bd-125">Idite na karticu **Veze**.</span><span class="sxs-lookup"><span data-stu-id="705bd-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="705bd-126">Izaberite **Dodaj vezu** da biste kreirali novu vezu.</span><span class="sxs-lookup"><span data-stu-id="705bd-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="705bd-127">Odaberite iz padajućeg menija koju vrstu veze želite da kreirate.</span><span class="sxs-lookup"><span data-stu-id="705bd-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="705bd-128">U oknu **Podešavanje veze**, navedite potrebne detalje.</span><span class="sxs-lookup"><span data-stu-id="705bd-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="705bd-129">**Ime za prikaz** i vrsta veze opisuju vezu.</span><span class="sxs-lookup"><span data-stu-id="705bd-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="705bd-130">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj ove veze.</span><span class="sxs-lookup"><span data-stu-id="705bd-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="705bd-131">Tačna polja zavise od usluge na koju se povezujete.</span><span class="sxs-lookup"><span data-stu-id="705bd-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="705bd-132">Više o detaljima određenog tipa veze možete saznati u članku o ciljnoj usluzi.</span><span class="sxs-lookup"><span data-stu-id="705bd-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="705bd-133">Da biste kreirali vezu, izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="705bd-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="705bd-134">Takođe možete da izaberete **Podešavanje** na pločici na kartici **Otkrivanje**.</span><span class="sxs-lookup"><span data-stu-id="705bd-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="705bd-135">Dozvolite saradnicima da koriste vezu za izvoz</span><span class="sxs-lookup"><span data-stu-id="705bd-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="705bd-136">Kada podešavate ili uređujete vezu za izvoz, vi birate koji korisnici smeju da koriste ovu određenu vezu za definisanje [izvoza](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="705bd-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="705bd-137">Podrazumevano je veza dostupna korisnicima sa administratorskom ulogom.</span><span class="sxs-lookup"><span data-stu-id="705bd-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="705bd-138">Ovo podešavanje možete promeniti u delu **Izaberite ko može da koristi ovu vezu** i dozvolite korisnicima sa ulogom saradnika da koriste ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="705bd-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="705bd-139">Saradnici neće moći da vide ili izmene vezu.</span><span class="sxs-lookup"><span data-stu-id="705bd-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="705bd-140">Videće samo ime za prikaz i tip veze prilikom kreiranja izvoza.</span><span class="sxs-lookup"><span data-stu-id="705bd-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="705bd-141">Deljenjem veze omogućavate saradnicima da je koriste.</span><span class="sxs-lookup"><span data-stu-id="705bd-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="705bd-142">Saradnici će videti zajedničke veze kada uspostave izvoz.</span><span class="sxs-lookup"><span data-stu-id="705bd-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="705bd-143">Oni mogu upravljati svakim izvozom koji koristi ovu specifičnu vezu.</span><span class="sxs-lookup"><span data-stu-id="705bd-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="705bd-144">Možete da promenite ovo podešavanje, a da zadržite izvoz koji su već definisali saradnici.</span><span class="sxs-lookup"><span data-stu-id="705bd-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="705bd-145">Uređivanje veze</span><span class="sxs-lookup"><span data-stu-id="705bd-145">Edit a connection</span></span>

1. <span data-ttu-id="705bd-146">Idite na **Administrator** > **Veze (pregled)**.</span><span class="sxs-lookup"><span data-stu-id="705bd-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="705bd-147">Idite na karticu **Veze**.</span><span class="sxs-lookup"><span data-stu-id="705bd-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="705bd-148">Izaberite vertikalne tri tačke za vezu koju želite da uredite.</span><span class="sxs-lookup"><span data-stu-id="705bd-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="705bd-149">Izaberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="705bd-149">Select **Edit**.</span></span>

1. <span data-ttu-id="705bd-150">Promenite vrednosti koje želite da ažurirate i izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="705bd-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="705bd-151">Uklanjanje veze</span><span class="sxs-lookup"><span data-stu-id="705bd-151">Remove a connection</span></span>

<span data-ttu-id="705bd-152">Ako se veza koju uklanjate koristi za obogaćivanje ili izvoz, prvo ih morate odvojiti ili ukloniti.</span><span class="sxs-lookup"><span data-stu-id="705bd-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="705bd-153">Dijalog za uklanjanje vodiće vas do relevantnih obogaćivanja ili izvoza.</span><span class="sxs-lookup"><span data-stu-id="705bd-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="705bd-154">Odvojena obogaćivanja i izvozi postaju neaktivni.</span><span class="sxs-lookup"><span data-stu-id="705bd-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="705bd-155">Ponovo ih aktivirate dodavanjem druge veze sa njima na stranici [Obogaćivanja](enrichment-hub.md) ili [Izvozi](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="705bd-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="705bd-156">Idite na **Administrator** > **Veze (pregled)**.</span><span class="sxs-lookup"><span data-stu-id="705bd-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="705bd-157">Idite na karticu **Veze**.</span><span class="sxs-lookup"><span data-stu-id="705bd-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="705bd-158">Izaberite vertikalne tri tačke za vezu koju želite da uklonite.</span><span class="sxs-lookup"><span data-stu-id="705bd-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="705bd-159">Izaberite **Ukloni** iz padajućeg menija.</span><span class="sxs-lookup"><span data-stu-id="705bd-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="705bd-160">Prikazuje se dijalog za potvrdu.</span><span class="sxs-lookup"><span data-stu-id="705bd-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="705bd-161">Ako postoje obogaćivanja ili izvozi koji koriste ovu vezu, izaberite dugme da biste videli šta koristi vezu.</span><span class="sxs-lookup"><span data-stu-id="705bd-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="705bd-162">**Izvozi:** Možete da uklonite ili prekinete izvoz kako biste mogli da uklonite vezu.</span><span class="sxs-lookup"><span data-stu-id="705bd-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="705bd-163">Da bi prekinuli izvoz, administratori mogu da koriste radnju **Prekini vezu**.</span><span class="sxs-lookup"><span data-stu-id="705bd-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="705bd-164">Ova radnja je dostupna za pojedinačne i višestruko izabrane izvoze.</span><span class="sxs-lookup"><span data-stu-id="705bd-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="705bd-165">Prekidom veze zadržavate konfiguraciju izvoza, ali ona se neće pokrenuti dok joj se ne doda druga veza.</span><span class="sxs-lookup"><span data-stu-id="705bd-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="705bd-166">**Obogaćivanja:** Možete da uklonite ili deaktivirate obogaćivanja kako biste mogli da uklonite vezu.</span><span class="sxs-lookup"><span data-stu-id="705bd-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="705bd-167">Kada veza nema više zavisnosti, vratite se na **Administrator** > **Veze** i pokušajte ponovo da uklonite vezu.</span><span class="sxs-lookup"><span data-stu-id="705bd-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="705bd-168">Da biste potvrdili brisanje, izaberite **Ukloni**.</span><span class="sxs-lookup"><span data-stu-id="705bd-168">To confirm the deletion select **Remove**.</span></span>

