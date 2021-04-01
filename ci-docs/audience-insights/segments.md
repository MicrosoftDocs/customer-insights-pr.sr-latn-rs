---
title: Kreiranje segmenata i upravljanje njima
description: Napravite segmente klijenata da biste ih grupisali na osnovu različitih atributa.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597074"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="9a2dc-103">Kreiranje segmenata i upravljanje njima</span><span class="sxs-lookup"><span data-stu-id="9a2dc-103">Create and manage segments</span></span>

<span data-ttu-id="9a2dc-104">Segmenti vam omogućavaju da grupišete klijente na osnovu demografskih, transakcionih ili atributa ponašanja.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="9a2dc-105">Možete da koristite segmente za ciljanje promotivnih kampanja, prodajnih aktivnosti i aktivnosti podrške klijenata kako biste postigli svoje poslovne ciljeve.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="9a2dc-106">Možete definisati složene filtere oko entiteta Profil klijenta i s njim povezanih entiteta.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="9a2dc-107">Svaki segment nakon obrade kreira skup korisničkih zapisa koje možete da izvoziti i za koje možete da preduzimate neke korake.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="9a2dc-108">Neka [ograničenja usluga](service-limits.md) se primenjuju.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="9a2dc-109">Ako nije drugačije naznačeno, svi segmenti su **Dinamički segmenti**, koji se osvežavaju po redovnom rasporedu.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="9a2dc-110">Sledeći primer ilustruje korišćenje mogućnosti segmentacije.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="9a2dc-111">Definisali smo segment za klijente koji su naručili robu za najmanje 500 USD u poslednjih 90 dana *i* koji su bili uključeni u poziv korisničke službe koji je prosleđen.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9a2dc-112">![Više grupa](media/segmentation-group1-2.png "Više grupa")</span><span class="sxs-lookup"><span data-stu-id="9a2dc-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="9a2dc-113">Kreirajte novi segment</span><span class="sxs-lookup"><span data-stu-id="9a2dc-113">Create a new segment</span></span>

<span data-ttu-id="9a2dc-114">Segmentima se upravlja na stranici **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="9a2dc-115">U uvidima o korisnicima idite na stranicu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="9a2dc-116">Izaberite **Novo** > **Prazan segment**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="9a2dc-117">U oknu **Novi segment** odaberite tip segmenta i navedite **Ime**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="9a2dc-118">Opcionalno, unesite ime za prikaz i opis koji pomaže u prepoznavanju segmenta.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="9a2dc-119">Izaberite **Sledeće** da dođete na stranicu **Graditelj segmenata** na kojoj definišete grupu.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="9a2dc-120">Grupa je skup klijenata.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="9a2dc-121">Odaberite entitet koji obuhvata atribute po kojima želite da segmentirate.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="9a2dc-122">Odaberite atribut po segmentu.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="9a2dc-123">Ovaj atribut može imati jedan od četiri tipa vrednosti: numerički, niska, datum ili logički.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="9a2dc-124">Odaberite operator i vrednost za izabrani atribut.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9a2dc-125">![Prilagođeni filter grupe](media/customer-group-numbers.png "Filter grupe klijenata")</span><span class="sxs-lookup"><span data-stu-id="9a2dc-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="9a2dc-126">Broj</span><span class="sxs-lookup"><span data-stu-id="9a2dc-126">Number</span></span> |<span data-ttu-id="9a2dc-127">Definicija</span><span class="sxs-lookup"><span data-stu-id="9a2dc-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="9a2dc-128">1</span><span class="sxs-lookup"><span data-stu-id="9a2dc-128">1</span></span>     |<span data-ttu-id="9a2dc-129">Entity</span><span class="sxs-lookup"><span data-stu-id="9a2dc-129">Entity</span></span>          |
   |<span data-ttu-id="9a2dc-130">2</span><span class="sxs-lookup"><span data-stu-id="9a2dc-130">2</span></span>     |<span data-ttu-id="9a2dc-131">Atribut</span><span class="sxs-lookup"><span data-stu-id="9a2dc-131">Attribute</span></span>          |
   |<span data-ttu-id="9a2dc-132">3</span><span class="sxs-lookup"><span data-stu-id="9a2dc-132">3</span></span>    |<span data-ttu-id="9a2dc-133">Operator</span><span class="sxs-lookup"><span data-stu-id="9a2dc-133">Operator</span></span>         |
   |<span data-ttu-id="9a2dc-134">4</span><span class="sxs-lookup"><span data-stu-id="9a2dc-134">4</span></span>    |<span data-ttu-id="9a2dc-135">Vrednost</span><span class="sxs-lookup"><span data-stu-id="9a2dc-135">Value</span></span>         |

