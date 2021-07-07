---
title: Izvoz Customer Insights podataka u Sendinblue
description: Saznajte kako da konfigurišete vezu i izvezete je u uslugu Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314667"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="43e53-103">Izvoz segmenata u Sendinblue (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="43e53-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="43e53-104">Izvezite segmente ujednačenih profila klijenata da biste generisali kampanje, obezbedili marketing e-poštom i koristili određene grupe klijenata sa uslugom Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="43e53-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="43e53-105">Preduslovi za vezu</span><span class="sxs-lookup"><span data-stu-id="43e53-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="43e53-106">Imate [Sendinblue nalog](https://www.sendinblue.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="43e53-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="43e53-107">Postoje postojeće liste u usluzi Sendinblue i odgovarajući ID-ovi.</span><span class="sxs-lookup"><span data-stu-id="43e53-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="43e53-108">Imate [konfigurisane segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="43e53-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="43e53-109">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="43e53-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="43e53-110">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="43e53-110">Known limitations</span></span>

- <span data-ttu-id="43e53-111">Do 1 milion profila po izvozu u Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="43e53-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="43e53-112">Izvoz u Sendinblue je ograničen na segmente.</span><span class="sxs-lookup"><span data-stu-id="43e53-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="43e53-113">Izvoz segmenata sa ukupno milion profila može trajati do 90 minuta.</span><span class="sxs-lookup"><span data-stu-id="43e53-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="43e53-114">Broj profila koje možete da izvezete u Sendinblue zavisi od vašeg ugovora sa uslugom Sendinblue i ograničen je njime.</span><span class="sxs-lookup"><span data-stu-id="43e53-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="43e53-115">Podešavanje veze sa uslugom Sendinblue</span><span class="sxs-lookup"><span data-stu-id="43e53-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="43e53-116">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="43e53-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="43e53-117">Izaberite **Dodaj vezu** i birajte **Sendinblue** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="43e53-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="43e53-118">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="43e53-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="43e53-119">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="43e53-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="43e53-120">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="43e53-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="43e53-121">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="43e53-121">Choose who can use this connection.</span></span> <span data-ttu-id="43e53-122">Podrazumevano su to samo administratori.</span><span class="sxs-lookup"><span data-stu-id="43e53-122">By default it's only administrators.</span></span> <span data-ttu-id="43e53-123">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="43e53-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="43e53-124">Unesite svoj **[Sendinblue API ključ](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="43e53-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="43e53-125">Izaberite **Slažem se** da biste potvrdili **Privatnost i usklađenost podataka** i izaberite **Poveži se** za inicijalizaciju veze sa uslugom Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="43e53-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="43e53-126">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="43e53-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="43e53-127">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="43e53-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="43e53-128">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="43e53-128">Configure an export</span></span>

<span data-ttu-id="43e53-129">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="43e53-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="43e53-130">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="43e53-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="43e53-131">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="43e53-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="43e53-132">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="43e53-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="43e53-133">U polju **Veza za izvoz**, izaberite vezu iz odeljka Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="43e53-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="43e53-134">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="43e53-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="43e53-135">Unesite **ID Sendinblue liste**</span><span class="sxs-lookup"><span data-stu-id="43e53-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="43e53-136">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="43e53-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="43e53-137">Opcionalno, možete da izvezete polja **Ime**, **Prezime** i **Telefon** da biste kreirali personalizovanije adrese e-pošte.</span><span class="sxs-lookup"><span data-stu-id="43e53-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="43e53-138">Izaberite **Dodaj atribut** za mapiranje ovih polja.</span><span class="sxs-lookup"><span data-stu-id="43e53-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="43e53-139">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="43e53-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="43e53-140">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="43e53-140">Select **Save**.</span></span>

<span data-ttu-id="43e53-141">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="43e53-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="43e53-142">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="43e53-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="43e53-143">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="43e53-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="43e53-144">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="43e53-144">Data privacy and compliance</span></span>

<span data-ttu-id="43e53-145">Kada omogućite Dynamics 365 Customer Insights za prenos podataka u Sendinblue, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="43e53-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="43e53-146">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Sendinblue ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="43e53-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="43e53-147">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="43e53-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="43e53-148">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="43e53-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
