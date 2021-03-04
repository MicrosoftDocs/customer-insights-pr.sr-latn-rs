---
title: Izvezite Customer Insights podatke u Mailchimp
description: Saznajte kako da konfigurišete vezu sa uslugom Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267190"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="4f8ab-103">Konektor za Mailchimp (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="4f8ab-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="4f8ab-104">Izvezite segmente objedinjenih profila klijenata u Mailchimp da biste kreirali biltene i kampanje e-pošte.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4f8ab-105">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="4f8ab-105">Prerequisites</span></span>

-   <span data-ttu-id="4f8ab-106">Imate [Mailchimp nalog](https://mailchimp.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4f8ab-107">Postoji postojeća publika u Mailchimp-u i odgovarajući ID-ovi.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="4f8ab-108">Za više informacija pogledajte [Mailchimp korisnici](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="4f8ab-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="4f8ab-109">Imate [konfigurisane segmente](segments.md)</span><span class="sxs-lookup"><span data-stu-id="4f8ab-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="4f8ab-110">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="4f8ab-111">Povežite sa uslugom Mailchimp</span><span class="sxs-lookup"><span data-stu-id="4f8ab-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="4f8ab-112">Idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="4f8ab-113">Pod **Mailchimp**, izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="4f8ab-114">Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="4f8ab-115">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4f8ab-116">Unesite **[Mailchimp ID korisnika](https://mailchimp.com/help/find-audience-id/)** i izaberite **Povežite se** da biste započeli povezivanje sa Mailchimp-om.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="4f8ab-117">Izaberite **Potvrdite identitet u Mailchimp-u** i navedite akreditive za Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="4f8ab-118">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Izvezite snimak ekrana za vezu sa uslugom Mailchimp":::

1. <span data-ttu-id="4f8ab-120">Izaberite **Sledeće** da biste konfigurisali izvoz.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="4f8ab-121">Konfigurisanje konektora</span><span class="sxs-lookup"><span data-stu-id="4f8ab-121">Configure the connector</span></span>

1. <span data-ttu-id="4f8ab-122">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="4f8ab-123">Po želji možete da izvezete **Ime** i **Prezime** kao dodatna polja za stvaranje personalizovanih e-poruka.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="4f8ab-124">Izaberite **Dodaj atribut** za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="4f8ab-125">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-125">Select the segments you want to export.</span></span> <span data-ttu-id="4f8ab-126">U usluzi Mailchimp možete ukupno izvesti do 1 milion korisničkih profila.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Izaberite polja i segmente za izvoz u Mailchimp":::

1. <span data-ttu-id="4f8ab-128">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="4f8ab-129">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="4f8ab-129">Export the data</span></span>

<span data-ttu-id="4f8ab-130">Možete da [izvezete podatke na zahtev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="4f8ab-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="4f8ab-131">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4f8ab-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4f8ab-132">U Mailchimp-u sada možete pronaći segmente u odeljku [Mailchimp korisnici](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="4f8ab-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4f8ab-133">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="4f8ab-133">Known limitations</span></span>

- <span data-ttu-id="4f8ab-134">Do 1 milion profila po izvozu u usluzi Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="4f8ab-135">Izvoz u Mailchimp je ograničen na segmente.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="4f8ab-136">Izvoz segmenata sa ukupno 1 milion profila može trajati do tri sata zbog ograničenja na strani dobavljača.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="4f8ab-137">Broj profila koje možete da izvezete u Mailchimp zavisi od i ograničen je vašim ugovorom sa kompanijom Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4f8ab-138">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="4f8ab-138">Data privacy and compliance</span></span>

<span data-ttu-id="4f8ab-139">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Mailchimp, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4f8ab-140">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Mailchimp ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4f8ab-141">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4f8ab-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4f8ab-142">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="4f8ab-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]