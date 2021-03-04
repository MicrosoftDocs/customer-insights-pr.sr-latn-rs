---
title: Izvezite Customer Insights podatke u Autopilot
description: Saznajte kako da konfigurišete vezu sa uslugom Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269255"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="c0898-103">Konektor za Autopilot (pregled)</span><span class="sxs-lookup"><span data-stu-id="c0898-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="c0898-104">Izvezite segmente objedinjenih profila klijenata u Autopilot i koristite ih za marketing putem e-pošte u usluzi Autopilot.</span><span class="sxs-lookup"><span data-stu-id="c0898-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c0898-105">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="c0898-105">Prerequisites</span></span>

-   <span data-ttu-id="c0898-106">Imate [Autopilot nalog](https://www.autopilothq.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="c0898-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c0898-107">[Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="c0898-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c0898-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="c0898-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="c0898-109">Povezivanje sa uslugom Autopilot</span><span class="sxs-lookup"><span data-stu-id="c0898-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="c0898-110">Idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="c0898-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c0898-111">U delu **Autopilot** izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="c0898-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="c0898-112">Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="c0898-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Okno za konfiguraciju za vezu sa uslugom Autopilot.":::

1. <span data-ttu-id="c0898-114">Unesite svoj **API ključ za Autopilot** [API ključ za Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="c0898-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="c0898-115">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="c0898-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c0898-116">Izaberite **Poveži se** za inicijalizaciju veze sa uslugom Autopilot.</span><span class="sxs-lookup"><span data-stu-id="c0898-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="c0898-117">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c0898-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c0898-118">Izaberite **Sledeće** da biste konfigurisali izvoz.</span><span class="sxs-lookup"><span data-stu-id="c0898-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c0898-119">Konfigurisanje konektora</span><span class="sxs-lookup"><span data-stu-id="c0898-119">Configure the connector</span></span>

1. <span data-ttu-id="c0898-120">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="c0898-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c0898-121">Ponovite iste korake za druga opcionalna polja kao što su **Ime**, **Prezime**.</span><span class="sxs-lookup"><span data-stu-id="c0898-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="c0898-122">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="c0898-122">Select the segments you want to export.</span></span> <span data-ttu-id="c0898-123">Izričito **preporučujemo da ne izvozite ukupno više od 100.000 profila klijenata** u Autopilot.</span><span class="sxs-lookup"><span data-stu-id="c0898-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="c0898-124">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="c0898-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c0898-125">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="c0898-125">Export the data</span></span>

<span data-ttu-id="c0898-126">Možete da [izvezete podatke na zahtev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c0898-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c0898-127">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c0898-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c0898-128">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="c0898-128">Known limitations</span></span>

- <span data-ttu-id="c0898-129">U uslugu Autopilot možete da izvezete ukupno do 100.000 profila.</span><span class="sxs-lookup"><span data-stu-id="c0898-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="c0898-130">Izvoz u Autopilot je ograničen na segmente.</span><span class="sxs-lookup"><span data-stu-id="c0898-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="c0898-131">Izvoz do 100.000 profila u Autopilot može da potraje do nekoliko sati.</span><span class="sxs-lookup"><span data-stu-id="c0898-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="c0898-132">Broj profila koje možete da izvezete u Autopilot zavisi od vašeg ugovora sa kompanijom Autopilot i ograničen je njime.</span><span class="sxs-lookup"><span data-stu-id="c0898-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c0898-133">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="c0898-133">Data privacy and compliance</span></span>

<span data-ttu-id="c0898-134">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Autopilot, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="c0898-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c0898-135">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Autopilot ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="c0898-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="c0898-136">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c0898-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c0898-137">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="c0898-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]