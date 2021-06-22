---
title: Izvoz Customer Insights podataka u Campaign Monitor
description: Saznajte kako da konfigurišete vezu i izvezete sadržaj u Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124198"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="79052-103">Izvoz segmenata u Campaign Monitor (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="79052-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="79052-104">Izvezite segmente objedinjenih profila klijenata u Campaign Monitor i koristite ih za marketinške aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="79052-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="79052-105">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="79052-105">Prerequisites</span></span>

-   <span data-ttu-id="79052-106">Imate [Campaign Monitor nalog](https://www.campaignmonitor.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="79052-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="79052-107">[Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="79052-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="79052-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="79052-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="79052-109">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="79052-109">Known limitations</span></span>

- <span data-ttu-id="79052-110">Možete izvesti do 1 milion profila po izvozu u Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="79052-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="79052-111">Izvoz u Campaign Monitor ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="79052-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="79052-112">Izvoz do 1 milion profila u Campaign Monitor može potrajati do 20 minuta.</span><span class="sxs-lookup"><span data-stu-id="79052-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="79052-113">Broj profila koje možete da izvezete u Campaign Monitor zavisi i ograničen je vašim ugovorom sa uslugom Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="79052-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="79052-114">Podešavanje veze sa uslugom Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="79052-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="79052-115">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="79052-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="79052-116">Izaberite **Dodaj vezu** i birajte **Campaign Monitor** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="79052-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="79052-117">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="79052-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="79052-118">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="79052-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="79052-119">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="79052-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="79052-120">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="79052-120">Choose who can use this connection.</span></span> <span data-ttu-id="79052-121">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="79052-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="79052-122">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="79052-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="79052-123">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="79052-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="79052-124">Izaberite **Povežite se** da bi se inicijalizovala veza sa uslugom Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="79052-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="79052-125">Izaberite **Potvrdite identitet pomoću usluge Campaign Monitor** i obezbedite svoje administratorske akreditive za Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="79052-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="79052-126">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="79052-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="79052-127">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="79052-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="79052-128">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="79052-128">Configure an export</span></span>

<span data-ttu-id="79052-129">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="79052-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="79052-130">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="79052-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="79052-131">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="79052-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="79052-132">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="79052-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="79052-133">U polju **Veza za izvoz**, odaberite vezu iz odeljka Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="79052-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="79052-134">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="79052-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="79052-135">Unesite [**ID Campaign Monitor liste**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="79052-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="79052-136">Prvo [generišite API ključ](https://www.campaignmonitor.com/api/getting-started/) u odeljku **Podešavanja naloga** u usluzi Campaign Monitor da biste videli ID API liste.</span><span class="sxs-lookup"><span data-stu-id="79052-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="79052-137">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="79052-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="79052-138">To je potrebno da izvezete segmente u Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="79052-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="79052-139">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="79052-139">Select **Save**.</span></span>

<span data-ttu-id="79052-140">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="79052-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="79052-141">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="79052-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="79052-142">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="79052-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="79052-143">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="79052-143">Data privacy and compliance</span></span>

<span data-ttu-id="79052-144">Kada omogućite Dynamics 365 Customer Insights za prenos podataka u Campaign Monitor, dozvoljavate prenos podataka izvan granica usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="79052-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="79052-145">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Campaign Monitor ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="79052-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="79052-146">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="79052-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="79052-147">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="79052-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
