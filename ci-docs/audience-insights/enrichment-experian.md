---
title: Obogaćivanje putem nezavisnog obogaćivanja Experian
description: Opšte informacije o Experian nezavisnom obogaćivanju.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309837"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="a076b-103">Obogatite profile klijenata demografskim podacima iz usluge Experian (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="a076b-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="a076b-104">Experian je globalni lider u izveštavanju o potrošačkim i poslovnim kreditima i marketinškim uslugama.</span><span class="sxs-lookup"><span data-stu-id="a076b-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="a076b-105">Koristeći Experian usluge obogaćivanja podataka, možete da razvijete dublje razumevanje svojih klijenata obogaćujući svoje profile klijenata demografskim podacima kao što su veličina domaćinstva, prihod i još mnogo toga.</span><span class="sxs-lookup"><span data-stu-id="a076b-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a076b-106">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="a076b-106">Prerequisites</span></span>

<span data-ttu-id="a076b-107">Da biste konfigurisali Experian, morate ispuniti sledeće preduslove:</span><span class="sxs-lookup"><span data-stu-id="a076b-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a076b-108">Imate aktivnu pretplatu na Experian.</span><span class="sxs-lookup"><span data-stu-id="a076b-108">You have an active Experian subscription.</span></span> <span data-ttu-id="a076b-109">Da biste nabavili pretplatu, [kontaktirajte Experian](https://www.experian.com/marketing-services/contact) direktno.</span><span class="sxs-lookup"><span data-stu-id="a076b-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="a076b-110">[Saznajte više o Experian obogaćivanju podataka](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="a076b-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="a076b-111">Administrator je već konfigurisao vezu sa uslugom Experian *ili* imate dozvole [administratora](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="a076b-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="a076b-112">Takođe su vam potrebni ID korisnika, ID stranke i broj modela za vaš SSH omogućeni nalog za bezbedni transport (ST)koji je usluga Experian kreirala za vas.</span><span class="sxs-lookup"><span data-stu-id="a076b-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="a076b-113">Podržane zemlje/regioni</span><span class="sxs-lookup"><span data-stu-id="a076b-113">Supported countries/regions</span></span>

<span data-ttu-id="a076b-114">Trenutno podržavamo obogaćivanje profila kupaca samo u Sjedinjenim Državama.</span><span class="sxs-lookup"><span data-stu-id="a076b-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="a076b-115">Konfigurisanje obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="a076b-115">Configure the enrichment</span></span>

1. <span data-ttu-id="a076b-116">Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.</span><span class="sxs-lookup"><span data-stu-id="a076b-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="a076b-117">Izaberite **Obogati moje podatke** na pločici Experian.</span><span class="sxs-lookup"><span data-stu-id="a076b-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a076b-118">![Experian pločic](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="a076b-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="a076b-119">Izaberite [vezu](connections.md) sa padajuće liste.</span><span class="sxs-lookup"><span data-stu-id="a076b-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="a076b-120">Ako veza nije dostupna, obratite se administratoru.</span><span class="sxs-lookup"><span data-stu-id="a076b-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="a076b-121">Ako ste administrator, vezu možete da napravite ako izaberete **Dodaj vezu** i birate Experian sa padajuće liste.</span><span class="sxs-lookup"><span data-stu-id="a076b-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="a076b-122">Izaberite **Poveži se za uslugom Experian** da biste potvrdili izbor veze.</span><span class="sxs-lookup"><span data-stu-id="a076b-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="a076b-123">Izaberite **Sledeće** i birajte **Skup podataka o klijentu** koji želite da obogatite demografskim podacima iz usluge Experian.</span><span class="sxs-lookup"><span data-stu-id="a076b-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="a076b-124">Možete izabrati entitet **Klijent** da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="a076b-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Snimak ekrana prilikom odabira skupa podataka o klijentima.":::

1. <span data-ttu-id="a076b-126">Izaberite **Sledeće** i definišite koji tip polja iz vaših objedinjenih profila treba da koristite za traženje odgovarajućih demografskih podataka iz usluge Experian.</span><span class="sxs-lookup"><span data-stu-id="a076b-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="a076b-127">Obavezno je barem jedno od polja **Ime i adresa**, **Telefon** ili **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="a076b-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="a076b-128">Za veću preciznost podudaranja, mogu se dodati još dva polja.</span><span class="sxs-lookup"><span data-stu-id="a076b-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="a076b-129">Ovaj izbor će uticati na polja za mapiranje kojima imate pristup u sledećem koraku.</span><span class="sxs-lookup"><span data-stu-id="a076b-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="a076b-130">Više atributa identifikatora ključa poslatih usluzi Experian povećavaju verovatnoću postizanja više stope podudaranja.</span><span class="sxs-lookup"><span data-stu-id="a076b-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="a076b-131">Izaberite **Sledeće** da biste započeli mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="a076b-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="a076b-132">Definišite koja polja iz vaših objedinjenih profila treba da koristite za traženje odgovarajućih demografskih podataka iz usluge Experian.</span><span class="sxs-lookup"><span data-stu-id="a076b-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="a076b-133">Obavezna polja su označena.</span><span class="sxs-lookup"><span data-stu-id="a076b-133">Required fields are marked.</span></span>

1. <span data-ttu-id="a076b-134">Obezbedite naziv za obogaćivanje i naziv za izlazni entitet.</span><span class="sxs-lookup"><span data-stu-id="a076b-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="a076b-135">Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.</span><span class="sxs-lookup"><span data-stu-id="a076b-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="a076b-136">Konfigurisanje veze za Experian</span><span class="sxs-lookup"><span data-stu-id="a076b-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="a076b-137">Morate biti administrator da biste konfigurisali veze.</span><span class="sxs-lookup"><span data-stu-id="a076b-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="a076b-138">Izaberite **Dodaj vezu** kada konfigurišete obogaćivanje *ili* idite na **Administrator** > **Veze** i izaberite **Podesiti** na pločici Experian.</span><span class="sxs-lookup"><span data-stu-id="a076b-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="a076b-139">Izaberite **Prvi koraci**.</span><span class="sxs-lookup"><span data-stu-id="a076b-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="a076b-140">Unesite naziv veze u polje **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="a076b-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="a076b-141">Unesite važeći ID korisnika, ID stranke i broj modela za svoj nalog za Experian bezbedan transport.</span><span class="sxs-lookup"><span data-stu-id="a076b-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="a076b-142">Pregledajte i dajte saglasnost za **Privatnost podataka i usklađenost** izborom opcije **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="a076b-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="a076b-143">Izaberite **Verifikuj** da biste proverili valjanost konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="a076b-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="a076b-144">Po završetku verifikacije, izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="a076b-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Okno za konfiguraciju Experian veze.":::

## <a name="enrichment-results"></a><span data-ttu-id="a076b-146">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="a076b-146">Enrichment results</span></span>

<span data-ttu-id="a076b-147">Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake.</span><span class="sxs-lookup"><span data-stu-id="a076b-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="a076b-148">Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a076b-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a076b-149">Vreme obrade zavisiće od veličine vaših podataka o klijentu i procesa obogaćivanja koje je za vaš nalog podesio Experian.</span><span class="sxs-lookup"><span data-stu-id="a076b-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="a076b-150">Nakon završetka procesa obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod opcijom **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="a076b-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="a076b-151">Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="a076b-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a076b-152">Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.</span><span class="sxs-lookup"><span data-stu-id="a076b-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a076b-153">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="a076b-153">Next steps</span></span>

<span data-ttu-id="a076b-154">Nadogradite na obogaćenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="a076b-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a076b-155">Kreirajte [segmente](segments.md) i [mere](measures.md), pa čak i [izvoz podataka](export-destinations.md) da pružite personalizovana iskustva svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="a076b-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a076b-156">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="a076b-156">Data privacy and compliance</span></span>

<span data-ttu-id="a076b-157">Kada omogućite Dynamics 365 Customer Insights za prenos podataka u Experian, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="a076b-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a076b-158">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Experian ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="a076b-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a076b-159">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a076b-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a076b-160">Vaš Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="a076b-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
