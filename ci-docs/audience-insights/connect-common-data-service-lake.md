---
title: Povežite se sa entitetima u Common Data Service nadgledanom jezeru
description: Uvoz podataka iz Common Data Service upravljanog jezera podataka.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596976"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="41ff6-103">Povežite se sa podacima u Common Data Service upravljanom jezeru podataka</span><span class="sxs-lookup"><span data-stu-id="41ff6-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="41ff6-104">Ovaj članak pruža informacije o tome kako postojeći Dynamics 365 korisnici mogu brzo da se povežu sa svojim analitičkim entitetima u Common Data Service upravljanom jezeru.</span><span class="sxs-lookup"><span data-stu-id="41ff6-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="41ff6-105">Morate biti administrator Common Data Service organizacije kako biste nastavili i videli spisak entiteta dostupnih u upravljanom jezeru.</span><span class="sxs-lookup"><span data-stu-id="41ff6-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="41ff6-106">Važna razmatranja</span><span class="sxs-lookup"><span data-stu-id="41ff6-106">Important considerations</span></span>

<span data-ttu-id="41ff6-107">Podaci uskladišteni u mrežnim uslugama, kao što je Azure Data Lake Storage, mogu se skladištiti na lokaciji različitoj od one na kojoj se podaci obrađuju ili skladište u usluzi Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="41ff6-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="41ff6-108"> Uvozom ili povezivanjem podataka uskladištenih u mrežnoj usluzi, slažete se da se podaci mogu preneti i skladištiti u usluzi Dynamics 365 Customer Insights. [Saznajte više u Microsoft centru za pouzdanost.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="41ff6-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="41ff6-109">Povežite se sa Common Data Service upravljanim jezerom</span><span class="sxs-lookup"><span data-stu-id="41ff6-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="41ff6-110">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="41ff6-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="41ff6-111">Izaberite **Dodaj izvor podataka**.</span><span class="sxs-lookup"><span data-stu-id="41ff6-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="41ff6-112">Izaberite **Povezivanje sa uslugom Common Data Service** i izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="41ff6-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="41ff6-113">Unesite **Naziv** izvora podataka i izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="41ff6-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="41ff6-114">Smernice za nazive:</span><span class="sxs-lookup"><span data-stu-id="41ff6-114">Name guidelines:</span></span> 
   - <span data-ttu-id="41ff6-115">Započnite slovom.</span><span class="sxs-lookup"><span data-stu-id="41ff6-115">Start with a letter.</span></span>
   - <span data-ttu-id="41ff6-116">Koristite samo slova i brojeve.</span><span class="sxs-lookup"><span data-stu-id="41ff6-116">Use letters and numbers only.</span></span> <span data-ttu-id="41ff6-117">Posebni znakovi i razmaci nisu dozvoljeni.</span><span class="sxs-lookup"><span data-stu-id="41ff6-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="41ff6-118">Koristite između 3 i 64 znaka.</span><span class="sxs-lookup"><span data-stu-id="41ff6-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="41ff6-119">Navedite **Adresu servera** za vašu Common Data Service organizaciju i izaberite **Prijavite se**.</span><span class="sxs-lookup"><span data-stu-id="41ff6-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41ff6-120">![Dijalog za unos Common Data Service adrese servera](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="41ff6-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="41ff6-121">Izaberite entitete koje želite da unesete sa dostupne liste.</span><span class="sxs-lookup"><span data-stu-id="41ff6-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="41ff6-122">Ako su neki entiteti već izabrani, mogu ih koristiti druge Dynamics 365 aplikacije (kao što su Dynamics 365 Sales Insights ili Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="41ff6-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="41ff6-123">Ne možete promeniti izbor.</span><span class="sxs-lookup"><span data-stu-id="41ff6-123">You can't change the selection.</span></span> <span data-ttu-id="41ff6-124">Ovi entiteti će biti dostupni nakon kreiranja izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="41ff6-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41ff6-125">![Dijalog koji prikazuje listu entiteta u Common Data Service organizaciji](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="41ff6-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="41ff6-126">Sačuvajte svoj izbor da biste započeli sinhronizaciju izabranih entiteta sa Common Data Service upravljanim jezerom.</span><span class="sxs-lookup"><span data-stu-id="41ff6-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="41ff6-127">Novododatu vezu ćete pronaći na stranici **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="41ff6-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="41ff6-128">Biće postavljena u red za osvežavanje i prikazaće brojeve entiteta kao 0 dok se svi entiteti ne sinhronizuju.</span><span class="sxs-lookup"><span data-stu-id="41ff6-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="41ff6-129">Samo jedan izvor podataka okruženja može istovremeno da koristi isto Common Data Service nadgledano jezero.</span><span class="sxs-lookup"><span data-stu-id="41ff6-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="41ff6-130">Uredite izvor podataka za Common Data Service upravljano jezero</span><span class="sxs-lookup"><span data-stu-id="41ff6-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="41ff6-131">Izbor entiteta uređujete tek nakon što kreirate izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="41ff6-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="41ff6-132">Na primer, ako su dodati dodatni entiteti u uslugu Common Data Service, a želite i da ih uvozite.</span><span class="sxs-lookup"><span data-stu-id="41ff6-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="41ff6-133">Da biste se povezali sa drugom uslugom Common Data Service, [kreirajte novi izvor podataka](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="41ff6-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="41ff6-134">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="41ff6-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="41ff6-135">Pored izvora podataka koji želite da ažurirate, izaberite tri tačke.</span><span class="sxs-lookup"><span data-stu-id="41ff6-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="41ff6-136">Izaberite opciju **Uredi** sa liste.</span><span class="sxs-lookup"><span data-stu-id="41ff6-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="41ff6-137">Izaberite dodatne entitete s dostupne liste entiteta i izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="41ff6-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]