---
title: Odnosi između entiteta i putanja entiteta
description: Pravite i upravljajte odnosima između entiteta iz više izvora podataka.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406822"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="d33fd-103">Relacije između entiteta</span><span class="sxs-lookup"><span data-stu-id="d33fd-103">Relationships between entities</span></span>

<span data-ttu-id="d33fd-104">Relacije vam pomažu da povežete entitete i generišete grafikon vaših podataka kada entiteti dele zajednički identifikator (strani ključ) koji se može referencirati iz jednog entiteta u drugi.</span><span class="sxs-lookup"><span data-stu-id="d33fd-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="d33fd-105">Povezani entiteti vam omogućavaju da definišete segmente i mere na osnovu više izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="d33fd-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="d33fd-106">Postoje dva tipa relacija.</span><span class="sxs-lookup"><span data-stu-id="d33fd-106">There are two types of relationships.</span></span> <span data-ttu-id="d33fd-107">Sistemske relacije koje se ne mogu uređivati, koje se kreiraju automatski, i prilagođene relacije, koje kreiraju i konfigurišu korisnici.</span><span class="sxs-lookup"><span data-stu-id="d33fd-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="d33fd-108">Tokom procesa podudaranja i spajanja, sistemske relacije se kreiraju se iza scene na osnovu inteligentnog podudaranja.</span><span class="sxs-lookup"><span data-stu-id="d33fd-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="d33fd-109">Ove relacije pomažu da se povežu evidencije profila klijenata sa podacima drugih entiteta.</span><span class="sxs-lookup"><span data-stu-id="d33fd-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="d33fd-110">Sledeći dijagram ilustruje kreiranje tri sistemske relacije kada se entitet klijenta podudari sa dodatnim entitetima kako bi se proizveo konačni entitet Profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="d33fd-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d33fd-111">![Kreiranje relacije](media/relationships-entities-merge.png "Kreiranje relacije")</span><span class="sxs-lookup"><span data-stu-id="d33fd-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="d33fd-112">**Relacija *CustomerToContact*** je kreirana između entiteta Klijent i kontaktnog entiteta.</span><span class="sxs-lookup"><span data-stu-id="d33fd-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="d33fd-113">Entitet Klijent dobija ključno polje **Contact_contactId** da stupi u relaciju sa poljem ključa entiteta Kontakt **contactId**.</span><span class="sxs-lookup"><span data-stu-id="d33fd-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="d33fd-114">**Relacija _CustomerToContact_** je kreirana između entiteta Klijent i entiteta Poslovni kontakt.</span><span class="sxs-lookup"><span data-stu-id="d33fd-114">**_CustomerToAccount_ relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="d33fd-115">Entitet Klijent dobija polje ključa **Account_accountId** da stupi u relaciju sa poljem ključa entiteta Poslovni kontakt **accountId**.</span><span class="sxs-lookup"><span data-stu-id="d33fd-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="d33fd-116">**Relacija _CustomerToWebAccount_** je kreirana između entiteta Klijent i entiteta WebAccount.</span><span class="sxs-lookup"><span data-stu-id="d33fd-116">**_CustomerToWebAccount_ relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="d33fd-117">Entitet Klijent dobija polje ključa **WebAccount_webaccountId** da stupi u relaciju sa poljem ključa entiteta WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="d33fd-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="d33fd-118">Kreiranje odnosa</span><span class="sxs-lookup"><span data-stu-id="d33fd-118">Create a relationship</span></span>

