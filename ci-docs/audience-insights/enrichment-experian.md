---
title: Obogaćivanje pomoću obogaćivanja treće strane Experian
description: Opšte informacije o Experian obogaćivanju treće strane.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269577"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="57b9d-103">Obogatite profile klijenata demografskim podacima kompanije Experian (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="57b9d-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="57b9d-104">Experian je globalni lider u izveštavanju o potrošačkim i poslovnim kreditima i marketinškim uslugama.</span><span class="sxs-lookup"><span data-stu-id="57b9d-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="57b9d-105">Pomoću usluga obogaćivanja podataka kompanije Experian, možete da izgradite dublje razumevanje svojih klijenata obogaćivanjem profila klijenata demografskim podacima kao što su veličina domaćinstva, prihod i još mnogo toga.</span><span class="sxs-lookup"><span data-stu-id="57b9d-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="57b9d-106">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="57b9d-106">Prerequisites</span></span>

<span data-ttu-id="57b9d-107">Da biste konfigurisali Experian, moraju da se ispune sledeći preduslovi:</span><span class="sxs-lookup"><span data-stu-id="57b9d-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="57b9d-108">Imate aktivnu pretplatu na Experian.</span><span class="sxs-lookup"><span data-stu-id="57b9d-108">You have an active Experian subscription.</span></span> <span data-ttu-id="57b9d-109">Da biste dobili pretplatu, [obratite se kompaniji Experian](https://www.experian.com/marketing-services/contact) direktno.</span><span class="sxs-lookup"><span data-stu-id="57b9d-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="57b9d-110">[Saznajte više o Experian obogaćivanju podataka](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="57b9d-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="57b9d-111">Imate ID korisnika, ID stranke i broj modela za SSH omogućeni Secure Transport (ST) nalog koji je Experian kreirao za vas.</span><span class="sxs-lookup"><span data-stu-id="57b9d-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="57b9d-112">Imate [administratorske](permissions.md#administrator) dozvole u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="57b9d-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="57b9d-113">Konfigurisanje</span><span class="sxs-lookup"><span data-stu-id="57b9d-113">Configuration</span></span>

1. <span data-ttu-id="57b9d-114">Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.</span><span class="sxs-lookup"><span data-stu-id="57b9d-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="57b9d-115">Izaberite **Obogati moje podatke** na Experian pločici.</span><span class="sxs-lookup"><span data-stu-id="57b9d-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="57b9d-116">![Experian pločica](media/experian-tile.png "Experian pločica")</span><span class="sxs-lookup"><span data-stu-id="57b9d-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="57b9d-117">Izaberite **Započnite** i unesite ID korisnika, ID stranke i broj modela za vaš Experian Secure Transport nalog.</span><span class="sxs-lookup"><span data-stu-id="57b9d-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="57b9d-118">Pregledajte i dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="57b9d-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="57b9d-119">Potvrdite sve unose izborom **Primeni**.</span><span class="sxs-lookup"><span data-stu-id="57b9d-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="57b9d-120">Mapiranje polja</span><span class="sxs-lookup"><span data-stu-id="57b9d-120">Map your fields</span></span>

1.  <span data-ttu-id="57b9d-121">Izaberite **Dodaj podatke** i izaberite **Skup podataka o klijentima** koji želite da obogatite demografskim podacima kompanije Experian.</span><span class="sxs-lookup"><span data-stu-id="57b9d-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="57b9d-122">Možete izabrati entitet **Klijent** da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="57b9d-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="57b9d-123">Izaberite svoje ključne identifikatore iz polja **Ime i adresa**, **E-adresa** ili **Telefon** koje ćete poslati kompaniji Experian radi rešavanja identiteta.</span><span class="sxs-lookup"><span data-stu-id="57b9d-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="57b9d-124">Više atributa ključnih identifikatora poslatih u Experian verovatno daje veću stopu podudaranja.</span><span class="sxs-lookup"><span data-stu-id="57b9d-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="57b9d-125">Izaberite **Sledeće** i mapirajte odgovarajuće atribute iz vašeg objedinjenog entiteta klijenta za izabrana polja ključnog identifikatora.</span><span class="sxs-lookup"><span data-stu-id="57b9d-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="57b9d-126">Izaberite **Dodaj atribut** da biste mapirali sve dodatne atribute koje biste želeli da pošaljete kompaniji Experian.</span><span class="sxs-lookup"><span data-stu-id="57b9d-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="57b9d-127">Izaberite **Sačuvaj** da biste dovršili mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="57b9d-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="57b9d-128">![Mapiranje polja za Experian](media/experian-field-mapping.png "Mapiranje polja za Experian")</span><span class="sxs-lookup"><span data-stu-id="57b9d-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="57b9d-129">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="57b9d-129">Enrichment results</span></span>

<span data-ttu-id="57b9d-130">Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake.</span><span class="sxs-lookup"><span data-stu-id="57b9d-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="57b9d-131">Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="57b9d-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="57b9d-132">Vreme obrade zavisiće od veličine vaših podataka o klijentima i procesa obogaćivanja koje je za vaš nalog podesio Experian.</span><span class="sxs-lookup"><span data-stu-id="57b9d-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="57b9d-133">Nakon završetka procesa obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod opcijom **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="57b9d-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="57b9d-134">Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="57b9d-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="57b9d-135">Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.</span><span class="sxs-lookup"><span data-stu-id="57b9d-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="57b9d-136">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="57b9d-136">Next steps</span></span>

<span data-ttu-id="57b9d-137">Nadogradite na obogaćenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="57b9d-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="57b9d-138">Kreirajte [segmente](segments.md), [mere](measures.md), pa čak i [izvezite podatke](export-destinations.md) da biste pružili personalizovana iskustva svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="57b9d-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="57b9d-139">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="57b9d-139">Data privacy and compliance</span></span>

<span data-ttu-id="57b9d-140">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Experian, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="57b9d-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="57b9d-141">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Experian ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="57b9d-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="57b9d-142">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="57b9d-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="57b9d-143">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="57b9d-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]