8. <span data-ttu-id="9a2dc-136">Ako je entitet povezan putem objedinjenog entiteta klijenta putem [odnosa](relationships.md), morate definisati putanju odnosa da biste kreirali važeći segment.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="9a2dc-137">Dodajte entitete iz putanje odnosa dok ne budete mogli da izaberete entitet **Klijent: CustomerInsights** iz padajuće liste.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="9a2dc-138">Zatim odaberite **Svi zapisi** za svaki uslov.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9a2dc-139">![Putanja odnosa tokom kreiranja segmenta](media/segments-multiple-relationships.png "Putanja odnosa tokom kreiranja segmenta")</span><span class="sxs-lookup"><span data-stu-id="9a2dc-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="9a2dc-140">Podrazumevano, segmenti generišu izlazni entitet koji sadrži sve atribute korisničkih profila koji se podudaraju sa definisanim filterima.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="9a2dc-141">Ako se segment zasniva na drugim entitetima osim na entitetu *Klijent*, izlaznom entitetu možete dodati više atributa iz tih entiteta.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="9a2dc-142">Izaberite **Atributi projekta** da biste odabrali atribute koji će biti dodati izlaznom entitetu.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="9a2dc-143">Primer: Segment se zasniva na entitetu koji sadrži podatke o aktivnostima klijenata koji su povezani sa entitetom *Klijent*.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="9a2dc-144">Segment traži sve klijente koji su pozvali tehničku podršku u poslednjih 60 dana.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="9a2dc-145">Možete odabrati da dodate trajanje poziva i broj poziva svim podudarnim zapisima klijenata u izlaznom entitetu.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="9a2dc-146">Ove informacije mogu biti korisne za slanje e-pošte sa korisnim vezama do članaka pomoći na mreži i često postavljanih pitanja klijentima koji su često zvali.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="9a2dc-147">Izaberite **Sačuvaj** da biste sačuvali segment.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="9a2dc-148">Vaš segment će biti sačuvan i obrađen ukoliko su svi zahtevi potvrđeni.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="9a2dc-149">U suprotnom, biće sačuvan kao radna verzija.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="9a2dc-150">Izaberite **Nazad na segmente** da biste se vratili na stranicu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="9a2dc-151">Upravljanje postojećim segmentima</span><span class="sxs-lookup"><span data-stu-id="9a2dc-151">Manage existing segments</span></span>

