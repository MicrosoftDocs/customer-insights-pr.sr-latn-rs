---
title: Izvezite Customer Insights podatke u DotDigital
description: Saznajte kako da konfigurišete vezu i izvezete u DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976863"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="ba954-103">Izvoz listi segmenata u DotDigital (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="ba954-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="ba954-104">Izvezite segmente objedinjenih profila kupaca u DotDigital adresare i koristite ih za kampanje, marketing putem e-pošte i za izgradnju segmenata kupaca pomoću usluge DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ba954-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ba954-105">Preduslovi za vezu</span><span class="sxs-lookup"><span data-stu-id="ba954-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="ba954-106">Imate [DotDigital nalog](https://dotdigital.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="ba954-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ba954-107">Postoji postojeća publika u adresarima u usluzi DotDigital i odgovarajući ID-ovi.</span><span class="sxs-lookup"><span data-stu-id="ba954-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="ba954-108">ID se može naći u URL-u kada odaberete i otvorite adresar.</span><span class="sxs-lookup"><span data-stu-id="ba954-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="ba954-109">Za više informacija pogledajte [adresare za DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="ba954-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="ba954-110">[Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="ba954-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ba954-111">Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.</span><span class="sxs-lookup"><span data-stu-id="ba954-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ba954-112">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="ba954-112">Known limitations</span></span>

- <span data-ttu-id="ba954-113">Do 1 milion profila po izvozu u usluzi DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ba954-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="ba954-114">Izvoz u DotDigital je ograničen na segmente.</span><span class="sxs-lookup"><span data-stu-id="ba954-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="ba954-115">Izvoz segmenata sa ukupno 1 milion profila može trajati do 3 sata zbog ograničenja na strani dobavljača.</span><span class="sxs-lookup"><span data-stu-id="ba954-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="ba954-116">Broj profila koje možete da izvezete u DotDigital zavisi od i ograničen je vašim ugovorom sa kompanijom DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ba954-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="ba954-117">Podešavanje veze u usluzi DotDigital</span><span class="sxs-lookup"><span data-stu-id="ba954-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="ba954-118">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="ba954-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ba954-119">Izaberite **Dodaj vezu** i birajte **DotDigital** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="ba954-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="ba954-120">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="ba954-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ba954-121">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="ba954-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ba954-122">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="ba954-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ba954-123">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="ba954-123">Choose who can use this connection.</span></span> <span data-ttu-id="ba954-124">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="ba954-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ba954-125">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ba954-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ba954-126">Unesite svoje **korisničko ime i lozinku za DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="ba954-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="ba954-127">Unesite **[ID DotDigital adresara](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="ba954-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="ba954-128">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="ba954-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ba954-129">Izaberite **Poveži se** za inicijalizaciju veze sa uslugom DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ba954-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="ba954-130">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ba954-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ba954-131">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="ba954-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="ba954-132">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="ba954-132">Configure an export</span></span>

<span data-ttu-id="ba954-133">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="ba954-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ba954-134">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ba954-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ba954-135">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="ba954-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ba954-136">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="ba954-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ba954-137">U polju **Veza za izvoz**, odaberite vezu iz odeljka DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ba954-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="ba954-138">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="ba954-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="ba954-139">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="ba954-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ba954-140">Ponovite iste korake za druga opcionalna polja kao što su **Ime**, **Prezime**, **Puno ime**, **Pol** i **Poštanski broj**.</span><span class="sxs-lookup"><span data-stu-id="ba954-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="ba954-141">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="ba954-141">Select the segments you want to export.</span></span> <span data-ttu-id="ba954-142">U usluzi DotDigital možete ukupno izvesti do 1 milion korisničkih profila.</span><span class="sxs-lookup"><span data-stu-id="ba954-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="ba954-143">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="ba954-143">Select **Save**.</span></span>

<span data-ttu-id="ba954-144">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="ba954-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ba954-145">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ba954-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ba954-146">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ba954-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="ba954-147">U usluzi DotDigital sada možete da pronađete svoje segmente u [DotDigital adresarima](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="ba954-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ba954-148">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="ba954-148">Data privacy and compliance</span></span>

<span data-ttu-id="ba954-149">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u DotDigital, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="ba954-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ba954-150">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da DotDigital ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="ba954-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ba954-151">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ba954-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ba954-152">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="ba954-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