<span data-ttu-id="d33fd-119">Definišite prilagođene relacije na stranici **Relacije**.</span><span class="sxs-lookup"><span data-stu-id="d33fd-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="d33fd-120">Svaka relacija se sastoji od izvornog entiteta (entiteta koji drži strani ključ) i ciljnog entiteta (entiteta na koji ukazuje na strani ključ izvornog entiteta).</span><span class="sxs-lookup"><span data-stu-id="d33fd-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="d33fd-121">U uvidima o korisnicima idite na **Podaci** > **Odnosi**.</span><span class="sxs-lookup"><span data-stu-id="d33fd-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="d33fd-122">Izaberite **Nova relacija**.</span><span class="sxs-lookup"><span data-stu-id="d33fd-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="d33fd-123">U oknu **Nova relacija**, navedite sledeće informacije:</span><span class="sxs-lookup"><span data-stu-id="d33fd-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d33fd-124">![Unesite detalje relacije](media/relationships-add.png "Unesite detalje relacije")</span><span class="sxs-lookup"><span data-stu-id="d33fd-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="d33fd-125">**Naziv relacije**: Ime koje odražava svrhu relacije (na primer, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="d33fd-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="d33fd-126">**Opis**: Opis relacije.</span><span class="sxs-lookup"><span data-stu-id="d33fd-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="d33fd-127">**Izvorni entitet**: Izaberite entitet koji se koristi kao izvor u relaciji (na primer, WebLog).</span><span class="sxs-lookup"><span data-stu-id="d33fd-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="d33fd-128">**Kardinalnost**: Izaberite kardinalnost izvornih zapisa entiteta.</span><span class="sxs-lookup"><span data-stu-id="d33fd-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="d33fd-129">Na primer, „mnogo“ znači da je više Weblog zapisa u relaciji sa jednim entitetom WebAccount.</span><span class="sxs-lookup"><span data-stu-id="d33fd-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="d33fd-130">**Izvorno polje ključa**: Ovo predstavlja polje stranog ključa u izvornom entitetu.</span><span class="sxs-lookup"><span data-stu-id="d33fd-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="d33fd-131">Na primer, WebLog ima polje stranog ključa **accountId**.</span><span class="sxs-lookup"><span data-stu-id="d33fd-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="d33fd-132">**Ciljni entitet**: Izaberite entitet koji se koristi kao cilj u relaciji (na primer, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="d33fd-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="d33fd-133">**Ciljna kardinalnost**: Izaberite kardinalnost ciljnih zapisa entiteta.</span><span class="sxs-lookup"><span data-stu-id="d33fd-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="d33fd-134">Na primer, „jedan“ znači da je više Weblog zapisa u relaciji sa jednim entitetom WebAccount.</span><span class="sxs-lookup"><span data-stu-id="d33fd-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="d33fd-135">**Ciljno polje ključa**: Ovo polje predstavlja polje ključa ciljnog entiteta.</span><span class="sxs-lookup"><span data-stu-id="d33fd-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="d33fd-136">Na primer, WebAccount ima polje ključa **accountId**.</span><span class="sxs-lookup"><span data-stu-id="d33fd-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="d33fd-137">Podržani su samo relacije više-prema-jedan i jedan-prema-jedan.</span><span class="sxs-lookup"><span data-stu-id="d33fd-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="d33fd-138">Relacije više-prema-više mogu da se kreiraju pomoću dve relacije više-prema-jedan i jednog entiteta veze (entiteta koji se koristi za povezivanje izvornog entiteta i ciljnog entiteta).</span><span class="sxs-lookup"><span data-stu-id="d33fd-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="d33fd-139">Brisanje relacije</span><span class="sxs-lookup"><span data-stu-id="d33fd-139">Delete a relationship</span></span>

1. <span data-ttu-id="d33fd-140">U uvidima o korisnicima idite na **Podaci** > **Odnosi**.</span><span class="sxs-lookup"><span data-stu-id="d33fd-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="d33fd-141">Izaberite polja za potvrdu za relacije koje želite da izbrišete.</span><span class="sxs-lookup"><span data-stu-id="d33fd-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="d33fd-142">Izaberite **Izbriši** na vrhu tabele **Relacije**.</span><span class="sxs-lookup"><span data-stu-id="d33fd-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="d33fd-143">Potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="d33fd-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="d33fd-144">Sledeći korak</span><span class="sxs-lookup"><span data-stu-id="d33fd-144">Next step</span></span>

<span data-ttu-id="d33fd-145">Sistemske i prilagođene relacije se koriste za kreiranje segmenata na osnovu više izvora podataka koji se više ne biraju.</span><span class="sxs-lookup"><span data-stu-id="d33fd-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="d33fd-146">Za više informacija, pogledajte članak [Segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d33fd-146">For more information, see [Segments](segments.md).</span></span>
