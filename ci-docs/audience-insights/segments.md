---
title: Segmenti u uvidima u ciljnu grupu
description: Pregled segmenata i način kreiranja i upravljanja njima.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306274"
---
# <a name="segments-overview"></a><span data-ttu-id="fabdf-103">Pregled segmenata</span><span class="sxs-lookup"><span data-stu-id="fabdf-103">Segments overview</span></span>

<span data-ttu-id="fabdf-104">Segmenti vam omogućavaju da grupišete klijente na osnovu demografskih, transakcionih ili atributa ponašanja.</span><span class="sxs-lookup"><span data-stu-id="fabdf-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="fabdf-105">Možete da koristite segmente za ciljanje promotivnih kampanja, prodajnih aktivnosti i aktivnosti podrške klijenata kako biste postigli svoje poslovne ciljeve.</span><span class="sxs-lookup"><span data-stu-id="fabdf-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="fabdf-106">Korisnički profili koji se podudaraju sa filterima definicije segmenta nazivaju se *članovima* segmenta.</span><span class="sxs-lookup"><span data-stu-id="fabdf-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="fabdf-107">Neka [ograničenja usluga](service-limits.md) se primenjuju.</span><span class="sxs-lookup"><span data-stu-id="fabdf-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="fabdf-108">Kreirajte novi segment</span><span class="sxs-lookup"><span data-stu-id="fabdf-108">Create a new segment</span></span>

