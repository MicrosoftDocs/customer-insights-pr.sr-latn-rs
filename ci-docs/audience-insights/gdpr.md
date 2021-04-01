---
title: Zahtevi na osnovu prava subjekta podataka (DSR) u okviru GDPR | Microsoft Docs
description: Odgovorite na zahteve subjekta podataka za Dynamics 365 Customer Insights mogućnost uvida o korisnicima.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9c453c9b416bff0e6362a8ccf7ff534f4efa1e00
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597528"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="034ab-103">Zahtevi na osnovu prava subjekta podataka (DSR) u okviru GDPR</span><span class="sxs-lookup"><span data-stu-id="034ab-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="034ab-104">Odgovaranje na zahteve za brisanje GDPR subjekta podataka za Dynamics 365 Customer Insights mogućnost uvida o korisnicima</span><span class="sxs-lookup"><span data-stu-id="034ab-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="034ab-105">„Pravo na brisanje“ uklanjanjem ličnih podataka iz podataka o klijentima organizacije predstavlja ključnu zaštitu u Opštoj uredbi o zaštiti podataka (GDPR).</span><span class="sxs-lookup"><span data-stu-id="034ab-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="034ab-106">Uklanjanje ličnih podataka uključuje uklanjanje svih ličnih podataka i sistemski generisanih evidencija, osim informacija iz evidencije nadgledanja.</span><span class="sxs-lookup"><span data-stu-id="034ab-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="034ab-107">Upravljanje zahtevima za brisanje subjekta podataka</span><span class="sxs-lookup"><span data-stu-id="034ab-107">Manage data subject delete requests</span></span>

<span data-ttu-id="034ab-108">Uvidi o korisnicima nude sledeće iskustvo u vezi sa proizvodom za brisanje ličnih podataka određenog klijenta ili Customer Insights korisnika:</span><span class="sxs-lookup"><span data-stu-id="034ab-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="034ab-109">**Upravljajte zahtevima brisanje podataka o klijentu**: Podaci o klijentu u usluzi Customer Insights uneti su iz originalnih izvora podataka koji su spoljašnji za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="034ab-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="034ab-110">Svi GDPR zahtevi za brisanje moraju se obaviti u originalnom izvoru podataka.</span><span class="sxs-lookup"><span data-stu-id="034ab-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="034ab-111">**Upravljajte zahtevima za brisanje korisničkih podataka korisnika usluge Customer Insights**: Podatke za korisnike kreira Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="034ab-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="034ab-112">Svi GDPR zahtevi za brisanje moraju se obaviti u usluzi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="034ab-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="034ab-113">Upravljanje zahtevima za brisanje podataka o klijentima</span><span class="sxs-lookup"><span data-stu-id="034ab-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="034ab-114">Administrator usluge Customer Insights može da prati ove korake za uklanjanje podataka o klijentima koji su izbrisani u izvoru podataka:</span><span class="sxs-lookup"><span data-stu-id="034ab-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="034ab-115">Prijavite se u Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="034ab-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="034ab-116">U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**</span><span class="sxs-lookup"><span data-stu-id="034ab-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="034ab-117">Za svaki izvor podataka na listi koji sadrži izbrisane podatke o klijentima:</span><span class="sxs-lookup"><span data-stu-id="034ab-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="034ab-118">Izaberite (...), pa izaberite **Osveži**.</span><span class="sxs-lookup"><span data-stu-id="034ab-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="034ab-119">Proverite status izvora podataka u odeljku **Status**.</span><span class="sxs-lookup"><span data-stu-id="034ab-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="034ab-120">Znak potvrde znači da je osvežavanje bilo uspešno.</span><span class="sxs-lookup"><span data-stu-id="034ab-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="034ab-121">Trokut upozorenja znači da nešto nije u redu.</span><span class="sxs-lookup"><span data-stu-id="034ab-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="034ab-122">Ako se prikaže trougao upozorenja, kontaktirajte D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="034ab-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="034ab-123">![Rukovanje GDPR zahtevima za brisanje podataka o klijentima](media/gdpr-data-sources.png "Rukovanje GDPR zahtevima za brisanje podataka o klijentima")</span><span class="sxs-lookup"><span data-stu-id="034ab-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="034ab-124">Upravljanje zahtevima za brisanje podataka o korisnicima</span><span class="sxs-lookup"><span data-stu-id="034ab-124">Manage delete requests for user data</span></span>

