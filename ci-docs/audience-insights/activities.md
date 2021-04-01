---
title: Aktivnosti klijenta
description: Definišite aktivnosti klijenata i pregledajte ih na vremenskoj osi klijenata.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596746"
---
# <a name="customer-activities"></a><span data-ttu-id="11fb8-103">Aktivnosti klijenta</span><span class="sxs-lookup"><span data-stu-id="11fb8-103">Customer activities</span></span>

<span data-ttu-id="11fb8-104">Kombinujte aktivnosti klijenata iz [raznih izvora podataka](data-sources.md) u usluzi Dynamics 365 Customer Insights da biste kreirali vremensku osu klijenata koja navodi aktivnosti u hronološkom redosledu.</span><span class="sxs-lookup"><span data-stu-id="11fb8-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="11fb8-105">Vremensku osu možete uključiti u aplikacije za angažovanje korisnika u sistemu Dynamics 365 preko [programskog dodatka kartice klijenta](customer-card-add-in.md) ili u Power BI kontrolnoj tabli.</span><span class="sxs-lookup"><span data-stu-id="11fb8-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="11fb8-106">Definišite aktivnost</span><span class="sxs-lookup"><span data-stu-id="11fb8-106">Define an activity</span></span>

<span data-ttu-id="11fb8-107">Vaši izvori podataka uključuju entitete koji imaju podatke o transakcijama i aktivnostima iz više izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="11fb8-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="11fb8-108">Identifikujte ove entitete i izaberite aktivnosti koje želite da vidite na vremenskoj osi klijenta.</span><span class="sxs-lookup"><span data-stu-id="11fb8-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="11fb8-109">Odaberite entitet koji uključuje vaše ciljne aktivnosti ili aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="11fb8-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="11fb8-110">U uvidima o korisnicima idite na **Podaci** > **Aktivnosti**.</span><span class="sxs-lookup"><span data-stu-id="11fb8-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="11fb8-111">Izaberite **Dodaj aktivnost**.</span><span class="sxs-lookup"><span data-stu-id="11fb8-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="11fb8-112">Entitet mora imati najmanje jedan atribut tipa **Datum** da bi bio uključeni u vremensku osu klijenta i dodavati entitete koji nemaju polja tipa **Datum**.</span><span class="sxs-lookup"><span data-stu-id="11fb8-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="11fb8-113">Kontrola **Dodajte aktivnost** je onemogućena ako nije pronađen takav entitet.</span><span class="sxs-lookup"><span data-stu-id="11fb8-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="11fb8-114">U oknu **Dodajte aktivnost**, postavite vrednosti za sledeća polja:</span><span class="sxs-lookup"><span data-stu-id="11fb8-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="11fb8-115">**Entitet**: Odaberite entitet koji uključuje podatke o transakcijama ili aktivnostima.</span><span class="sxs-lookup"><span data-stu-id="11fb8-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="11fb8-116">**Primarni ključ**: Izaberite polje koje jedinstveno identifikuje zapis.</span><span class="sxs-lookup"><span data-stu-id="11fb8-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="11fb8-117">Ono ne bi smelo da sadrži duplikate, prazne vrednosti ili vrednosti koje nedostaju.</span><span class="sxs-lookup"><span data-stu-id="11fb8-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="11fb8-118">**Vremenska oznaka**: Izaberite polje koje predstavlja vreme početka vaše aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="11fb8-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="11fb8-119">**Događaj**: Izaberite polje koje je događaj za aktivnost.</span><span class="sxs-lookup"><span data-stu-id="11fb8-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="11fb8-120">**Veb-adresa**: Izaberite polje koje predstavlja URL adresu koja pruža dodatne informacije o ovoj aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="11fb8-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="11fb8-121">Na primer, transakcioni sistem koji je izvor ove aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="11fb8-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="11fb8-122">Ova URL adresa može biti bilo koje polje iz izvora podataka ili se može napraviti kao novo polje pomoću Power Query transformacije.</span><span class="sxs-lookup"><span data-stu-id="11fb8-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="11fb8-123">Podaci ove URL adrese će biti sačuvani u entitetu objedinjenih aktivnosti, koji može da se koristi na nižem toku pomoću API-ja.</span><span class="sxs-lookup"><span data-stu-id="11fb8-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="11fb8-124">**Detalji**: Po želji, odaberite polje koje ćete dodati za dodatne detalje.</span><span class="sxs-lookup"><span data-stu-id="11fb8-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="11fb8-125">**Ikona**: Po želji odaberite ikonu koja predstavlja ovu aktivnost.</span><span class="sxs-lookup"><span data-stu-id="11fb8-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="11fb8-126">**Tip aktivnosti**: Definišite referencu tipa aktivnosti na Common Data Model koji najbolje opisuje semantičku definiciju aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="11fb8-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="11fb8-127">U odeljku **Uspostavite odnos**, konfigurišite detalje da biste povezali podatke o aktivnostima sa odgovarajućim klijentom.</span><span class="sxs-lookup"><span data-stu-id="11fb8-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="11fb8-128">**Polje entiteta aktivnosti**: Izaberite polje u vašem entitetu aktivnosti koje će se koristiti za uspostavljanje veze sa drugim entitetom.</span><span class="sxs-lookup"><span data-stu-id="11fb8-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="11fb8-129">**Entitet klijenta**: Izaberite odgovarajući entitet korisnika sa kojim će vaš odnos biti u relaciji.</span><span class="sxs-lookup"><span data-stu-id="11fb8-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="11fb8-130">Možete se odnositi samo na one izvorne entitete klijenata koji se koriste u postupku objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="11fb8-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="11fb8-131">**Polje entiteta klijenta**: Ovo polje prikazuje primarni ključ izvornog entiteta klijenta kako je izabran u procesu mapiranja.</span><span class="sxs-lookup"><span data-stu-id="11fb8-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="11fb8-132">Ovo polje primarnog ključa u izvornom entitetu klijenta koristi se za uspostavljanje relacije sa entitetom aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="11fb8-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="11fb8-133">**Naziv**: Ako relacija između ovog entiteta aktivnosti i izabranog izvornog entiteta klijenta već postoji, naziv relacije će biti u režimu samo za čitanje.</span><span class="sxs-lookup"><span data-stu-id="11fb8-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="11fb8-134">Ako takva relacija ne postoji, stvoriće se nova relacija sa ovde navedenim nazivom.</span><span class="sxs-lookup"><span data-stu-id="11fb8-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11fb8-135">![Definisanje relacije entiteta](media/activities-entities-define.png "Definisanje relacije entiteta")</span><span class="sxs-lookup"><span data-stu-id="11fb8-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="11fb8-136">Izaberite **Sačuvaj** da primenite promene.</span><span class="sxs-lookup"><span data-stu-id="11fb8-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="11fb8-137">Na stranici **Aktivnosti**, izaberite **Pokreni**.</span><span class="sxs-lookup"><span data-stu-id="11fb8-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="11fb8-138">Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese.</span><span class="sxs-lookup"><span data-stu-id="11fb8-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="11fb8-139">Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="11fb8-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="11fb8-140">Možete izabrati status procesa da biste videli detalje o toku celog posla.</span><span class="sxs-lookup"><span data-stu-id="11fb8-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="11fb8-141">Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.</span><span class="sxs-lookup"><span data-stu-id="11fb8-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="11fb8-142">Uređivanje aktivnosti</span><span class="sxs-lookup"><span data-stu-id="11fb8-142">Edit an activity</span></span>