<span data-ttu-id="fabdf-109">Postoji više načina za kreiranje novog segmenta:</span><span class="sxs-lookup"><span data-stu-id="fabdf-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="fabdf-110">Složeni segment sa kreatorom segmenata: [Prazan segment](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="fabdf-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="fabdf-111">Jednostavni segmenti sa jednim operatorom: [Brzi segment](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="fabdf-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="fabdf-112">Način omogućen veštačkom inteligencijom za pronalaženje sličnih klijenata: [Slični klijenti](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="fabdf-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="fabdf-113">Predlozi omogućeni veštačkom inteligencijom zasnovani na merama ili atributima: [Predloženi segmenti za poboljšanje mera](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="fabdf-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="fabdf-114">Predlozi zasnovani na aktivnostima: [Predloženi segmenti na osnovu aktivnosti klijenata](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="fabdf-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="fabdf-115">Upravljanje postojećim segmentima</span><span class="sxs-lookup"><span data-stu-id="fabdf-115">Manage existing segments</span></span>

<span data-ttu-id="fabdf-116">Idite na stranicu **Segmenti** da biste prikazali sve sačuvane segmente i upravljali njima.</span><span class="sxs-lookup"><span data-stu-id="fabdf-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="fabdf-117">Svaki segment predstavljen je redom koji sadrži dodatne informacije o segmentu.</span><span class="sxs-lookup"><span data-stu-id="fabdf-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Izabrani segment sa padajućom listom opcija i dostupnim opcijama.":::

<span data-ttu-id="fabdf-119">Sledeća radnja je dostupna kada odaberete segment:</span><span class="sxs-lookup"><span data-stu-id="fabdf-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="fabdf-120">**Prikaz** detalja segmenta, uključujući trend broja članova, pregled članova segmenta.</span><span class="sxs-lookup"><span data-stu-id="fabdf-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="fabdf-121">**Uredite** segment da biste promenili njegova svojstva.</span><span class="sxs-lookup"><span data-stu-id="fabdf-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="fabdf-122">**Napravite duplikat** segmenta.</span><span class="sxs-lookup"><span data-stu-id="fabdf-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="fabdf-123">Možete odabrati da uredite njegova svojstva ili jednostavno sačuvate duplikat.</span><span class="sxs-lookup"><span data-stu-id="fabdf-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="fabdf-124">**Osvežite** segment tako da uključuje najnovije podatke.</span><span class="sxs-lookup"><span data-stu-id="fabdf-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="fabdf-125">**Aktivirajte** ili **Deaktivirajte** segment.</span><span class="sxs-lookup"><span data-stu-id="fabdf-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="fabdf-126">Segmenti imaju dva moguća stanja - aktivno ili neaktivno.</span><span class="sxs-lookup"><span data-stu-id="fabdf-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="fabdf-127">Ova stanja dobro dođu prilikom uređivanja segmenta.</span><span class="sxs-lookup"><span data-stu-id="fabdf-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="fabdf-128">Za neaktivne segmente definicija segmenta postoji, ali još uvek ne sadrži klijente.</span><span class="sxs-lookup"><span data-stu-id="fabdf-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="fabdf-129">Kada aktivirate segment, njegovo stanje se menja iz „neaktivan“ u „aktivan“ i on počinje da traži klijente koji odgovaraju definiciji segmenta.</span><span class="sxs-lookup"><span data-stu-id="fabdf-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="fabdf-130">Ako je [zakazano osvežavanje](system.md#schedule-tab) konfigurisano, neaktivni segmenti imaju **Status** naveden kao **Preskočeno**, što ukazuje da osvežavanje nije ni pokušano.</span><span class="sxs-lookup"><span data-stu-id="fabdf-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="fabdf-131">Kada se aktivira neaktivni segment, osvežiće se i biće uključen u zakazana osvežavanja.</span><span class="sxs-lookup"><span data-stu-id="fabdf-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="fabdf-132">Alternativno, možete da koristite funkcionalnost **Isplaniraj za kasnije** u padajućoj listi **Aktiviraj/Deaktiviraj** da navedete budući datum i vreme za aktivaciju i deaktivaciju određenog segmenta.</span><span class="sxs-lookup"><span data-stu-id="fabdf-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="fabdf-133">**Preimenujte** segment.</span><span class="sxs-lookup"><span data-stu-id="fabdf-133">**Rename** the segment.</span></span>
- <span data-ttu-id="fabdf-134">**Preuzmite** listu članova kao .CSV datoteku.</span><span class="sxs-lookup"><span data-stu-id="fabdf-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="fabdf-135">**Upravljanje izvozima** da biste videli segment povezan sa izvozom i upravljali njime.</span><span class="sxs-lookup"><span data-stu-id="fabdf-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="fabdf-136">Saznajte više o izvozima.</span><span class="sxs-lookup"><span data-stu-id="fabdf-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="fabdf-137">**Izbrišite** segment.</span><span class="sxs-lookup"><span data-stu-id="fabdf-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="fabdf-138">Osvežavanje segmenata</span><span class="sxs-lookup"><span data-stu-id="fabdf-138">Refresh segments</span></span>

<span data-ttu-id="fabdf-139">Možete da osvežite sve segmente odjednom ako izaberete **Osvežite sve** na stranici **Segmenti**, a možete i da osvežiti jedan ili više segmenata kada ih izaberete, pa odaberete **Osveži** iz opcija.</span><span class="sxs-lookup"><span data-stu-id="fabdf-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="fabdf-140">Alternativno, možete konfigurisati ponavljajuće osvežavanje u odeljku **Administrator** > **Sistem** > **Raspored**.</span><span class="sxs-lookup"><span data-stu-id="fabdf-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="fabdf-141">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="fabdf-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="fabdf-142">Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="fabdf-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="fabdf-143">Možete izabrati status procesa da biste videli detalje o toku celog posla.</span><span class="sxs-lookup"><span data-stu-id="fabdf-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="fabdf-144">Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="fabdf-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="fabdf-145">Izvoz segmenata</span><span class="sxs-lookup"><span data-stu-id="fabdf-145">Export segments</span></span>

<span data-ttu-id="fabdf-146">Segment možete izvesti sa stranice segmenata ili [stranica izvoza](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="fabdf-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="fabdf-147">Idite na stranicu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="fabdf-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="fabdf-148">Izaberite **Prikaži još [...]** za segment koji želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="fabdf-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="fabdf-149">Izaberite **Upravljanje izvozom** sa padajuće liste radnji.</span><span class="sxs-lookup"><span data-stu-id="fabdf-149">Select **Manage exports** from the actions dropdown list.</span></span>

1. <span data-ttu-id="fabdf-150">Otvara se stranica **Izvozi (pregled) za segment**.</span><span class="sxs-lookup"><span data-stu-id="fabdf-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="fabdf-151">Možete da vidite sve konfigurisane izvoze grupisane prema izvozima koji sadrže trenutni segment ili ga ne sadrže.</span><span class="sxs-lookup"><span data-stu-id="fabdf-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="fabdf-152">Da biste izabrani segment dodali u izvoz, izaberite izvoz na listi i izaberite **Dodaj segment**.</span><span class="sxs-lookup"><span data-stu-id="fabdf-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="fabdf-153">Da biste kreirali novi izvoz sa izabranim segmentom, izaberite **Dodaj izvoz**.</span><span class="sxs-lookup"><span data-stu-id="fabdf-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="fabdf-154">Za više informacija o kreiranju izvoza, pogledajte [Podešavanje novog izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="fabdf-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="fabdf-155">Izaberite **Nazad** da se vratite na glavnu stranicu za segmente.</span><span class="sxs-lookup"><span data-stu-id="fabdf-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="fabdf-156">Pogledajte istoriju obrade i članove segmenta</span><span class="sxs-lookup"><span data-stu-id="fabdf-156">View processing history and segment members</span></span>

<span data-ttu-id="fabdf-157">Konsolidovane podatke o segmentu možete videti tako što ćete pregledati njegove detalje.</span><span class="sxs-lookup"><span data-stu-id="fabdf-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="fabdf-158">Na stranici **Segmenti** izaberite segment koji želite da pregledate.</span><span class="sxs-lookup"><span data-stu-id="fabdf-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="fabdf-159">Gornji deo stranice sadrži grafikon trenda koji vizuelno prikazuje promene u broju članova.</span><span class="sxs-lookup"><span data-stu-id="fabdf-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="fabdf-160">Zadržite pokazivač iznad tačaka podataka da biste videli broj članova određenog datuma.</span><span class="sxs-lookup"><span data-stu-id="fabdf-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="fabdf-161">Možete da ažurirate vremenski okvir vizuelizacije.</span><span class="sxs-lookup"><span data-stu-id="fabdf-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fabdf-162">![Vremenski period segmenta](media/segment-time-range.png "Vremenski period segmenta")</span><span class="sxs-lookup"><span data-stu-id="fabdf-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="fabdf-163">Donji deo sadrži listu članova segmenta.</span><span class="sxs-lookup"><span data-stu-id="fabdf-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="fabdf-164">Polja koja se pojavljuju na ovoj listi zasnivaju se na atributima entiteta vašeg segmenta.</span><span class="sxs-lookup"><span data-stu-id="fabdf-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="fabdf-165">Lista je pregled odgovarajućih članova segmenta i pokazuje prvih 100 zapisa vašeg segmenta tako da ga možete brzo proceniti i pregledati njegove definicije, ako je potrebno.</span><span class="sxs-lookup"><span data-stu-id="fabdf-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="fabdf-166">Da biste videli sve odgovarajuće zapise, morate da [izvezete segment](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="fabdf-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
