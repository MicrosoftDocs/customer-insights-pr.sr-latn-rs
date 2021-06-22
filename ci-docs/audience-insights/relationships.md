---
title: Odnosi između entiteta i putanja entiteta
description: Pravite i upravljajte odnosima između entiteta iz više izvora podataka.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171181"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="26dd5-103">Relacije između entiteta</span><span class="sxs-lookup"><span data-stu-id="26dd5-103">Relationships between entities</span></span>

<span data-ttu-id="26dd5-104">Relacije povezuju entitete i definišu grafikon vaših podataka kada entiteti dele zajednički identifikator, strani ključ.</span><span class="sxs-lookup"><span data-stu-id="26dd5-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="26dd5-105">Ovaj strani ključ može se referencirati iz jednog entiteta na drugi.</span><span class="sxs-lookup"><span data-stu-id="26dd5-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="26dd5-106">Povezani entiteti omogućavaju definiciju segmenata i mere na osnovu više izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="26dd5-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="26dd5-107">Postoje tri vrste relacija:</span><span class="sxs-lookup"><span data-stu-id="26dd5-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="26dd5-108">Sistemske relacije koje ne mogu da se uređuju, kreira ih sistem kao deo procesa ujednačavanja podataka</span><span class="sxs-lookup"><span data-stu-id="26dd5-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="26dd5-109">Nasleđene relacije bez mogućnosti uređivanja, koje se automatski kreiraju iz unosa izvora podataka</span><span class="sxs-lookup"><span data-stu-id="26dd5-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="26dd5-110">Prilagođene relacije sa mogućnošću uređivanja, koje kreiraju i konfigurišu korisnici</span><span class="sxs-lookup"><span data-stu-id="26dd5-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="26dd5-111">Sistemske relacije koje ne mogu da se uređuju</span><span class="sxs-lookup"><span data-stu-id="26dd5-111">Non-editable system relationships</span></span>

<span data-ttu-id="26dd5-112">Tokom ujednačavanja podataka, sistemske relacije se automatski kreiraju na osnovu inteligentnog podudaranja.</span><span class="sxs-lookup"><span data-stu-id="26dd5-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="26dd5-113">Ove relacije pomažu da se povežu zapisi profila klijenata sa odgovarajućim zapisima.</span><span class="sxs-lookup"><span data-stu-id="26dd5-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="26dd5-114">Sledeći dijagram ilustruje kreiranje tri sistemske relacije.</span><span class="sxs-lookup"><span data-stu-id="26dd5-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="26dd5-115">Entitet klijenta se podudara sa drugim entitetima kako bi se napravio objedinjeni entitet *Klijent*.</span><span class="sxs-lookup"><span data-stu-id="26dd5-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Dijagram sa putanjama relacija za entitet klijenta sa tri relacije „1-n“.":::

- <span data-ttu-id="26dd5-117">**Relacija *CustomerToContact*** je kreirana između entiteta *Klijent* i entiteta *Kontakt*.</span><span class="sxs-lookup"><span data-stu-id="26dd5-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="26dd5-118">Entitet *Klijent* dobija ključno polje **Contact_contactID** da stupi u relaciju sa poljem **contactId** ključa entiteta *Kontakt*.</span><span class="sxs-lookup"><span data-stu-id="26dd5-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="26dd5-119">**Relacija *CustomerToAccount*** je kreirana između entiteta *Klijent* i entiteta *Poslovni kontakt*.</span><span class="sxs-lookup"><span data-stu-id="26dd5-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="26dd5-120">Entitet *Klijent* dobija polje ključa **Account_accountID** da stupi u relaciju sa poljem **accountID** ključa entiteta *Poslovni kontakt*.</span><span class="sxs-lookup"><span data-stu-id="26dd5-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="26dd5-121">**Relacija *CustomerToWebAccount*** je kreirana između entiteta *Klijent* i entiteta *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="26dd5-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="26dd5-122">Entitet *Klijent* dobija polje ključa **WebAccount_webaccountID** da stupi u relaciju sa poljem **webaccountID** ključa entiteta *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="26dd5-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="26dd5-123">Nasleđene relacije koje ne mogu da se uređuju</span><span class="sxs-lookup"><span data-stu-id="26dd5-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="26dd5-124">Tokom procesa unosa podataka, sistem proverava postoje li relacije u izvorima podataka.</span><span class="sxs-lookup"><span data-stu-id="26dd5-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="26dd5-125">Ako ne postoje relacije, sistem ih automatski kreira.</span><span class="sxs-lookup"><span data-stu-id="26dd5-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="26dd5-126">Te relacije se takođe koriste u posledičnim procesima.</span><span class="sxs-lookup"><span data-stu-id="26dd5-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="26dd5-127">Kreiranje prilagođene relacije</span><span class="sxs-lookup"><span data-stu-id="26dd5-127">Create a custom relationship</span></span>

