---
title: Izvezite Customer Insights podatke u Marketo
description: Saznajte kako da konfigurišete vezu sa uslugom Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267098"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="4bf13-103">Konektor za Marketo (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="4bf13-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="4bf13-104">Izvezite segmente objedinjenih profila klijenata da biste generisali kampanje, obezbedili marketing e-poštom i koristili određene grupe klijenata sa uslugom Marketo.</span><span class="sxs-lookup"><span data-stu-id="4bf13-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4bf13-105">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="4bf13-105">Prerequisites</span></span>

-   <span data-ttu-id="4bf13-106">Imate [Marketo nalog](https://login.marketo.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="4bf13-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4bf13-107">Postoje postojeće liste u usluzi Marketo i odgovarajući ID-ovi.</span><span class="sxs-lookup"><span data-stu-id="4bf13-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="4bf13-108">Za više informacija pogledajte [Marketo liste](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="4bf13-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="4bf13-109">Imate [konfigurisane segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="4bf13-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="4bf13-110">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="4bf13-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="4bf13-111">Povezivanje sa uslugom Marketo</span><span class="sxs-lookup"><span data-stu-id="4bf13-111">Connect to Marketo</span></span>

1. <span data-ttu-id="4bf13-112">Idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="4bf13-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="4bf13-113">Pod **Marketo**, izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="4bf13-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="4bf13-114">Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="4bf13-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="4bf13-115">Unesite **[ Marketo ID klijenta, tajnu klijenta i ime hosta REST krajnje tačke](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="4bf13-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="4bf13-116">Unesite **[ID Marketo liste](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="4bf13-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="4bf13-117">Izaberite **Slažem se** da biste potvrdili **Privatnost podataka i usklađenost** i izaberite **Poveži se** radi uspostavljanja veze sa uslugom Marketo.</span><span class="sxs-lookup"><span data-stu-id="4bf13-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="4bf13-118">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4bf13-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Izvezite snimak ekrana za vezu sa uslugom Marketo":::

1. <span data-ttu-id="4bf13-120">Izaberite **Sledeće** da biste konfigurisali izvoz.</span><span class="sxs-lookup"><span data-stu-id="4bf13-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="4bf13-121">Konfigurisanje konektora</span><span class="sxs-lookup"><span data-stu-id="4bf13-121">Configure the connector</span></span>

1. <span data-ttu-id="4bf13-122">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="4bf13-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="4bf13-123">Po želji možete da izvezete **Ime**, **Prezime**, **Grad**, **Državu** i **Zemlju/region** kao dodatna polja za stvaranje personalizovanih e-poruka.</span><span class="sxs-lookup"><span data-stu-id="4bf13-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="4bf13-124">Izaberite **Dodaj atribut** za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="4bf13-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="4bf13-125">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="4bf13-125">Select the segments you want to export.</span></span> <span data-ttu-id="4bf13-126">U usluzi Marketo možete ukupno izvesti do 1 milion korisničkih profila.</span><span class="sxs-lookup"><span data-stu-id="4bf13-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Izaberite polja i segmente za izvoz u Marketo":::

1. <span data-ttu-id="4bf13-128">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="4bf13-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="4bf13-129">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="4bf13-129">Export the data</span></span>

<span data-ttu-id="4bf13-130">Možete da [izvezete podatke na zahtev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="4bf13-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="4bf13-131">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4bf13-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4bf13-132">U Marketo-u sada možete pronaći segmente u odeljku [Marketo liste](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="4bf13-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4bf13-133">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="4bf13-133">Known limitations</span></span>

- <span data-ttu-id="4bf13-134">Do 1 milion profila po izvozu u usluzi Marketo.</span><span class="sxs-lookup"><span data-stu-id="4bf13-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="4bf13-135">Izvoz u Marketo je ograničen na segmente.</span><span class="sxs-lookup"><span data-stu-id="4bf13-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="4bf13-136">Izvoz segmenata sa ukupno 1 milion profila može trajati do 3 sata.</span><span class="sxs-lookup"><span data-stu-id="4bf13-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="4bf13-137">Broj profila koje možete da izvezete u Marketo zavisi od i ograničen je vašim ugovorom sa kompanijom Marketo.</span><span class="sxs-lookup"><span data-stu-id="4bf13-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4bf13-138">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="4bf13-138">Data privacy and compliance</span></span>

<span data-ttu-id="4bf13-139">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Marketo, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="4bf13-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4bf13-140">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Marketo ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="4bf13-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4bf13-141">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4bf13-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4bf13-142">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="4bf13-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]