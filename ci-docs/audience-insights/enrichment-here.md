---
title: Obogaćivanje pomoću obogaćivanja treće strane HERE Technologies
description: Opšte informacije o HERE Technologies obogaćivanju treće strane.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269531"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="690e7-103">Obogaćivanje profila klijenata uz HERE Technologies (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="690e7-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="690e7-104">verzija za pregled je kompanija za platformu lokacije koja pruža podatke i usluge usmerene na lokaciju.</span><span class="sxs-lookup"><span data-stu-id="690e7-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="690e7-105">Pomoću usluga obogaćivanja podataka kompanije HERE Technologies možete da izgradite preciznije razumevanje lokacije svojih klijenata pomoću normalizacije adresa, izdvajanja geografske širine i dužine i još mnogo toga.</span><span class="sxs-lookup"><span data-stu-id="690e7-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="690e7-106">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="690e7-106">Prerequisites</span></span>

<span data-ttu-id="690e7-107">Da biste konfigurisali verzija za pregled obogaćivanja, moraju biti ispunjeni sledeći preduslovi:</span><span class="sxs-lookup"><span data-stu-id="690e7-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="690e7-108">Morate imati aktivnu pretplatu za HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="690e7-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="690e7-109">Da biste dobili pretplatu, možete [da se registrujete ovde](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ili [kontaktirajte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direktno.</span><span class="sxs-lookup"><span data-stu-id="690e7-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="690e7-110">Saznajte više o HERE Technologies obogaćivanju lokacije.</span><span class="sxs-lookup"><span data-stu-id="690e7-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="690e7-111">Imate HERE Technologies API ključ.</span><span class="sxs-lookup"><span data-stu-id="690e7-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="690e7-112">Imate [administratorske](permissions.md#administrator) dozvole.</span><span class="sxs-lookup"><span data-stu-id="690e7-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="690e7-113">Konfigurisanje</span><span class="sxs-lookup"><span data-stu-id="690e7-113">Configuration</span></span>

1. <span data-ttu-id="690e7-114">Idite na **Podaci** > **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="690e7-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="690e7-115">Na HERE Technologies pločici izaberite **Obogati moje podatke**.</span><span class="sxs-lookup"><span data-stu-id="690e7-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="690e7-116">![HERE Technologies pločica](media/HERE-tile.png "HERE Technologies pločica")</span><span class="sxs-lookup"><span data-stu-id="690e7-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="690e7-117">Unesite aktivan **HERE Technologies API ključ**.</span><span class="sxs-lookup"><span data-stu-id="690e7-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="690e7-118">Pregledajte i dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="690e7-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="690e7-119">Potvrdite oba ulaza izborom opcije **Povežite se na HERE**.</span><span class="sxs-lookup"><span data-stu-id="690e7-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="690e7-120">Izaberite **Dodaj podatke**, pa odaberite **Skup podataka o klijentima** koji želite da obogatite podacima o lokaciji kompanije HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="690e7-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="690e7-121">Možete izabrati entitet **Klijent** da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="690e7-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Snimak ekrana prilikom odabira skupa podataka o klijentima.":::

1. <span data-ttu-id="690e7-123">Odaberite da li želite da mapirate polja sa primarnom i/ili sekundarnom adresom.</span><span class="sxs-lookup"><span data-stu-id="690e7-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="690e7-124">Možete da navedete mapiranje polja za obe adrese (na primer, kućnu i poslovnu adresu) i zasebno obogatiti profile za obe adrese.</span><span class="sxs-lookup"><span data-stu-id="690e7-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="690e7-125">Izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="690e7-125">Select **Next**.</span></span>

1. <span data-ttu-id="690e7-126">Definišite koja polja iz vaših objedinjenih profila treba koristiti za podudaranje podataka o lokaciji od kompanije HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="690e7-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="690e7-127">Polja **Ulica 1** i **Poštanski broj** su obavezna za odabranu primarnu i/ili sekundarnu adresu.</span><span class="sxs-lookup"><span data-stu-id="690e7-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="690e7-128">Za veću preciznost podudaranja može se dodati više polja.</span><span class="sxs-lookup"><span data-stu-id="690e7-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="690e7-129">![Stranica za konfiguraciju HERE Technologies obogaćivanja](media/enrichment-HERE-configuration.png "Stranica za konfiguraciju HERE Technologies obogaćivanja")</span><span class="sxs-lookup"><span data-stu-id="690e7-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="690e7-130">Izaberite **Primeni** da dovršite mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="690e7-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="690e7-131">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="690e7-131">Enrichment results</span></span>

<span data-ttu-id="690e7-132">Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake.</span><span class="sxs-lookup"><span data-stu-id="690e7-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="690e7-133">Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="690e7-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="690e7-134">Vreme obrade zavisiće od veličine podataka o klijentima i vremena odziva API-ja kompanije HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="690e7-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="690e7-135">Nakon završetka procesa obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod opcijom **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="690e7-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="690e7-136">Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="690e7-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="690e7-137">Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.</span><span class="sxs-lookup"><span data-stu-id="690e7-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="690e7-138">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="690e7-138">Next steps</span></span>

<span data-ttu-id="690e7-139">Nadogradite na obogaćenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="690e7-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="690e7-140">Kreirajte [segmente](segments.md), [mere](measures.md), pa čak i [izvezite podatke](export-destinations.md) da biste pružili personalizovana iskustva svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="690e7-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="690e7-141">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="690e7-141">Data privacy and compliance</span></span>

<span data-ttu-id="690e7-142">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u HERE Technologies, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="690e7-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="690e7-143">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da HERE Technologies ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="690e7-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="690e7-144">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="690e7-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="690e7-145">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="690e7-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]