---
title: Izvoz Customer Insights podataka u Constant Contact
description: Saznajte kako da konfigurišete vezu i izvezete sadržaj u Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760621"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="d1878-103">Izvoz listi segmenata u Constant Contact (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="d1878-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="d1878-104">Izvezite segmente objedinjenih profila klijenata u Constant Contact i koristite ih za marketinške aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="d1878-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d1878-105">Preduslovi za vezu</span><span class="sxs-lookup"><span data-stu-id="d1878-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="d1878-106">Imate [Constant Contact nalog](https://www.constantcontact.com/account-home) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="d1878-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d1878-107">[Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="d1878-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d1878-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="d1878-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d1878-109">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="d1878-109">Known limitations</span></span>

- <span data-ttu-id="d1878-110">Možete izvesti do 1 milion profila po izvozu u Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="d1878-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="d1878-111">Izvoz u Constant Contact ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="d1878-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="d1878-112">Izvoz do 1 milion profila u Constant Contact može potrajati do 1 sata.</span><span class="sxs-lookup"><span data-stu-id="d1878-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="d1878-113">Broj profila koje možete da izvezete u Constant Contact zavisi i ograničen je vašim ugovorom sa uslugom Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="d1878-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="d1878-114">Podešavanje veze sa uslugom Constant Contact</span><span class="sxs-lookup"><span data-stu-id="d1878-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="d1878-115">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="d1878-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d1878-116">Izaberite **Dodaj vezu** i birajte **Constant Contact** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="d1878-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="d1878-117">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="d1878-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d1878-118">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="d1878-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d1878-119">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="d1878-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d1878-120">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="d1878-120">Choose who can use this connection.</span></span> <span data-ttu-id="d1878-121">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="d1878-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d1878-122">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d1878-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d1878-123">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="d1878-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d1878-124">Izaberite **Povežite se** da bi se inicijalizovala veza sa uslugom Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="d1878-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="d1878-125">Izaberite **Potvrdite identitet pomoću usluge AdRoll** i obezbedite svoje administratorske akreditive za Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="d1878-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="d1878-126">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d1878-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d1878-127">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="d1878-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d1878-128">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="d1878-128">Configure an export</span></span>

<span data-ttu-id="d1878-129">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="d1878-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d1878-130">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d1878-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d1878-131">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="d1878-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d1878-132">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="d1878-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d1878-133">U polju **Veza za izvoz**, odaberite vezu iz odeljka Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="d1878-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="d1878-134">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="d1878-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d1878-135">Unesite [**ID Constant Contact liste**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="d1878-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="d1878-136">Otvorite listu u usluzi Constant Contact da biste pronašli ID liste u URL adresi.</span><span class="sxs-lookup"><span data-stu-id="d1878-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="d1878-137">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="d1878-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d1878-138">To je potrebno da izvezete segmente u Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="d1878-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="d1878-139">Po želji možete da izvezete Ime i Prezime kao dodatna polja za stvaranje personalizovanih e-poruka.</span><span class="sxs-lookup"><span data-stu-id="d1878-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="d1878-140">Izaberite **Dodaj atribut** za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="d1878-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="d1878-141">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="d1878-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="d1878-142">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="d1878-142">Select **Save**.</span></span>

<span data-ttu-id="d1878-143">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="d1878-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d1878-144">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d1878-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d1878-145">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d1878-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d1878-146">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="d1878-146">Data privacy and compliance</span></span>

<span data-ttu-id="d1878-147">Kada omogućite Dynamics 365 Customer Insights za prenos podataka u Constant Contact, dozvoljavate prenos podataka izvan granica usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="d1878-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d1878-148">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Constant Contact ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="d1878-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d1878-149">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d1878-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d1878-150">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="d1878-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
