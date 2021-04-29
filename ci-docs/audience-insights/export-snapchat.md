---
title: Izvoz Customer Insights podataka u Snapchat
description: Saznajte kako da konfigurišete vezu i izvezete u Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760620"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="04d57-103">Izvoz listi segmenata u Snapchat (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="04d57-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="04d57-104">Izvezite segmente objedinjenih profila klijenata u Snapchat i koristite ih za oglašavanje.</span><span class="sxs-lookup"><span data-stu-id="04d57-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="04d57-105">Preduslovi za vezu</span><span class="sxs-lookup"><span data-stu-id="04d57-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="04d57-106">Imate [Snapchat Business nalog](https://business.snapchat.com/), [Snapchat Ads nalog](https://ads.snapchat.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="04d57-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="04d57-107">[Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="04d57-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="04d57-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="04d57-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="04d57-109">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="04d57-109">Known limitations</span></span>

- <span data-ttu-id="04d57-110">Izvoz u Snapchat ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="04d57-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="04d57-111">Izvoz do 1 milion profila u Snapchat može potrajati do 15 minuta.</span><span class="sxs-lookup"><span data-stu-id="04d57-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="04d57-112">Podešavanje veze u usluzi Snapchat</span><span class="sxs-lookup"><span data-stu-id="04d57-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="04d57-113">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="04d57-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="04d57-114">Izaberite **Dodaj vezu** i birajte **Snapchat** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="04d57-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="04d57-115">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="04d57-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="04d57-116">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="04d57-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="04d57-117">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="04d57-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="04d57-118">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="04d57-118">Choose who can use this connection.</span></span> <span data-ttu-id="04d57-119">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="04d57-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="04d57-120">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="04d57-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="04d57-121">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="04d57-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="04d57-122">Izaberite **Povežite se** da bi se inicijalizovala veza sa uslugom Snapchat.</span><span class="sxs-lookup"><span data-stu-id="04d57-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="04d57-123">Izaberite **Potvrdite identitet pomoću usluge Snapchat** i obezbedite svoje administratorske akreditive za Snapchat.</span><span class="sxs-lookup"><span data-stu-id="04d57-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="04d57-124">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="04d57-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="04d57-125">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="04d57-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="04d57-126">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="04d57-126">Configure an export</span></span>

<span data-ttu-id="04d57-127">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="04d57-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="04d57-128">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="04d57-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="04d57-129">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="04d57-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="04d57-130">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="04d57-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="04d57-131">U polju **Veza za izvoz**, odaberite vezu iz odeljka Snapchat.</span><span class="sxs-lookup"><span data-stu-id="04d57-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="04d57-132">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="04d57-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="04d57-133">Unesite [**ID ciljne grupe za Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="04d57-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="04d57-134">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="04d57-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="04d57-135">To je potrebno da izvezete segmente u Snapchat.</span><span class="sxs-lookup"><span data-stu-id="04d57-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="04d57-136">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="04d57-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="04d57-137">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="04d57-137">Select **Save**.</span></span>

<span data-ttu-id="04d57-138">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="04d57-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="04d57-139">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="04d57-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="04d57-140">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="04d57-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="04d57-141">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="04d57-141">Data privacy and compliance</span></span>

<span data-ttu-id="04d57-142">Kada omogućite Dynamics 365 Customer Insights za prenos podataka u Snapchat, dozvoljavate prenos podataka izvan granica usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="04d57-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="04d57-143">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Snapchat ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="04d57-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="04d57-144">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="04d57-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="04d57-145">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="04d57-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
