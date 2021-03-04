---
title: Izvezite Customer Insights podatke u SFTP hostove
description: Naučite kako da konfigurišete vezu na SFTP hostom.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268015"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="c59a1-103">Konektor za SFTP (pregled)</span><span class="sxs-lookup"><span data-stu-id="c59a1-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="c59a1-104">Koristite podatke o klijentima u nezavisnim aplikacijama tako što ćete ih izvesti na Secure File Transfer Protocol (SFTP) host.</span><span class="sxs-lookup"><span data-stu-id="c59a1-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c59a1-105">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="c59a1-105">Prerequisites</span></span>

- <span data-ttu-id="c59a1-106">Dostupnost SFTP hosta i odgovarajućih akreditiva.</span><span class="sxs-lookup"><span data-stu-id="c59a1-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="c59a1-107">Povezivanje sa SFTP</span><span class="sxs-lookup"><span data-stu-id="c59a1-107">Connect to SFTP</span></span>

1. <span data-ttu-id="c59a1-108">Idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="c59a1-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c59a1-109">Pod **SFTP**, izaberite **Postavi**.</span><span class="sxs-lookup"><span data-stu-id="c59a1-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="c59a1-110">Dajte odredištu prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="c59a1-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c59a1-111">Navedite **korisničko ime**, **lozinku**, **ime hosta** i **fasciklu za izvoz** za SFTP nalog.</span><span class="sxs-lookup"><span data-stu-id="c59a1-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="c59a1-112">Izaberite **Verifikuj** da testirate vezu.</span><span class="sxs-lookup"><span data-stu-id="c59a1-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="c59a1-113">Nakon uspešne verifikacije, izaberite da li želite da izvezete podatke u obliku **Gzipped** ili **Raspakovano** i izaberite **graničnik polja** za izvezene datoteke.</span><span class="sxs-lookup"><span data-stu-id="c59a1-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="c59a1-114">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="c59a1-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c59a1-115">Izaberite **Sledeće** da biste započeli konfigurisanje izvoza.</span><span class="sxs-lookup"><span data-stu-id="c59a1-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="c59a1-116">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="c59a1-116">Configure the export</span></span>

1. <span data-ttu-id="c59a1-117">Izaberite entitete, na primer segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="c59a1-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c59a1-118">Svaki izabrani entitet će imati do pet izlaznih datoteka prilikom izvoza.</span><span class="sxs-lookup"><span data-stu-id="c59a1-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="c59a1-119">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="c59a1-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c59a1-120">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="c59a1-120">Export the data</span></span>

<span data-ttu-id="c59a1-121">Možete da [izvezete podatke na zahtev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c59a1-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c59a1-122">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c59a1-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c59a1-123">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="c59a1-123">Known limitations</span></span>

- <span data-ttu-id="c59a1-124">Vreme izvoženja zavisi od performansi vašeg sistema.</span><span class="sxs-lookup"><span data-stu-id="c59a1-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="c59a1-125">Preporučujemo dva jezgra procesora i 1 GB memorije kao minimalnu konfiguraciju vašeg servera.</span><span class="sxs-lookup"><span data-stu-id="c59a1-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="c59a1-126">Izvoz entiteta sa do 100 miliona korisničkih profila može potrajati 90 minuta kada se koristi preporučena minimalna konfiguracija sa dva jezgra procesora i 1 GB memorije.</span><span class="sxs-lookup"><span data-stu-id="c59a1-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c59a1-127">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="c59a1-127">Data privacy and compliance</span></span>

<span data-ttu-id="c59a1-128">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke putem SFTP-a, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="c59a1-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c59a1-129">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da odredište za izvoz ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="c59a1-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c59a1-130">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c59a1-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c59a1-131">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="c59a1-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]