---
title: Izvoz podataka iz usluge Customer Insights
description: Upravljajte izvozima da biste delili podatke.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016653"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="8617e-103">Pregled izvoza (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="8617e-103">Exports (preview) overview</span></span>

<span data-ttu-id="8617e-104">Stranica **Izvoz** prikazuje sve konfigurisane izvoze.</span><span class="sxs-lookup"><span data-stu-id="8617e-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="8617e-105">Izvozi dele određene podatke sa raznim aplikacijama.</span><span class="sxs-lookup"><span data-stu-id="8617e-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="8617e-106">Mogu da uključuju profile klijenata ili entitete, šeme i detalje o mapiranju.</span><span class="sxs-lookup"><span data-stu-id="8617e-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="8617e-107">Svaki izvoz zahteva [vezu koju je postavio administrator radi upravljanja potvrdom identiteta i pristupom](connections.md).</span><span class="sxs-lookup"><span data-stu-id="8617e-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="8617e-108">Idite na **Podaci** > **Izvozi** da biste videli stranicu izvoza.</span><span class="sxs-lookup"><span data-stu-id="8617e-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="8617e-109">Sve korisničke uloge imaju pristup za prikaz konfigurisanih izvoza.</span><span class="sxs-lookup"><span data-stu-id="8617e-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="8617e-110">Koristite polje za pretragu na komandnoj traci da biste pronalazili izvoze prema njihovom nazivu, nazivu veze ili tipu veze.</span><span class="sxs-lookup"><span data-stu-id="8617e-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="8617e-111">Podešavanje novog izvoza</span><span class="sxs-lookup"><span data-stu-id="8617e-111">Set up a new export</span></span>

<span data-ttu-id="8617e-112">Da biste podesili ili uredili izvoz, moraju vam biti dostupne veze.</span><span class="sxs-lookup"><span data-stu-id="8617e-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="8617e-113">Veze zavise od vaše [korisničke uloge](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="8617e-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="8617e-114">Administratori imaju pristup svim vezama.</span><span class="sxs-lookup"><span data-stu-id="8617e-114">Administrators have access to all connections.</span></span> <span data-ttu-id="8617e-115">Oni takođe mogu da kreiraju nove veze prilikom podešavanja izvoza.</span><span class="sxs-lookup"><span data-stu-id="8617e-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="8617e-116">Saradnici mogu imati pristup određenim vezama.</span><span class="sxs-lookup"><span data-stu-id="8617e-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="8617e-117">Oni zavise od administratora da konfigurišu i dele veze.</span><span class="sxs-lookup"><span data-stu-id="8617e-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="8617e-118">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8617e-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="8617e-119">Gledaoci mogu samo da vide postojeće izvoze, ali ne i da ih kreiraju.</span><span class="sxs-lookup"><span data-stu-id="8617e-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="8617e-120">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="8617e-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8617e-121">Izaberite **Dodaj izvoz** da biste kreirali novo odredište za izvoz.</span><span class="sxs-lookup"><span data-stu-id="8617e-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="8617e-122">U oknu **Podešavanje izvoza**, izaberite koju vezu da koristite.</span><span class="sxs-lookup"><span data-stu-id="8617e-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="8617e-123">[Vezama](connections.md) upravljaju administratori.</span><span class="sxs-lookup"><span data-stu-id="8617e-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="8617e-124">Navedite potrebne detalje i izaberite **Sačuvati** da biste kreirali izvoz.</span><span class="sxs-lookup"><span data-stu-id="8617e-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="8617e-125">Uređivanje izvoza</span><span class="sxs-lookup"><span data-stu-id="8617e-125">Edit an export</span></span>

1. <span data-ttu-id="8617e-126">Izaberite vertikalne tri tačke za odredište za izvoz koje želite da uređujete.</span><span class="sxs-lookup"><span data-stu-id="8617e-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="8617e-127">U padajućem meniju izaberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="8617e-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="8617e-128">Promenite vrednosti koje želite da ažurirate i izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="8617e-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="8617e-129">Prikaz izvoza i detalji o izvozu</span><span class="sxs-lookup"><span data-stu-id="8617e-129">View Exports and export details</span></span>

<span data-ttu-id="8617e-130">Nakon kreiranja odredišta za izvoz, ona su navedena na stranici **Podaci** > **Izvoz**.</span><span class="sxs-lookup"><span data-stu-id="8617e-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="8617e-131">Svi korisnici mogu videti koji se podaci dele i koji je njihov najnoviji status.</span><span class="sxs-lookup"><span data-stu-id="8617e-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="8617e-132">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="8617e-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8617e-133">Korisnici bez dozvole za uređivanje biraju **Prikaži** umesto **Uredi** da bi videli detalje o izvozu.</span><span class="sxs-lookup"><span data-stu-id="8617e-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="8617e-134">Ovo bočno okno prikazuje podešavanje ovog izvoza.</span><span class="sxs-lookup"><span data-stu-id="8617e-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="8617e-135">Bez dozvola za uređivanje ne možete menjati vrednosti.</span><span class="sxs-lookup"><span data-stu-id="8617e-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="8617e-136">Izaberite **Zatvori** da biste se vratili na stranicu izvoza.</span><span class="sxs-lookup"><span data-stu-id="8617e-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="8617e-137">Pokretanje izvoza na zahtev</span><span class="sxs-lookup"><span data-stu-id="8617e-137">Run exports on demand</span></span>

<span data-ttu-id="8617e-138">Nakon konfigurisanja, izvoz će se pokrenuti sa svakim [zakazanim osvežavanjem](system.md#schedule-tab) sve dok ima funkcionalnu vezu.</span><span class="sxs-lookup"><span data-stu-id="8617e-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="8617e-139">Da biste izvezli podatke bez čekanja na zakazano osvežavanje, idite na stranicu **Podaci** > **Izvoz**.</span><span class="sxs-lookup"><span data-stu-id="8617e-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="8617e-140">Na raspolaganju su vam dve opcije:</span><span class="sxs-lookup"><span data-stu-id="8617e-140">You have two options:</span></span>

- <span data-ttu-id="8617e-141">Da biste pokrenuli sve izvoze, izaberite **Pokreni sve** u komandnoj traci.</span><span class="sxs-lookup"><span data-stu-id="8617e-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="8617e-142">Da biste pokrenuli pojedinačni izvoz, izaberite tri tačke (...) na stavci liste, a zatim odaberite **Pokreni**.</span><span class="sxs-lookup"><span data-stu-id="8617e-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="8617e-143">Uklanjanje izvoza</span><span class="sxs-lookup"><span data-stu-id="8617e-143">Remove an Export</span></span>

1. <span data-ttu-id="8617e-144">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="8617e-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8617e-145">Odaberite vertikalne tri tačke za izvoz koji želite da uklonite.</span><span class="sxs-lookup"><span data-stu-id="8617e-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="8617e-146">Izaberite **Ukloni** iz padajućeg menija.</span><span class="sxs-lookup"><span data-stu-id="8617e-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="8617e-147">Potvrdite uklanjanje odabirom **Ukloni** na ekranu za potvrdu.</span><span class="sxs-lookup"><span data-stu-id="8617e-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
