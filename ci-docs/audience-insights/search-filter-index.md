---
title: Pretraga i filtriranje profila klijenata
description: Brzo pronađite informacije o objedinjenim profilima klijenata i filtrirajte prema određenim atributima.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597160"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="79c0b-103">Profili klijenata: Indeks za pretraživanje i filtriranje</span><span class="sxs-lookup"><span data-stu-id="79c0b-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="79c0b-104">Rezultat objedinjavanja podataka o klijentima je entitet profila klijenta koji pruža jedinstven pogled na vašu ukupnu korisničku bazu.</span><span class="sxs-lookup"><span data-stu-id="79c0b-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="79c0b-105">Da biste brzo [pronašli informacije o određenom klijentu ili grupi klijenata](customer-profiles.md), možete da konfigurišete mogućnosti **pretrage** i **filtriranja** na stranici **Klijenti**.</span><span class="sxs-lookup"><span data-stu-id="79c0b-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="79c0b-106">Čitajte dalje kako biste saznali kako administratori mogu da uređuju atribute na stranici **Indeks pretrage i filtriranja**, koje su na raspolaganju korisnicima za pretraživanje i filtriranje.</span><span class="sxs-lookup"><span data-stu-id="79c0b-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79c0b-107">![Filter pretrage](media/search-filter.png "Filter pretrage")</span><span class="sxs-lookup"><span data-stu-id="79c0b-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="79c0b-108">Dodajte polja i odredite atribute</span><span class="sxs-lookup"><span data-stu-id="79c0b-108">Add fields and specify attributes</span></span>

<span data-ttu-id="79c0b-109">Ako kao administrator prvi put definišete atribute koji se mogu pretraživati, prvo morate definisati indeksirana polja.</span><span class="sxs-lookup"><span data-stu-id="79c0b-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="79c0b-110">Predlažemo vam da odaberete sve atribute po kojima korisnici mogu da pretražuju i filtriraju klijente na stranici **Klijenti**.</span><span class="sxs-lookup"><span data-stu-id="79c0b-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="79c0b-111">Možete odrediti samo one atribute koji postoje u entitetu Profil klijenta koji ste kreirali tokom postupka objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="79c0b-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="79c0b-112">Otvorite stranicu **Klijenti** i izaberite **Indeks pretrage i filtriranja**.</span><span class="sxs-lookup"><span data-stu-id="79c0b-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="79c0b-113">Izaberite **+ Dodaj** da biste naveli indeksirana polja.</span><span class="sxs-lookup"><span data-stu-id="79c0b-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="79c0b-114">Izaberite atribute u listi koju želite da dodate kao indeksirana polja.</span><span class="sxs-lookup"><span data-stu-id="79c0b-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="79c0b-115">Uvek možete dodati više atributa ako izaberete **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="79c0b-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="79c0b-116">Takođe možete ukloniti sve odabrane atribute ako izaberete simbol **Ukloni**.</span><span class="sxs-lookup"><span data-stu-id="79c0b-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="79c0b-117">Istražite tabelu sa indeksiranim poljima klijenata</span><span class="sxs-lookup"><span data-stu-id="79c0b-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="79c0b-118">Sledeće informacije su predstavljene u tabeli.</span><span class="sxs-lookup"><span data-stu-id="79c0b-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="79c0b-119">**Ime**: Predstavlja ime atributa onako kako je prikazano u entitetu Profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="79c0b-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="79c0b-120">**Tip podataka**: Određuje da li je tip podataka niska, broj ili datum.</span><span class="sxs-lookup"><span data-stu-id="79c0b-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="79c0b-121">**Uključeno u pretragu**: Određuje da li se ovaj atribut može koristiti za pretraživanje klijenata na stranici **Klijenti** pomoću polja **Pretraga**.</span><span class="sxs-lookup"><span data-stu-id="79c0b-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="79c0b-122">**Dodaj filter**: Kontrola za definisanje kako se ovaj atribut može koristiti za filtriranje na stranici **Klijenti**.</span><span class="sxs-lookup"><span data-stu-id="79c0b-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="79c0b-123">Uređivanje opcija filtriranja za određeni atribut</span><span class="sxs-lookup"><span data-stu-id="79c0b-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="79c0b-124">Meni **Filter** na stranici **Klijenti** može da sadrži različit broj nivoa atributa (npr. različite starosne grupe po kojima se klijenti filtriraju).</span><span class="sxs-lookup"><span data-stu-id="79c0b-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="79c0b-125">Izaberite **Dodaj filter** za dati atribut na stranici **Indeks pretrage i filtriranja**.</span><span class="sxs-lookup"><span data-stu-id="79c0b-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="79c0b-126">Možete definisati broj rezultata i redosled po kome će oni biti organizovani.</span><span class="sxs-lookup"><span data-stu-id="79c0b-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="79c0b-127">U zavisnosti od tipa podataka atributa, pojavljuje se jedno od sledećih okana.</span><span class="sxs-lookup"><span data-stu-id="79c0b-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="79c0b-128">Atributi tipa niske: Navedite broj željenih rezultata u oknu **Opcije filtriranja niski** i smernice za redosled po kom će biti organizovani.</span><span class="sxs-lookup"><span data-stu-id="79c0b-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="79c0b-129">Atributi numeričkog tipa: Navedite obuhvaćene intervale u oknu **Opcije filtriranja brojeva** i smernice za redosled po kom će biti organizovani.</span><span class="sxs-lookup"><span data-stu-id="79c0b-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="79c0b-130">Atributi datuma tipa: Navedite obuhvaćene intervale u oknu **Opcije filtriranja datuma** i smernice za redosled po kom će biti organizovani.</span><span class="sxs-lookup"><span data-stu-id="79c0b-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="79c0b-131">Izaberite **Sačuvaj** da primenite promene.</span><span class="sxs-lookup"><span data-stu-id="79c0b-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="79c0b-132">Izaberite **Pokreni** kada budete spremni da primenite svoja podešavanja.</span><span class="sxs-lookup"><span data-stu-id="79c0b-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="79c0b-133">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="79c0b-133">Next steps</span></span>

<span data-ttu-id="79c0b-134">Idite na stranicu **Klijenti** za pretragu profila klijenata ili pomoću indeksiranih polja da biste videli podskup svih profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="79c0b-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]