---
title: Obogaćivanje pomoću obogaćivanja treće strane HERE Technologies
description: Opšte informacije o HERE Technologies obogaćivanju treće strane.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896068"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="e4605-103">Obogaćivanje profila klijenata uz HERE Technologies (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="e4605-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="e4605-104">verzija za pregled je kompanija za platformu lokacije koja pruža podatke i usluge usmerene na lokaciju.</span><span class="sxs-lookup"><span data-stu-id="e4605-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="e4605-105">Pomoću usluga obogaćivanja podataka kompanije HERE Technologies možete da izgradite preciznije razumevanje lokacije svojih klijenata pomoću normalizacije adresa, izdvajanja geografske širine i dužine i još mnogo toga.</span><span class="sxs-lookup"><span data-stu-id="e4605-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e4605-106">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="e4605-106">Prerequisites</span></span>

<span data-ttu-id="e4605-107">Da biste konfigurisali verzija za pregled obogaćivanja, moraju biti ispunjeni sledeći preduslovi:</span><span class="sxs-lookup"><span data-stu-id="e4605-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e4605-108">Morate imati aktivnu pretplatu za HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e4605-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="e4605-109">Da biste dobili pretplatu, možete [da se registrujete ovde](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ili [kontaktirajte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direktno.</span><span class="sxs-lookup"><span data-stu-id="e4605-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="e4605-110">Saznajte više o HERE Technologies obogaćivanju lokacije.</span><span class="sxs-lookup"><span data-stu-id="e4605-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="e4605-111">Dostupna je HERE [veza](connections.md) *ili* imate dozvole [administratora](permissions.md#administrator) i HERE Technologies API ključ.</span><span class="sxs-lookup"><span data-stu-id="e4605-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="e4605-112">Konfigurisanje obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="e4605-112">Configure the enrichment</span></span>

1. <span data-ttu-id="e4605-113">Idite na **Podaci** > **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="e4605-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="e4605-114">Izaberite **Obogati moje podatke** na pločici HERE Technologies i izaberite **Započni**.</span><span class="sxs-lookup"><span data-stu-id="e4605-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e4605-115">![HERE Technologies pločica](media/HERE-tile.png "HERE Technologies pločica")</span><span class="sxs-lookup"><span data-stu-id="e4605-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="e4605-116">Izaberite [vezu](connections.md) iz padajuće liste.</span><span class="sxs-lookup"><span data-stu-id="e4605-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="e4605-117">Ako veza nije dostupna, obratite se administratoru.</span><span class="sxs-lookup"><span data-stu-id="e4605-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="e4605-118">Ako ste administrator, vezu možete da napravite izborom **Dodaj vezu**.</span><span class="sxs-lookup"><span data-stu-id="e4605-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="e4605-119">Odaberite **HERE Technologies** iz padajućeg menija.</span><span class="sxs-lookup"><span data-stu-id="e4605-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="e4605-120">Izaberite **Povežite se sa HERE Technologies** da potvrdite izbor.</span><span class="sxs-lookup"><span data-stu-id="e4605-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="e4605-121">Izaberite **Sledeće** i odaberite **Skup podataka klijenta** koji želite da obogatite sa podacima o lokaciji kompanije HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e4605-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="e4605-122">Možete izabrati entitet **Klijent** da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="e4605-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Snimak ekrana prilikom odabira skupa podataka o klijentima.":::

1. <span data-ttu-id="e4605-124">Odaberite da li želite da mapirate polja sa primarnom i/ili sekundarnom adresom.</span><span class="sxs-lookup"><span data-stu-id="e4605-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="e4605-125">Možete odrediti mapiranje polja za obe adrese i obogatiti profile za obe adrese zasebno.</span><span class="sxs-lookup"><span data-stu-id="e4605-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="e4605-126">Na primer, ako postoje kućna i poslovna adresa.</span><span class="sxs-lookup"><span data-stu-id="e4605-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="e4605-127">Izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="e4605-127">Select **Next**.</span></span>

1. <span data-ttu-id="e4605-128">Definišite koja polja iz vaših objedinjenih profila treba koristiti za podudaranje podataka o lokaciji od kompanije HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e4605-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="e4605-129">Polja **Ulica 1** i **Poštanski broj** su obavezna za odabranu primarnu i/ili sekundarnu adresu.</span><span class="sxs-lookup"><span data-stu-id="e4605-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="e4605-130">Za veću preciznost podudaranja može se dodati više polja.</span><span class="sxs-lookup"><span data-stu-id="e4605-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e4605-131">![Stranica za konfiguraciju HERE Technologies obogaćivanja](media/enrichment-HERE-configuration.png "Stranica za konfiguraciju HERE Technologies obogaćivanja")</span><span class="sxs-lookup"><span data-stu-id="e4605-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="e4605-132">Izaberite **Sledeće** da biste dovršili mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="e4605-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="e4605-133">Navedite naziv obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="e4605-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="e4605-134">1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.</span><span class="sxs-lookup"><span data-stu-id="e4605-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="e4605-135">Konfigurišite vezu za HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="e4605-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="e4605-136">Morate biti administrator da biste konfigurisali veze.</span><span class="sxs-lookup"><span data-stu-id="e4605-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="e4605-137">Izaberite **Dodaj vezu** prilikom konfigurisanja obogaćivanja *ili* idite na **Administrator** > **Veze** i izaberite **Podešavanje** na pločici HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e4605-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="e4605-138">Unesite naziv veze u polje **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="e4605-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="e4605-139">Navedite važeći HERE Technologies API ključ.</span><span class="sxs-lookup"><span data-stu-id="e4605-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="e4605-140">Pregledajte i dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**</span><span class="sxs-lookup"><span data-stu-id="e4605-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="e4605-141">Izaberite **Verifikuj** da biste proverili valjanost konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="e4605-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="e4605-142">Po završetku verifikacije, izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="e4605-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="e4605-143">![Stranica za konfiguraciju veze za HERE Technologies](media/enrichment-HERE-connection.png "Stranica za konfiguraciju veze za HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="e4605-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="e4605-144">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="e4605-144">Enrichment results</span></span>

<span data-ttu-id="e4605-145">Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake.</span><span class="sxs-lookup"><span data-stu-id="e4605-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e4605-146">Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e4605-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e4605-147">Vreme obrade zavisiće od veličine podataka o klijentima i vremena odziva API-ja kompanije HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e4605-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="e4605-148">Nakon završetka procesa obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod opcijom **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="e4605-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="e4605-149">Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="e4605-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e4605-150">Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.</span><span class="sxs-lookup"><span data-stu-id="e4605-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e4605-151">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="e4605-151">Next steps</span></span>

<span data-ttu-id="e4605-152">Nadogradite na obogaćenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="e4605-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e4605-153">Kreirajte [segmente](segments.md), [mere](measures.md), pa čak i [izvezite podatke](export-destinations.md) da biste pružili personalizovana iskustva svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="e4605-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e4605-154">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="e4605-154">Data privacy and compliance</span></span>

<span data-ttu-id="e4605-155">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u HERE Technologies, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="e4605-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e4605-156">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da HERE Technologies ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="e4605-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e4605-157">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e4605-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e4605-158">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="e4605-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
