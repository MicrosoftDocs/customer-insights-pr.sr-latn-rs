---
title: Izvezite Customer Insights podatke u DotDigital
description: Saznajte kako da konfigurišete vezu sa uslugom DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269117"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="3bb7c-103">Konektor za DotDigital (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="3bb7c-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="3bb7c-104">Izvezite segmente objedinjenih profila kupaca u DotDigital adresare i koristite ih za kampanje, marketing putem e-pošte i za izgradnju segmenata kupaca pomoću usluge DotDigital.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="3bb7c-105">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="3bb7c-105">Prerequisites</span></span>

-   <span data-ttu-id="3bb7c-106">Imate [DotDigital nalog](https://dotdigital.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3bb7c-107">Postoji postojeća publika u adresarima u usluzi DotDigital i odgovarajući ID-ovi.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="3bb7c-108">ID se može naći u URL-u kada odaberete i otvorite adresar.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="3bb7c-109">Za više informacija pogledajte [adresare za DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="3bb7c-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="3bb7c-110">[Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="3bb7c-111">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="3bb7c-112">Povezivanje sa uslugom DotDigital</span><span class="sxs-lookup"><span data-stu-id="3bb7c-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="3bb7c-113">Idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3bb7c-114">U odeljku **DotDigital**, izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="3bb7c-115">Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Okno za konfiguraciju izvoza usluge DotDigital.":::

1. <span data-ttu-id="3bb7c-117">Unesite svoje **korisničko ime i lozinku za DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="3bb7c-118">Unesite **[ID DotDigital adresara](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="3bb7c-119">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3bb7c-120">Izaberite **Poveži se** za inicijalizaciju veze sa uslugom DotDigital.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="3bb7c-121">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3bb7c-122">Izaberite **Sledeće** da biste konfigurisali izvoz.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="3bb7c-123">Konfigurisanje konektora</span><span class="sxs-lookup"><span data-stu-id="3bb7c-123">Configure the connector</span></span>

1. <span data-ttu-id="3bb7c-124">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="3bb7c-125">Ponovite iste korake za druga opcionalna polja kao što su **Ime**, **Prezime**, **Puno ime**, **Pol** i **Poštanski broj**.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="3bb7c-126">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-126">Select the segments you want to export.</span></span> <span data-ttu-id="3bb7c-127">U usluzi DotDigital možete ukupno izvesti do 1 milion korisničkih profila.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="3bb7c-128">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3bb7c-129">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="3bb7c-129">Export the data</span></span>

<span data-ttu-id="3bb7c-130">Možete da [izvezete podatke na zahtev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3bb7c-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3bb7c-131">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3bb7c-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3bb7c-132">U usluzi DotDigital sada možete da pronađete svoje segmente u [DotDigital adresarima](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="3bb7c-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3bb7c-133">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="3bb7c-133">Known limitations</span></span>

- <span data-ttu-id="3bb7c-134">Do 1 milion profila po izvozu u usluzi DotDigital.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="3bb7c-135">Izvoz u DotDigital je ograničen na segmente.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="3bb7c-136">Izvoz segmenata sa ukupno 1 milion profila može trajati do 3 sata zbog ograničenja na strani dobavljača.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="3bb7c-137">Broj profila koje možete da izvezete u DotDigital zavisi od i ograničen je vašim ugovorom sa kompanijom DotDigital.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3bb7c-138">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="3bb7c-138">Data privacy and compliance</span></span>

<span data-ttu-id="3bb7c-139">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u DotDigital, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3bb7c-140">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da DotDigital ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="3bb7c-141">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3bb7c-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3bb7c-142">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="3bb7c-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]