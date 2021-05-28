---
title: Kreiranje segmenata i upravljanje njima
description: Napravite segmente klijenata da biste ih grupisali na osnovu različitih atributa.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064954"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="83655-103">Kreiranje segmenata i upravljanje njima</span><span class="sxs-lookup"><span data-stu-id="83655-103">Create and manage segments</span></span>

<span data-ttu-id="83655-104">Definišite složene filtere oko jedinstvenog entiteta klijenta i sa njim povezanih entiteta.</span><span class="sxs-lookup"><span data-stu-id="83655-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="83655-105">Svaki segment nakon obrade kreira skup korisničkih zapisa koje možete da izvoziti i za koje možete da preduzimate neke korake.</span><span class="sxs-lookup"><span data-stu-id="83655-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="83655-106">Segmentima se upravlja na stranici **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="83655-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="83655-107">Sledeći primer ilustruje korišćenje mogućnosti segmentacije.</span><span class="sxs-lookup"><span data-stu-id="83655-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="83655-108">Definisali smo segment za klijente koji su naručili robu za najmanje 500 USD u poslednjih 90 dana *i* koji su bili uključeni u poziv korisničke službe koji je prosleđen.</span><span class="sxs-lookup"><span data-stu-id="83655-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Snimak ekrana korisničkog interfejsa kreatora segmenata sa dve grupe koje određuju segment klijenata.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="83655-110">Kreirajte novi segment</span><span class="sxs-lookup"><span data-stu-id="83655-110">Create a new segment</span></span>

