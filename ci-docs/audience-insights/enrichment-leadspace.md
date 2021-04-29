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
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895930"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="84ebd-103">Obogaćivanje profila preduzeća uz Leadspace (pregled)</span><span class="sxs-lookup"><span data-stu-id="84ebd-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="84ebd-104">Leadspace je kompanija za nauku o podacima koja obezbeđuje B2B platformu za podatke o klijentima.</span><span class="sxs-lookup"><span data-stu-id="84ebd-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="84ebd-105">Omogućuje klijentima sa objedinjenim profilima klijenata za kompanije da obogaćuju svoje podatke.</span><span class="sxs-lookup"><span data-stu-id="84ebd-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="84ebd-106">Obogaćivanja obuhvataju više atributa kao što su veličina preduzeća, lokacija, delatnost i još mnogo toga.</span><span class="sxs-lookup"><span data-stu-id="84ebd-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="84ebd-107">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="84ebd-107">Prerequisites</span></span>

<span data-ttu-id="84ebd-108">Da biste konfigurisali Leadspace, morate da ispunite sledeće preduslove:</span><span class="sxs-lookup"><span data-stu-id="84ebd-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="84ebd-109">Imate aktivnu Leadspace licencu.</span><span class="sxs-lookup"><span data-stu-id="84ebd-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="84ebd-110">Imate [objedinjene profile klijenata](customer-profiles.md) za kompanije.</span><span class="sxs-lookup"><span data-stu-id="84ebd-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="84ebd-111">Administrator je već konfigurisao Leadspace vezu ili imate dozvole [administratora](permissions.md#administrator) i „večiti ključ“ (koji se zove **Leadspace token**).</span><span class="sxs-lookup"><span data-stu-id="84ebd-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="84ebd-112">Kontaktirajte [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) direktno da biste saznali detalje o njihovom proizvodu.</span><span class="sxs-lookup"><span data-stu-id="84ebd-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="84ebd-113">Konfigurisanje obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="84ebd-113">Configure the enrichment</span></span>

1. <span data-ttu-id="84ebd-114">U uvidima o korisnicima idite na **Podaci** > **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="84ebd-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="84ebd-115">Izaberite **Obogati moje podatke** na pločici Leadspace i izaberite **Započni**.</span><span class="sxs-lookup"><span data-stu-id="84ebd-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Snimak ekrana Leadspace pločice.":::

1. <span data-ttu-id="84ebd-117">Izaberite [vezu](connections.md) iz padajuće liste.</span><span class="sxs-lookup"><span data-stu-id="84ebd-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="84ebd-118">Ako veza nije dostupna, obratite se administratoru.</span><span class="sxs-lookup"><span data-stu-id="84ebd-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="84ebd-119">Ako ste administrator, vezu možete kreirati izborom **Dodaj vezu** i biranjem opcije **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="84ebd-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="84ebd-120">Izaberite **Povežite se sa uslugom Leadspace** da biste potvrdili izbor veze.</span><span class="sxs-lookup"><span data-stu-id="84ebd-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="84ebd-121">Izaberite **Sledeće** i birajte **Skup podataka klijenta** koji želite da obogatite podacima preduzeća iz usluge Leadspace.</span><span class="sxs-lookup"><span data-stu-id="84ebd-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="84ebd-122">Možete izabrati entitet **Klijent** da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="84ebd-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Snimak ekrana prilikom odabira skupa podataka o klijentima.":::

1. <span data-ttu-id="84ebd-124">Izaberite **Sledeće** i definišite koja polja iz vaših objedinjenih profila se koriste za podudaranje podataka o preduzeću iz usluge Leadspace.</span><span class="sxs-lookup"><span data-stu-id="84ebd-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="84ebd-125">Polje **Ime kompanije** je obavezno.</span><span class="sxs-lookup"><span data-stu-id="84ebd-125">The **Name of company** field is required.</span></span> <span data-ttu-id="84ebd-126">Za veću preciznost podudaranja, do dva druga polja, **Veb-lokacija kompanije** i **Lokacija kompanije**, mogu se dodati.</span><span class="sxs-lookup"><span data-stu-id="84ebd-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Okno za mapiranje polja Leadspace.":::

1. <span data-ttu-id="84ebd-128">Izaberite **Sledeće** da biste dovršili mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="84ebd-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="84ebd-129">Navedite ime za obogaćivanje i izaberite **Sačuvaj obogaćivanje** nakon pregleda vašeg izbora.</span><span class="sxs-lookup"><span data-stu-id="84ebd-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="84ebd-130">Konfigurišite vezu za Leadspace</span><span class="sxs-lookup"><span data-stu-id="84ebd-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="84ebd-131">Morate biti administrator da biste konfigurisali veze.</span><span class="sxs-lookup"><span data-stu-id="84ebd-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="84ebd-132">Izaberite **Dodaj vezu** prilikom konfigurisanja obogaćivanja *ili* idite na **Administrator** > **Veze** i izaberite **Podešavanje** na pločici Leadspace.</span><span class="sxs-lookup"><span data-stu-id="84ebd-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="84ebd-133">Izaberite **Prvi koraci**</span><span class="sxs-lookup"><span data-stu-id="84ebd-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="84ebd-134">Unesite naziv veze u polje **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="84ebd-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="84ebd-135">Navedite važeći token za Leadspace.</span><span class="sxs-lookup"><span data-stu-id="84ebd-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="84ebd-136">Pregledajte i dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**</span><span class="sxs-lookup"><span data-stu-id="84ebd-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="84ebd-137">Izaberite **Verifikuj** da biste proverili valjanost konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="84ebd-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="84ebd-138">Po završetku verifikacije, izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="84ebd-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Stranica za konfiguraciju veze za Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="84ebd-140">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="84ebd-140">Enrichment results</span></span>

<span data-ttu-id="84ebd-141">Nakon osvežavanja obogaćivanja, možete pregledati novo obogaćene podatke kompanije u delu [Moja obogaćenja](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="84ebd-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="84ebd-142">Možete pronaći vreme poslednjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="84ebd-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="84ebd-143">Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.</span><span class="sxs-lookup"><span data-stu-id="84ebd-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="84ebd-144">Više informacija potražite u članku [Leadspace API-ji](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="84ebd-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="84ebd-145">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="84ebd-145">Next steps</span></span>

<span data-ttu-id="84ebd-146">Nadogradite na obogaćenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="84ebd-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="84ebd-147">Kreirajte [segmente](segments.md), [mere](measures.md), pa čak i [izvezite podatke](export-destinations.md) da biste pružili personalizovana iskustva svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="84ebd-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="84ebd-148">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="84ebd-148">Data privacy and compliance</span></span>

<span data-ttu-id="84ebd-149">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Leadspace, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="84ebd-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="84ebd-150">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Leadspace ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="84ebd-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="84ebd-151">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="84ebd-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="84ebd-152">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="84ebd-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
