---
title: Izvezite Customer Insights podatke u menadžer Facebook oglasa
description: Naučite kako da konfigurišete vezu u okviru Facebook menadžera oglasa.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643700"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="9ce30-103">Konektor za Facebook menadžer oglasa (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="9ce30-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="9ce30-104">Izvezite segmente objedinjenih korisničkih profila u Facebook menadžer oglasa za kreiranje kampanja na Facebook i Instagram.</span><span class="sxs-lookup"><span data-stu-id="9ce30-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9ce30-105">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="9ce30-105">Prerequisites</span></span>

- <span data-ttu-id="9ce30-106">Morate da imate [**Facebook** nalog za oglašavanje](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) koji uključuje [**Facebook poslovni nalog**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="9ce30-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="9ce30-107">Morate da budete administrator na [**Facebook nalogu za oglašavanje**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="9ce30-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="9ce30-108">Povezivanje sa Facebook menadžerom oglasa</span><span class="sxs-lookup"><span data-stu-id="9ce30-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="9ce30-109">Idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="9ce30-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9ce30-110">Pod **Facebook menadžer oglasa**, izaberite **Postavi**.</span><span class="sxs-lookup"><span data-stu-id="9ce30-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="9ce30-111">Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="9ce30-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9ce30-112">Izaberite **Nastavi sa Facebook** da se prijavite na svoj Facebook nalog za oglašavanje.</span><span class="sxs-lookup"><span data-stu-id="9ce30-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="9ce30-113">Dajte dozvolu **ads_management** nakon potvrde identiteta sa uslugom Facebook.</span><span class="sxs-lookup"><span data-stu-id="9ce30-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="9ce30-114">Izaberite **Facebook nalog za oglašavanje** sa kojim želite da radite.</span><span class="sxs-lookup"><span data-stu-id="9ce30-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="9ce30-115">Izaberite **Postojeća prilagođena ciljna grupa** sa padajuće liste ili kreirajte **Novu prilagođenu ciljnu grupu**.</span><span class="sxs-lookup"><span data-stu-id="9ce30-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="9ce30-116">Za više informacija pogledajte [**Publika u Facebook menadžeru oglasa**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="9ce30-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="9ce30-117">Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.</span><span class="sxs-lookup"><span data-stu-id="9ce30-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9ce30-118">Izaberite **Sledeće** da biste konfigurisali izvoz.</span><span class="sxs-lookup"><span data-stu-id="9ce30-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="9ce30-119">Konfigurisanje konektora</span><span class="sxs-lookup"><span data-stu-id="9ce30-119">Configure the connector</span></span>

1. <span data-ttu-id="9ce30-120">U **Izaberite polje identifikatora ključa**, izaberite **E-pošta**, **Ime i adresa** ili **Telefon** koji biste poslali u Facebook menadžer oglasa.</span><span class="sxs-lookup"><span data-stu-id="9ce30-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="9ce30-121">Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za izabrani identifikator ključa.</span><span class="sxs-lookup"><span data-stu-id="9ce30-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="9ce30-122">[SAVET] Najbolje šanse za podudaranje nastaju ako odaberete **E-pošta** kao ključni identifikator.</span><span class="sxs-lookup"><span data-stu-id="9ce30-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="9ce30-123">Dodavanje dodatnih identifikatora može poboljšati podudaranje.</span><span class="sxs-lookup"><span data-stu-id="9ce30-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="9ce30-124">Izaberite **Dodaj atribut** da biste mapirali dodatne atribute koje treba poslati u Facebook menadžer oglasa.</span><span class="sxs-lookup"><span data-stu-id="9ce30-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="9ce30-125">Atributi iz Facebook menadžera oglasa se preslikavaju na sledeća imena prilagođena korisniku: **IME** = **Ime**, **PR** = **Prezime**, **PS** = **Prvo slovo imena**, **TEL** = **Telefon**, **POL** = **Pol**, **ROĐ** = **Datum rođenja**, **DRŽ** = **Država**, **GR** = **Grad**, **P. BR.** = **Poštanski broj**, **ZMLJ** = **Zemlja**</span><span class="sxs-lookup"><span data-stu-id="9ce30-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="9ce30-126">Izaberite segmente koje želite da izvezete.</span><span class="sxs-lookup"><span data-stu-id="9ce30-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="9ce30-127">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="9ce30-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9ce30-128">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="9ce30-128">Export the data</span></span>

<span data-ttu-id="9ce30-129">Možete da [izvezete podatke na zahtev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9ce30-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9ce30-130">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9ce30-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9ce30-131">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="9ce30-131">Data privacy and compliance</span></span>

<span data-ttu-id="9ce30-132">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u menadžer Facebook oglasa, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="9ce30-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9ce30-133">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Facebook oglasi ispunjavaju sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="9ce30-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="9ce30-134">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9ce30-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9ce30-135">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="9ce30-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
