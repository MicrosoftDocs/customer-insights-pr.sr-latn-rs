---
title: Izvoz Customer Insights podataka u RollWorks
description: Saznajte kako da konfigurišete vezu i izvezete u RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124106"
---
# <a name="export-segments-to-rollworks-preview"></a><span data-ttu-id="16749-103">Izvoz segmenata u RollWorks (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="16749-103">Export segments to RollWorks (preview)</span></span>

<span data-ttu-id="16749-104">Izvezite segmente objedinjenih profila klijenata u RollWorks i koristite ih za oglašavanje.</span><span class="sxs-lookup"><span data-stu-id="16749-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="16749-105">Preduslovi za vezu</span><span class="sxs-lookup"><span data-stu-id="16749-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="16749-106">Imate [RollWorks nalog](https://www.rollworks.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="16749-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="16749-107">[Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="16749-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="16749-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="16749-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="16749-109">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="16749-109">Known limitations</span></span>

- <span data-ttu-id="16749-110">Možete izvesti do 250.000 profila po izvozu u RollWorks.</span><span class="sxs-lookup"><span data-stu-id="16749-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="16749-111">Ne možete da izvezete segmente sa manje od 100 profila u RollWorks.</span><span class="sxs-lookup"><span data-stu-id="16749-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="16749-112">Izvoz u RollWorks ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="16749-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="16749-113">Izvoz do 250.000 profila u RollWorks može potrajati do 10 minuta.</span><span class="sxs-lookup"><span data-stu-id="16749-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="16749-114">Broj profila koje možete da izvezete u RollWorks zavisi i ograničen je vašim ugovorom sa uslugom RollWorks.</span><span class="sxs-lookup"><span data-stu-id="16749-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="16749-115">Podešavanje veze sa uslugom RollWorks</span><span class="sxs-lookup"><span data-stu-id="16749-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="16749-116">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="16749-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="16749-117">Izaberite **Dodaj vezu** i birajte **RollWorks** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="16749-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="16749-118">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="16749-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="16749-119">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="16749-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="16749-120">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="16749-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="16749-121">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="16749-121">Choose who can use this connection.</span></span> <span data-ttu-id="16749-122">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="16749-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="16749-123">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="16749-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="16749-124">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="16749-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="16749-125">Izaberite **Povežite se** da bi se inicijalizovala veza sa uslugom RollWorks.</span><span class="sxs-lookup"><span data-stu-id="16749-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="16749-126">Izaberite **Potvrdite identitet pomoću usluge RollWorks** i obezbedite svoje administratorske akreditive za RollWorks.</span><span class="sxs-lookup"><span data-stu-id="16749-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="16749-127">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="16749-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="16749-128">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="16749-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="16749-129">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="16749-129">Configure an export</span></span>

<span data-ttu-id="16749-130">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="16749-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="16749-131">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="16749-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="16749-132">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="16749-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="16749-133">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="16749-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="16749-134">U polju **Veza za izvoz**, odaberite vezu iz odeljka RollWorks.</span><span class="sxs-lookup"><span data-stu-id="16749-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="16749-135">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="16749-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="16749-136">Unesite svoj **ID RollWorks oglašavača** [RollWorks oglas](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="16749-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="16749-137">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="16749-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="16749-138">To je potrebno da izvezete segmente u RollWorks.</span><span class="sxs-lookup"><span data-stu-id="16749-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="16749-139">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="16749-139">Select the segments you want to export.</span></span> <span data-ttu-id="16749-140">Izaberite segment sa najmanje 100 članova.</span><span class="sxs-lookup"><span data-stu-id="16749-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="16749-141">Ne možete izvoziti manje segmente.</span><span class="sxs-lookup"><span data-stu-id="16749-141">You can't export smaller segments.</span></span> <span data-ttu-id="16749-142">Pored toga, maksimalna veličina segmenta za izvoz je 250.000 članova po izvozu.</span><span class="sxs-lookup"><span data-stu-id="16749-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="16749-143">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="16749-143">Select **Save**.</span></span>

<span data-ttu-id="16749-144">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="16749-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="16749-145">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="16749-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="16749-146">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="16749-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="16749-147">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="16749-147">Data privacy and compliance</span></span>

<span data-ttu-id="16749-148">Kada omogućite Dynamics 365 Customer Insights za prenos podataka u RollWorks, dozvoljavate prenos podataka izvan granica usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="16749-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="16749-149">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da RollWorks ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="16749-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="16749-150">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="16749-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="16749-151">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="16749-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
