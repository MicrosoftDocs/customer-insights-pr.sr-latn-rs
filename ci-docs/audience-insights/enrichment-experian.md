---
title: Obogaćivanje pomoću obogaćivanja treće strane Experian
description: Opšte informacije o Experian obogaćivanju treće strane.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896390"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="e8eb5-103">Obogatite profile klijenata demografskim podacima kompanije Experian (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="e8eb5-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="e8eb5-104">Experian je globalni lider u izveštavanju o potrošačkim i poslovnim kreditima i marketinškim uslugama.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="e8eb5-105">Pomoću usluga obogaćivanja podataka kompanije Experian, možete da izgradite dublje razumevanje svojih klijenata obogaćivanjem profila klijenata demografskim podacima kao što su veličina domaćinstva, prihod i još mnogo toga.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e8eb5-106">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="e8eb5-106">Prerequisites</span></span>

<span data-ttu-id="e8eb5-107">Da biste konfigurisali Experian, moraju da se ispune sledeći preduslovi:</span><span class="sxs-lookup"><span data-stu-id="e8eb5-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e8eb5-108">Imate aktivnu pretplatu na Experian.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-108">You have an active Experian subscription.</span></span> <span data-ttu-id="e8eb5-109">Da biste dobili pretplatu, [obratite se kompaniji Experian](https://www.experian.com/marketing-services/contact) direktno.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="e8eb5-110">[Saznajte više o Experian obogaćivanju podataka](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="e8eb5-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="e8eb5-111">Administrator je već konfigurisao Experian vezu *ili* imate dozvole [administratora](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="e8eb5-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="e8eb5-112">Takođe su vam potrebni ID korisnika, ID stranke i broj modela za vaš nalog za bezbedni transport (ST) koji omogućava SSH i koji je Experian kreirao za vas.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="e8eb5-113">Konfigurisanje obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="e8eb5-113">Configure the enrichment</span></span>

1. <span data-ttu-id="e8eb5-114">Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="e8eb5-115">Izaberite **Obogati moje podatke** na Experian pločici.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e8eb5-116">![Experian pločica](media/experian-tile.png "Experian pločica")</span><span class="sxs-lookup"><span data-stu-id="e8eb5-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="e8eb5-117">Izaberite [vezu](connections.md) iz padajuće liste.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="e8eb5-118">Ako veza nije dostupna, obratite se administratoru.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="e8eb5-119">Ako ste administrator, vezu možete da napravite ako izaberete **Dodaj vezu** i birate Experian iz padajućeg menija.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="e8eb5-120">Izaberite **Povežite se sa uslugom Experian** da potvrdite izbor veze.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="e8eb5-121">Izaberite **Sledeće** i odaberite **Skup podataka klijenta** koji želite da obogatite demografskim podacima usluge Experian.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="e8eb5-122">Možete izabrati entitet **Klijent** da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Snimak ekrana prilikom odabira skupa podataka o klijentima.":::

1. <span data-ttu-id="e8eb5-124">Izaberite **Sledeće** i definišite koji tip polja iz vaših objedinjenih profila treba koristiti za traženje odgovarajućih demografskih podataka iz usluge Experian.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="e8eb5-125">Obavezno je barem jedno od polja **Ime i adresa**, **Telefon** ili **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="e8eb5-126">Za veću preciznost podudaranja, mogu se dodati još dva polja.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="e8eb5-127">Ovaj izbor će uticati na polja za mapiranje kojima imate pristup u sledećem koraku.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="e8eb5-128">Više atributa ključnih identifikatora poslatih u Experian verovatno daje veću stopu podudaranja.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="e8eb5-129">Izaberite **Sledeće** da biste započeli mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="e8eb5-130">Definišite koji tip polja iz vaših objedinjenih profila treba koristiti za traženje odgovarajućih demografskih podataka iz usluge Experian.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="e8eb5-131">Obavezna polja su označena.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-131">Required fields are marked.</span></span>

1. <span data-ttu-id="e8eb5-132">Obezbedite naziv za obogaćivanje i naziv za izlazni entitet.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="e8eb5-133">Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="e8eb5-134">Konfigurišite vezu za Experian</span><span class="sxs-lookup"><span data-stu-id="e8eb5-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="e8eb5-135">Morate biti administrator da biste konfigurisali veze.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="e8eb5-136">Izaberite **Dodaj vezu** prilikom konfigurisanja obogaćivanja *ili* idite na **Administrator** > **Veze** i izaberite **Podešavanje** na pločici Experian.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="e8eb5-137">Izaberite **Prvi koraci**.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="e8eb5-138">Unesite naziv veze u polje **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="e8eb5-139">Unesite važeći ID korisnika, ID stranke i broj modela za svoj nalog za Experian bezbedni transport.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="e8eb5-140">Pregledajte i dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**</span><span class="sxs-lookup"><span data-stu-id="e8eb5-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="e8eb5-141">Izaberite **Verifikuj** da biste proverili valjanost konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="e8eb5-142">Po završetku verifikacije, izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Okno za konfiguraciju veze za Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="e8eb5-144">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="e8eb5-144">Enrichment results</span></span>

<span data-ttu-id="e8eb5-145">Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e8eb5-146">Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e8eb5-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e8eb5-147">Vreme obrade zavisiće od veličine vaših podataka o klijentima i procesa obogaćivanja koje je za vaš nalog podesio Experian.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="e8eb5-148">Nakon završetka procesa obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod opcijom **Moja obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="e8eb5-149">Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e8eb5-150">Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e8eb5-151">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="e8eb5-151">Next steps</span></span>

<span data-ttu-id="e8eb5-152">Nadogradite na obogaćenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e8eb5-153">Kreirajte [segmente](segments.md), [mere](measures.md), pa čak i [izvezite podatke](export-destinations.md) da biste pružili personalizovana iskustva svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e8eb5-154">Privatnost podataka i usaglašenost</span><span class="sxs-lookup"><span data-stu-id="e8eb5-154">Data privacy and compliance</span></span>

<span data-ttu-id="e8eb5-155">Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Experian, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e8eb5-156">Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Experian ispunjava sve obaveze privatnosti ili bezbednosti koje imate.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e8eb5-157">Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e8eb5-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e8eb5-158">Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.</span><span class="sxs-lookup"><span data-stu-id="e8eb5-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
