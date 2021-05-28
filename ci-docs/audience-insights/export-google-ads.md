---
title: Izvezite Customer Insights podatke u Google oglasima
description: Saznajte kako da konfigurišete vezu i izvezete u Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976335"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="7bdd0-103">Izvoz segmenata u Google Ads (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="7bdd0-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="7bdd0-104">Izvezite segmente objedinjenih profila klijenata u listu korisnika Google oglasa i koristite ih za oglašavanje u Google pretrazi, na Gmail-u, YouTube-u i Google mreži multimedijalnog oglašavanja.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="7bdd0-105">Preduslovi za vezu</span><span class="sxs-lookup"><span data-stu-id="7bdd0-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="7bdd0-106">Imate [nalog Google oglasa](https://ads.google.com/) i odgovarajuće akreditive administratora.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7bdd0-107">Vi imate [odobreni token za Google Ads programera](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="7bdd0-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="7bdd0-108">Ispunjavate zahteve [politike podudaranja klijenata](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="7bdd0-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="7bdd0-109">Ispunjavate zahteve [veličine lista za ponovno oglašavanje](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="7bdd0-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="7bdd0-110">Postoji postojeća publika u Google oglasima i odgovarajući ID-ovi.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="7bdd0-111">Za više informacija pogledajte [Korisnici Google oglasa](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="7bdd0-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="7bdd0-112">Imate [konfigurisane segmente](segments.md)</span><span class="sxs-lookup"><span data-stu-id="7bdd0-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="7bdd0-113">Objedinjeni profili klijenata u izvezenim segmentima sadrže polja koja predstavljaju adresu e-pošte, ime i prezime</span><span class="sxs-lookup"><span data-stu-id="7bdd0-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7bdd0-114">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="7bdd0-114">Known limitations</span></span>

- <span data-ttu-id="7bdd0-115">Do 1 milion profila po izvozu u Google oglasima.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="7bdd0-116">Izvoz u Google oglase je ograničen na segmente.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="7bdd0-117">Izvoz segmenata sa ukupno 1 milion profila može trajati do 5 minuta zbog ograničenja na strani dobavljača.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="7bdd0-118">Podudaranje u Google oglasima može da potraje do 48 sati.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="7bdd0-119">Podešavanje veze sa uslugom Google Ads</span><span class="sxs-lookup"><span data-stu-id="7bdd0-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="7bdd0-120">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7bdd0-121">Izaberite **Dodaj vezu** i birajte **Google Ads** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="7bdd0-122">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7bdd0-123">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7bdd0-124">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7bdd0-125">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-125">Choose who can use this connection.</span></span> <span data-ttu-id="7bdd0-126">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7bdd0-127">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7bdd0-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7bdd0-128">Unesite **[ID klijenta za Google oglase](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="7bdd0-129">Unesite **[token odobrenog programera za Google oglase](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="7bdd0-130">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7bdd0-131">Izaberite **Potvrdite identitet u Google oglasima** i navedite akreditive za Google oglase.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="7bdd0-132">Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7bdd0-133">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="7bdd0-134">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="7bdd0-134">Configure an export</span></span>

<span data-ttu-id="7bdd0-135">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7bdd0-136">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7bdd0-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7bdd0-137">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7bdd0-138">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7bdd0-139">U polju **Veza za izvoz**, odaberite vezu iz odeljka Google Ads.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="7bdd0-140">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7bdd0-141">Unesite **[ID korisnika za Google oglase](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** i izaberite **Povežite se** da biste započeli povezivanje sa Google oglasima.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="7bdd0-142">U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="7bdd0-143">Ponovite iste korake za polja **Ime** i **Prezime**.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="7bdd0-144">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-144">Select the segments you want to export.</span></span> <span data-ttu-id="7bdd0-145">U Google oglasima možete ukupno izvesti do 1 milion korisničkih profila.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="7bdd0-146">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7bdd0-147">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7bdd0-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7bdd0-148">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7bdd0-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7bdd0-149">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="7bdd0-149">Data privacy and compliance</span></span>

<span data-ttu-id="7bdd0-150">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Google oglase, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7bdd0-151">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Google oglasi ispunjavaju sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="7bdd0-152">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7bdd0-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7bdd0-153">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="7bdd0-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
