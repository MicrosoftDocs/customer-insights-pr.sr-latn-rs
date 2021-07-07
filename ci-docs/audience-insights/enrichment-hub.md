---
title: Obogatite objedinjene profile klijenata
description: Koristite mogućnosti za obogaćivanje podataka o klijentima.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305265"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="7b72b-103">Obogaćivanje za profile korisnika (pregled)</span><span class="sxs-lookup"><span data-stu-id="7b72b-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="7b72b-104">Koristite podatke iz izvora kao što su Microsoft i drugi partneri da biste obogatili podatke o klijentima.</span><span class="sxs-lookup"><span data-stu-id="7b72b-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stranica čvorišta za obogaćivanje":::

<span data-ttu-id="7b72b-106">U uvidima o korisnicima idite na **Podaci** > **Obogaćivanje** da biste koristili opcije obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="7b72b-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="7b72b-107">Da biste kreirali ili menjali obogaćivanja, morate da imate dozvole saradnika ili administratora.</span><span class="sxs-lookup"><span data-stu-id="7b72b-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="7b72b-108">Više informacija potražite u [dozvolama](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="7b72b-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="7b72b-109">Na kartici **Otkrivanje** ćete pronaći sledeća obogaćivanja:</span><span class="sxs-lookup"><span data-stu-id="7b72b-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="7b72b-110">[Brendove](enrichment-microsoft.md) obezbeđuje Microsoft</span><span class="sxs-lookup"><span data-stu-id="7b72b-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="7b72b-111">[Interesovanja](enrichment-microsoft.md) obezbeđuje Microsoft</span><span class="sxs-lookup"><span data-stu-id="7b72b-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="7b72b-112">[Poboljšane adrese](enrichment-enhanced-addresses.md) obezbeđuje Microsoft</span><span class="sxs-lookup"><span data-stu-id="7b72b-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="7b72b-113">[Podaci o kompaniji](enrichment-leadspace.md) koje pruža Leadspace</span><span class="sxs-lookup"><span data-stu-id="7b72b-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="7b72b-114">[Demografski podaci](enrichment-experian.md) koje obezbeđuje Experian</span><span class="sxs-lookup"><span data-stu-id="7b72b-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="7b72b-115">[Podatke o lokaciji](enrichment-here.md) pruža HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="7b72b-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="7b72b-116">[Prilagođeni podaci](enrichment-SFTP-custom-import.md) pomoću protokola Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="7b72b-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="7b72b-117">Na kartici **Moja obogaćivanja** možete da vidite obogaćivanja koja ste konfigurisali i da menjate njihova svojstva.</span><span class="sxs-lookup"><span data-stu-id="7b72b-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="7b72b-118">Upravljanje postojećim obogaćivanjima</span><span class="sxs-lookup"><span data-stu-id="7b72b-118">Manage existing enrichments</span></span>

<span data-ttu-id="7b72b-119">Idite na karticu **Moja obogaćivanja** da biste videli sva konfigurisana obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="7b72b-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="7b72b-120">Svako obogaćivanje predstavljeno je kao red koji uključuje dodatne informacije o obogaćivanju.</span><span class="sxs-lookup"><span data-stu-id="7b72b-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="7b72b-121">Izaberite obogaćivanje da biste videli dostupne opcije.</span><span class="sxs-lookup"><span data-stu-id="7b72b-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="7b72b-122">Takođe možete odabrati tri tačke (...) na stavci liste da biste videli opcije.</span><span class="sxs-lookup"><span data-stu-id="7b72b-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcije za upravljanje obogaćivanjima na listi obogaćivanja":::

- <span data-ttu-id="7b72b-124">**Prikažite** detalje obogaćivanja sa brojem obogaćenih profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="7b72b-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="7b72b-125">**Uređujte** konfiguraciju obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="7b72b-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="7b72b-126">**Pokrenite** obogaćivanje radi ažuriranja profila klijenata najnovijim podacima.</span><span class="sxs-lookup"><span data-stu-id="7b72b-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="7b72b-127">**Deaktivirajte** postojeće obogaćivanje kako bi se zaustavili automatsko osvežavanje sa svakim zakazanim osvežavanjem.</span><span class="sxs-lookup"><span data-stu-id="7b72b-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="7b72b-128">Podaci iz poslednjeg uspešnog osvežavanja i dalje će biti dostupni.</span><span class="sxs-lookup"><span data-stu-id="7b72b-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="7b72b-129">**Aktivirajte** neaktivno obogaćivanje da biste ponovo pokrenuli automatsko osvežavanje sa svakim zakazanim osvežavanjem.</span><span class="sxs-lookup"><span data-stu-id="7b72b-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="7b72b-130">**Izbrišite** obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="7b72b-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="7b72b-131">Možete da pokrenete ili deaktivirate više obogaćivanja odjednom tako što ćete ih izabrati na listi.</span><span class="sxs-lookup"><span data-stu-id="7b72b-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="7b72b-132">Opcije pregleda i uređivanja nisu dostupne kao masovna radnja i rade samo za jedno obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="7b72b-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="7b72b-133">Obogaćivanja i veze</span><span class="sxs-lookup"><span data-stu-id="7b72b-133">Enrichments and connections</span></span>

<span data-ttu-id="7b72b-134">Obogaćenja trećih lica se konfigurišu pomoću [veza](connections.md) koje administrator postavlja sa akreditivima i daje saglasnost za prenos podataka.</span><span class="sxs-lookup"><span data-stu-id="7b72b-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="7b72b-135">Vezu mogu da koriste administratori i saradnici da bi konfigurisali obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="7b72b-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="7b72b-136">Višestruka obogaćivanja istog tipa</span><span class="sxs-lookup"><span data-stu-id="7b72b-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="7b72b-137">Entitet koji treba obogatiti navodi se tokom konfiguracije obogaćivanja, što vam omogućava da obogatite samo podskup svojih profila.</span><span class="sxs-lookup"><span data-stu-id="7b72b-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="7b72b-138">Na primer, obogatite podatke samo za određeni segment.</span><span class="sxs-lookup"><span data-stu-id="7b72b-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="7b72b-139">Možete da konfigurišete nekoliko obogaćivanja istog tipa i da ponovo koristite istu vezu.</span><span class="sxs-lookup"><span data-stu-id="7b72b-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="7b72b-140">Neka obogaćivanja će imati ograničenja u broju obogaćivanja istog tipa koja se mogu kreirati.</span><span class="sxs-lookup"><span data-stu-id="7b72b-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="7b72b-141">Ograničenja i trenutna upotreba mogu se videti na stranici **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="7b72b-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
