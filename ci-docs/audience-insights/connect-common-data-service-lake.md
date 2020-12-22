---
title: Povežite se sa entitetima u Common Data Service nadgledanom jezeru
description: Uvoz podataka iz Common Data Service upravljanog jezera podataka.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643415"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="da2f1-103">Povežite se sa podacima u Common Data Service upravljanom jezeru podataka</span><span class="sxs-lookup"><span data-stu-id="da2f1-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="da2f1-104">Ovaj članak pruža informacije o tome kako postojeći Dynamics 365 korisnici mogu brzo da se povežu sa svojim analitičkim entitetima u Common Data Service upravljanom jezeru.</span><span class="sxs-lookup"><span data-stu-id="da2f1-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="da2f1-105">Morate biti administrator Common Data Service organizacije kako biste nastavili i videli spisak entiteta dostupnih u upravljanom jezeru.</span><span class="sxs-lookup"><span data-stu-id="da2f1-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="da2f1-106">Važna razmatranja</span><span class="sxs-lookup"><span data-stu-id="da2f1-106">Important considerations</span></span>

<span data-ttu-id="da2f1-107">Podaci uskladišteni u mrežnim uslugama, kao što je Azure Data Lake Storage, mogu se skladištiti na lokaciji različitoj od one na kojoj se podaci obrađuju ili skladište u usluzi Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="da2f1-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="da2f1-108"> Uvozom ili povezivanjem podataka uskladištenih u mrežnoj usluzi, slažete se da se podaci mogu preneti i skladištiti u usluzi Dynamics 365 Customer Insights. [Saznajte više u Microsoft centru za pouzdanost.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="da2f1-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="da2f1-109">Povežite se sa Common Data Service upravljanim jezerom</span><span class="sxs-lookup"><span data-stu-id="da2f1-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="da2f1-110">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="da2f1-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="da2f1-111">Izaberite **Dodaj izvor podataka**.</span><span class="sxs-lookup"><span data-stu-id="da2f1-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="da2f1-112">Izaberite **Povezivanje sa uslugom Common Data Service** i izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="da2f1-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="da2f1-113">Unesite **Naziv** izvora podataka i izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="da2f1-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="da2f1-114">Navedite **Adresu servera** za vašu Common Data Service organizaciju i izaberite **Prijavite se**.</span><span class="sxs-lookup"><span data-stu-id="da2f1-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="da2f1-115">![Dijalog za unos Common Data Service adrese servera](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="da2f1-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="da2f1-116">Izaberite entitete koje želite da unesete sa dostupne liste.</span><span class="sxs-lookup"><span data-stu-id="da2f1-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="da2f1-117">Ako su neki entiteti već izabrani, mogu ih koristiti druge Dynamics 365 aplikacije (kao što su Dynamics 365 Sales Insights ili Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="da2f1-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="da2f1-118">Ne možete promeniti izbor.</span><span class="sxs-lookup"><span data-stu-id="da2f1-118">You can't change the selection.</span></span> <span data-ttu-id="da2f1-119">Ovi entiteti će biti dostupni nakon kreiranja izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="da2f1-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="da2f1-120">![Dijalog koji prikazuje listu entiteta u Common Data Service organizaciji](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="da2f1-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="da2f1-121">Sačuvajte svoj izbor da biste započeli sinhronizaciju izabranih entiteta sa Common Data Service upravljanim jezerom.</span><span class="sxs-lookup"><span data-stu-id="da2f1-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="da2f1-122">Novododatu vezu ćete pronaći na stranici **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="da2f1-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="da2f1-123">Biće postavljena u red za osvežavanje i prikazaće brojeve entiteta kao 0 dok se svi entiteti ne sinhronizuju.</span><span class="sxs-lookup"><span data-stu-id="da2f1-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="da2f1-124">Samo jedan izvor podataka okruženja može istovremeno da koristi isto Common Data Service nadgledano jezero.</span><span class="sxs-lookup"><span data-stu-id="da2f1-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="da2f1-125">Uredite izvor podataka za Common Data Service upravljano jezero</span><span class="sxs-lookup"><span data-stu-id="da2f1-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="da2f1-126">Izbor entiteta uređujete tek nakon što kreirate izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="da2f1-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="da2f1-127">Na primer, ako su dodati dodatni entiteti u uslugu Common Data Service, a želite i da ih uvozite.</span><span class="sxs-lookup"><span data-stu-id="da2f1-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="da2f1-128">Da biste se povezali sa drugom uslugom Common Data Service, [kreirajte novi izvor podataka](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="da2f1-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="da2f1-129">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.</span><span class="sxs-lookup"><span data-stu-id="da2f1-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="da2f1-130">Pored izvora podataka koji želite da ažurirate, izaberite tri tačke.</span><span class="sxs-lookup"><span data-stu-id="da2f1-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="da2f1-131">Izaberite opciju **Uredi** sa liste.</span><span class="sxs-lookup"><span data-stu-id="da2f1-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="da2f1-132">Izaberite dodatne entitete s dostupne liste entiteta i izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="da2f1-132">Select additional entities from the available list of entities and select **Save**.</span></span>