<span data-ttu-id="9a2dc-152">Na stranici **Segmenti**, možete videti sve sačuvane segmente i njima upravljati.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="9a2dc-153">Svaki segment predstavljen je redom koji sadrži dodatne informacije o segmentu.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="9a2dc-154">Segmente možete sortirati u koloni odabirom naslova kolone.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="9a2dc-155">Koristite polje **Pretraga** u gornjem desnom uglu da biste filtrirali segmente.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9a2dc-156">![Opcije za upravljanje postojećim segmentom](media/segments-selected-segment.png "Opcije za upravljanje postojećim segmentom")</span><span class="sxs-lookup"><span data-stu-id="9a2dc-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="9a2dc-157">Sledeća radnja je dostupna kada odaberete segment:</span><span class="sxs-lookup"><span data-stu-id="9a2dc-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="9a2dc-158">**Prikaz** detalja segmenta, uključujući trend broja članova, pregled članova segmenta.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="9a2dc-159">**Uredite** segment da biste promenili njegova svojstva.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="9a2dc-160">**Napravite duplikat** segmenta.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="9a2dc-161">Možete odabrati da uredite njegova svojstva ili jednostavno sačuvate duplikat.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="9a2dc-162">**Osvežite** segment tako da uključuje najnovije podatke.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="9a2dc-163">**Aktivirajte** ili **Deaktivirajte** segment.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="9a2dc-164">Segmenti imaju dva moguća stanja - aktivno ili neaktivno.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="9a2dc-165">Ova stanja dobro dođu prilikom uređivanja segmenta.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="9a2dc-166">Za neaktivne segmente definicija segmenta postoji, ali još uvek ne sadrži klijente.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="9a2dc-167">Kada aktivirate segment, njegovo stanje se menja iz „neaktivan“ u „aktivan“ i on počinje da traži klijente koji odgovaraju definiciji segmenta.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="9a2dc-168">Ako je [zakazano osvežavanje](system.md#schedule-tab) konfigurisano, neaktivni segmenti imaju **Status** naveden kao **Preskočeno**, što ukazuje da osvežavanje nije ni pokušano.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="9a2dc-169">Kada se aktivira neaktivni segment, osvežiće se i biće uključen u zakazana osvežavanja.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="9a2dc-170">Alternativno, možete da koristite funkcionalnost **Isplaniraj za kasnije** u padajućoj listi **Aktiviraj/Deaktiviraj** da navedete budući datum i vreme za aktivaciju i deaktivaciju određenog segmenta.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="9a2dc-171">**Preimenujte** segment.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-171">**Rename** the segment.</span></span>
- <span data-ttu-id="9a2dc-172">**Preuzmite** listu članova kao .CSV datoteku.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="9a2dc-173">Opcija **Dodaj u** šalje listu ID-ova klijenata u segmentu na obradu u drugoj aplikaciji.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="9a2dc-174">**Izbrišite** segment.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="9a2dc-175">Osvežavanje segmenata</span><span class="sxs-lookup"><span data-stu-id="9a2dc-175">Refresh segments</span></span>

<span data-ttu-id="9a2dc-176">Možete da osvežite sve segmente odjednom ako izaberete **Osvežite sve** na stranici **Segmenti**, a možete i da osvežiti jedan ili više segmenata kada ih izaberete, pa odaberete **Osveži** iz opcija.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="9a2dc-177">Alternativno, možete konfigurisati ponavljajuće osvežavanje u odeljku **Administrator** > **Sistem** > **Raspored**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="9a2dc-178">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="9a2dc-179">Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="9a2dc-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="9a2dc-180">Možete izabrati status procesa da biste videli detalje o toku celog posla.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="9a2dc-181">Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="9a2dc-182">Preuzimanje i izvoz segmenata</span><span class="sxs-lookup"><span data-stu-id="9a2dc-182">Download and export segments</span></span>

<span data-ttu-id="9a2dc-183">Možete preuzeti svoje segmente u CSV datoteku ili ih izvesti u Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="9a2dc-184">Preuzmite segmente u CSV datoteku</span><span class="sxs-lookup"><span data-stu-id="9a2dc-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="9a2dc-185">U uvidima o korisnicima idite na stranicu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="9a2dc-186">Izaberite tri tačke na pločici određenog segmenta.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="9a2dc-187">Izaberite **Preuzmi kao CSV** sa padajuće liste radnji.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="9a2dc-188">Izvoz segmenata u Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="9a2dc-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="9a2dc-189">Pre izvoza segmenata u Dynamics 365 Sales, administrator treba [kreiraj odredište za izvoz](export-destinations.md) za Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="9a2dc-190">U uvidima o korisnicima idite na stranicu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="9a2dc-191">Izaberite tri tačke na pločici određenog segmenta.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="9a2dc-192">Izaberite **Dodaj u** iz padajuće liste radnji i izaberite odredište za izvoz u koje želite da pošaljete podatke.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="9a2dc-193">Režim radne verzije za segmente</span><span class="sxs-lookup"><span data-stu-id="9a2dc-193">Draft mode for segments</span></span>

<span data-ttu-id="9a2dc-194">Ako nisu ispunjeni svi zahtevi za obradu segmenta, možete da sačuvate segment kao radnu verziju i pristupite mu sa stranice **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="9a2dc-195">Biće sačuvan kao neaktivan segment i nećete moći da ga aktivirate dok ne postane važeći.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="9a2dc-196">Dodajte više uslova grupi</span><span class="sxs-lookup"><span data-stu-id="9a2dc-196">Add more conditions to a group</span></span>

