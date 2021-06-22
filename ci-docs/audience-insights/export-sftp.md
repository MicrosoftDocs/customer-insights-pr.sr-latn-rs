---
title: Izvezite Customer Insights podatke u SFTP hostove
description: Saznajte kako da konfigurišete vezu i izvezete na SFTP lokaciju.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 000b44dc8e5cc419132bd17e359fbdd5879caf1b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124336"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a><span data-ttu-id="68518-103">Izvoz segmenata i ostalih podataka u SFTP (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="68518-103">Export segments and other data to SFTP (preview)</span></span>

<span data-ttu-id="68518-104">Koristite podatke o klijentima u nezavisnim aplikacijama tako što ćete ih izvesti na lokaciju protokola za bezbedni prenos datoteka (SFTP).</span><span class="sxs-lookup"><span data-stu-id="68518-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="68518-105">Preduslovi za vezu</span><span class="sxs-lookup"><span data-stu-id="68518-105">Prerequisites for connection</span></span>

- <span data-ttu-id="68518-106">Dostupnost SFTP hosta i odgovarajućih akreditiva.</span><span class="sxs-lookup"><span data-stu-id="68518-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="68518-107">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="68518-107">Known limitations</span></span>

- <span data-ttu-id="68518-108">Vreme izvoženja zavisi od performansi vašeg sistema.</span><span class="sxs-lookup"><span data-stu-id="68518-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="68518-109">Preporučujemo dva jezgra procesora i 1 GB memorije kao minimalnu konfiguraciju vašeg servera.</span><span class="sxs-lookup"><span data-stu-id="68518-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="68518-110">Izvoz entiteta sa do 100 miliona korisničkih profila može potrajati 90 minuta kada se koristi preporučena minimalna konfiguracija sa dva jezgra procesora i 1 GB memorije.</span><span class="sxs-lookup"><span data-stu-id="68518-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="68518-111">Podešavanje veze sa SFTP</span><span class="sxs-lookup"><span data-stu-id="68518-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="68518-112">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="68518-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="68518-113">Izaberite **Dodaj vezu** i birajte **SFTP** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="68518-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="68518-114">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="68518-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="68518-115">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="68518-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="68518-116">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="68518-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="68518-117">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="68518-117">Choose who can use this connection.</span></span> <span data-ttu-id="68518-118">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="68518-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="68518-119">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="68518-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="68518-120">Navedite **korisničko ime**, **lozinku**, **ime hosta** i **fasciklu za izvoz** za SFTP nalog.</span><span class="sxs-lookup"><span data-stu-id="68518-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="68518-121">Izaberite **Verifikuj** da testirate vezu.</span><span class="sxs-lookup"><span data-stu-id="68518-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="68518-122">Odaberite da li želite da izvezete podatke **spakovano** ili **raspakovano** i **separator polja** za izvezene datoteke.</span><span class="sxs-lookup"><span data-stu-id="68518-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="68518-123">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="68518-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="68518-124">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="68518-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="68518-125">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="68518-125">Configure an export</span></span>

<span data-ttu-id="68518-126">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="68518-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="68518-127">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="68518-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="68518-128">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="68518-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="68518-129">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="68518-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="68518-130">U polju **Veza za izvoz**, odaberite vezu iz odeljka SFTP.</span><span class="sxs-lookup"><span data-stu-id="68518-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="68518-131">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="68518-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="68518-132">Izaberite entitete, na primer segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="68518-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="68518-133">Svaki izabrani entitet biće podeljen na do pet izlaznih datoteka prilikom izvoza.</span><span class="sxs-lookup"><span data-stu-id="68518-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="68518-134">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="68518-134">Select **Save**.</span></span>

<span data-ttu-id="68518-135">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="68518-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="68518-136">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="68518-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="68518-137">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="68518-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="68518-138">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="68518-138">Data privacy and compliance</span></span>

<span data-ttu-id="68518-139">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke putem SFTP-a, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="68518-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="68518-140">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da odredište za izvoz ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="68518-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="68518-141">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="68518-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="68518-142">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="68518-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
