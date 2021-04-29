---
title: Izvezite Customer Insights podatke u Autopilot
description: Saznajte kako da konfigurišete vezu i izvezete u Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760160"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="85787-103">Izvoz segmenata u Autopilot (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="85787-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="85787-104">Izvezite segmente objedinjenih profila klijenata u Autopilot i koristite ih za marketing putem e-pošte u usluzi Autopilot.</span><span class="sxs-lookup"><span data-stu-id="85787-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="85787-105">Preduslovi za vezu</span><span class="sxs-lookup"><span data-stu-id="85787-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="85787-106">Imate [Autopilot nalog](https://www.autopilothq.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="85787-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="85787-107">[Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="85787-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="85787-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="85787-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="85787-109">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="85787-109">Known limitations</span></span>

- <span data-ttu-id="85787-110">U uslugu Autopilot možete da izvezete ukupno do 100.000 profila.</span><span class="sxs-lookup"><span data-stu-id="85787-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="85787-111">Izvoz u Autopilot je ograničen na segmente.</span><span class="sxs-lookup"><span data-stu-id="85787-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="85787-112">Izvoz do 100.000 profila u Autopilot može da potraje do nekoliko sati.</span><span class="sxs-lookup"><span data-stu-id="85787-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="85787-113">Broj profila koje možete da izvezete u Autopilot zavisi od vašeg ugovora sa kompanijom Autopilot i ograničen je njime.</span><span class="sxs-lookup"><span data-stu-id="85787-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="85787-114">Podešavanje veze sa uslugom Autopilot</span><span class="sxs-lookup"><span data-stu-id="85787-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="85787-115">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="85787-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="85787-116">Izaberite **Dodaj vezu** i birajte **Autopilot** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="85787-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="85787-117">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="85787-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="85787-118">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="85787-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="85787-119">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="85787-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="85787-120">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="85787-120">Choose who can use this connection.</span></span> <span data-ttu-id="85787-121">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="85787-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="85787-122">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="85787-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="85787-123">Unesite svoj [API ključ za Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="85787-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="85787-124">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="85787-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="85787-125">Izaberite **Poveži se** za inicijalizaciju veze sa uslugom Autopilot.</span><span class="sxs-lookup"><span data-stu-id="85787-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="85787-126">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="85787-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="85787-127">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="85787-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="85787-128">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="85787-128">Configure an export</span></span>

<span data-ttu-id="85787-129">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="85787-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="85787-130">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="85787-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="85787-131">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="85787-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="85787-132">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="85787-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="85787-133">U polju **Veza za izvoz**, odaberite vezu iz odeljka Autopilot.</span><span class="sxs-lookup"><span data-stu-id="85787-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="85787-134">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="85787-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="85787-135">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="85787-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="85787-136">Ponovite iste korake za druga opcionalna polja kao što su **Ime**, **Prezime**.</span><span class="sxs-lookup"><span data-stu-id="85787-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="85787-137">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="85787-137">Select the segments you want to export.</span></span> <span data-ttu-id="85787-138">Izričito **preporučujemo da ne izvozite ukupno više od 100.000 profila klijenata** u Autopilot.</span><span class="sxs-lookup"><span data-stu-id="85787-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="85787-139">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="85787-139">Select **Save**.</span></span>

<span data-ttu-id="85787-140">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="85787-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="85787-141">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="85787-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="85787-142">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="85787-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="85787-143">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="85787-143">Data privacy and compliance</span></span>

<span data-ttu-id="85787-144">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Autopilot, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="85787-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="85787-145">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Autopilot ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="85787-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="85787-146">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="85787-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="85787-147">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="85787-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
