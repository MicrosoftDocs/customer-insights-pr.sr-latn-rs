---
title: Izvezite Customer Insights podatke u SFTP hostove
description: Naučite kako da konfigurišete vezu na SFTP hostom.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643520"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="de6c0-103">Konektor za SFTP (pregled)</span><span class="sxs-lookup"><span data-stu-id="de6c0-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="de6c0-104">Koristite podatke o klijentima u nezavisnim aplikacijama tako što ćete ih izvesti na Secure File Transfer Protocol (SFTP) host.</span><span class="sxs-lookup"><span data-stu-id="de6c0-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="de6c0-105">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="de6c0-105">Prerequisites</span></span>

- <span data-ttu-id="de6c0-106">Dostupnost SFTP hosta i odgovarajućih akreditiva.</span><span class="sxs-lookup"><span data-stu-id="de6c0-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="de6c0-107">Povezivanje na SFTP</span><span class="sxs-lookup"><span data-stu-id="de6c0-107">Connect to SFTP</span></span>

1. <span data-ttu-id="de6c0-108">Idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="de6c0-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="de6c0-109">Pod **SFTP**, izaberite **Postavi**.</span><span class="sxs-lookup"><span data-stu-id="de6c0-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="de6c0-110">Dajte odredištu prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="de6c0-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="de6c0-111">Navedite **Korisničko ime**, **Lozinku** i **Ime hosta** za SFTP nalog.</span><span class="sxs-lookup"><span data-stu-id="de6c0-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="de6c0-112">Primer: Ako je osnovnom direktorijum vašeg SFTP servera /root/folder, a želite da se podaci izvezu u /root/folder/ci_export_destination_folder, host treba da bude sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="de6c0-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="de6c0-113">Izaberite **Verifikuj** da testirate vezu.</span><span class="sxs-lookup"><span data-stu-id="de6c0-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="de6c0-114">Nakon uspešne verifikacije, izaberite da li želite da izvezite svoje podatke kao **Komprimovanu datoteku** ili **Raspakovati datoteku**, a zatim izaberite **znak razgraničavanja polja** za izvezene datoteke.</span><span class="sxs-lookup"><span data-stu-id="de6c0-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="de6c0-115">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="de6c0-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="de6c0-116">Izaberite **Sledeće** da biste započeli konfigurisanje izvoza.</span><span class="sxs-lookup"><span data-stu-id="de6c0-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="de6c0-117">Konfigurisanje veze</span><span class="sxs-lookup"><span data-stu-id="de6c0-117">Configure the connection</span></span>

1. <span data-ttu-id="de6c0-118">Izaberite **atribute klijenta** koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="de6c0-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="de6c0-119">Možete da izvezete jedan ili više atributa.</span><span class="sxs-lookup"><span data-stu-id="de6c0-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="de6c0-120">Izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="de6c0-120">Select **Next**.</span></span>

1. <span data-ttu-id="de6c0-121">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="de6c0-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="de6c0-122">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="de6c0-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="de6c0-123">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="de6c0-123">Export the data</span></span>

<span data-ttu-id="de6c0-124">Možete da [izvezete podatke na zahtev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="de6c0-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="de6c0-125">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="de6c0-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="de6c0-126">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="de6c0-126">Data privacy and compliance</span></span>

<span data-ttu-id="de6c0-127">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke putem SFTP-a, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="de6c0-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="de6c0-128">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da odredište za izvoz ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="de6c0-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="de6c0-129">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="de6c0-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="de6c0-130">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="de6c0-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