<span data-ttu-id="034ab-125">Administrator usluge Customer Insights može da sledi sledeće korake za brisanje podataka o Customer Insights korisnicima:</span><span class="sxs-lookup"><span data-stu-id="034ab-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="034ab-126">Prijavite se u Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="034ab-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="034ab-127">U uvidima o korisnicima idite na **Administrator** > **Dozvole**.</span><span class="sxs-lookup"><span data-stu-id="034ab-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="034ab-128">Izaberite polje za potvrdu za korisnika kojeg želite da izbrišete.</span><span class="sxs-lookup"><span data-stu-id="034ab-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="034ab-129">Izaberite **Ukloni**.</span><span class="sxs-lookup"><span data-stu-id="034ab-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="034ab-130">![Upravljanje GDPR zahtevima za brisanje podataka o korisnicima](media/gdpr-permissions.png "Upravljanje GDPR zahtevima za brisanje podataka o korisnicima")</span><span class="sxs-lookup"><span data-stu-id="034ab-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="034ab-131">Odgovaranje na GDPR zahteve za izvoz subjekta podataka</span><span class="sxs-lookup"><span data-stu-id="034ab-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="034ab-132">Kao deo naše posvećenosti da zajedno sa vama sarađujemo na vašem putu do Opšte uredbe o zaštiti podataka (GDPR), razvili smo dokumentaciju koja će vam pomoći da se pripremite.</span><span class="sxs-lookup"><span data-stu-id="034ab-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="034ab-133">Ova dokumentacija opisuje korake koje danas možete preduzeti da biste podržali poštovanje GDPR-a kada koristite uvide o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="034ab-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="034ab-134">Upravljanje izvozom i prikaz zahteva</span><span class="sxs-lookup"><span data-stu-id="034ab-134">Manage export and view requests</span></span>

<span data-ttu-id="034ab-135">Pravo prenosivosti podataka omogućava subjektima podataka da zatraže kopiju svojih ličnih podataka u elektronskom formatu (definisanom kao "strukturirani, uobičajeno upotrebljiv, mašinski čitljiv i interoperabilni format") koji se može preneti na drugog kontrolora podataka.</span><span class="sxs-lookup"><span data-stu-id="034ab-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="034ab-136">Izvoz podataka o klijentu (administrator zakupca)</span><span class="sxs-lookup"><span data-stu-id="034ab-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="034ab-137">Administrator zakupca može da prati ove korake za izvoz podataka:</span><span class="sxs-lookup"><span data-stu-id="034ab-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="034ab-138">Pošaljite e-poruku na D365CI@microsoft.com navodeći adresu e-pošte klijenta u zahtevu.</span><span class="sxs-lookup"><span data-stu-id="034ab-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="034ab-139">Customer Insights tim će poslati e-poruku na registrovanu adresu e-pošte administratora registrovanog zakupca, tražeći potvrdu za izvoz podataka.</span><span class="sxs-lookup"><span data-stu-id="034ab-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="034ab-140">Potvrdite potvrdu za izvoz podataka za traženog klijenta.</span><span class="sxs-lookup"><span data-stu-id="034ab-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="034ab-141">Primite izvezene podatke putem e-adrese administratora zakupca.</span><span class="sxs-lookup"><span data-stu-id="034ab-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="034ab-142">Izvoz podataka o korisniku (administrator zakupca)</span><span class="sxs-lookup"><span data-stu-id="034ab-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="034ab-143">Pošaljite e-poruku na D365CI@microsoft.com navodeći adresu e-pošte korisnika u zahtevu.</span><span class="sxs-lookup"><span data-stu-id="034ab-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="034ab-144">Customer Insights tim će poslati e-poruku na registrovanu adresu e-pošte administratora registrovanog zakupca, tražeći potvrdu za izvoz podataka.</span><span class="sxs-lookup"><span data-stu-id="034ab-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="034ab-145">Prihvatite potvrdu za izvoz podataka za traženog korisnika.</span><span class="sxs-lookup"><span data-stu-id="034ab-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="034ab-146">Primite izvezene podatke putem e-adrese administratora zakupca.</span><span class="sxs-lookup"><span data-stu-id="034ab-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]