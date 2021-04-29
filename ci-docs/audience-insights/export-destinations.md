---
title: Izvoz podataka iz usluge Customer Insights
description: Upravljajte izvozima da biste delili podatke.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896160"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="2c9d0-103">Pregled izvoza (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="2c9d0-103">Exports (preview) overview</span></span>

<span data-ttu-id="2c9d0-104">Stranica **Izvoz** prikazuje sve konfigurisane izvoze.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="2c9d0-105">Izvozi dele određene podatke sa raznim aplikacijama.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="2c9d0-106">Mogu da uključuju profile klijenata ili entitete, šeme i detalje o mapiranju.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="2c9d0-107">Svaki izvoz zahteva [vezu koju je postavio administrator radi upravljanja potvrdom identiteta i pristupom](connections.md).</span><span class="sxs-lookup"><span data-stu-id="2c9d0-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2c9d0-108">Do marta 2021. godine, izvozi su automatski kreirali vezu sa odgovarajućom uslugom.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="2c9d0-109">Izvozi sada zahtevaju [vezu koju kreira i deli administrator](connections.md) pre nego što budete mogli da ih kreirate.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="2c9d0-110">Idite na **Podaci** > **Izvozi** da biste videli stranicu izvoza.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="2c9d0-111">Sve korisničke uloge imaju pristup za prikaz konfigurisanih izvoza.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="2c9d0-112">Koristite polje za pretragu na komandnoj traci da biste pronalazili izvoze prema njihovom nazivu, nazivu veze ili tipu veze.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="2c9d0-113">Podešavanje novog izvoza</span><span class="sxs-lookup"><span data-stu-id="2c9d0-113">Set up a new export</span></span>

<span data-ttu-id="2c9d0-114">Da biste podesili ili uredili izvoz, moraju vam biti dostupne veze.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="2c9d0-115">Veze zavise od vaše [korisničke uloge](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="2c9d0-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="2c9d0-116">Administratori imaju pristup svim vezama.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-116">Administrators have access to all connections.</span></span> <span data-ttu-id="2c9d0-117">Oni takođe mogu da kreiraju nove veze prilikom podešavanja izvoza.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="2c9d0-118">Saradnici mogu imati pristup određenim vezama.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="2c9d0-119">Oni zavise od administratora da konfigurišu i dele veze.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="2c9d0-120">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2c9d0-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="2c9d0-121">Gledaoci mogu samo da vide postojeće izvoze, ali ne i da ih kreiraju.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="2c9d0-122">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2c9d0-123">Izaberite **Dodaj izvoz** da biste kreirali novo odredište za izvoz.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="2c9d0-124">U oknu **Podešavanje izvoza**, izaberite koju vezu da koristite.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="2c9d0-125">[Vezama](connections.md) upravljaju administratori.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="2c9d0-126">Navedite potrebne detalje i izaberite **Sačuvati** da biste kreirali izvoz.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="2c9d0-127">Uređivanje izvoza</span><span class="sxs-lookup"><span data-stu-id="2c9d0-127">Edit an export</span></span>

1. <span data-ttu-id="2c9d0-128">Izaberite vertikalne tri tačke za odredište za izvoz koje želite da uređujete.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="2c9d0-129">U padajućem meniju izaberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="2c9d0-130">Promenite vrednosti koje želite da ažurirate i izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="2c9d0-131">Prikaz izvoza i detalji o izvozu</span><span class="sxs-lookup"><span data-stu-id="2c9d0-131">View Exports and export details</span></span>

<span data-ttu-id="2c9d0-132">Nakon kreiranja odredišta za izvoz, ona su navedena na stranici **Podaci** > **Izvoz**.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="2c9d0-133">Svi korisnici mogu videti koji se podaci dele i koji je njihov najnoviji status.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="2c9d0-134">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2c9d0-135">Korisnici bez dozvole za uređivanje biraju **Prikaži** umesto **Uredi** da bi videli detalje o izvozu.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="2c9d0-136">Ovo bočno okno prikazuje podešavanje ovog izvoza.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="2c9d0-137">Bez dozvola za uređivanje ne možete menjati vrednosti.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="2c9d0-138">Izaberite **Zatvori** da biste se vratili na stranicu izvoza.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="2c9d0-139">Pokretanje izvoza na zahtev</span><span class="sxs-lookup"><span data-stu-id="2c9d0-139">Run exports on demand</span></span>

<span data-ttu-id="2c9d0-140">Nakon konfigurisanja, izvoz će se pokrenuti sa svakim [zakazanim osvežavanjem](system.md#schedule-tab) sve dok ima funkcionalnu vezu.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="2c9d0-141">Da biste izvezli podatke bez čekanja na zakazano osvežavanje, idite na stranicu **Podaci** > **Izvoz**.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="2c9d0-142">Na raspolaganju su vam dve opcije:</span><span class="sxs-lookup"><span data-stu-id="2c9d0-142">You have two options:</span></span>

- <span data-ttu-id="2c9d0-143">Da biste pokrenuli sve izvoze, izaberite **Pokreni sve** u komandnoj traci.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="2c9d0-144">Da biste pokrenuli pojedinačni izvoz, izaberite tri tačke (...) na stavci liste, a zatim odaberite **Pokreni**.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="2c9d0-145">Uklanjanje izvoza</span><span class="sxs-lookup"><span data-stu-id="2c9d0-145">Remove an Export</span></span>

1. <span data-ttu-id="2c9d0-146">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2c9d0-147">Odaberite vertikalne tri tačke za izvoz koji želite da uklonite.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="2c9d0-148">Izaberite **Ukloni** iz padajućeg menija.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="2c9d0-149">Potvrdite uklanjanje odabirom **Ukloni** na ekranu za potvrdu.</span><span class="sxs-lookup"><span data-stu-id="2c9d0-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