<span data-ttu-id="83655-111">Postoji više načina za kreiranje novog segmenta.</span><span class="sxs-lookup"><span data-stu-id="83655-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="83655-112">Ovaj odeljak opisuje kako se kreira *prazan segment* ispočetka.</span><span class="sxs-lookup"><span data-stu-id="83655-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="83655-113">Takođe možete da kreirate *brzi segment* na osnovu postojećih entiteta ili iskoristite modele mašinskog učenja da biste dobili *predložene segmente*.</span><span class="sxs-lookup"><span data-stu-id="83655-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="83655-114">Još informacija: [Pregled segmenata](segments.md).</span><span class="sxs-lookup"><span data-stu-id="83655-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="83655-115">Dok pravite segment, možete da sačuvate radnu verziju.</span><span class="sxs-lookup"><span data-stu-id="83655-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="83655-116">Biće sačuvana kao neaktivni segment i ne može se aktivirati kao završena sa važećom konfiguracijom.</span><span class="sxs-lookup"><span data-stu-id="83655-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="83655-117">Idite na stranicu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="83655-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="83655-118">Izaberite **Novo** > **Prazan segment**.</span><span class="sxs-lookup"><span data-stu-id="83655-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="83655-119">U oknu **Novi segment**, odaberite vrstu segmenta:</span><span class="sxs-lookup"><span data-stu-id="83655-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="83655-120">**Dinamički segmenti** se [osvežavaju](segments.md#refresh-segments) po redovnom rasporedu.</span><span class="sxs-lookup"><span data-stu-id="83655-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="83655-121">**Statički segmenti** se pokreću jednom kada ih kreirate.</span><span class="sxs-lookup"><span data-stu-id="83655-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="83655-122">Navedite **Izlazni naziv entiteta** za segment.</span><span class="sxs-lookup"><span data-stu-id="83655-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="83655-123">Opcionalno, unesite ime za prikaz i opis koji pomaže u prepoznavanju segmenta.</span><span class="sxs-lookup"><span data-stu-id="83655-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="83655-124">Izaberite **Sledeće** da dođete na stranicu **Graditelj segmenata** na kojoj definišete grupu.</span><span class="sxs-lookup"><span data-stu-id="83655-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="83655-125">Grupa je skup klijenata.</span><span class="sxs-lookup"><span data-stu-id="83655-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="83655-126">Odaberite entitet koji obuhvata atribute po kojima želite da segmentirate.</span><span class="sxs-lookup"><span data-stu-id="83655-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="83655-127">Odaberite atribut po segmentu.</span><span class="sxs-lookup"><span data-stu-id="83655-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="83655-128">Ovaj atribut može imati jedan od četiri tipa vrednosti: numerički, niska, datum ili logički.</span><span class="sxs-lookup"><span data-stu-id="83655-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="83655-129">Odaberite operator i vrednost za izabrani atribut.</span><span class="sxs-lookup"><span data-stu-id="83655-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="83655-130">![Prilagođeni filter grupe](media/customer-group-numbers.png "Filter grupe klijenata")</span><span class="sxs-lookup"><span data-stu-id="83655-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="83655-131">Broj</span><span class="sxs-lookup"><span data-stu-id="83655-131">Number</span></span> |<span data-ttu-id="83655-132">Definicija</span><span class="sxs-lookup"><span data-stu-id="83655-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="83655-133">1</span><span class="sxs-lookup"><span data-stu-id="83655-133">1</span></span>     |<span data-ttu-id="83655-134">Entity</span><span class="sxs-lookup"><span data-stu-id="83655-134">Entity</span></span>          |
   |<span data-ttu-id="83655-135">2</span><span class="sxs-lookup"><span data-stu-id="83655-135">2</span></span>     |<span data-ttu-id="83655-136">Atribut</span><span class="sxs-lookup"><span data-stu-id="83655-136">Attribute</span></span>          |
   |<span data-ttu-id="83655-137">3</span><span class="sxs-lookup"><span data-stu-id="83655-137">3</span></span>    |<span data-ttu-id="83655-138">Operator</span><span class="sxs-lookup"><span data-stu-id="83655-138">Operator</span></span>         |
   |<span data-ttu-id="83655-139">4</span><span class="sxs-lookup"><span data-stu-id="83655-139">4</span></span>    |<span data-ttu-id="83655-140">Vrednost</span><span class="sxs-lookup"><span data-stu-id="83655-140">Value</span></span>         |

   1. <span data-ttu-id="83655-141">Da biste grupi dodali više uslova, možete da koristite dva logička operatora:</span><span class="sxs-lookup"><span data-stu-id="83655-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="83655-142">Operator **I**: Oba uslova moraju da budu ispunjena kao deo procesa segmentacije.</span><span class="sxs-lookup"><span data-stu-id="83655-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="83655-143">Ova opcija je najkorisnija kada definišete uslove u različitim entitetima.</span><span class="sxs-lookup"><span data-stu-id="83655-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="83655-144">Operator **ILI**: Bilo koji od uslova mora biti ispunjen kao deo procesa segmentacije.</span><span class="sxs-lookup"><span data-stu-id="83655-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="83655-145">Ova opcija je najkorisnija kada definišete više uslova u istom entitetu.</span><span class="sxs-lookup"><span data-stu-id="83655-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="83655-146">![Operator ILI gde je potrebno ispuniti bilo koji uslov](media/segmentation-either-condition.png "Operator ILI gde je potrebno ispuniti bilo koji uslov")</span><span class="sxs-lookup"><span data-stu-id="83655-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="83655-147">Trenutno je moguće ugnezditi operator **ILI** unutar operatora **I**, ali ne i obrnuto.</span><span class="sxs-lookup"><span data-stu-id="83655-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="83655-148">Svaka grupa se podudara sa skupom klijenata.</span><span class="sxs-lookup"><span data-stu-id="83655-148">Each group matches set of customers.</span></span> <span data-ttu-id="83655-149">Možete kombinovati grupe da biste uključili klijente potrebne za vaš poslovni predmet.</span><span class="sxs-lookup"><span data-stu-id="83655-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="83655-150">Izaberite **Dodaj grupu**.</span><span class="sxs-lookup"><span data-stu-id="83655-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="83655-151">![Grupa klijenata dodaj grupu](media/customer-group-add-group.png "Grupa klijenata dodaj grupu")</span><span class="sxs-lookup"><span data-stu-id="83655-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="83655-152">Izaberite jedan od operatora skupova: **Unija**, **Presek** ili **Razlika**.</span><span class="sxs-lookup"><span data-stu-id="83655-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="83655-153">![Grupa klijenata dodaj uniju](media/customer-group-union.png "Grupa klijenata dodaj uniju")</span><span class="sxs-lookup"><span data-stu-id="83655-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="83655-154">**Unija** objedinjuje dve grupe.</span><span class="sxs-lookup"><span data-stu-id="83655-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="83655-155">**Presek** preklapa dve grupe.</span><span class="sxs-lookup"><span data-stu-id="83655-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="83655-156">Samo podaci koji *su zajednički* za obe grupe zadržavaju se u objedinjenoj grupi.</span><span class="sxs-lookup"><span data-stu-id="83655-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="83655-157">**Osim** kombinuje dve grupe.</span><span class="sxs-lookup"><span data-stu-id="83655-157">**Except** combines the two groups.</span></span> <span data-ttu-id="83655-158">Samo podaci u grupi A koji *nisu zajednički* sa podacima iz grupe B zadržavaju se.</span><span class="sxs-lookup"><span data-stu-id="83655-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="83655-159">Ako je entitet povezan putem objedinjenog entiteta klijenta putem [odnosa](relationships.md), morate definisati putanju odnosa da biste kreirali važeći segment.</span><span class="sxs-lookup"><span data-stu-id="83655-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="83655-160">Dodajte entitete iz putanje odnosa dok ne budete mogli da izaberete entitet **Klijent: CustomerInsights** iz padajuće liste.</span><span class="sxs-lookup"><span data-stu-id="83655-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="83655-161">Zatim odaberite **Svi zapisi** za svaki korak.</span><span class="sxs-lookup"><span data-stu-id="83655-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="83655-162">![Putanja odnosa tokom kreiranja segmenta](media/segments-multiple-relationships.png "Putanja odnosa tokom kreiranja segmenta")</span><span class="sxs-lookup"><span data-stu-id="83655-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="83655-163">Podrazumevano, segmenti generišu izlazni entitet koji sadrži sve atribute korisničkih profila koji se podudaraju sa definisanim filterima.</span><span class="sxs-lookup"><span data-stu-id="83655-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="83655-164">Ako se segment zasniva na drugim entitetima osim na entitetu *Klijent*, izlaznom entitetu možete dodati više atributa iz tih entiteta.</span><span class="sxs-lookup"><span data-stu-id="83655-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="83655-165">Izaberite **Atributi projekta** da biste odabrali atribute koji će biti dodati izlaznom entitetu.</span><span class="sxs-lookup"><span data-stu-id="83655-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="83655-166">Primer: Segment se zasniva na entitetu koji sadrži podatke o aktivnostima klijenata koji su povezani sa entitetom *Klijent*.</span><span class="sxs-lookup"><span data-stu-id="83655-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="83655-167">Segment traži sve klijente koji su pozvali tehničku podršku u poslednjih 60 dana.</span><span class="sxs-lookup"><span data-stu-id="83655-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="83655-168">Možete odabrati da dodate trajanje poziva i broj poziva svim podudarnim zapisima klijenata u izlaznom entitetu.</span><span class="sxs-lookup"><span data-stu-id="83655-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="83655-169">Ove informacije mogu biti korisne za slanje e-pošte sa korisnim vezama do članaka pomoći na mreži i često postavljanih pitanja klijentima koji su često zvali.</span><span class="sxs-lookup"><span data-stu-id="83655-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="83655-170">Projektovani atributi rade samo za entitete koji imaju odnos „jedan prema više“ sa entitetom klijenta.</span><span class="sxs-lookup"><span data-stu-id="83655-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="83655-171">Na primer, jedan klijent može imati više pretplata.</span><span class="sxs-lookup"><span data-stu-id="83655-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="83655-172">Atribute možete projektovati samo iz entiteta koji se koristi u svakoj grupi upita za segmente koji gradite.</span><span class="sxs-lookup"><span data-stu-id="83655-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="83655-173">Projektovani atributi uzimaju se u obzir kada se koriste operatori skupova.</span><span class="sxs-lookup"><span data-stu-id="83655-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="83655-174">Izaberite **Sačuvaj** da biste sačuvali segment.</span><span class="sxs-lookup"><span data-stu-id="83655-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="83655-175">Vaš segment će biti sačuvan i obrađen ukoliko su svi zahtevi potvrđeni.</span><span class="sxs-lookup"><span data-stu-id="83655-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="83655-176">U suprotnom, biće sačuvan kao radna verzija.</span><span class="sxs-lookup"><span data-stu-id="83655-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="83655-177">Izaberite **Nazad na segmente** da biste se vratili na stranicu **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="83655-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="83655-178">Brzi segmenti</span><span class="sxs-lookup"><span data-stu-id="83655-178">Quick segments</span></span>

