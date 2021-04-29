---
title: Aktivnosti klijenta
description: Definišite aktivnosti klijenata i pregledajte ih na vremenskoj osi klijenata.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866424"
---
# <a name="customer-activities"></a><span data-ttu-id="96891-103">Aktivnosti klijenta</span><span class="sxs-lookup"><span data-stu-id="96891-103">Customer activities</span></span>

<span data-ttu-id="96891-104">Kombinujte aktivnosti klijenata iz [raznih izvora podataka](data-sources.md) u usluzi Dynamics 365 Customer Insights kako biste kreirali vremensku osu koja hronološki navodi aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="96891-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="96891-105">Uključite hronologiju u Dynamics 365 aplikacije sa rešenjem [Programski dodatak za korisničku karticu](customer-card-add-in.md) ili u Power BI kontrolnoj tabli.</span><span class="sxs-lookup"><span data-stu-id="96891-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="96891-106">Definišite aktivnost</span><span class="sxs-lookup"><span data-stu-id="96891-106">Define an activity</span></span>

<span data-ttu-id="96891-107">Vaši izvori podataka mogu da uključe entitete koji imaju podatke o transakcijama i aktivnostima iz više izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="96891-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="96891-108">Identifikujte ove entitete i izaberite aktivnosti koje želite da vidite na vremenskoj osi klijenta.</span><span class="sxs-lookup"><span data-stu-id="96891-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="96891-109">Odaberite entitet koji uključuje vaše ciljne aktivnosti ili aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="96891-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="96891-110">Entitet mora imati najmanje jedan atribut tipa **Datum** da bi bio uključeni u vremensku osu klijenta i dodavati entitete koji nemaju polja tipa **Datum**.</span><span class="sxs-lookup"><span data-stu-id="96891-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="96891-111">Kontrola **Dodajte aktivnost** je onemogućena ako nije pronađen takav entitet.</span><span class="sxs-lookup"><span data-stu-id="96891-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="96891-112">U uvidima o korisnicima idite na **Podaci** > **Aktivnosti**.</span><span class="sxs-lookup"><span data-stu-id="96891-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="96891-113">Izaberite **Dodaj aktivnost** da biste započeli vođeno iskustvo za postupak podešavanja aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="96891-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="96891-114">U koraku **Podaci o aktivnostima**, podesite vrednosti za sledeća polja:</span><span class="sxs-lookup"><span data-stu-id="96891-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="96891-115">**Naziv aktivnosti**: Izaberite ime za svoju aktivnost.</span><span class="sxs-lookup"><span data-stu-id="96891-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="96891-116">**Entitet**: Odaberite entitet koji uključuje podatke o transakcijama ili aktivnostima.</span><span class="sxs-lookup"><span data-stu-id="96891-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="96891-117">**Primarni ključ**: Izaberite polje koje jedinstveno identifikuje zapis.</span><span class="sxs-lookup"><span data-stu-id="96891-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="96891-118">Ono ne bi smelo da sadrži duplikate, prazne vrednosti ili vrednosti koje nedostaju.</span><span class="sxs-lookup"><span data-stu-id="96891-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Podesite podatke o aktivnosti sa imenom, entitetom i primarnim ključem.":::

1. <span data-ttu-id="96891-120">Izaberite **Sledeće** da pređete na sledeći korak.</span><span class="sxs-lookup"><span data-stu-id="96891-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="96891-121">U koraku **Relacija** konfigurišite detalje za povezivanje podataka o aktivnostima sa odgovarajućim klijentom.</span><span class="sxs-lookup"><span data-stu-id="96891-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="96891-122">Ovaj korak vizualizuje vezu između entiteta.</span><span class="sxs-lookup"><span data-stu-id="96891-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="96891-123">**Prvi**: Strano polje u entitetu aktivnosti koje će se koristiti za uspostavljanje relacije sa drugim entitetom.</span><span class="sxs-lookup"><span data-stu-id="96891-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="96891-124">**Drugi**: Odgovarajući izvorni entitet klijenta sa kojim će vaš entitet aktivnosti biti u relaciji.</span><span class="sxs-lookup"><span data-stu-id="96891-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="96891-125">Možete se povezati samo sa izvornim entitetima klijenata koji se koriste u procesu objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="96891-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="96891-126">**Treći**: Ako relacija između ovog entiteta aktivnosti i izabranog izvornog entiteta klijenta već postoji, naziv relacije će biti u režimu samo za čitanje.</span><span class="sxs-lookup"><span data-stu-id="96891-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="96891-127">Ako takva relacija ne postoji, kreiraće se nova relacija pod nazivom koji navedete u ovom polju.</span><span class="sxs-lookup"><span data-stu-id="96891-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definisanje relacije između entiteta.":::

