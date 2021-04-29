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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896022"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="12903-103">Obogaćivanje za profile korisnika (pregled)</span><span class="sxs-lookup"><span data-stu-id="12903-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="12903-104">Koristite podatke iz izvora kao što su Microsoft i drugi partneri da biste obogatili podatke o klijentima.</span><span class="sxs-lookup"><span data-stu-id="12903-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stranica čvorišta za obogaćivanje":::

<span data-ttu-id="12903-106">U uvidima o korisnicima idite na **Podaci** > **Obogaćivanje** da biste koristili opcije obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="12903-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="12903-107">Da biste kreirali ili menjali obogaćivanja, morate da imate dozvole saradnika ili administratora.</span><span class="sxs-lookup"><span data-stu-id="12903-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="12903-108">Više informacija potražite u [dozvolama](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="12903-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="12903-109">Na kartici **Otkrivanje** ćete pronaći sledeća obogaćivanja:</span><span class="sxs-lookup"><span data-stu-id="12903-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="12903-110">[Brendove](enrichment-microsoft.md) obezbeđuje Microsoft</span><span class="sxs-lookup"><span data-stu-id="12903-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="12903-111">[Interesovanja](enrichment-microsoft.md) obezbeđuje Microsoft</span><span class="sxs-lookup"><span data-stu-id="12903-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="12903-112">[Podaci o kompaniji](enrichment-leadspace.md) koje pruža Leadspace</span><span class="sxs-lookup"><span data-stu-id="12903-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="12903-113">[Demografski podaci](enrichment-experian.md) koje pruža Experian</span><span class="sxs-lookup"><span data-stu-id="12903-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="12903-114">[Podatke o lokaciji](enrichment-here.md) pruža HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="12903-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="12903-115">[Prilagođeni podaci](enrichment-SFTP-custom-import.md) pomoću protokola Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="12903-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="12903-116">Na kartici **Moja obogaćivanja** možete da vidite obogaćivanja koja ste konfigurisali i da menjate njihova svojstva.</span><span class="sxs-lookup"><span data-stu-id="12903-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="12903-117">Upravljanje postojećim obogaćivanjima</span><span class="sxs-lookup"><span data-stu-id="12903-117">Manage existing enrichments</span></span>

<span data-ttu-id="12903-118">Idite na **Moja obogaćivanja** da vidite sva konfigurisana obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="12903-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="12903-119">Svako obogaćivanje predstavljeno je kao red koji uključuje dodatne informacije o obogaćivanju.</span><span class="sxs-lookup"><span data-stu-id="12903-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="12903-120">Izaberite obogaćivanje da biste videli dostupne opcije.</span><span class="sxs-lookup"><span data-stu-id="12903-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="12903-121">Takođe možete odabrati tri tačke (...) na stavci liste da biste videli opcije.</span><span class="sxs-lookup"><span data-stu-id="12903-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcije za upravljanje obogaćivanjima na listi obogaćivanja":::

- <span data-ttu-id="12903-123">**Prikažite** detalje obogaćivanja sa brojem obogaćenih profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="12903-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="12903-124">**Uređujte** konfiguraciju obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="12903-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="12903-125">**Pokrenite** obogaćivanje radi ažuriranja profila klijenata najnovijim podacima.</span><span class="sxs-lookup"><span data-stu-id="12903-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="12903-126">**Deaktivirajte** postojeće obogaćivanje kako bi se zaustavili automatsko osvežavanje sa svakim zakazanim osvežavanjem.</span><span class="sxs-lookup"><span data-stu-id="12903-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="12903-127">Podaci iz poslednjeg uspešnog osvežavanja i dalje će biti dostupni.</span><span class="sxs-lookup"><span data-stu-id="12903-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="12903-128">**Aktivirajte** neaktivno obogaćivanje da biste ponovo pokrenuli automatsko osvežavanje sa svakim zakazanim osvežavanjem.</span><span class="sxs-lookup"><span data-stu-id="12903-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="12903-129">**Izbrišite** obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="12903-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="12903-130">Možete da pokrenete ili deaktivirate više obogaćivanja odjednom tako što ćete ih izabrati na listi.</span><span class="sxs-lookup"><span data-stu-id="12903-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="12903-131">Opcije pregleda i uređivanja nisu dostupne kao masovna radnja i rade samo za jedno obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="12903-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="12903-132">Obogaćivanja i veze</span><span class="sxs-lookup"><span data-stu-id="12903-132">Enrichments and connections</span></span>

<span data-ttu-id="12903-133">Obogaćenja trećih lica se konfigurišu pomoću [veza](connections.md) koje administrator postavlja sa akreditivima i daje saglasnost za prenos podataka.</span><span class="sxs-lookup"><span data-stu-id="12903-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="12903-134">Vezu mogu da koriste administratori i saradnici da bi konfigurisali obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="12903-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="12903-135">Višestruka obogaćivanja istog tipa</span><span class="sxs-lookup"><span data-stu-id="12903-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="12903-136">Entitet koji treba obogatiti navodi se tokom konfiguracije obogaćivanja, što vam omogućava da obogatite samo podskup svojih profila.</span><span class="sxs-lookup"><span data-stu-id="12903-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="12903-137">Na primer, obogatite podatke samo za određeni segment.</span><span class="sxs-lookup"><span data-stu-id="12903-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="12903-138">Možete da konfigurišete nekoliko obogaćivanja istog tipa i da ponovo koristite istu vezu.</span><span class="sxs-lookup"><span data-stu-id="12903-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="12903-139">Neka obogaćivanja će imati ograničenja u broju obogaćivanja istog tipa koja se mogu kreirati.</span><span class="sxs-lookup"><span data-stu-id="12903-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="12903-140">Ograničenja i trenutna upotreba mogu se videti na stranici **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="12903-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