<span data-ttu-id="26dd5-128">Relacija se sastoji od *izvornog entiteta* koji sadrži strani ključ i *ciljni entitet* na koji ukazuje strani ključ izvornog entiteta.</span><span class="sxs-lookup"><span data-stu-id="26dd5-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="26dd5-129">U uvidima o korisnicima idite na **Podaci** > **Odnosi**.</span><span class="sxs-lookup"><span data-stu-id="26dd5-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="26dd5-130">Izaberite **Nova relacija**.</span><span class="sxs-lookup"><span data-stu-id="26dd5-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="26dd5-131">U oknu **Nova relacija**, navedite sledeće informacije:</span><span class="sxs-lookup"><span data-stu-id="26dd5-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Novo bočno okno relacije sa praznim poljima za unos.":::

   - <span data-ttu-id="26dd5-133">**Naziv relacije**: Naziv koji odražava svrhu veze.</span><span class="sxs-lookup"><span data-stu-id="26dd5-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="26dd5-134">Primer: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="26dd5-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="26dd5-135">**Opis**: Opis relacije.</span><span class="sxs-lookup"><span data-stu-id="26dd5-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="26dd5-136">**Izvorni entitet**: Entitet koji se koristi kao izvor u relaciji.</span><span class="sxs-lookup"><span data-stu-id="26dd5-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="26dd5-137">Primer: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="26dd5-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="26dd5-138">**Ciljni entitet**: Entitet koji se koristi kao cilj u relaciji.</span><span class="sxs-lookup"><span data-stu-id="26dd5-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="26dd5-139">Primer: Klijent.</span><span class="sxs-lookup"><span data-stu-id="26dd5-139">Example: Customer.</span></span>
   - <span data-ttu-id="26dd5-140">**Izvorna kardinalnost**: Navedite kardinalnost izvornog entiteta.</span><span class="sxs-lookup"><span data-stu-id="26dd5-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="26dd5-141">Kardinalnost opisuje broj mogućih elemenata u skupu.</span><span class="sxs-lookup"><span data-stu-id="26dd5-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="26dd5-142">Uvek se odnosi na ciljnu kardinalnost.</span><span class="sxs-lookup"><span data-stu-id="26dd5-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="26dd5-143">Možete birati između **Jedan** i **Više**.</span><span class="sxs-lookup"><span data-stu-id="26dd5-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="26dd5-144">Podržani su samo relacije više-prema-jedan i jedan-prema-jedan.</span><span class="sxs-lookup"><span data-stu-id="26dd5-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="26dd5-145">Više prema jedan: Više izvornih zapisa može se odnositi na jedan ciljni zapis.</span><span class="sxs-lookup"><span data-stu-id="26dd5-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="26dd5-146">Primer: Više slučajeva podrške od jednog klijenta.</span><span class="sxs-lookup"><span data-stu-id="26dd5-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="26dd5-147">Jedan prema jedan: Jedan izvorni zapis odnosi se na jedan ciljni zapis.</span><span class="sxs-lookup"><span data-stu-id="26dd5-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="26dd5-148">Primer: Jedan ID lojalnosti za jednog klijenta.</span><span class="sxs-lookup"><span data-stu-id="26dd5-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="26dd5-149">Relacije „Više prema više“ mogu se kreirati pomoću dve relacije „više prema jedan“ i povezujućeg entiteta, koji povezuje izvorni entitet i ciljni entitet.</span><span class="sxs-lookup"><span data-stu-id="26dd5-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="26dd5-150">**Ciljna kardinalnost**: Izaberite kardinalnost ciljnih zapisa entiteta.</span><span class="sxs-lookup"><span data-stu-id="26dd5-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="26dd5-151">**Polje izvornog ključa**: Polje stranog ključa u izvornom entitetu.</span><span class="sxs-lookup"><span data-stu-id="26dd5-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="26dd5-152">Primer: SupportCase može koristiti CaseID kao polje stranog ključa.</span><span class="sxs-lookup"><span data-stu-id="26dd5-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="26dd5-153">**Polje ciljnog ključa**: Polje ključa ciljnog entiteta.</span><span class="sxs-lookup"><span data-stu-id="26dd5-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="26dd5-154">Primer „Klijent“ bi mogao da koristi polje ključa **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="26dd5-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="26dd5-155">Izaberite **Sačuvaj** da biste kreirali prilagođenu relaciju.</span><span class="sxs-lookup"><span data-stu-id="26dd5-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="26dd5-156">Prikaz relacija</span><span class="sxs-lookup"><span data-stu-id="26dd5-156">View relationships</span></span>