<span data-ttu-id="9a2dc-197">Da biste grupi dodali više uslova, možete da koristite dva logička operatora:</span><span class="sxs-lookup"><span data-stu-id="9a2dc-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="9a2dc-198">Operator **I**: Oba uslova moraju da budu ispunjena kao deo procesa segmentacije.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="9a2dc-199">Ova opcija je najkorisnija kada definišete uslove u različitim entitetima.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="9a2dc-200">Operator **ILI**: Bilo koji od uslova mora biti ispunjen kao deo procesa segmentacije.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="9a2dc-201">Ova opcija je najkorisnija kada definišete više uslova u istom entitetu.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9a2dc-202">![Operator ILI gde je potrebno ispuniti bilo koji uslov](media/segmentation-either-condition.png "Operator ILI gde je potrebno ispuniti bilo koji uslov")</span><span class="sxs-lookup"><span data-stu-id="9a2dc-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="9a2dc-203">Trenutno je moguće ugnezditi operator **ILI** unutar operatora **I**, ali ne i obrnuto.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="9a2dc-204">Kombinovanje više grupa</span><span class="sxs-lookup"><span data-stu-id="9a2dc-204">Combine multiple groups</span></span>

<span data-ttu-id="9a2dc-205">Svaka grupa proizvodi određeni skup klijenata.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="9a2dc-206">Možete kombinovati ove grupe da biste uključili klijente potrebne za vaš predmet poslovanja.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="9a2dc-207">U uvidima o klijentima idite na stranicu **Segmenti** i izaberite segment.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="9a2dc-208">Izaberite **Dodaj grupu**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9a2dc-209">![Grupa klijenata dodaj grupu](media/customer-group-add-group.png "Grupa klijenata dodaj grupu")</span><span class="sxs-lookup"><span data-stu-id="9a2dc-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="9a2dc-210">Izaberite jedan od sledećih skupa operatora: **Unija**, **Presek** ili **Izuzimanje**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9a2dc-211">![Grupa klijenata dodaj uniju](media/customer-group-union.png "Grupa klijenata dodaj uniju")</span><span class="sxs-lookup"><span data-stu-id="9a2dc-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="9a2dc-212">Izaberite operator skupa da biste definisali novu grupu.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="9a2dc-213">Čuvanje različitih grupa radi određivanja koji podaci se zadržavaju:</span><span class="sxs-lookup"><span data-stu-id="9a2dc-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="9a2dc-214">**Unija** objedinjuje dve grupe.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="9a2dc-215">**Presek** preklapa dve grupe.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="9a2dc-216">Samo podaci koji *su zajednički* za obe grupe zadržavaju se u objedinjenoj grupi.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="9a2dc-217">**Osim** kombinuje dve grupe.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-217">**Except** combines the two groups.</span></span> <span data-ttu-id="9a2dc-218">Samo podaci u grupi A koji *nisu zajednički* sa podacima iz grupe B zadržavaju se.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="9a2dc-219">Pogledajte istoriju obrade i članove segmenta</span><span class="sxs-lookup"><span data-stu-id="9a2dc-219">View processing history and segment members</span></span>

