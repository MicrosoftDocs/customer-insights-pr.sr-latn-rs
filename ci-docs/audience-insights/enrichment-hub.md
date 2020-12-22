---
title: Obogatite objedinjene profile klijenata
description: Koristite mogućnosti za obogaćivanje podataka o klijentima.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667111"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="17b46-103">Obogaćivanje za profile korisnika (pregled)</span><span class="sxs-lookup"><span data-stu-id="17b46-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="17b46-104">Koristite podatke iz izvora kao što su Microsoft i drugi partneri da biste obogatili podatke o klijentima.</span><span class="sxs-lookup"><span data-stu-id="17b46-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stranica čvorišta za obogaćivanje":::

<span data-ttu-id="17b46-106">U uvidima o korisnicima idite na **Podaci** > **Obogaćivanje** da biste koristili opcije obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="17b46-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="17b46-107">Da biste kreirali ili menjali obogaćivanja, morate da imate dozvole saradnika ili administratora.</span><span class="sxs-lookup"><span data-stu-id="17b46-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="17b46-108">Više informacija potražite u [dozvolama](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="17b46-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="17b46-109">Na kartici **Otkrivanje** ćete pronaći sledeća obogaćivanja:</span><span class="sxs-lookup"><span data-stu-id="17b46-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="17b46-110">[Brendovi](enrichment-microsoft-graph.md) koje pruža Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="17b46-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="17b46-111">[Interesovanja](enrichment-microsoft-graph.md) koje pruža Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="17b46-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="17b46-112">[Podaci o kompaniji](enrichment-leadspace.md) koje pruža Leadspace</span><span class="sxs-lookup"><span data-stu-id="17b46-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="17b46-113">[Demografski podaci](enrichment-experian.md) koje pruža Experian</span><span class="sxs-lookup"><span data-stu-id="17b46-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="17b46-114">[Podatke o lokaciji](enrichment-here.md) pruža HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="17b46-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="17b46-115">[Prilagođeni podaci](enrichment-SFTP-custom-import.md) pomoću protokola Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="17b46-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="17b46-116">Na kartici **Moja obogaćivanja** možete da vidite obogaćivanja koja ste konfigurisali i da menjate njihova svojstva.</span><span class="sxs-lookup"><span data-stu-id="17b46-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="17b46-117">Upravljanje postojećim obogaćivanjima</span><span class="sxs-lookup"><span data-stu-id="17b46-117">Manage existing enrichments</span></span>

<span data-ttu-id="17b46-118">Idite na **Moja obogaćivanja** da vidite sva konfigurisana obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="17b46-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="17b46-119">Svako obogaćivanje predstavljeno je kao red koji uključuje dodatne informacije o obogaćivanju.</span><span class="sxs-lookup"><span data-stu-id="17b46-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="17b46-120">Izaberite obogaćivanje da biste videli dostupne opcije.</span><span class="sxs-lookup"><span data-stu-id="17b46-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="17b46-121">Alternativno, možete odabrati tri tačke (...) na stavki liste da biste videli opcije.</span><span class="sxs-lookup"><span data-stu-id="17b46-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcije za upravljanje obogaćivanjima na listi obogaćivanja":::

- <span data-ttu-id="17b46-123">**Prikažite** detalje obogaćivanja sa brojem obogaćenih profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="17b46-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="17b46-124">**Uređujte** konfiguraciju obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="17b46-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="17b46-125">**Pokrenite** obogaćivanje radi ažuriranja profila klijenata najnovijim podacima.</span><span class="sxs-lookup"><span data-stu-id="17b46-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="17b46-126">**Deaktivirajte** postojeće obogaćivanje kako bi se zaustavili automatsko osvežavanje sa svakim zakazanim osvežavanjem.</span><span class="sxs-lookup"><span data-stu-id="17b46-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="17b46-127">Podaci iz poslednjeg uspešnog osvežavanja i dalje će biti dostupni.</span><span class="sxs-lookup"><span data-stu-id="17b46-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="17b46-128">**Aktivirajte** neaktivno obogaćivanje da biste ponovo pokrenuli automatsko osvežavanje sa svakim zakazanim osvežavanjem.</span><span class="sxs-lookup"><span data-stu-id="17b46-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="17b46-129">**Izbrišite** obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="17b46-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="17b46-130">Možete da pokrenete ili deaktivirate više obogaćivanja odjednom tako što ćete ih izabrati na listi.</span><span class="sxs-lookup"><span data-stu-id="17b46-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="17b46-131">Opcije pregleda i uređivanja nisu dostupne kao masovna radnja i rade samo za jedno obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="17b46-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>