<span data-ttu-id="83655-179">Brzi segmenti vam omogućavaju brzu izgradnju jednostavnih segmenata pomoću jednog operatora za brže uvide.</span><span class="sxs-lookup"><span data-stu-id="83655-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="83655-180">Na stranici **Segmenti**, izaberite **Novo** > **Kreiraj iz**.</span><span class="sxs-lookup"><span data-stu-id="83655-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="83655-181">Izaberite opciju **Profili** da izgradite segment koji je zasnovan na entitetu *objedinjenog klijenta*.</span><span class="sxs-lookup"><span data-stu-id="83655-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="83655-182">Izaberite opciju **Mere** za izgradnju segmenta oko mera koje ste prethodno kreirali.</span><span class="sxs-lookup"><span data-stu-id="83655-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="83655-183">Izaberite opciju **Obaveštavanje** da izgradite segment oko jednog od izlaznih entiteta koje ste generisali koristeći mogućnosti **Predviđanja** ili **Prilagođeni modeli**.</span><span class="sxs-lookup"><span data-stu-id="83655-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="83655-184">U dijalogu **Novi brzi segment** izaberite atribut iz padajuće liste **Polje**.</span><span class="sxs-lookup"><span data-stu-id="83655-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="83655-185">Sistem će vam pružiti neke dodatne uvide koji će vam pomoći da stvorite bolje segmente svojih klijenata.</span><span class="sxs-lookup"><span data-stu-id="83655-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="83655-186">Za kategorijska polja prikazaćemo 10 glavnih brojeva klijenta.</span><span class="sxs-lookup"><span data-stu-id="83655-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="83655-187">Odaberite **Vrednost** i izabrali **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="83655-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="83655-188">Za numerički atribut, sistem će pokazati koja vrednost atributa spada ispod svakog procenta klijenta.</span><span class="sxs-lookup"><span data-stu-id="83655-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="83655-189">Odaberite **Operator** i **Vrednost**, a zatim izaberite **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="83655-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="83655-190">Sistem će vam pružiti **Procenjenu veličinu segmenta**.</span><span class="sxs-lookup"><span data-stu-id="83655-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="83655-191">Možete odabrati da li da generišete segment koji ste definisali ili da ga prvo pregledate kako biste dobili drugu veličinu segmenta.</span><span class="sxs-lookup"><span data-stu-id="83655-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="83655-192">![Naziv i procena za brzi segment](media/quick-segment-name.png "Naziv i procena za brzi segment")</span><span class="sxs-lookup"><span data-stu-id="83655-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="83655-193">Navedite **Naziv** za segment.</span><span class="sxs-lookup"><span data-stu-id="83655-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="83655-194">Opcionalno, navedite **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="83655-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="83655-195">Izaberite **Sačuvaj** da biste kreirali segment.</span><span class="sxs-lookup"><span data-stu-id="83655-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="83655-196">Nakon završetka obrade segmenta, možete ga pregledati kao i bilo koji drugi segment koji ste kreirali.</span><span class="sxs-lookup"><span data-stu-id="83655-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="83655-197">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="83655-197">Next steps</span></span>

<span data-ttu-id="83655-198">[Izvezite segment](export-destinations.md) i istražite [karticu klijenta](customer-card-add-in.md) i [konektore](export-power-bi.md) da biste dobili uvid na nivou klijenta.</span><span class="sxs-lookup"><span data-stu-id="83655-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