<span data-ttu-id="9a2dc-220">Konsolidovane podatke o segmentu možete videti tako što ćete pregledati njegove detalje.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="9a2dc-221">Na stranici **Segmenti** izaberite segment koji želite da pregledate.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="9a2dc-222">Gornji deo stranice sadrži grafikon trenda koji vizuelno prikazuje promene u broju članova.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="9a2dc-223">Zadržite pokazivač iznad tačaka podataka da biste videli broj članova određenog datuma.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="9a2dc-224">Možete da ažurirate vremenski okvir vizuelizacije.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9a2dc-225">![Vremenski period segmenta](media/segment-time-range.png "Vremenski period segmenta")</span><span class="sxs-lookup"><span data-stu-id="9a2dc-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="9a2dc-226">Donji deo sadrži listu članova segmenta.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="9a2dc-227">Polja koja se pojavljuju na ovoj listi zasnivaju se na atributima entiteta vašeg segmenta.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="9a2dc-228">Lista je pregled odgovarajućih članova segmenta i pokazuje prvih 100 zapisa vašeg segmenta tako da ga možete brzo proceniti i pregledati njegove definicije, ako je potrebno.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="9a2dc-229">Da biste videli sve odgovarajuće zapise, morate da [izvezete segment](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9a2dc-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="9a2dc-230">Brzi segmenti</span><span class="sxs-lookup"><span data-stu-id="9a2dc-230">Quick segments</span></span>

<span data-ttu-id="9a2dc-231">Pored alatke za pravljenje segmenata, postoji još jedan put za kreiranje segmenata.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="9a2dc-232">Brzi segmenti vam omogućavaju da napravite jednostavne segmente, sa jednim operatorom, brzo i uz trenutne uvide.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="9a2dc-233">Na stranici **Segmenti** izaberite **Nova** > **Brzo kreirajte od**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="9a2dc-234">Izaberite opciju **Profili** za izgradnju segmenta koji je zasnovan na objedinjenom entitetu Klijent.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="9a2dc-235">Izaberite opciju **Mere** za izgradnju segmenta oko svake vrste mera atributa klijenta koje ste prethodno kreirali na stranici **Mere**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="9a2dc-236">Izaberite opciju **Obaveštavanje** da izgradite segment oko jednog od izlaznih entiteta koje ste generisali koristeći mogućnosti **Predviđanja** ili **Prilagođeni modeli**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="9a2dc-237">U dijalogu **Novi brzi segment** izaberite atribut iz padajuće liste **Polje**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="9a2dc-238">Sistem će vam pružiti neke dodatne uvide koji će vam pomoći da stvorite bolje segmente svojih klijenata.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="9a2dc-239">Za kategorijska polja prikazaćemo 10 glavnih brojeva klijenta.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="9a2dc-240">Odaberite **Vrednost** i izabrali **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="9a2dc-241">Za numerički atribut, sistem će pokazati koja vrednost atributa spada ispod svakog procenta klijenta.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="9a2dc-242">Odaberite **Operator** i **Vrednost**, a zatim izaberite **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="9a2dc-243">Sistem će vam pružiti **Procenjenu veličinu segmenta**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="9a2dc-244">Možete odabrati da li da generišete segment koji ste definisali ili da ga prvo pregledate kako biste dobili drugu veličinu segmenta.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9a2dc-245">![Naziv i procena za brzi segment](media/quick-segment-name.png "Naziv i procena za brzi segment")</span><span class="sxs-lookup"><span data-stu-id="9a2dc-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="9a2dc-246">Navedite **Naziv** za segment.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="9a2dc-247">Opcionalno, navedite **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="9a2dc-248">Izaberite **Sačuvaj** da biste kreirali segment.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="9a2dc-249">Nakon završetka obrade segmenta, možete ga pregledati kao i bilo koji drugi segment koji ste kreirali.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="9a2dc-250">Za sledeće scenarije, savetujemo upotrebu alata za pravljenje segmenata umesto preporučenih mogućnosti segmenata:</span><span class="sxs-lookup"><span data-stu-id="9a2dc-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="9a2dc-251">Stvaranje segmenata sa filterima na kategorijskim poljima gde je operator drugačiji od operatora **Da li je**</span><span class="sxs-lookup"><span data-stu-id="9a2dc-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="9a2dc-252">Kreiranje segmenata sa filterima na numeričkim poljima gde je operator drugačiji od operatora **Između**, **Veće od** i **Manje od**</span><span class="sxs-lookup"><span data-stu-id="9a2dc-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="9a2dc-253">Kreiranje segmenata sa filterima na poljima tipa datuma</span><span class="sxs-lookup"><span data-stu-id="9a2dc-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="9a2dc-254">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="9a2dc-254">Next steps</span></span>

<span data-ttu-id="9a2dc-255">[Izvezite segment](export-destinations.md) i istražite [karticu klijenta](customer-card-add-in.md) i [konektore](export-power-bi.md) da biste dobili uvid na nivou klijenta.</span><span class="sxs-lookup"><span data-stu-id="9a2dc-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]