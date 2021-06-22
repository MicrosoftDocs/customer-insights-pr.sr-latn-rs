---
title: Izvezite Customer Insights podatke u Mailchimp
description: Saznajte kako da konfigurišete vezu i izvezete u Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124244"
---
# <a name="export-segments-to-mailchimp-preview"></a><span data-ttu-id="83d96-103">Izvoz segmenata u Mailchimp (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="83d96-103">Export segments to Mailchimp (preview)</span></span>

<span data-ttu-id="83d96-104">Izvezite segmente objedinjenih profila klijenata u Mailchimp da biste kreirali biltene i kampanje e-pošte.</span><span class="sxs-lookup"><span data-stu-id="83d96-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="83d96-105">Preduslovi za vezu</span><span class="sxs-lookup"><span data-stu-id="83d96-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="83d96-106">Imate [Mailchimp nalog](https://mailchimp.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="83d96-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="83d96-107">Postoji postojeća publika u usluzi Mailchimp i odgovarajući ID-ovi.</span><span class="sxs-lookup"><span data-stu-id="83d96-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="83d96-108">Za više informacija pogledajte [Mailchimp korisnici](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="83d96-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="83d96-109">Imate [konfigurisane segmente](segments.md)</span><span class="sxs-lookup"><span data-stu-id="83d96-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="83d96-110">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="83d96-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="83d96-111">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="83d96-111">Known limitations</span></span>

- <span data-ttu-id="83d96-112">Do 1 milion profila po izvozu u usluzi Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="83d96-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="83d96-113">Izvoz u Mailchimp je ograničen na segmente.</span><span class="sxs-lookup"><span data-stu-id="83d96-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="83d96-114">Izvoz segmenata sa 1 milion profila može trajati do tri sata.</span><span class="sxs-lookup"><span data-stu-id="83d96-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="83d96-115">Broj profila koje možete da izvezete u Mailchimp zavisi od i ograničen je vašim ugovorom sa kompanijom Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="83d96-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="83d96-116">Podešavanje veze sa uslugom Mailchimp</span><span class="sxs-lookup"><span data-stu-id="83d96-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="83d96-117">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="83d96-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="83d96-118">Izaberite **Dodaj vezu** i birajte **Autopilot** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="83d96-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="83d96-119">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="83d96-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="83d96-120">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="83d96-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="83d96-121">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="83d96-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="83d96-122">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="83d96-122">Choose who can use this connection.</span></span> <span data-ttu-id="83d96-123">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="83d96-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="83d96-124">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="83d96-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="83d96-125">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="83d96-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="83d96-126">Izaberite **Povežite se** da bi se inicijalizovala veza sa uslugom Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="83d96-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="83d96-127">Izaberite **Potvrdite identitet u usluzi Mailchimp** i navedite akreditive za Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="83d96-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="83d96-128">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="83d96-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="83d96-129">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="83d96-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="83d96-130">Konfigurisanje konektora</span><span class="sxs-lookup"><span data-stu-id="83d96-130">Configure the connector</span></span>

<span data-ttu-id="83d96-131">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="83d96-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="83d96-132">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="83d96-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="83d96-133">Idite na **Podaci**> **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="83d96-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="83d96-134">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="83d96-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="83d96-135">U polju **Veza za izvoz**, odaberite vezu iz odeljka Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="83d96-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="83d96-136">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="83d96-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="83d96-137">Unesite **[ID ciljne grupe za Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="83d96-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="83d96-138">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="83d96-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="83d96-139">Opcionalno, možete da izvezete **Ime** i **Prezime** da biste kreirali personalizovanije e-poruke.</span><span class="sxs-lookup"><span data-stu-id="83d96-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="83d96-140">Izaberite **Dodaj atribut** za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="83d96-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="83d96-141">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="83d96-141">Select the segments you want to export.</span></span> <span data-ttu-id="83d96-142">U usluzi Mailchimp možete ukupno izvesti do 1 milion korisničkih profila.</span><span class="sxs-lookup"><span data-stu-id="83d96-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="83d96-143">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="83d96-143">Select **Save**.</span></span>

<span data-ttu-id="83d96-144">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="83d96-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="83d96-145">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="83d96-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="83d96-146">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="83d96-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="83d96-147">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="83d96-147">Data privacy and compliance</span></span>

<span data-ttu-id="83d96-148">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Mailchimp, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="83d96-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="83d96-149">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Mailchimp ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="83d96-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="83d96-150">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="83d96-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="83d96-151">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="83d96-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
