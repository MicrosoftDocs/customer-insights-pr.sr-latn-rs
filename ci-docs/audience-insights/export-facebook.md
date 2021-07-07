---
title: Izvezite Customer Insights podatke u menadžer Facebook oglasa
description: Saznajte kako da konfigurišete vezu i izvezete u Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e20c7b7fd3989d7621cb7765f38b85c8ab4adfcb
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305127"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="23192-103">Izvoz segmenata u Facebook Ads Manager (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="23192-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="23192-104">Izvezite segmente objedinjenih korisničkih profila u Facebook menadžer oglasa za kreiranje kampanja na Facebook i Instagram.</span><span class="sxs-lookup"><span data-stu-id="23192-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="23192-105">Preduslovi za vezu</span><span class="sxs-lookup"><span data-stu-id="23192-105">Prerequisites for connection</span></span>

- <span data-ttu-id="23192-106">Potrebno je da imate [**Facebook Ads nalog**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) koji uključuje [**Facebook poslovni nalog**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="23192-106">You need to have a [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="23192-107">Morate biti administrator [**Facebook Ads naloga**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="23192-107">You need to be an administrator on the [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="23192-108">Poznata ograničenja</span><span class="sxs-lookup"><span data-stu-id="23192-108">Known limitations</span></span>

- <span data-ttu-id="23192-109">Do 10 miliona profila klijenata po izvozu u Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="23192-109">Up to 10 million customer profiles per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="23192-110">Izvoz u Facebook Ads Manager je ograničen na segmente.</span><span class="sxs-lookup"><span data-stu-id="23192-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="23192-111">Napravite ili ažurirajte prilagođenu ciljnu grupu u Facebook samo tipa *lista klijenata*.</span><span class="sxs-lookup"><span data-stu-id="23192-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="23192-112">Izvoz segmenata sa ukupno 10 miliona profila može potrajati do 90 minuta.</span><span class="sxs-lookup"><span data-stu-id="23192-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="23192-113">Podešavanje veze sa uslugom Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="23192-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="23192-114">Da bi korisnici mogli da naprave izvoz, administrator mora da konfiguriše vezu sa uslugom i dozvoli saradnicima da koriste vezu.</span><span class="sxs-lookup"><span data-stu-id="23192-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="23192-115">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="23192-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="23192-116">Izaberite **Dodaj vezu** i birajte **Facebook Ads Manager** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="23192-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="23192-117">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="23192-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="23192-118">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="23192-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="23192-119">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="23192-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="23192-120">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="23192-120">Choose who can use this connection.</span></span> <span data-ttu-id="23192-121">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="23192-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="23192-122">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="23192-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="23192-123">Potvrdite verodostojnost pomoću usluge Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="23192-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="23192-124">Izaberite **Nastavi sa Facebook-om** da biste se prijavili na svoj Facebook Ads nalog.</span><span class="sxs-lookup"><span data-stu-id="23192-124">Select **Continue with Facebook** to sign in to your Facebook Ads account.</span></span>

   1. <span data-ttu-id="23192-125">Dajte dozvolu **ads_management** nakon potvrde identiteta sa uslugom Facebook.</span><span class="sxs-lookup"><span data-stu-id="23192-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="23192-126">Izaberite **Facebook nalog za oglašavanje** sa kojim želite da radite.</span><span class="sxs-lookup"><span data-stu-id="23192-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="23192-127">Izaberite **Postojeća prilagođena ciljna grupa** sa padajuće liste ili kreirajte **novu prilagođenu ciljnu grupu**.</span><span class="sxs-lookup"><span data-stu-id="23192-127">Select an **Existing custom audience** from the dropdown list or create a **New custom audience**.</span></span> <span data-ttu-id="23192-128">Za više informacija pogledajte [**Publika u Facebook menadžeru oglasa**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="23192-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="23192-129">Ovim izvozom u usluzi Facebook možete samo da kreirate ili ažurirate prilagođenu ciljnu grupu tipa *lista klijenata*.</span><span class="sxs-lookup"><span data-stu-id="23192-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="23192-130">U nekim slučajevima, na padajućoj listi vidite prilagođenu ciljnu grupu različitih vrsta.</span><span class="sxs-lookup"><span data-stu-id="23192-130">In some cases, you see custom audiences of different types in the dropdown list.</span></span> <span data-ttu-id="23192-131">Izbor nekog drugog tipa umesto *liste klijenata* dovešće do neuspelog izvoza.</span><span class="sxs-lookup"><span data-stu-id="23192-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="23192-132">Pregledajte **Privatnost podataka i usklađenost** i izaberite **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="23192-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="23192-133">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="23192-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="23192-134">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="23192-134">Configure an export</span></span>

<span data-ttu-id="23192-135">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="23192-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="23192-136">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="23192-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="23192-137">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="23192-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="23192-138">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="23192-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="23192-139">U polju **Veza za izvoz** odaberite vezu iz odeljka **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="23192-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="23192-140">Ako ne vidite naziv ovog odeljka, tada vam nisu dostupne veze ovog tipa.</span><span class="sxs-lookup"><span data-stu-id="23192-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="23192-141">U **Izaberite polje identifikatora ključa**, izaberite **E-pošta**, **Ime i adresa** ili **Telefon** koji biste poslali u Facebook menadžer oglasa.</span><span class="sxs-lookup"><span data-stu-id="23192-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="23192-142">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="23192-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="23192-143">Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za izabrani identifikator ključa.</span><span class="sxs-lookup"><span data-stu-id="23192-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > [!TIP]
   > <span data-ttu-id="23192-144">Najbolje šanse za podudaranje nastaju ako odaberete opciju **E-pošta** kao ključni identifikator.</span><span class="sxs-lookup"><span data-stu-id="23192-144">The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="23192-145">Dodavanje dodatnih identifikatora može poboljšati podudaranje.</span><span class="sxs-lookup"><span data-stu-id="23192-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="23192-146">Izaberite **Dodaj atribut** da biste mapirali više atributa za slanje u Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="23192-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="23192-147">Atributi iz usluge Facebook Ads Manager se preslikavaju na sledeća imena prilagođena korisniku: **FN** = **Ime**, **LN** = **Prezime**, **FI** = **Prvo slovo imena**, **PHONE** = **Telefon**, **GEN** = **Pol**, **DOB** = **Datum rođenja**, **ST** = **Država**, **CT** = **Grad**, **ZIP** = **Poštanski broj**, **COUNTRY** = **Zemlja**</span><span class="sxs-lookup"><span data-stu-id="23192-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / ZIP Code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="23192-148">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="23192-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="23192-149">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="23192-149">Select **Save**.</span></span>

<span data-ttu-id="23192-150">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="23192-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="23192-151">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="23192-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="23192-152">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="23192-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="23192-153">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="23192-153">Data privacy and compliance</span></span>

<span data-ttu-id="23192-154">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u menadžer Facebook oglasa, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="23192-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="23192-155">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Facebook oglasi ispunjavaju sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="23192-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="23192-156">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="23192-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="23192-157">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="23192-157">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