<span data-ttu-id="26dd5-157">Na stranici Relacije navedene su sve relacije koje su kreirane.</span><span class="sxs-lookup"><span data-stu-id="26dd5-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="26dd5-158">Svaki red predstavlja relaciju, što takođe uključuje detalje o izvornom entitetu, ciljnom entitetu i kardinalnosti.</span><span class="sxs-lookup"><span data-stu-id="26dd5-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Lista relacija i opcija na traci sa radnjama na stranici Relacije.":::

<span data-ttu-id="26dd5-160">Ova stranica nudi skup opcija za postojeće i nove relacije:</span><span class="sxs-lookup"><span data-stu-id="26dd5-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="26dd5-161">**Nova relacija**: [Kreiranje nove relacije](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="26dd5-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="26dd5-162">**Vizuelizator**: [Istražite vizuelizator odnosa](#explore-the-relationship-visualizer) da biste videli mrežni dijagram postojećih relacija i njihovu kardinalnost.</span><span class="sxs-lookup"><span data-stu-id="26dd5-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="26dd5-163">**Filtriraj prema**: Izaberite tip relacija koji će se prikazivati na listi.</span><span class="sxs-lookup"><span data-stu-id="26dd5-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="26dd5-164">**Pretraga relacija**: Koristite tekstualnu pretragu svojstava relacija.</span><span class="sxs-lookup"><span data-stu-id="26dd5-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="26dd5-165">Istražite vizuelizator relacija</span><span class="sxs-lookup"><span data-stu-id="26dd5-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="26dd5-166">Vizuelizator relacija prikazuje mrežni dijagram postojećih relacija između povezanih entiteta i njihovu kardinalnost.</span><span class="sxs-lookup"><span data-stu-id="26dd5-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="26dd5-167">Da biste prilagodili prikaz, možete da promenite položaj okvira tako što ćete ih prevući na podlogu.</span><span class="sxs-lookup"><span data-stu-id="26dd5-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Snimak ekrana mrežnog dijagrama vizuelizatora relacija sa vezama između povezanih entiteta.":::

<span data-ttu-id="26dd5-169">Dostupne opcije:</span><span class="sxs-lookup"><span data-stu-id="26dd5-169">Available options:</span></span> 
- <span data-ttu-id="26dd5-170">**Izvezi kao sliku**: Snimite trenutni prikaz kao datoteku slike.</span><span class="sxs-lookup"><span data-stu-id="26dd5-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="26dd5-171">**Promena na horizontalni/vertikalni raspored**: Promenite poravnanje entiteta i relacija.</span><span class="sxs-lookup"><span data-stu-id="26dd5-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="26dd5-172">**Uredi**: Ažurirajte svojstva prilagođenih relacija u oknu za uređivanje i sačuvajte promene.</span><span class="sxs-lookup"><span data-stu-id="26dd5-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="26dd5-173">Upravljanje postojećim relacijama</span><span class="sxs-lookup"><span data-stu-id="26dd5-173">Manage existing relationships</span></span> 

<span data-ttu-id="26dd5-174">Na stranici Relacije, svaka relacija je predstavljena jednim redom.</span><span class="sxs-lookup"><span data-stu-id="26dd5-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="26dd5-175">Izaberite relaciju i odaberite jednu od sledećih opcija:</span><span class="sxs-lookup"><span data-stu-id="26dd5-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="26dd5-176">**Uredi**: Ažurirajte svojstva prilagođenih relacija u oknu za uređivanje i sačuvajte promene.</span><span class="sxs-lookup"><span data-stu-id="26dd5-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="26dd5-177">**Izbriši**: Izbrišite prilagođene relacije.</span><span class="sxs-lookup"><span data-stu-id="26dd5-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="26dd5-178">**Prikaz**: Prikažite sistemski kreirane i nasleđene relacije.</span><span class="sxs-lookup"><span data-stu-id="26dd5-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="26dd5-179">Sledeći korak</span><span class="sxs-lookup"><span data-stu-id="26dd5-179">Next step</span></span>

<span data-ttu-id="26dd5-180">Sistemske i prilagođene relacije se koriste za [kreiranje segmenata](segments.md) na osnovu više izvora podataka koji više nisu u silosu.</span><span class="sxs-lookup"><span data-stu-id="26dd5-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
