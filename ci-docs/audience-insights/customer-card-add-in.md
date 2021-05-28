---
title: Programski dodatak za karticu klijenta za Dynamics 365 aplikacije
description: Prikažite podatke iz uvida u ciljnu grupu u Dynamics 365 aplikacijama sa ovim programskim dodatkom.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059605"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="bbb62-103">Dodatak za karticu klijenta (pregled)</span><span class="sxs-lookup"><span data-stu-id="bbb62-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bbb62-104">Steknite pregled svojih klijenata od 360 stepeni direktno u Dynamics 365 aplikacijama.</span><span class="sxs-lookup"><span data-stu-id="bbb62-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="bbb62-105">Kada je programski dodatak za klijentsku karticu instaliran u podržanoj Dynamics 365 aplikaciji, možete odabrati da prikazujete demografske podatke, uvide i vremenske ose aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="bbb62-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="bbb62-106">Programski dodatak će preuzeti podatke iz usluge Customer Insights bez uticaja na podatke u povezanoj Dynamics 365 aplikaciji.</span><span class="sxs-lookup"><span data-stu-id="bbb62-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="bbb62-107">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="bbb62-107">Prerequisites</span></span>

- <span data-ttu-id="bbb62-108">Programski dodatak radi samo sa Dynamics 365 aplikacijama zasnovanim na modelu, kao što su Sales ili Customer Service, verzije 9.0 i novije.</span><span class="sxs-lookup"><span data-stu-id="bbb62-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="bbb62-109">Da bi se vaši Dynamics 365 podaci mapirali u korisničke profile uvida u ciljnu grupu, oni treba da budu [uneti iz Dynamics 365 aplikacije pomoću Common Data Service konektora](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="bbb62-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="bbb62-110">Svi Dynamics 365 korisnici programskog dodatka za kartice klijenta moraju biti [dodati kao korisnici](permissions.md) u uvidima u ciljnu grupu da biste videli podatke.</span><span class="sxs-lookup"><span data-stu-id="bbb62-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="bbb62-111">[Konfigurisane mogućnosti pretrage i filtriranja](search-filter-index.md) u uvidima u ciljnu grupu su potrebne da bi pronalaženje podataka funkcionisalo.</span><span class="sxs-lookup"><span data-stu-id="bbb62-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="bbb62-112">Svaka kontrola programskog dodatka oslanja se na određene podatke u uvidima u ciljnu grupu:</span><span class="sxs-lookup"><span data-stu-id="bbb62-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="bbb62-113">Kontrola mere: Zahteva [konfigurisane mere](measures.md).</span><span class="sxs-lookup"><span data-stu-id="bbb62-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="bbb62-114">Kontrola obaveštavanja: Zahteva podatke generisane korišćenjem [predviđanja](predictions.md) ili [prilagođenih modela](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="bbb62-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="bbb62-115">Demografska kontrola: Demografska polja (kao što su starost ili pol) dostupna su u objedinjenom profilu klijenta.</span><span class="sxs-lookup"><span data-stu-id="bbb62-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="bbb62-116">Kontrola obogaćivanja: Zahteva da se aktivna [obogaćivanja](enrichment-hub.md) primene se na profile klijenata.</span><span class="sxs-lookup"><span data-stu-id="bbb62-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="bbb62-117">Kontrola vremenske linije: Zahteva[ konfigurisane aktivnosti](activities.md).</span><span class="sxs-lookup"><span data-stu-id="bbb62-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="bbb62-118">Instalirajte i koristite dodatak za karticu klijenta</span><span class="sxs-lookup"><span data-stu-id="bbb62-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="bbb62-119">Programski dodatak za karticu klijenta je rešenje za Customer Engagement aplikacije u sistemu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="bbb62-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="bbb62-120">Da biste instalirali rešenje, idite na AppSource i potražite **Dynamics karticu klijenta**.</span><span class="sxs-lookup"><span data-stu-id="bbb62-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="bbb62-121">Izaberite [dodatak za karticu klijenta u usluzi AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i izaberite **Preuzmi odmah**.</span><span class="sxs-lookup"><span data-stu-id="bbb62-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="bbb62-122">Možda ćete morati da se prijavite pomoću akreditiva administratora za aplikaciju Dynamics 365 da biste instalirali rešenje.</span><span class="sxs-lookup"><span data-stu-id="bbb62-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="bbb62-123">Možda će biti potrebno neko vreme da se rešenje instalira u vaše okruženje.</span><span class="sxs-lookup"><span data-stu-id="bbb62-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="bbb62-124">Konfigurisanje dodatka klijentske kartice</span><span class="sxs-lookup"><span data-stu-id="bbb62-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="bbb62-125">Kao administrator, idite u odeljak **Podešavanja** u sistemu Dynamics 365 i izaberite **Rešenja**.</span><span class="sxs-lookup"><span data-stu-id="bbb62-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="bbb62-126">Izaberite vezu **Ime za prikaz** za rešenje **Dynamics 365 Customer Insights dodatak klijentske kartice (pregled)**.</span><span class="sxs-lookup"><span data-stu-id="bbb62-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bbb62-127">![Izaberite ime za prikaz](media/select-display-name.png "Izaberite ime za prikaz")</span><span class="sxs-lookup"><span data-stu-id="bbb62-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="bbb62-128">Izaberite **Prijavljivanje** i unesite akreditive za nalog administratora koji koristite za konfigurisanje usluge Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bbb62-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bbb62-129">Proverite da li blokator iskačućih prozora pregledača ne blokira prozor za potvrdu identiteta kada izaberete dugme **Prijavljivanje**.</span><span class="sxs-lookup"><span data-stu-id="bbb62-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="bbb62-130">Izaberite instancu Customer Insights okruženja iz kojeg želite da preuzmete podatke.</span><span class="sxs-lookup"><span data-stu-id="bbb62-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="bbb62-131">Definišite mapiranje polja na zapise u Dynamics 365 aplikaciji.</span><span class="sxs-lookup"><span data-stu-id="bbb62-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="bbb62-132">U zavisnosti od vaših podataka u usluzi Customer Insights, možete odabrati da mapirate sledeće opcije:</span><span class="sxs-lookup"><span data-stu-id="bbb62-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="bbb62-133">Da biste mapirali kontakt, odaberite polje u entitetu klijenta koje se podudara sa ID-om vašeg entiteta kontakta.</span><span class="sxs-lookup"><span data-stu-id="bbb62-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="bbb62-134">Da biste mapirali poslovni kontakt, odaberite polje u entitetu klijenta koje se podudara sa ID-om vašeg entiteta poslovnog kontakta.</span><span class="sxs-lookup"><span data-stu-id="bbb62-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bbb62-135">![Polje ID kontakta](media/contact-id-field.png "Polje ID kontakta")</span><span class="sxs-lookup"><span data-stu-id="bbb62-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="bbb62-136">Izaberite **Sačuvaj konfiguraciju** da biste sačuvali podešavanja.</span><span class="sxs-lookup"><span data-stu-id="bbb62-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="bbb62-137">Zatim treba da dodelite bezbednosne uloge u sistemu Dynamics 365 kako bi korisnici mogli da prilagođavaju i vide korisničku karticu.</span><span class="sxs-lookup"><span data-stu-id="bbb62-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="bbb62-138">U sistemu Dynamics 365, idite na **Podešavanja** > **Bezbednost** > **Korisnici**.</span><span class="sxs-lookup"><span data-stu-id="bbb62-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="bbb62-139">Izaberite korisnike da biste izmenili korisničke uloge i izaberite **Upravljaj ulogama**.</span><span class="sxs-lookup"><span data-stu-id="bbb62-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="bbb62-140">Dodelite ulogu **Stručnjak za prilagođavanje Customer Insights kartica** korisnicima koji će za celu organizaciju prilagođavati sadržaj prikazan na kartici.</span><span class="sxs-lookup"><span data-stu-id="bbb62-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="bbb62-141">Dodajte kontrole kartice klijenta u obrasce</span><span class="sxs-lookup"><span data-stu-id="bbb62-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="bbb62-142">Da biste dodali kontrole kartice klijenta u obrazac za kontakt, idite na **Podešavanja** > **Prilagođavanja** u Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="bbb62-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="bbb62-143">Izaberite **Prilagodi sistem**.</span><span class="sxs-lookup"><span data-stu-id="bbb62-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="bbb62-144">Dođite do entiteta **Kontakt**, proširite ga, a zatim izaberite **Obrasci**.</span><span class="sxs-lookup"><span data-stu-id="bbb62-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="bbb62-145">Izaberite obrazac kontakta na koji želite da dodate kontrole kartice klijenta.</span><span class="sxs-lookup"><span data-stu-id="bbb62-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bbb62-146">![Izbor obrasca Kontakta](media/contact-active-forms.png "Izbor obrasca Kontakta")</span><span class="sxs-lookup"><span data-stu-id="bbb62-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="bbb62-147">Da biste dodali kontrolu, u uređivaču obrazaca prevucite bilo koje polje iz **Istraživača polja** tamo gde želite da se kontrola prikazuje.</span><span class="sxs-lookup"><span data-stu-id="bbb62-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="bbb62-148">Izaberite polje na obrascu koje ste upravo dodali, a zatim izaberite **Promeni svojstva**.</span><span class="sxs-lookup"><span data-stu-id="bbb62-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="bbb62-149">Idite do kartice **Kontrole** i izaberite **Dodaj kontrolu**.</span><span class="sxs-lookup"><span data-stu-id="bbb62-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="bbb62-150">Izaberite neku od dostupnih prilagođenih kontrola i izaberite **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="bbb62-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="bbb62-151">U dijalogu **Svojstva polja**, obrišite polje za potvrdu **Prikažite oznaku na obrascu**.</span><span class="sxs-lookup"><span data-stu-id="bbb62-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="bbb62-152">Izaberite opciju **Veb** za kontrolu.</span><span class="sxs-lookup"><span data-stu-id="bbb62-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="bbb62-153">Za kontrolu obogaćivanja izaberite tip obogaćivanja koji želite da prikažete konfigurisanjem polja **Tip obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="bbb62-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="bbb62-154">Dodajte zasebnu kontrolu obogaćivanja za svaku vrstu obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="bbb62-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="bbb62-155">Izaberite **Sačuvaj** i **Objavi** da biste objavili ažurirani obrazac za kontakt.</span><span class="sxs-lookup"><span data-stu-id="bbb62-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="bbb62-156">Idite na objavljeni obrazac kontakta.</span><span class="sxs-lookup"><span data-stu-id="bbb62-156">Go to the published contact form.</span></span> <span data-ttu-id="bbb62-157">Videćete novododatu kontrolu.</span><span class="sxs-lookup"><span data-stu-id="bbb62-157">You'll see the newly added control.</span></span> <span data-ttu-id="bbb62-158">Možda ćete morati da se prijavite prilikom prvog korišćenja.</span><span class="sxs-lookup"><span data-stu-id="bbb62-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="bbb62-159">Da biste prilagodili šta želite da prikažete na prilagođenoj kontroli, izaberite dugme za uređivanje u gornjem desnom uglu.</span><span class="sxs-lookup"><span data-stu-id="bbb62-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="bbb62-160">Nadogradnja programskog dodatka za karticu klijenta</span><span class="sxs-lookup"><span data-stu-id="bbb62-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="bbb62-161">Programski dodatak za korisničku karticu se ne nadograđuje automatski.</span><span class="sxs-lookup"><span data-stu-id="bbb62-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="bbb62-162">Da biste nadogradili na najnoviju verziju, sledite ovaj postupak u Dynamics 365 aplikaciji u kojoj je instaliran programski dodatak.</span><span class="sxs-lookup"><span data-stu-id="bbb62-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="bbb62-163">U Dynamics 365 aplikaciji idite na **Podešavanja** > **Prilagođavanje** i izaberite **Rešenja**.</span><span class="sxs-lookup"><span data-stu-id="bbb62-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="bbb62-164">U tabeli dodataka potražite **CustomerInsightsCustomerCard** i izaberite red.</span><span class="sxs-lookup"><span data-stu-id="bbb62-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="bbb62-165">Izaberite **Primeni nadogradnju rešenja** u traci sa radnjama.</span><span class="sxs-lookup"><span data-stu-id="bbb62-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Nadogradite rešenje u oblasti Prilagođavanje Dynamics 365 aplikacija":::

1. <span data-ttu-id="bbb62-167">Kada započnete proces nadogradnje, videćete indikator učitavanja dok se nadogradnja ne završi.</span><span class="sxs-lookup"><span data-stu-id="bbb62-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="bbb62-168">Ako nema novije verzije, nadogradnja će prikazati poruku o grešci.</span><span class="sxs-lookup"><span data-stu-id="bbb62-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
