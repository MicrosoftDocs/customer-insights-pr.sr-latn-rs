---
title: Izvoz Customer Insights podataka u LinkedIn Ads
description: Saznajte kako da konfigurišete vezu i izvozite u LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124545"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="0cad8-103">Izvoz segmenata u LinkedIn Ads (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="0cad8-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="0cad8-104">Izvezite segmente objedinjenih profila klijenata u LinkedIn Ads da biste kreirali podudarnu ciljnu grupu.</span><span class="sxs-lookup"><span data-stu-id="0cad8-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="0cad8-105">Koristite podudarnu ciljnu grupu za ciljanje preduzeća i ciljanje kontakata.</span><span class="sxs-lookup"><span data-stu-id="0cad8-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0cad8-106">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="0cad8-106">Prerequisites</span></span>

-   <span data-ttu-id="0cad8-107">Imate [LinkedIn Campaign Manager nalog](https://business.linkedin.com/marketing-solutions/ads) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="0cad8-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0cad8-108">[Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="0cad8-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0cad8-109">Korisnički profili u izvezenim segmentima sadrže polje sa adresom e-pošte.</span><span class="sxs-lookup"><span data-stu-id="0cad8-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0cad8-110">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="0cad8-110">Known limitations</span></span>

- <span data-ttu-id="0cad8-111">Možete izvesti do 100.000 profila po izvozu u LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="0cad8-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="0cad8-112">Izvoz u LinkedIn Ads ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="0cad8-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="0cad8-113">Izvoz do 100.000 profila u LinkedIn Ads može potrajati do 10 minuta.</span><span class="sxs-lookup"><span data-stu-id="0cad8-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="0cad8-114">Podesite vezu sa uslugom LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="0cad8-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="0cad8-115">U uvidima u ciljne grupe, idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="0cad8-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0cad8-116">Izaberite **Dodaj vezu** i birajte **LinkedIn Ads** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="0cad8-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="0cad8-117">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="0cad8-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0cad8-118">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="0cad8-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0cad8-119">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="0cad8-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0cad8-120">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="0cad8-120">Choose who can use this connection.</span></span> <span data-ttu-id="0cad8-121">Ako ništa ne preduzmete, podrazumevaju se Administratori.</span><span class="sxs-lookup"><span data-stu-id="0cad8-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="0cad8-122">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0cad8-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0cad8-123">Navedite svoj [ID LinkedIn Campaign Manager naloga](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="0cad8-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="0cad8-124">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="0cad8-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0cad8-125">Izaberite **Povežite se** da bi se inicijalizovala veza sa uslugom Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="0cad8-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="0cad8-126">Izaberite **Potvrdite identitet pomoću usluge LinkedIn** i obezbedite svoje administratorske akreditive za LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="0cad8-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="0cad8-127">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0cad8-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0cad8-128">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="0cad8-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0cad8-129">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="0cad8-129">Configure an export</span></span>

<span data-ttu-id="0cad8-130">Izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="0cad8-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="0cad8-131">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0cad8-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0cad8-132">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="0cad8-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0cad8-133">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="0cad8-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0cad8-134">U polju **Veza za izvoz**, odaberite vezu iz odeljka LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="0cad8-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="0cad8-135">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="0cad8-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0cad8-136">Odaberite da li želite da izvezete podatke da obavite [kontakt ciljanje](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ili [ciljanje kompanije](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) u usluzi LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="0cad8-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="0cad8-137">U odeljku **Podudaranje podataka** izaberite polje u vašem objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="0cad8-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0cad8-138">Potrebno je da izvezete segmente u LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="0cad8-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="0cad8-139">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="0cad8-139">Select the segments you want to export.</span></span> <span data-ttu-id="0cad8-140">Publika koja se podudara u usluzi LinkedIn Campaign Manager automatski će se kreirati sa nazivom segmenata koje ste izabrali za izvoz.</span><span class="sxs-lookup"><span data-stu-id="0cad8-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="0cad8-141">Svaki segment će rezultirati zasebnom podudarnom ciljnom grupom.</span><span class="sxs-lookup"><span data-stu-id="0cad8-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="0cad8-142">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="0cad8-142">Select **Save**.</span></span>

<span data-ttu-id="0cad8-143">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="0cad8-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0cad8-144">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0cad8-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0cad8-145">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0cad8-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0cad8-146">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="0cad8-146">Data privacy and compliance</span></span>

<span data-ttu-id="0cad8-147">Kada omogućite Dynamics 365 Customer Insights za prenos podataka u LinkedIn Ads, dozvoljavate prenos podataka izvan granica usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="0cad8-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0cad8-148">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da LinkedIn Ads ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="0cad8-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0cad8-149">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0cad8-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="0cad8-150">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="0cad8-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
