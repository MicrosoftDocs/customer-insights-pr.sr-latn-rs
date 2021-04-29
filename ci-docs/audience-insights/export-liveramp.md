---
title: LiveRamp konektor
description: Saznajte kako da konfigurišete vezu i izvezete u LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760344"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="54556-103">Izvoz segmenata u LiveRamp&reg; (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="54556-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="54556-104">Aktivirajte svoje podatke u usluzi LiveRamp da biste se povezali sa preko 500 platformi na digitalnim, društvenim i televizijskim sistemima.</span><span class="sxs-lookup"><span data-stu-id="54556-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="54556-105">Radite sa svojim podacima u usluzi LiveRamp da biste ciljali, potisnuli i personalizovali oglasne kampanje.</span><span class="sxs-lookup"><span data-stu-id="54556-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="54556-106">Preduslovi za vezu</span><span class="sxs-lookup"><span data-stu-id="54556-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="54556-107">Za upotrebu ovog konektora potrebna vam je pretplata na LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="54556-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="54556-108">Da biste dobili pretplatu, [kontaktirajte LiveRamp](https://liveramp.com/contact/) direktno.</span><span class="sxs-lookup"><span data-stu-id="54556-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="54556-109">[Saznajte više o usluzi LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="54556-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="54556-110">Podešavanje veze u usluzi LiveRamp</span><span class="sxs-lookup"><span data-stu-id="54556-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="54556-111">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="54556-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="54556-112">Izaberite **Dodaj vezu** i birajte **LiveRamp** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="54556-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="54556-113">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="54556-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="54556-114">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="54556-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="54556-115">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="54556-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="54556-116">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="54556-116">Choose who can use this connection.</span></span> <span data-ttu-id="54556-117">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="54556-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="54556-118">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="54556-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="54556-119">Obezbedite **Korisničko ime** i **Lozinku** za svoj LiveRamp Secure FTP (SFTP) nalog.</span><span class="sxs-lookup"><span data-stu-id="54556-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="54556-120">Ovi akreditivi mogu biti različiti od vaših akreditiva za LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="54556-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="54556-121">Izaberite **Verifikuj** da testirate vezu sa uslugom LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="54556-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="54556-122">Nakon uspešne verifikacije, dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="54556-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="54556-123">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="54556-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="54556-124">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="54556-124">Configure an export</span></span>

<span data-ttu-id="54556-125">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="54556-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="54556-126">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="54556-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="54556-127">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="54556-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="54556-128">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="54556-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="54556-129">U polju **Veza za izvoz**, odaberite vezu iz odeljka LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="54556-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="54556-130">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="54556-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="54556-131">U polju **Odaberite svoj identifikator ključa**, izaberite **E-pošta**, **Ime i adresa** ili **Telefon** za slanje u LiveRamp radi rešavanja identiteta.</span><span class="sxs-lookup"><span data-stu-id="54556-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="54556-132">![LiveRamp konektor sa mapiranjem atributa](media/export-liveramp-segments.png "LiveRamp konektor sa mapiranjem atributa")</span><span class="sxs-lookup"><span data-stu-id="54556-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="54556-133">Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za izabrani identifikator ključa.</span><span class="sxs-lookup"><span data-stu-id="54556-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="54556-134">Izaberite **Dodaj atribut** da biste mapirali više atributa za slanje u LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="54556-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="54556-135">Ako pošaljete više ključnih atributa identifikatora u LiveRamp, verovatno će dobiti višu stopu podudaranja.</span><span class="sxs-lookup"><span data-stu-id="54556-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="54556-136">Izaberite segmente koje želite da izvezete u LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="54556-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="54556-137">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="54556-137">Select **Save**.</span></span>

<span data-ttu-id="54556-138">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="54556-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="54556-139">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="54556-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="54556-140">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="54556-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="54556-141">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="54556-141">Data privacy and compliance</span></span>

<span data-ttu-id="54556-142">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Liveramp, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="54556-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="54556-143">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Liveramp ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="54556-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="54556-144">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="54556-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="54556-145">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="54556-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