1. <span data-ttu-id="11fb8-143">U uvidima o korisnicima idite na **Podaci** > **Aktivnosti**.</span><span class="sxs-lookup"><span data-stu-id="11fb8-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="11fb8-144">Izaberite entitet aktivnosti koji želite da izmenite i izaberite **Uređuj**.</span><span class="sxs-lookup"><span data-stu-id="11fb8-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="11fb8-145">Ili možete da zadržite pokazivač preko reda entiteta i izaberite ikonu **Uređuj**.</span><span class="sxs-lookup"><span data-stu-id="11fb8-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="11fb8-146">Kliknite na ikonu **Uređuj**.</span><span class="sxs-lookup"><span data-stu-id="11fb8-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="11fb8-147">U oknu **Uređivanje aktivnosti**, ažurirajte vrednosti i izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="11fb8-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="11fb8-148">Na stranici **Aktivnosti**, izaberite **Pokreni**.</span><span class="sxs-lookup"><span data-stu-id="11fb8-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="11fb8-149">Izbriši aktivnost</span><span class="sxs-lookup"><span data-stu-id="11fb8-149">Delete an activity</span></span>

1. <span data-ttu-id="11fb8-150">U uvidima o korisnicima idite na **Podaci** > **Aktivnosti**.</span><span class="sxs-lookup"><span data-stu-id="11fb8-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="11fb8-151">Izaberite entitet aktivnosti koji želite da uklonite i izaberite **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="11fb8-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="11fb8-152">Ili možete da zadržite pokazivač preko reda entiteta i izaberite ikonu **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="11fb8-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="11fb8-153">Pored toga, možete izabrati više entiteta aktivnosti koje ćete istovremeno izbrisati.</span><span class="sxs-lookup"><span data-stu-id="11fb8-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11fb8-154">![Uređivanje ili brisanje relacija između entiteta](media/activities-entities-edit-delete.png "Uređivanje ili brisanje relacija između entiteta")</span><span class="sxs-lookup"><span data-stu-id="11fb8-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="11fb8-155">Izaberite ikonu **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="11fb8-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="11fb8-156">Potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="11fb8-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]