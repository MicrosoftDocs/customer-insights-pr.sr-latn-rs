---
title: Izvoz Customer Insights podataka u AdRoll
description: Saznajte kako da konfigurišete vezu sa uslugom AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697091"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="984fa-103">Konektor za AdRoll (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="984fa-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="984fa-104">Izvezite segmente objedinjenih profila klijenata u AdRoll i koristite ih za oglašavanje.</span><span class="sxs-lookup"><span data-stu-id="984fa-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="984fa-105">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="984fa-105">Prerequisites</span></span>

-   <span data-ttu-id="984fa-106">Imate [AdRoll nalog](https://www.adroll.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="984fa-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="984fa-107">[Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="984fa-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="984fa-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="984fa-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="984fa-109">Povežite se sa uslugom AdRoll</span><span class="sxs-lookup"><span data-stu-id="984fa-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="984fa-110">Idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="984fa-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="984fa-111">U odeljku **AdRoll** izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="984fa-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="984fa-112">Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="984fa-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Okno za konfiguraciju za vezu sa uslugom AdRoll.":::

1. <span data-ttu-id="984fa-114">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="984fa-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="984fa-115">Izaberite **Poveži se** za inicijalizaciju veze sa uslugom AdRoll.</span><span class="sxs-lookup"><span data-stu-id="984fa-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="984fa-116">Izaberite **Potvrdite identitet u usluzi AdRoll** i navedite svoje akreditive administratora za AdRoll.</span><span class="sxs-lookup"><span data-stu-id="984fa-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="984fa-117">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="984fa-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="984fa-118">Unesite svoj **ID AdRoll oglašavača** [koji može da se oglašava u usluzi AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="984fa-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="984fa-119">Izaberite **Sledeće** da biste konfigurisali izvoz.</span><span class="sxs-lookup"><span data-stu-id="984fa-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="984fa-120">Konfigurisanje konektora</span><span class="sxs-lookup"><span data-stu-id="984fa-120">Configure the connector</span></span>

1. <span data-ttu-id="984fa-121">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="984fa-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="984fa-122">To je potrebno za izvoz segmenata u AdRoll.</span><span class="sxs-lookup"><span data-stu-id="984fa-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="984fa-123">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="984fa-123">Select the segments you want to export.</span></span> <span data-ttu-id="984fa-124">Izaberite segment sa najmanje 100 članova.</span><span class="sxs-lookup"><span data-stu-id="984fa-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="984fa-125">Ne možete izvoziti manje segmente.</span><span class="sxs-lookup"><span data-stu-id="984fa-125">You can't export smaller segments.</span></span> <span data-ttu-id="984fa-126">Pored toga, maksimalna veličina segmenta za izvoz je 250.000 članova po izvozu.</span><span class="sxs-lookup"><span data-stu-id="984fa-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="984fa-127">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="984fa-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="984fa-128">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="984fa-128">Export the data</span></span>

<span data-ttu-id="984fa-129">Možete da [izvezete podatke na zahtev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="984fa-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="984fa-130">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="984fa-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="984fa-131">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="984fa-131">Known limitations</span></span>

- <span data-ttu-id="984fa-132">U uslugu AdRoll možete da izvezete ukupno do 250.000 profila po izvozu.</span><span class="sxs-lookup"><span data-stu-id="984fa-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="984fa-133">U AdRoll ne možete da izvezete segmente sa manje od 100 profila.</span><span class="sxs-lookup"><span data-stu-id="984fa-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="984fa-134">Izvoz u AdRoll je ograničen na segmente.</span><span class="sxs-lookup"><span data-stu-id="984fa-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="984fa-135">Izvoz do 250.000 profila u AdRoll može da potraje do 10 minuta.</span><span class="sxs-lookup"><span data-stu-id="984fa-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="984fa-136">Broj profila koje možete da izvezete u AdRoll zavisi od i ograničen je vašim ugovorom sa kompanijom AdRoll.</span><span class="sxs-lookup"><span data-stu-id="984fa-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="984fa-137">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="984fa-137">Data privacy and compliance</span></span>

<span data-ttu-id="984fa-138">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u AdRoll, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="984fa-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="984fa-139">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da AdRoll ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="984fa-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="984fa-140">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="984fa-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="984fa-141">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="984fa-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
