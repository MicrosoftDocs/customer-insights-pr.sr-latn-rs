---
title: LiveRamp konektor
description: Saznajte kako da izvezete podatke u LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667201"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="0e534-103">LiveRamp&reg; konektor (pregled)</span><span class="sxs-lookup"><span data-stu-id="0e534-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="0e534-104">Aktivirajte svoje podatke u usluzi LiveRamp da biste se povezali sa preko 500 platformi u digitalnim, društvenim i TV ekosistemima.</span><span class="sxs-lookup"><span data-stu-id="0e534-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="0e534-105">Radite sa svojim podacima u usluzi LiveRamp da biste ciljali, potisnuli i personalizovali oglasne kampanje.</span><span class="sxs-lookup"><span data-stu-id="0e534-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0e534-106">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="0e534-106">Prerequisites</span></span>

- <span data-ttu-id="0e534-107">Za upotrebu ovog konektora potrebna vam je pretplata na LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="0e534-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="0e534-108">Da biste dobili pretplatu, [kontaktirajte LiveRamp](https://liveramp.com/contact/) direktno.</span><span class="sxs-lookup"><span data-stu-id="0e534-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="0e534-109">[Saznajte više o usluzi LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="0e534-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="0e534-110">Povezivanje na LiveRamp</span><span class="sxs-lookup"><span data-stu-id="0e534-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="0e534-111">U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="0e534-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0e534-112">Na pločici **LiveRamp** izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="0e534-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="0e534-113">Dajte odredištu prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="0e534-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0e534-114">Obezbedite **Korisničko ime** i **Lozinku** za svoj LiveRamp Secure FTP (SFTP) nalog.</span><span class="sxs-lookup"><span data-stu-id="0e534-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="0e534-115">Ovi akreditivi mogu biti različiti od vaših akreditiva za LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="0e534-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="0e534-116">Izaberite **Verifikuj** da testirate vezu sa uslugom LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="0e534-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="0e534-117">Nakon uspešne verifikacije, dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="0e534-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="0e534-118">Izaberite **Sledeće** da podesite LiveRamp konektor.</span><span class="sxs-lookup"><span data-stu-id="0e534-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="0e534-119">Konfigurisanje konektora</span><span class="sxs-lookup"><span data-stu-id="0e534-119">Configure the connector</span></span>

1. <span data-ttu-id="0e534-120">U polju **Odaberite svoj identifikator ključa**, izaberite **E-pošta**, **Ime i adresa** ili **Telefon** za slanje u LiveRamp radi rešavanja identiteta.</span><span class="sxs-lookup"><span data-stu-id="0e534-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="0e534-121">Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za izabrani identifikator ključa.</span><span class="sxs-lookup"><span data-stu-id="0e534-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="0e534-122">Izaberite **Dodaj atribut** da biste mapirali dodatne atribute koje treba poslati u LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="0e534-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="0e534-123">Ako pošaljete više ključnih atributa identifikatora u LiveRamp, verovatno će dobiti višu stopu podudaranja.</span><span class="sxs-lookup"><span data-stu-id="0e534-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="0e534-124">Izaberite segmente koje želite da izvezete u LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="0e534-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="0e534-125">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="0e534-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e534-126">![LiveRamp konektor sa mapiranjem atributa](media/export-liveramp-segments.png "LiveRamp konektor sa mapiranjem atributa")</span><span class="sxs-lookup"><span data-stu-id="0e534-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0e534-127">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="0e534-127">Export the data</span></span>

<span data-ttu-id="0e534-128">Izvoz će početi uskoro ako su ispunjeni svi preduslovi za izvoz.</span><span class="sxs-lookup"><span data-stu-id="0e534-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="0e534-129">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0e534-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="0e534-130">Nakon što je izvoz uspešno završen, možete se prijaviti u LiveRamp Onboarding da biste aktivirali i distribuirali svoje podatke.</span><span class="sxs-lookup"><span data-stu-id="0e534-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0e534-131">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="0e534-131">Data privacy and compliance</span></span>

<span data-ttu-id="0e534-132">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Liveramp, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="0e534-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0e534-133">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Liveramp ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="0e534-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0e534-134">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0e534-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0e534-135">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="0e534-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>