1. <span data-ttu-id="96891-129">Izaberite **Sledeće** da pređete na sledeći korak.</span><span class="sxs-lookup"><span data-stu-id="96891-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="96891-130">U koraku **Objedinjavanje aktivnosti**, odaberite događaj aktivnosti i vreme početka aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="96891-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="96891-131">**Obavezna polja**</span><span class="sxs-lookup"><span data-stu-id="96891-131">**Required fields**</span></span>
      1. <span data-ttu-id="96891-132">**Aktivnost događaja**: Polje koje je događaj za ovu aktivnost</span><span class="sxs-lookup"><span data-stu-id="96891-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="96891-133">**Vremenska oznaka**: Polje koje predstavlja vreme početka vaše aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="96891-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="96891-134">**Opcionalna polja**</span><span class="sxs-lookup"><span data-stu-id="96891-134">**Optional fields**</span></span>
      1. <span data-ttu-id="96891-135">**Dodatni detalj**: Polje sa relevantnim informacijama za ovu aktivnost.</span><span class="sxs-lookup"><span data-stu-id="96891-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="96891-136">**Ikona**: Ikona koja najbolje predstavlja ovu vrstu aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="96891-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="96891-137">**Veb-adresa**: Polje koje sadrži URL adresu sa informacijama o ovoj aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="96891-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="96891-138">Na primer, transakcioni sistem koji je izvor ove aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="96891-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="96891-139">Ova URL adresa može biti bilo koje polje iz izvora podataka ili se može napraviti kao novo polje pomoću Power Query transformacije.</span><span class="sxs-lookup"><span data-stu-id="96891-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="96891-140">Podaci o URL adresi biće sačuvani u entitetu *Objedinjena aktivnost*, koji se može posledično koristiti pomoću [API-ja](apis.md).</span><span class="sxs-lookup"><span data-stu-id="96891-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Navedite podatke o aktivnostima klijenata u entitetu Ujedinjene aktivnosti.":::

1. <span data-ttu-id="96891-142">Izaberite **Sledeće** da biste prešli na sledeći korak.</span><span class="sxs-lookup"><span data-stu-id="96891-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="96891-143">Možete izabrati **Završite i pregledaj** da biste sada sačuvali aktivnost sa tipom aktivnosti podešenim na **Ostalo**.</span><span class="sxs-lookup"><span data-stu-id="96891-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="96891-144">U koraku **Tip aktivnosti**, odaberite tip aktivnosti i opcionalno odaberite ako želite da semantički mapirate neke od vrsta aktivnosti za upotrebu u drugim oblastima usluge Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="96891-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="96891-145">Trenutno, tipovi aktivnosti *Pretplata* i *Detalj ulazne porudžbine* mogu se semantički mapirati nakon dogovora o mapiranju polja.</span><span class="sxs-lookup"><span data-stu-id="96891-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="96891-146">Ako vrsta aktivnosti nije relevantna za novu aktivnost, možete odabrati *Ostalo* ili *Kreiraj novu* za prilagođeni tip aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="96891-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="96891-147">Izaberite **Sledeće** da biste prešli na sledeći korak.</span><span class="sxs-lookup"><span data-stu-id="96891-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="96891-148">U koraku **Pregled**, potvrdite svoje izbore.</span><span class="sxs-lookup"><span data-stu-id="96891-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="96891-149">Vratite se na bilo koji od prethodnih koraka i ažurirajte informacije ako je potrebno.</span><span class="sxs-lookup"><span data-stu-id="96891-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Pregledajte navedena polja za aktivnost.":::
   
1. <span data-ttu-id="96891-151">Izaberite **Sačuvaj aktivnost** da biste primenili promene i izabrali **Gotovo** da biste se vratili u **Podaci** > **Aktivnosti**.</span><span class="sxs-lookup"><span data-stu-id="96891-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="96891-152">Ovde vidite koje su aktivnosti postavljene da se prikazuju na vremenskoj osi.</span><span class="sxs-lookup"><span data-stu-id="96891-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="96891-153">Na stranici **Aktivnosti**, izaberite **Pokreni** da biste obradili aktivnost.</span><span class="sxs-lookup"><span data-stu-id="96891-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="96891-154">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="96891-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="96891-155">Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="96891-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="96891-156">Možete izabrati status procesa da biste videli detalje o toku celog posla.</span><span class="sxs-lookup"><span data-stu-id="96891-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="96891-157">Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="96891-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="96891-158">Upravljanje postojećim aktivnostima</span><span class="sxs-lookup"><span data-stu-id="96891-158">Manage existing activities</span></span>

<span data-ttu-id="96891-159">Na stranici **Podaci** > **Aktivnosti** možete da vidite sve sačuvane aktivnosti i upravljate njima.</span><span class="sxs-lookup"><span data-stu-id="96891-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="96891-160">Svaka aktivnost se predstavlja u redu koji takođe uključuje detalje o izvoru, entitetu i tipu aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="96891-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="96891-161">Sledeće radnje su dostupne kada izaberete aktivnost.</span><span class="sxs-lookup"><span data-stu-id="96891-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="96891-162">**Uredi**: Otvara podešavanje aktivnosti u koraku pregleda.</span><span class="sxs-lookup"><span data-stu-id="96891-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="96891-163">U ovom koraku možete promeniti bilo koju trenutnu konfiguraciju.</span><span class="sxs-lookup"><span data-stu-id="96891-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="96891-164">Kada promenite konfiguraciju, izaberite **Sačuvaj aktivnost**, a zatim izaberite **Pokreni** da biste obradili promene.</span><span class="sxs-lookup"><span data-stu-id="96891-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="96891-165">**Preimenuj**: Otvara dijalog u koji ćete uneti drugi naziv za izabranu aktivnost.</span><span class="sxs-lookup"><span data-stu-id="96891-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="96891-166">Izaberite **Sačuvaj** da primenite promene.</span><span class="sxs-lookup"><span data-stu-id="96891-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="96891-167">**Izbriši**: Otvara dijalog za potvrdu brisanja izabrane aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="96891-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="96891-168">Takođe možete izbrisati više aktivnosti odjednom tako što ćete izabrati aktivnosti, a zatim izabrati ikonu za brisanje.</span><span class="sxs-lookup"><span data-stu-id="96891-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="96891-169">Izaberite **Izbriši** da biste potvrdili brisanje.</span><span class="sxs-lookup"><span data-stu-id="96891-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
