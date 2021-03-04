---
title: Izvezite Customer Insights podatke u Google oglasima
description: Saznajte kako da konfigurišete vezu sa Google oglasima.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268979"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="dd3f1-103">Konektor za Google oglase (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="dd3f1-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="dd3f1-104">Izvezite segmente objedinjenih profila klijenata u listu korisnika Google oglasa i koristite ih za oglašavanje u Google pretrazi, na Gmail-u, YouTube-u i Google mreži multimedijalnog oglašavanja.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="dd3f1-105">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="dd3f1-105">Prerequisites</span></span>

-   <span data-ttu-id="dd3f1-106">Imate [nalog Google oglasa](https://ads.google.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="dd3f1-107">Postoji postojeća publika u Google oglasima i odgovarajući ID-ovi.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="dd3f1-108">Za više informacija pogledajte [Korisnici Google oglasa](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="dd3f1-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="dd3f1-109">Imate [konfigurisane segmente](segments.md)</span><span class="sxs-lookup"><span data-stu-id="dd3f1-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="dd3f1-110">Objedinjeni profili klijenata u izvezenim segmentima sadrže polja koja predstavljaju adresu e-pošte, ime i prezime</span><span class="sxs-lookup"><span data-stu-id="dd3f1-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="dd3f1-111">Povežite se sa Google oglasima</span><span class="sxs-lookup"><span data-stu-id="dd3f1-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="dd3f1-112">Idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="dd3f1-113">U odeljku **Google oglasi**, izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="dd3f1-114">Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="dd3f1-115">Unesite **[ID klijenta za Google oglase](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="dd3f1-116">Unesite **[token odobrenog programera za Google oglase](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="dd3f1-117">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="dd3f1-118">Unesite **[ID korisnika za Google oglase](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** i izaberite **Povežite se** da biste započeli povezivanje sa Google oglasima.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="dd3f1-119">Izaberite **Potvrdite identitet u Google oglasima** i navedite akreditive za Google oglase.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="dd3f1-120">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Izvezite snimak ekrana za vezu sa Google oglasima":::

1. <span data-ttu-id="dd3f1-122">Izaberite **Sledeće** da biste konfigurisali izvoz.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="dd3f1-123">Konfigurisanje konektora</span><span class="sxs-lookup"><span data-stu-id="dd3f1-123">Configure the connector</span></span>

1. <span data-ttu-id="dd3f1-124">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="dd3f1-125">Ponovite iste korake za polja **Ime** i **Prezime**.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="dd3f1-126">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-126">Select the segments you want to export.</span></span> <span data-ttu-id="dd3f1-127">U Google oglasima možete ukupno izvesti do 1 milion korisničkih profila.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="dd3f1-128">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="dd3f1-129">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="dd3f1-129">Export the data</span></span>

<span data-ttu-id="dd3f1-130">Možete da [izvezete podatke na zahtev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="dd3f1-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="dd3f1-131">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dd3f1-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dd3f1-132">U Google oglasima sada možete pronaći segmente u odeljku [Korisnici Google oglasa](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="dd3f1-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="dd3f1-133">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="dd3f1-133">Known limitations</span></span>

- <span data-ttu-id="dd3f1-134">Do 1 milion profila po izvozu u Google oglasima.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="dd3f1-135">Izvoz u Google oglase je ograničen na segmente.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="dd3f1-136">Izvoz segmenata sa ukupno 1 milion profila može trajati do 5 minuta zbog ograničenja na strani dobavljača.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="dd3f1-137">Podudaranje u Google oglasima može da potraje do 48 sati.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dd3f1-138">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="dd3f1-138">Data privacy and compliance</span></span>

<span data-ttu-id="dd3f1-139">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Google oglase, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dd3f1-140">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Google oglasi ispunjavaju sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="dd3f1-141">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dd3f1-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dd3f1-142">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="dd3f1-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]