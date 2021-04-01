---
title: Izvezite Customer Insights podatke u SendGrid
description: Saznajte kako da konfigurišete vezu sa uslugom SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597298"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="eedb5-103">Konektor za SendGrid (pregled)</span><span class="sxs-lookup"><span data-stu-id="eedb5-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="eedb5-104">Izvezite segmente objedinjenih profila klijenata u SendGrid liste kontakata i koristite ih za kampanje i marketing u usluzi SendGrid.</span><span class="sxs-lookup"><span data-stu-id="eedb5-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="eedb5-105">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="eedb5-105">Prerequisites</span></span>

-   <span data-ttu-id="eedb5-106">Imate [SendGrid nalog](https://sendgrid.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="eedb5-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="eedb5-107">Postoje postojeće liste kontakata u usluzi SendGrid i odgovarajući ID-ovi.</span><span class="sxs-lookup"><span data-stu-id="eedb5-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="eedb5-108">Za više informacija pogledajte [SendGrid – Upravljanje kontaktima](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="eedb5-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="eedb5-109">[Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="eedb5-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="eedb5-110">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="eedb5-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="eedb5-111">Povežite se sa uslugom SendGrid</span><span class="sxs-lookup"><span data-stu-id="eedb5-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="eedb5-112">Idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="eedb5-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="eedb5-113">U delu **SendGrid** izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="eedb5-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="eedb5-114">Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="eedb5-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Okno za konfiguraciju izvoza u usluzi SendGrid.":::

1. <span data-ttu-id="eedb5-116">Unesite svoj **SendGrid API ključ** [SendGrid API ključ](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="eedb5-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="eedb5-117">Unesite **[ID SendGrid liste](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="eedb5-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="eedb5-118">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="eedb5-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="eedb5-119">Izaberite **Poveži se** za inicijalizaciju veze sa uslugom SendGrid.</span><span class="sxs-lookup"><span data-stu-id="eedb5-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="eedb5-120">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="eedb5-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="eedb5-121">Izaberite **Sledeće** da biste konfigurisali izvoz.</span><span class="sxs-lookup"><span data-stu-id="eedb5-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="eedb5-122">Konfigurisanje konektora</span><span class="sxs-lookup"><span data-stu-id="eedb5-122">Configure the connector</span></span>

1. <span data-ttu-id="eedb5-123">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="eedb5-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="eedb5-124">Ponovite iste korake za druga opcionalna polja kao što su **Ime**, **Prezime**, **Zemlja/Region**, **Država**, **Grad** i **Poštanski broj**.</span><span class="sxs-lookup"><span data-stu-id="eedb5-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="eedb5-125">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="eedb5-125">Select the segments you want to export.</span></span> <span data-ttu-id="eedb5-126">Izričito **preporučujemo da ne izvozite ukupno više od 100.000 profila klijenata** u SendGrid.</span><span class="sxs-lookup"><span data-stu-id="eedb5-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="eedb5-127">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="eedb5-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="eedb5-128">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="eedb5-128">Export the data</span></span>

<span data-ttu-id="eedb5-129">Možete da [izvezete podatke na zahtev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="eedb5-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="eedb5-130">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eedb5-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="eedb5-131">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="eedb5-131">Known limitations</span></span>

- <span data-ttu-id="eedb5-132">Ukupno do 100.000 profila u SendGrid.</span><span class="sxs-lookup"><span data-stu-id="eedb5-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="eedb5-133">Izvoz u SendGrid je ograničen na segmente.</span><span class="sxs-lookup"><span data-stu-id="eedb5-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="eedb5-134">Izvoz do 100.000 profila u SendGrid može da potraje do nekoliko sati.</span><span class="sxs-lookup"><span data-stu-id="eedb5-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="eedb5-135">Broj profila koje možete da izvezete u SendGrid zavisi od vašeg ugovora sa kompanijom SendGrid i ograničen je njime.</span><span class="sxs-lookup"><span data-stu-id="eedb5-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="eedb5-136">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="eedb5-136">Data privacy and compliance</span></span>

<span data-ttu-id="eedb5-137">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u SendGrid, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="eedb5-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="eedb5-138">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da SendGrid ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="eedb5-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="eedb5-139">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="eedb5-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="eedb5-140">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="eedb5-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]