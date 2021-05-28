---
title: Izvezite Customer Insights podatke u SendGrid
description: Saznajte kako da konfigurišete vezu i izvezete u SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976933"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="f191c-103">Izvoz segmenata u SendGrid (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="f191c-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="f191c-104">Izvezite segmente objedinjenih profila klijenata u SendGrid liste kontakata i koristite ih za kampanje i marketing u usluzi SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f191c-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f191c-105">Preduslovi za vezu</span><span class="sxs-lookup"><span data-stu-id="f191c-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f191c-106">Imate [SendGrid nalog](https://sendgrid.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="f191c-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f191c-107">Postoje postojeće liste kontakata u usluzi SendGrid i odgovarajući ID-ovi.</span><span class="sxs-lookup"><span data-stu-id="f191c-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="f191c-108">Za više informacija pogledajte [SendGrid – Upravljanje kontaktima](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="f191c-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="f191c-109">[Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="f191c-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f191c-110">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="f191c-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f191c-111">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="f191c-111">Known limitations</span></span>

- <span data-ttu-id="f191c-112">Ukupno do 100.000 profila u SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f191c-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="f191c-113">Izvoz u SendGrid je ograničen na segmente.</span><span class="sxs-lookup"><span data-stu-id="f191c-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="f191c-114">Izvoz do 100.000 profila u SendGrid može da potraje do nekoliko sati.</span><span class="sxs-lookup"><span data-stu-id="f191c-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="f191c-115">Broj profila koje možete da izvezete u SendGrid zavisi od vašeg ugovora sa kompanijom SendGrid i ograničen je njime.</span><span class="sxs-lookup"><span data-stu-id="f191c-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="f191c-116">Podešavanje veze u usluzi SendGrid</span><span class="sxs-lookup"><span data-stu-id="f191c-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="f191c-117">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="f191c-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f191c-118">Izaberite **Dodaj vezu** i birajte **SendGrid** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="f191c-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="f191c-119">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="f191c-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f191c-120">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="f191c-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f191c-121">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="f191c-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f191c-122">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="f191c-122">Choose who can use this connection.</span></span> <span data-ttu-id="f191c-123">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="f191c-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f191c-124">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f191c-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f191c-125">Unesite svoj **SendGrid API ključ** [SendGrid API ključ](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="f191c-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="f191c-126">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="f191c-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f191c-127">Izaberite **Poveži se** za inicijalizaciju veze sa uslugom SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f191c-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="f191c-128">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f191c-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f191c-129">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="f191c-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f191c-130">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="f191c-130">Configure an export</span></span>

<span data-ttu-id="f191c-131">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="f191c-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f191c-132">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f191c-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f191c-133">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="f191c-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f191c-134">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="f191c-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f191c-135">U polju **Veza za izvoz**, odaberite vezu iz odeljka SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f191c-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="f191c-136">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="f191c-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f191c-137">Unesite **[ID SendGrid liste](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="f191c-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="f191c-138">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="f191c-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f191c-139">Ponovite iste korake za druga opcionalna polja kao što su **Ime**, **Prezime**, **Zemlja/Region**, **Država**, **Grad** i **Poštanski broj**.</span><span class="sxs-lookup"><span data-stu-id="f191c-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="f191c-140">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="f191c-140">Select the segments you want to export.</span></span> <span data-ttu-id="f191c-141">Izričito **preporučujemo da ne izvozite ukupno više od 100.000 profila klijenata** u SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f191c-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="f191c-142">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="f191c-142">Select **Save**.</span></span>

<span data-ttu-id="f191c-143">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="f191c-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f191c-144">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f191c-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f191c-145">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f191c-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f191c-146">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="f191c-146">Data privacy and compliance</span></span>

<span data-ttu-id="f191c-147">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u SendGrid, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="f191c-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f191c-148">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da SendGrid ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="f191c-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f191c-149">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f191c-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f191c-150">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="f191c-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]