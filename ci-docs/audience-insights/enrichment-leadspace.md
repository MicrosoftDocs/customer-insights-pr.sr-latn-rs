---
title: Obogaćivanje profila preduzeća nezavisnim Leadspace-om za obogaćivanje
description: Opšte informacije o Leadspace obogaćivanju treće strane.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305219"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="d3ee7-103">Obogaćivanje profila preduzeća uz Leadspace (pregled)</span><span class="sxs-lookup"><span data-stu-id="d3ee7-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="d3ee7-104">Leadspace je kompanija za nauku o podacima koja obezbeđuje B2B platformu za podatke o klijentima.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="d3ee7-105">Omogućuje klijentima sa objedinjenim profilima klijenata za kompanije da obogaćuju svoje podatke.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="d3ee7-106">Obogaćivanja obuhvataju više atributa kao što su veličina preduzeća, lokacija, delatnost i još mnogo toga.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3ee7-107">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="d3ee7-107">Prerequisites</span></span>

<span data-ttu-id="d3ee7-108">Da biste konfigurisali Leadspace, morate da ispunite sledeće preduslove:</span><span class="sxs-lookup"><span data-stu-id="d3ee7-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d3ee7-109">Imate aktivnu Leadspace licencu.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="d3ee7-110">Imate [objedinjene profile klijenata](customer-profiles.md) za kompanije.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="d3ee7-111">Administrator je već konfigurisao Leadspace vezu ili imate dozvole [administratora](permissions.md#administrator) i „večiti ključ“ (koji se zove **Leadspace token**).</span><span class="sxs-lookup"><span data-stu-id="d3ee7-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="d3ee7-112">Kontaktirajte [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) direktno da biste saznali detalje o njihovom proizvodu.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="d3ee7-113">Konfigurisanje obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="d3ee7-113">Configure the enrichment</span></span>

1. <span data-ttu-id="d3ee7-114">U uvidima o korisnicima idite na **Podaci** > **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="d3ee7-115">Izaberite **Obogati moje podatke** na pločici Leadspace i izaberite **Započni**.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Snimak ekrana Leadspace pločice.":::

1. <span data-ttu-id="d3ee7-117">Izaberite [vezu](connections.md) sa padajuće liste.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="d3ee7-118">Ako veza nije dostupna, obratite se administratoru.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="d3ee7-119">Ako ste administrator, vezu možete kreirati izborom **Dodaj vezu** i biranjem opcije **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="d3ee7-120">Izaberite **Povežite se sa uslugom Leadspace** da biste potvrdili izbor veze.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="d3ee7-121">Izaberite **Sledeće** i birajte **Skup podataka klijenta** koji želite da obogatite podacima preduzeća iz usluge Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="d3ee7-122">Možete izabrati entitet **Klijent** da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Snimak ekrana prilikom odabira skupa podataka o klijentima.":::

1. <span data-ttu-id="d3ee7-124">Izaberite **Sledeće** i definišite koja polja iz vaših objedinjenih profila se koriste za podudaranje podataka o preduzeću iz usluge Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="d3ee7-125">Polje **Ime kompanije** je obavezno.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-125">The **Name of company** field is required.</span></span> <span data-ttu-id="d3ee7-126">Za veću preciznost podudaranja, do dva druga polja, **Veb-lokacija kompanije** i **Lokacija kompanije**, mogu se dodati.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Okno za mapiranje polja Leadspace.":::

1. <span data-ttu-id="d3ee7-128">Izaberite **Sledeće** da biste dovršili mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="d3ee7-129">Navedite ime za obogaćivanje i izaberite **Sačuvaj obogaćivanje** nakon pregleda vašeg izbora.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="d3ee7-130">Konfigurišite vezu za Leadspace</span><span class="sxs-lookup"><span data-stu-id="d3ee7-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="d3ee7-131">Morate biti administrator da biste konfigurisali veze.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="d3ee7-132">Izaberite **Dodaj vezu** prilikom konfigurisanja obogaćivanja *ili* idite na **Administrator** > **Veze** i izaberite **Podešavanje** na pločici Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="d3ee7-133">Izaberite **Prvi koraci**.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="d3ee7-134">Unesite naziv veze u polje **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="d3ee7-135">Navedite važeći token za Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="d3ee7-136">Pregledajte i dajte saglasnost za **Privatnost podataka i usklađenost** izborom opcije **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="d3ee7-137">Izaberite **Verifikuj** da biste proverili valjanost konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="d3ee7-138">Po završetku verifikacije, izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Stranica za konfiguraciju veze za Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="d3ee7-140">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="d3ee7-140">Enrichment results</span></span>

<span data-ttu-id="d3ee7-141">Nakon osvežavanja obogaćivanja, možete pregledati novo obogaćene podatke kompanije u delu [Moja obogaćenja](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="d3ee7-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="d3ee7-142">Možete pronaći vreme poslednjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d3ee7-143">Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="d3ee7-144">Više informacija potražite u članku [Leadspace API-ji](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="d3ee7-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d3ee7-145">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="d3ee7-145">Next steps</span></span>

<span data-ttu-id="d3ee7-146">Nadogradite na obogaćenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d3ee7-147">Kreirajte [segmente](segments.md) i [mere](measures.md), pa čak i [izvoz podataka](export-destinations.md) da pružite personalizovana iskustva svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d3ee7-148">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="d3ee7-148">Data privacy and compliance</span></span>

<span data-ttu-id="d3ee7-149">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Leadspace, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d3ee7-150">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Leadspace ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d3ee7-151">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d3ee7-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d3ee7-152">Vaš Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
