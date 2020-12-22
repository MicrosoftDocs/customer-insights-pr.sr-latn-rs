---
title: Obogaćivanje pomoću obogaćivanja treće strane Experian
description: Opšte informacije o Experian obogaćivanju treće strane.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668830"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="95133-103">Obogatite profile klijenata demografskim podacima kompanije Experian (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="95133-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="95133-104">Experian je globalni lider u izveštavanju o potrošačkim i poslovnim kreditima i marketinškim uslugama.</span><span class="sxs-lookup"><span data-stu-id="95133-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="95133-105">Pomoću usluga obogaćivanja podataka kompanije Experian, možete da izgradite dublje razumevanje svojih klijenata obogaćivanjem profila klijenata demografskim podacima kao što su veličina domaćinstva, prihod i još mnogo toga.</span><span class="sxs-lookup"><span data-stu-id="95133-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="95133-106">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="95133-106">Prerequisites</span></span>

<span data-ttu-id="95133-107">Da biste konfigurisali Experian, moraju da se ispune sledeći preduslovi:</span><span class="sxs-lookup"><span data-stu-id="95133-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="95133-108">Imate aktivnu pretplatu na Experian.</span><span class="sxs-lookup"><span data-stu-id="95133-108">You have an active Experian subscription.</span></span> <span data-ttu-id="95133-109">Da biste dobili pretplatu, [obratite se kompaniji Experian](https://www.experian.com/marketing-services/contact) direktno.</span><span class="sxs-lookup"><span data-stu-id="95133-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="95133-110">[Saznajte više o Experian obogaćivanju podataka](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="95133-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="95133-111">Imate ID korisnika, ID stranke i broj modela za SSH omogućeni Secure Transport (ST) nalog koji je Experian kreirao za vas.</span><span class="sxs-lookup"><span data-stu-id="95133-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="95133-112">Imate [administratorske](permissions.md#administrator) dozvole u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="95133-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="95133-113">Konfigurisanje</span><span class="sxs-lookup"><span data-stu-id="95133-113">Configuration</span></span>

1. <span data-ttu-id="95133-114">Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.</span><span class="sxs-lookup"><span data-stu-id="95133-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="95133-115">Izaberite **Obogati moje podatke** na Experian pločici.</span><span class="sxs-lookup"><span data-stu-id="95133-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="95133-116">![Experian pločica](media/experian-tile.png "Experian pločica")</span><span class="sxs-lookup"><span data-stu-id="95133-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="95133-117">Izaberite **Započnite** i unesite ID korisnika, ID stranke i broj modela za vaš Experian Secure Transport nalog.</span><span class="sxs-lookup"><span data-stu-id="95133-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="95133-118">Pregledajte i dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="95133-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="95133-119">Potvrdite sve unose izborom **Primeni**.</span><span class="sxs-lookup"><span data-stu-id="95133-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="95133-120">Mapiranje polja</span><span class="sxs-lookup"><span data-stu-id="95133-120">Map your fields</span></span>

1. <span data-ttu-id="95133-121">Izaberite **Dodaj podatke** i izaberite ključne identifikatore iz opcija **Ime i adresa**, **E-pošta** ili **Telefon** koje ćete poslati kompaniji Experian radi rešavanja identiteta.</span><span class="sxs-lookup"><span data-stu-id="95133-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="95133-122">Više atributa ključnih identifikatora poslatih u Experian verovatno daje veću stopu podudaranja.</span><span class="sxs-lookup"><span data-stu-id="95133-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="95133-123">Izaberite **Sledeće** i mapirajte odgovarajuće atribute iz vašeg objedinjenog entiteta klijenta za izabrana polja ključnog identifikatora.</span><span class="sxs-lookup"><span data-stu-id="95133-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="95133-124">Izaberite **Dodaj atribut** da biste mapirali sve dodatne atribute koje biste želeli da pošaljete kompaniji Experian.</span><span class="sxs-lookup"><span data-stu-id="95133-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="95133-125">Izaberite **Sačuvaj** da biste dovršili mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="95133-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="95133-126">![Mapiranje polja za Experian](media/experian-field-mapping.png "Mapiranje polja za Experian")</span><span class="sxs-lookup"><span data-stu-id="95133-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="95133-127">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="95133-127">Enrichment results</span></span>

<span data-ttu-id="95133-128">Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake.</span><span class="sxs-lookup"><span data-stu-id="95133-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="95133-129">Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="95133-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="95133-130">Vreme obrade zavisiće od veličine vaših podataka o klijentima i procesa obogaćivanja koje je za vaš nalog podesio Experian.</span><span class="sxs-lookup"><span data-stu-id="95133-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="95133-131">Nakon završetka procesa obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod opcijom **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="95133-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="95133-132">Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="95133-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="95133-133">Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.</span><span class="sxs-lookup"><span data-stu-id="95133-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="95133-134">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="95133-134">Next steps</span></span>

<span data-ttu-id="95133-135">Nadogradite na obogaćenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="95133-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="95133-136">Kreirajte [segmente](segments.md), [mere](measures.md), pa čak i [izvezite podatke](export-destinations.md) da biste pružili personalizovana iskustva svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="95133-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="95133-137">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="95133-137">Data privacy and compliance</span></span>

<span data-ttu-id="95133-138">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Experian, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="95133-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="95133-139">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Experian ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="95133-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="95133-140">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="95133-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="95133-141">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="95133-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
