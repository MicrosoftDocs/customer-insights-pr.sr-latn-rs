---
title: Izvezite Customer Insights podatke u Marketo
description: Saznajte kako da konfigurišete vezu i izvezete u Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059333"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="0dd38-103">Izvoz segmenata u Marketo (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="0dd38-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="0dd38-104">Izvezite segmente objedinjenih profila klijenata da biste generisali kampanje, obezbedili marketing e-poštom i koristili određene grupe klijenata sa uslugom Marketo.</span><span class="sxs-lookup"><span data-stu-id="0dd38-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="0dd38-105">Preduslovi za vezu</span><span class="sxs-lookup"><span data-stu-id="0dd38-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="0dd38-106">Imate [Marketo nalog](https://login.marketo.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="0dd38-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0dd38-107">Postoje postojeće liste u usluzi Marketo i odgovarajući ID-ovi.</span><span class="sxs-lookup"><span data-stu-id="0dd38-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="0dd38-108">Za više informacija pogledajte [Marketo liste](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="0dd38-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="0dd38-109">Imate [konfigurisane segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="0dd38-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="0dd38-110">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="0dd38-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0dd38-111">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="0dd38-111">Known limitations</span></span>

- <span data-ttu-id="0dd38-112">Do 1 milion profila po izvozu u usluzi Marketo.</span><span class="sxs-lookup"><span data-stu-id="0dd38-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="0dd38-113">Izvoz u Marketo je ograničen na segmente.</span><span class="sxs-lookup"><span data-stu-id="0dd38-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="0dd38-114">Izvoz segmenata sa ukupno 1 milion profila može trajati do 3 sata.</span><span class="sxs-lookup"><span data-stu-id="0dd38-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="0dd38-115">Broj profila koje možete da izvezete u Marketo zavisi od i ograničen je vašim ugovorom sa kompanijom Marketo.</span><span class="sxs-lookup"><span data-stu-id="0dd38-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="0dd38-116">Podešavanje veze za Marketo</span><span class="sxs-lookup"><span data-stu-id="0dd38-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="0dd38-117">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="0dd38-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0dd38-118">Izaberite **Dodaj vezu** i birajte **Marketo** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="0dd38-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="0dd38-119">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="0dd38-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0dd38-120">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="0dd38-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0dd38-121">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="0dd38-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0dd38-122">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="0dd38-122">Choose who can use this connection.</span></span> <span data-ttu-id="0dd38-123">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="0dd38-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0dd38-124">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0dd38-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0dd38-125">Unesite **[ID Marketo klijenta, tajnu klijenta i ime hosta REST krajnje tačke](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="0dd38-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="0dd38-126">Ime hosta REST krajnje tačke je samo ime hosta, bez `https://`.</span><span class="sxs-lookup"><span data-stu-id="0dd38-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="0dd38-127">Primer: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="0dd38-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="0dd38-128">Izaberite **Slažem se** da biste potvrdili **Privatnost podataka i usklađenost** i izaberite **Poveži se** radi uspostavljanja veze sa uslugom Marketo.</span><span class="sxs-lookup"><span data-stu-id="0dd38-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="0dd38-129">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0dd38-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0dd38-130">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="0dd38-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0dd38-131">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="0dd38-131">Configure an export</span></span>

<span data-ttu-id="0dd38-132">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="0dd38-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0dd38-133">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0dd38-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0dd38-134">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="0dd38-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0dd38-135">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="0dd38-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0dd38-136">U polju **Veza za izvoz**, odaberite vezu iz odeljka Marketo.</span><span class="sxs-lookup"><span data-stu-id="0dd38-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="0dd38-137">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="0dd38-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0dd38-138">Unesite **[ID Marketo liste](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="0dd38-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="0dd38-139">ID liste je čisto numerička vrednost.</span><span class="sxs-lookup"><span data-stu-id="0dd38-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="0dd38-140">Na primer, ako je vaš ID Marketo liste ST12345A7, uklonite znak pre i posle brojeva i unesite `12345`.</span><span class="sxs-lookup"><span data-stu-id="0dd38-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="0dd38-141">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="0dd38-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="0dd38-142">Po želji možete da izvezete **Ime**, **Prezime**, **Grad**, **Država** i **Zemlja/region** da biste kreirali personalizovanije e-poruke.</span><span class="sxs-lookup"><span data-stu-id="0dd38-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="0dd38-143">Izaberite **Dodaj atribut** za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="0dd38-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="0dd38-144">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="0dd38-144">Select the segments you want to export.</span></span> <span data-ttu-id="0dd38-145">U usluzi Marketo možete ukupno izvesti do 1 milion korisničkih profila.</span><span class="sxs-lookup"><span data-stu-id="0dd38-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="0dd38-146">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="0dd38-146">Select **Save**.</span></span>

<span data-ttu-id="0dd38-147">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="0dd38-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0dd38-148">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0dd38-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0dd38-149">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0dd38-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="0dd38-150">U usluzi Marketo sada možete pronaći segmente u odeljku [Marketo liste](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="0dd38-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0dd38-151">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="0dd38-151">Data privacy and compliance</span></span>

<span data-ttu-id="0dd38-152">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Marketo, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="0dd38-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0dd38-153">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Marketo ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="0dd38-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0dd38-154">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0dd38-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0dd38-155">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="0dd38-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
