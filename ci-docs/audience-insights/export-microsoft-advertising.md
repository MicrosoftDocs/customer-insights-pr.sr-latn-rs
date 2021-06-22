---
title: Izvoz Customer Insights podataka u Microsoft Advertising
description: Saznajte kako da konfigurišete vezu i izvezete sadržaj u Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124543"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="e93c9-103">Izvoz segmenata u Microsoft Advertising (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="e93c9-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="e93c9-104">Izvezite Customer Insights segmente u Microsoft Advertising da biste kreirali ciljne grupe za podudaranje klijenata.</span><span class="sxs-lookup"><span data-stu-id="e93c9-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="e93c9-105">Koristite ove ciljne grupe za svoje oglasne kampanje.</span><span class="sxs-lookup"><span data-stu-id="e93c9-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e93c9-106">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="e93c9-106">Prerequisites</span></span>

-   <span data-ttu-id="e93c9-107">Imate [Microsoft Advertising nalog](https://ads.microsoft.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="e93c9-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e93c9-108">Prihvatili ste uslove korišćenja za podudaranje klijenata.</span><span class="sxs-lookup"><span data-stu-id="e93c9-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="e93c9-109">[Konfigurisani segmenti](segments.md) u uvidima u ciljnu grupu.</span><span class="sxs-lookup"><span data-stu-id="e93c9-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e93c9-110">Objedinjeni korisnički profili u izvezenim segmentima sadrže polje sa adresom e-pošte.</span><span class="sxs-lookup"><span data-stu-id="e93c9-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e93c9-111">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="e93c9-111">Known limitations</span></span>

- <span data-ttu-id="e93c9-112">Možete izvesti do 500.000 profila po izvozu u Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="e93c9-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="e93c9-113">Izvoz u Microsoft Advertising ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="e93c9-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="e93c9-114">Izvoz do 500.000 profila u Microsoft Advertising može potrajati do 10 minuta.</span><span class="sxs-lookup"><span data-stu-id="e93c9-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="e93c9-115">Podešavanje veze sa uslugom Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="e93c9-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="e93c9-116">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="e93c9-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e93c9-117">Izaberite **Dodaj vezu** i birajte **Microsoft Advertising** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="e93c9-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="e93c9-118">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="e93c9-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e93c9-119">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="e93c9-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e93c9-120">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="e93c9-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e93c9-121">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="e93c9-121">Choose who can use this connection.</span></span> <span data-ttu-id="e93c9-122">Podrazumevano su administratori.</span><span class="sxs-lookup"><span data-stu-id="e93c9-122">The default is administrators.</span></span> <span data-ttu-id="e93c9-123">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e93c9-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e93c9-124">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="e93c9-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e93c9-125">Izaberite **Povežite se** da biste pokrenuli vezu sa uslugom Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="e93c9-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="e93c9-126">Izaberite **Potvrdi identitet pomoću usluge Microsoft Advertising** i obezbedite svoje administratorske akreditive za Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="e93c9-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="e93c9-127">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e93c9-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e93c9-128">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="e93c9-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e93c9-129">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="e93c9-129">Configure an export</span></span>

<span data-ttu-id="e93c9-130">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="e93c9-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e93c9-131">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e93c9-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e93c9-132">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="e93c9-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e93c9-133">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="e93c9-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e93c9-134">U polju **Veza za izvoz**, odaberite vezu iz odeljka Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="e93c9-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="e93c9-135">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="e93c9-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e93c9-136">Izaberite segmente za izvoz.</span><span class="sxs-lookup"><span data-stu-id="e93c9-136">Select the segments to export.</span></span> <span data-ttu-id="e93c9-137">Ciljne grupe za podudaranje klijenata u usluzi Microsoft Advertising automatski se kreira sa nazivom segmenata izabranih za izvoz.</span><span class="sxs-lookup"><span data-stu-id="e93c9-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="e93c9-138">Svaki segment će rezultirati zasebnom ciljnom grupom za podudaranje klijenata.</span><span class="sxs-lookup"><span data-stu-id="e93c9-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="e93c9-139">Unesite svoj **ID Microsoft Advertising klijenta i ID naloga**.</span><span class="sxs-lookup"><span data-stu-id="e93c9-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="e93c9-140">Možete pronaći ID klijenta (`cid`) i ID poslovnog kontakta (`aid`) u parametrima URL adrese kada se prijavite u Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="e93c9-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="e93c9-141">U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje u vašem objedinjenom profilu klijenta sa e-adresom klijenta.</span><span class="sxs-lookup"><span data-stu-id="e93c9-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="e93c9-142">Potrebno je da izvezete segmente u Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="e93c9-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="e93c9-143">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="e93c9-143">Select **Save**.</span></span>

<span data-ttu-id="e93c9-144">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="e93c9-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e93c9-145">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e93c9-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e93c9-146">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e93c9-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e93c9-147">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="e93c9-147">Data privacy and compliance</span></span>

<span data-ttu-id="e93c9-148">Kada omogućite Dynamics 365 Customer Insights za prenos podataka u Microsoft Advertising, dozvoljavate prenos podataka izvan granica usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="e93c9-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e93c9-149">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Microsoft Advertising ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="e93c9-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e93c9-150">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e93c9-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e93c9-151">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="e93c9-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
