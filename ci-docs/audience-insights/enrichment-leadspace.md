---
title: Obogaćivanje profila preduzeća nezavisnim Leadspace-om za obogaćivanje
description: Opšte informacije o Leadspace obogaćivanju treće strane.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269439"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="797e2-103">Obogaćivanje profila preduzeća uz Leadspace (pregled)</span><span class="sxs-lookup"><span data-stu-id="797e2-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="797e2-104">Leadspace je kompanija za nauku o podacima koja obezbeđuje B2B platformu za podatke o klijentima.</span><span class="sxs-lookup"><span data-stu-id="797e2-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="797e2-105">Omogućuje klijentima sa objedinjenim profilima klijenata za kompanije da obogaćuju svoje podatke.</span><span class="sxs-lookup"><span data-stu-id="797e2-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="797e2-106">Obogaćivanja obuhvataju dodatne atribute uključujući veličinu kompanije, lokaciju, delatnost i još mnogo toga.</span><span class="sxs-lookup"><span data-stu-id="797e2-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="797e2-107">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="797e2-107">Prerequisites</span></span>

<span data-ttu-id="797e2-108">Da biste konfigurisali Leadspace, morate da ispunite sledeće preduslove:</span><span class="sxs-lookup"><span data-stu-id="797e2-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="797e2-109">Imate aktivnu Leadspace licencu i „trajni ključ“ (nazvan **Leadspace token**).</span><span class="sxs-lookup"><span data-stu-id="797e2-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="797e2-110">Kontaktirajte direktno [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) za detalje o njihovom proizvodu.</span><span class="sxs-lookup"><span data-stu-id="797e2-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="797e2-111">Imate [administratorske](permissions.md#administrator) dozvole.</span><span class="sxs-lookup"><span data-stu-id="797e2-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="797e2-112">Imate [objedinjene profile klijenata](customer-profiles.md) za kompanije.</span><span class="sxs-lookup"><span data-stu-id="797e2-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="797e2-113">Konfigurisanje</span><span class="sxs-lookup"><span data-stu-id="797e2-113">Configuration</span></span>

1. <span data-ttu-id="797e2-114">U uvidima o korisnicima idite na **Podaci** > **Obogaćivanje**.</span><span class="sxs-lookup"><span data-stu-id="797e2-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="797e2-115">Izaberite **Obogati moje podatke** na pločici Leadspace.</span><span class="sxs-lookup"><span data-stu-id="797e2-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Snimak ekrana Leadspace pločice.":::

1. <span data-ttu-id="797e2-117">Izaberite **Započnite**, a zatim unesite aktivan **Leadspace token** (trajni ključ).</span><span class="sxs-lookup"><span data-stu-id="797e2-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="797e2-118">Pregledajte i dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="797e2-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="797e2-119">Potvrdite oba ulaza izborom opcije **Povežite se na Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="797e2-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="797e2-120">Izaberite **Mapiraj podatke** i odaberite skup podataka koji želite da obogatite podacima o preduzeću kompanije Leadspace.</span><span class="sxs-lookup"><span data-stu-id="797e2-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="797e2-121">Možete izabrati entitet *Klijent* da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="797e2-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Odaberite između profila klijenta i obogaćivanja segmenata.":::

1. <span data-ttu-id="797e2-123">Kliknite na **Sledeće** i definišite koja polja iz vaših objedinjenih profila treba koristiti za traženje odgovarajućih podataka o preduzeću od kompanije Leadspace.</span><span class="sxs-lookup"><span data-stu-id="797e2-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="797e2-124">Polje **Ime kompanije** je obavezno.</span><span class="sxs-lookup"><span data-stu-id="797e2-124">The **Name of company** field is required.</span></span> <span data-ttu-id="797e2-125">Za veću preciznost podudaranja, do dva druga polja, **Veb-lokacija kompanije** i **Lokacija kompanije**, mogu se dodati.</span><span class="sxs-lookup"><span data-stu-id="797e2-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Okno za mapiranje polja Leadspace.":::
   
1. <span data-ttu-id="797e2-127">Izaberite **Primeni** da dovršite mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="797e2-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="797e2-128">Izaberite **Pokreni** kako biste obogatili profile preduzeća.</span><span class="sxs-lookup"><span data-stu-id="797e2-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="797e2-129">Koliko dugo traje obogaćivanje, zavisi od broja objedinjenih profila klijenata.</span><span class="sxs-lookup"><span data-stu-id="797e2-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="797e2-130">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="797e2-130">Enrichment results</span></span>

<span data-ttu-id="797e2-131">Nakon osvežavanja obogaćivanja, možete pregledati novo obogaćene podatke kompanije u delu [Moja obogaćenja](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="797e2-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="797e2-132">Možete pronaći vreme poslednjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="797e2-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="797e2-133">Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.</span><span class="sxs-lookup"><span data-stu-id="797e2-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="797e2-134">Više informacija potražite u članku [Leadspace API-ji](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="797e2-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="797e2-135">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="797e2-135">Next steps</span></span>

<span data-ttu-id="797e2-136">Nadogradite na obogaćenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="797e2-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="797e2-137">Kreirajte [segmente](segments.md), [mere](measures.md), pa čak i [izvezite podatke](export-destinations.md) da biste pružili personalizovana iskustva svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="797e2-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="797e2-138">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="797e2-138">Data privacy and compliance</span></span>

<span data-ttu-id="797e2-139">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Leadspace, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="797e2-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="797e2-140">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Leadspace ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="797e2-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="797e2-141">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="797e2-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="797e2-142">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="797e2-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]