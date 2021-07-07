---
title: Izvezite Customer Insights podataka u Salesforce Marketing Cloud
description: Saznajte kako da konfigurišete vezu i izvezete je u Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314666"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="0f98a-103">Izvoz segmenata i drugih podataka u Salesforce Marketing Cloud (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="0f98a-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="0f98a-104">Koristite podatke o klijentima u usluzi Salesforce Marketing Cloud tako što ćete ih izvesti putem lokacije protokola sigurnog prenosa datoteka (SFTP).</span><span class="sxs-lookup"><span data-stu-id="0f98a-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="0f98a-105">Preduslovi za vezu</span><span class="sxs-lookup"><span data-stu-id="0f98a-105">Prerequisites for connection</span></span>

- <span data-ttu-id="0f98a-106">Dostupnost SFTP hosta i odgovarajućih administratorskih akreditiva.</span><span class="sxs-lookup"><span data-stu-id="0f98a-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="0f98a-107">Kako postaviti SFTP lokacije za Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="0f98a-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="0f98a-108">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="0f98a-108">Known limitations</span></span>

- <span data-ttu-id="0f98a-109">Vreme izvoženja zavisi od performansi vašeg sistema.</span><span class="sxs-lookup"><span data-stu-id="0f98a-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="0f98a-110">Preporučujemo dva jezgra procesora i 1 GB memorije kao minimalnu konfiguraciju vašeg servera.</span><span class="sxs-lookup"><span data-stu-id="0f98a-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="0f98a-111">Izvoz entiteta sa do 100 miliona korisničkih profila može potrajati 90 minuta kada se koristi preporučena minimalna konfiguracija.</span><span class="sxs-lookup"><span data-stu-id="0f98a-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="0f98a-112">Podešavanje veze sa uslugom Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="0f98a-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="0f98a-113">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="0f98a-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0f98a-114">Izaberite **Dodaj vezu** i izaberite **Salesforce Marketing Cloud** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="0f98a-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="0f98a-115">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="0f98a-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0f98a-116">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="0f98a-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0f98a-117">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="0f98a-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0f98a-118">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="0f98a-118">Choose who can use this connection.</span></span> <span data-ttu-id="0f98a-119">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="0f98a-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0f98a-120">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0f98a-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0f98a-121">Navedite **korisničko ime**, **lozinku**, **ime hosta** i **fasciklu za izvoz** za SFTP nalog.</span><span class="sxs-lookup"><span data-stu-id="0f98a-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="0f98a-122">Izaberite **Verifikuj** da testirate vezu.</span><span class="sxs-lookup"><span data-stu-id="0f98a-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="0f98a-123">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="0f98a-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0f98a-124">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="0f98a-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0f98a-125">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="0f98a-125">Configure an export</span></span>

<span data-ttu-id="0f98a-126">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="0f98a-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0f98a-127">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0f98a-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0f98a-128">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="0f98a-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0f98a-129">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="0f98a-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0f98a-130">U polju **Veza za izvoz**, odaberite vezu iz odeljka SFTP.</span><span class="sxs-lookup"><span data-stu-id="0f98a-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="0f98a-131">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="0f98a-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0f98a-132">Odaberite da li želite da izvezete podatke **spakovano** ili **raspakovano** i **separator polja** za izvezene datoteke.</span><span class="sxs-lookup"><span data-stu-id="0f98a-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="0f98a-133">Izaberite entitete, na primer segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="0f98a-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0f98a-134">Svaki izabrani entitet biće podeljen na do pet izlaznih datoteka prilikom izvoza.</span><span class="sxs-lookup"><span data-stu-id="0f98a-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="0f98a-135">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="0f98a-135">Select **Save**.</span></span>

<span data-ttu-id="0f98a-136">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="0f98a-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0f98a-137">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0f98a-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0f98a-138">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0f98a-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="0f98a-139">Izvezite Customer Insights podatke u sa SFTP lokacije Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="0f98a-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="0f98a-140">Kreirajte [proširenja podataka u usluzi Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) za uvoz Customer Insights datoteke podataka sa SFTP lokacije.</span><span class="sxs-lookup"><span data-stu-id="0f98a-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="0f98a-141">[Uvezite podatke sa SFTP lokacije](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) u Salesforce Marketing Cloud proširenje podataka.</span><span class="sxs-lookup"><span data-stu-id="0f98a-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="0f98a-142">Podesite automatizaciju za uvoz podataka u proširenja podataka.</span><span class="sxs-lookup"><span data-stu-id="0f98a-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="0f98a-143">Saznajte više o [automatizacijama otpuštanja datoteka i zakazanim automatizacijama](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="0f98a-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="0f98a-144">Definišite [automatizaciju otpuštanja datoteka](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ili [zakazanu automatizaciju](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="0f98a-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="0f98a-145">Evo primera [automatizacije sa SFTP-om](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="0f98a-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0f98a-146">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="0f98a-146">Data privacy and compliance</span></span>

<span data-ttu-id="0f98a-147">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke putem SFTP-a, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="0f98a-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0f98a-148">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da odredište za izvoz ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="0f98a-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0f98a-149">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0f98a-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0f98a-150">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="0f98a-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
