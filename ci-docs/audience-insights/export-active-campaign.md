---
title: Izvoz Customer Insights podataka u ActiveCampaign
description: Saznajte kako da konfigurišete vezu i izvezete je u uslugu ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314668"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="883d1-103">Izvoz segmenata u ActiveCampaign (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="883d1-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="883d1-104">Izvezite segmente objedinjenih profila kupaca u ActiveCampaign i koristite ih za marketinške aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="883d1-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="883d1-105">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="883d1-105">Prerequisites</span></span>

-   <span data-ttu-id="883d1-106">Imate [ActiveCampaign nalog](https://www.activecampaign.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="883d1-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="883d1-107">[Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="883d1-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="883d1-108">Objedinjeni korisnički profili u izvezenim segmentima sadrže polje sa adresom e-pošte.</span><span class="sxs-lookup"><span data-stu-id="883d1-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="883d1-109">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="883d1-109">Known limitations</span></span>

- <span data-ttu-id="883d1-110">Možete izvoziti do 1 milion profila po izvozu u ActiveCampaign, a to može potrajati i do 90 minuta.</span><span class="sxs-lookup"><span data-stu-id="883d1-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="883d1-111">Izvoz u ActiveCampaign je ograničen na segmente.</span><span class="sxs-lookup"><span data-stu-id="883d1-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="883d1-112">Broj profila koje možete da izvezete u ActiveCampaign zavisi od vašeg ugovora sa uslugom ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="883d1-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="883d1-113">Podesite vezu sa uslugom ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="883d1-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="883d1-114">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="883d1-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="883d1-115">Izaberite **Dodaj vezu** i izaberite **ActiveCampaign** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="883d1-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="883d1-116">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="883d1-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="883d1-117">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="883d1-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="883d1-118">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="883d1-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="883d1-119">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="883d1-119">Choose who can use this connection.</span></span> <span data-ttu-id="883d1-120">Podrazumevano su to samo administratori.</span><span class="sxs-lookup"><span data-stu-id="883d1-120">By default, it's only administrators.</span></span> <span data-ttu-id="883d1-121">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="883d1-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="883d1-122">Unesite svoj [ActiveCampaign API ključ i ime hosta REST krajnje tačke](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="883d1-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="883d1-123">Ime hosta REST krajnje tačke je samo ime hosta, bez https://.</span><span class="sxs-lookup"><span data-stu-id="883d1-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="883d1-124">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="883d1-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="883d1-125">Izaberite **Poveži se** za inicijalizaciju veze sa uslugom ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="883d1-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="883d1-126">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="883d1-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="883d1-127">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="883d1-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="883d1-128">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="883d1-128">Configure an export</span></span>

<span data-ttu-id="883d1-129">Izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="883d1-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="883d1-130">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="883d1-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="883d1-131">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="883d1-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="883d1-132">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="883d1-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="883d1-133">U polju **Veza za izvoz**, izaberite vezu iz odeljka ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="883d1-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="883d1-134">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="883d1-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="883d1-135">Unesite [**ID ActiveCampaign liste**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="883d1-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="883d1-136">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="883d1-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="883d1-137">U ActiveCampaign morate izvoziti segmente.</span><span class="sxs-lookup"><span data-stu-id="883d1-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="883d1-138">Opcionalno, možete da izvezete polja Ime, Prezime i Telefon da biste kreirali personalizovanije adrese e-pošte.</span><span class="sxs-lookup"><span data-stu-id="883d1-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="883d1-139">Izaberite Dodaj atribut za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="883d1-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="883d1-140">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="883d1-140">Select **Save**.</span></span>

<span data-ttu-id="883d1-141">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="883d1-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="883d1-142">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="883d1-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="883d1-143">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="883d1-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="883d1-144">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="883d1-144">Data privacy and compliance</span></span>

<span data-ttu-id="883d1-145">Kada omogućite Dynamics 365 Customer Insights za prenos podataka u ActiveCampaign, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="883d1-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="883d1-146">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da ActiveCampaign ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="883d1-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="883d1-147">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="883d1-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="883d1-148">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="883d1-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
