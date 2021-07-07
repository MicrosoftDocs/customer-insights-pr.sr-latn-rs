---
title: Prikaz profila klijenata
description: Steknite kombinovani prikaz objedinjenih podataka o klijentima.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: c9adb4d7db74573d0512ae7a68a0e7ab51c994a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304621"
---
# <a name="customer-profiles"></a><span data-ttu-id="750bf-103">Profili klijenata</span><span class="sxs-lookup"><span data-stu-id="750bf-103">Customer profiles</span></span>

<span data-ttu-id="750bf-104">Stranica **Klijenti** prikazuje kombinovani prikaz vaših klijenata na osnovu podataka sa profila prikupljenih iz [svih izvora podataka](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="750bf-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="750bf-105">Profili klijenata su vam dostupni nakon što ste [kreirali objedinjeni entitet Klijent](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="750bf-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="750bf-106">Obavezno dovršite postupak objedinjavanja podataka da biste stekli bogatije poglede svojih klijenata.</span><span class="sxs-lookup"><span data-stu-id="750bf-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="750bf-107">Ova stranica takođe vam omogućava da pretražujete klijente.</span><span class="sxs-lookup"><span data-stu-id="750bf-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="750bf-108">Klijenti mogu biti pojedinci ili organizacije (pregled).</span><span class="sxs-lookup"><span data-stu-id="750bf-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="750bf-109">Svaki profil klijenta ili organizacije predstavljen je pločicom.</span><span class="sxs-lookup"><span data-stu-id="750bf-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="750bf-110">Izaberite pločicu da biste videli dodatne informacije o tom konkretnom klijentu ili organizaciji.</span><span class="sxs-lookup"><span data-stu-id="750bf-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="750bf-111">Upotrebite kontrole za straničenje na dnu stranice da biste videli dodatne zapise.</span><span class="sxs-lookup"><span data-stu-id="750bf-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="750bf-112">![B2C profili klijenata](media/profiles-customers.png "B2C profili klijenata")</span><span class="sxs-lookup"><span data-stu-id="750bf-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="750bf-113">Organizacije (Pregled)</span><span class="sxs-lookup"><span data-stu-id="750bf-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="750bf-114">![B2B profili klijenata](media/profile-customers-b2b.png "B2B profili klijenata")</span><span class="sxs-lookup"><span data-stu-id="750bf-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="750bf-115">Ako ne možete da vidite pločice kada izaberete **Klijenti** u navigaciji, vaš administrator treba da [definiši barem jedan atribut se može da se pretražuje](search-filter-index.md) u odeljku **Indeks pretrage i filtriranja**.</span><span class="sxs-lookup"><span data-stu-id="750bf-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="750bf-116">Pretraga klijenata</span><span class="sxs-lookup"><span data-stu-id="750bf-116">Search for customers</span></span>

<span data-ttu-id="750bf-117">Pretražujte klijente unosom imena ili nekog drugog atributa u polje za pretragu.</span><span class="sxs-lookup"><span data-stu-id="750bf-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="750bf-118">Pretraživanje funkcioniše samo u entitetu Profil klijenta koji je kreiran tokom procesa objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="750bf-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="750bf-119">Kao administrator, možete konfigurisati atribute pretraživanja koristeći stranicu **Indeks pretrage i filtriranja**.</span><span class="sxs-lookup"><span data-stu-id="750bf-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="750bf-120">Za više informacija, pogledajte [Upravljajte indeksom pretrage i filtriranja](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="750bf-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="750bf-121">Filtriranje klijenata</span><span class="sxs-lookup"><span data-stu-id="750bf-121">Filter customers</span></span>

<span data-ttu-id="750bf-122">Možete filtrirati klijente po poljima entiteta Profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="750bf-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="750bf-123">Slično pretraživanju, vaš administrator će prvo morati da definiše polja tako da se mogu filtrirati na stranici **Indeks pretrage i filtriranja**.</span><span class="sxs-lookup"><span data-stu-id="750bf-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="750bf-124">Izaberite **Filter** na stranici **Klijenti**.</span><span class="sxs-lookup"><span data-stu-id="750bf-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="750bf-125">Označite polja pored atributa po kojima želite da filtrirate klijente.</span><span class="sxs-lookup"><span data-stu-id="750bf-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="750bf-126">![Profili klijenata](media/profiles-customers3.png "Profili klijenata")</span><span class="sxs-lookup"><span data-stu-id="750bf-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="750bf-127">Uklonite filtere izborom **Obriši filtere** na stranici **Klijenti**.</span><span class="sxs-lookup"><span data-stu-id="750bf-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="750bf-128">Stranica sa detaljima o klijentima</span><span class="sxs-lookup"><span data-stu-id="750bf-128">Customer details page</span></span>

<span data-ttu-id="750bf-129">Izaberite bilo koju pločicu klijenta da biste otvorili **stranicu sa detaljima o klijentu**.</span><span class="sxs-lookup"><span data-stu-id="750bf-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="750bf-130">Ovaj prikaz sadrži objedinjene informacije za izabranog klijenta.</span><span class="sxs-lookup"><span data-stu-id="750bf-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="750bf-131">Detalji o klijentu obuhvataju:</span><span class="sxs-lookup"><span data-stu-id="750bf-131">Customer details include:</span></span>

-   <span data-ttu-id="750bf-132">**Pločica profila klijenta**: Ova pločica prikazuje različite vrednosti iz entiteta objedinjenog profila klijenta.</span><span class="sxs-lookup"><span data-stu-id="750bf-132">**Customer profile tile**: This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="750bf-133">Ovi detalji mogu da uključuju adresu e-pošte, ime, grad itd.</span><span class="sxs-lookup"><span data-stu-id="750bf-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="750bf-134">**Potencijalna interesovanja, potencijalni brendovi**: Pokazuje da li ste konfigurisali direktno obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="750bf-134">**Potential interests, potential brands**: Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="750bf-135">Predstavlja potencijalna interesovanja i afinitete za brendove koje ima klijent sa profilom sličnim ovom klijentu.</span><span class="sxs-lookup"><span data-stu-id="750bf-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="750bf-136">Za više informacija, pogledajte [Obogaćivanje profila klijenata afinitetima prema brendovima i interesovanjima](enrichment-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="750bf-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft.md).</span></span>

-   <span data-ttu-id="750bf-137">**Mere**: Pokazuje da li ste konfigurisali jednu ili više mera određene vrste: mere atributa klijenta.</span><span class="sxs-lookup"><span data-stu-id="750bf-137">**Measures**: Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="750bf-138">Uključuju izračunate KPI-jeve oko vaših klijenata na nivou pojedinačnog klijenta.</span><span class="sxs-lookup"><span data-stu-id="750bf-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="750bf-139">Za više informacija pogledajte [Definisanje i upravljanje merama](measures.md).</span><span class="sxs-lookup"><span data-stu-id="750bf-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="750bf-140">**Vremenska osa aktivnosti**: Pokazuje da li ste konfigurisali aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="750bf-140">**Activity timeline**: Shows if you have configured activities.</span></span> <span data-ttu-id="750bf-141">Prikaz vremenske ose sadrži hronološki sortirane aktivnosti ovog klijenta, počev od najnovije aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="750bf-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="750bf-142">Za više informacija pogledajte [aktivnosti klijenta](activities.md).</span><span class="sxs-lookup"><span data-stu-id="750bf-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="750bf-143">Izaberite **Povratak na klijente** da biste se vratili na stranicu za pretragu klijenata.</span><span class="sxs-lookup"><span data-stu-id="750bf-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="750bf-144">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="750bf-144">Next steps</span></span>

<span data-ttu-id="750bf-145">[Dodajte još izvora podataka](data-sources.md) ili [kreirajte segmente klijenata](segments.md).</span><span class="sxs-lookup"><span data-stu-id="750bf-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
