---
title: LiveRamp konektor
description: Saznajte kako da izvezete podatke u LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597574"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="b65c9-103">LiveRamp&reg; konektor (pregled)</span><span class="sxs-lookup"><span data-stu-id="b65c9-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="b65c9-104">Aktivirajte svoje podatke u usluzi LiveRamp da biste se povezali sa preko 500 platformi u digitalnim, društvenim i TV ekosistemima.</span><span class="sxs-lookup"><span data-stu-id="b65c9-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="b65c9-105">Radite sa svojim podacima u usluzi LiveRamp da biste ciljali, potisnuli i personalizovali oglasne kampanje.</span><span class="sxs-lookup"><span data-stu-id="b65c9-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b65c9-106">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="b65c9-106">Prerequisites</span></span>

- <span data-ttu-id="b65c9-107">Za upotrebu ovog konektora potrebna vam je pretplata na LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b65c9-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="b65c9-108">Da biste dobili pretplatu, [kontaktirajte LiveRamp](https://liveramp.com/contact/) direktno.</span><span class="sxs-lookup"><span data-stu-id="b65c9-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="b65c9-109">[Saznajte više o usluzi LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="b65c9-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="b65c9-110">Povezivanje na LiveRamp</span><span class="sxs-lookup"><span data-stu-id="b65c9-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="b65c9-111">U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="b65c9-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b65c9-112">Na pločici **LiveRamp** izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="b65c9-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="b65c9-113">Dajte odredištu prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="b65c9-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b65c9-114">Obezbedite **Korisničko ime** i **Lozinku** za svoj LiveRamp Secure FTP (SFTP) nalog.</span><span class="sxs-lookup"><span data-stu-id="b65c9-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="b65c9-115">Ovi akreditivi mogu biti različiti od vaših akreditiva za LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="b65c9-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="b65c9-116">Izaberite **Verifikuj** da testirate vezu sa uslugom LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b65c9-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="b65c9-117">Nakon uspešne verifikacije, dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="b65c9-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="b65c9-118">Izaberite **Sledeće** da podesite LiveRamp konektor.</span><span class="sxs-lookup"><span data-stu-id="b65c9-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b65c9-119">Konfigurisanje konektora</span><span class="sxs-lookup"><span data-stu-id="b65c9-119">Configure the connector</span></span>

1. <span data-ttu-id="b65c9-120">U polju **Odaberite svoj identifikator ključa**, izaberite **E-pošta**, **Ime i adresa** ili **Telefon** za slanje u LiveRamp radi rešavanja identiteta.</span><span class="sxs-lookup"><span data-stu-id="b65c9-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="b65c9-121">Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za izabrani identifikator ključa.</span><span class="sxs-lookup"><span data-stu-id="b65c9-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="b65c9-122">Izaberite **Dodaj atribut** da biste mapirali dodatne atribute koje treba poslati u LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b65c9-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="b65c9-123">Ako pošaljete više ključnih atributa identifikatora u LiveRamp, verovatno će dobiti višu stopu podudaranja.</span><span class="sxs-lookup"><span data-stu-id="b65c9-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="b65c9-124">Izaberite segmente koje želite da izvezete u LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b65c9-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="b65c9-125">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="b65c9-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b65c9-126">![LiveRamp konektor sa mapiranjem atributa](media/export-liveramp-segments.png "LiveRamp konektor sa mapiranjem atributa")</span><span class="sxs-lookup"><span data-stu-id="b65c9-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b65c9-127">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="b65c9-127">Export the data</span></span>

<span data-ttu-id="b65c9-128">Izvoz će početi uskoro ako su ispunjeni svi preduslovi za izvoz.</span><span class="sxs-lookup"><span data-stu-id="b65c9-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="b65c9-129">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b65c9-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="b65c9-130">Nakon što je izvoz uspešno završen, možete se prijaviti u LiveRamp Onboarding da biste aktivirali i distribuirali svoje podatke.</span><span class="sxs-lookup"><span data-stu-id="b65c9-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b65c9-131">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="b65c9-131">Data privacy and compliance</span></span>

<span data-ttu-id="b65c9-132">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Liveramp, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="b65c9-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b65c9-133">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Liveramp ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="b65c9-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b65c9-134">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b65c9-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b65c9-135">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="b65c9-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]