---
title: Izvoz Customer Insights podataka u Omnisend
description: Saznajte kako da konfigurišete vezu i izvozite u Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124544"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="d9eff-103">Izvoz segmenata u Omnisend (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="d9eff-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="d9eff-104">Izvezite segmente objedinjenih profila klijenata u Omnisend i koristite ih za marketinške aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="d9eff-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d9eff-105">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="d9eff-105">Prerequisites</span></span>

-   <span data-ttu-id="d9eff-106">Imate [Omnisend nalog](https://www.omnisend.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="d9eff-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d9eff-107">[Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="d9eff-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d9eff-108">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="d9eff-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d9eff-109">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="d9eff-109">Known limitations</span></span>

- <span data-ttu-id="d9eff-110">Možete izvesti do 1 milion profila po izvozu u Omnisend, a to može potrajati do 4 sata.</span><span class="sxs-lookup"><span data-stu-id="d9eff-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="d9eff-111">Izvoz u Omnisend ograničen je na segmente.</span><span class="sxs-lookup"><span data-stu-id="d9eff-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="d9eff-112">Broj profila koje možete da izvezete u Omnisend zavisi od vašeg ugovora sa uslugom Omnisend.</span><span class="sxs-lookup"><span data-stu-id="d9eff-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="d9eff-113">Podešavanje veze u usluzi Omnisend</span><span class="sxs-lookup"><span data-stu-id="d9eff-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="d9eff-114">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="d9eff-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d9eff-115">Izaberite **Dodaj vezu** i birajte **Omnisend** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="d9eff-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="d9eff-116">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="d9eff-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d9eff-117">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="d9eff-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d9eff-118">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="d9eff-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d9eff-119">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="d9eff-119">Choose who can use this connection.</span></span> <span data-ttu-id="d9eff-120">Podrazumevano su to samo administratori.</span><span class="sxs-lookup"><span data-stu-id="d9eff-120">By default it's only administrators.</span></span> <span data-ttu-id="d9eff-121">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d9eff-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d9eff-122">Unesite svoj [API ključ za Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="d9eff-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="d9eff-123">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="d9eff-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d9eff-124">Izaberite **Povežite se** da bi se inicijalizovala veza sa uslugom Omnisend.</span><span class="sxs-lookup"><span data-stu-id="d9eff-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="d9eff-125">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d9eff-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d9eff-126">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="d9eff-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d9eff-127">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="d9eff-127">Configure an export</span></span>

<span data-ttu-id="d9eff-128">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="d9eff-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d9eff-129">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d9eff-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d9eff-130">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="d9eff-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d9eff-131">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="d9eff-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d9eff-132">U polju **Veza za izvoz**, odaberite vezu iz odeljka Omnisend.</span><span class="sxs-lookup"><span data-stu-id="d9eff-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="d9eff-133">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="d9eff-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d9eff-134">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="d9eff-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d9eff-135">Potrebno je da izvezete segmente u Omnisend.</span><span class="sxs-lookup"><span data-stu-id="d9eff-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="d9eff-136">Po želji možete da izvezete polja Ime, Prezime, Adresa, Zemlja/region, Država, Grad i Poštanski broj da biste kreirali personalizovanije e-poruke.</span><span class="sxs-lookup"><span data-stu-id="d9eff-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="d9eff-137">Izaberite **Dodaj atribut** za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="d9eff-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="d9eff-138">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="d9eff-138">Select **Save**.</span></span>

<span data-ttu-id="d9eff-139">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="d9eff-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d9eff-140">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d9eff-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d9eff-141">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d9eff-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d9eff-142">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="d9eff-142">Data privacy and compliance</span></span>

<span data-ttu-id="d9eff-143">Kada omogućite Dynamics 365 Customer Insights za prenos podataka u Omnisend, dozvoljavate prenos podataka izvan granica usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="d9eff-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d9eff-144">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Omnisend ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="d9eff-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d9eff-145">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d9eff-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d9eff-146">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="d9eff-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
