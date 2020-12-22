---
title: Instalirajte i konfigurišite Dodatak za karticu klijenta
description: Instalirajte i konfigurišite dodatak za karticu klijenta za Dynamics 365 Customer Insights.
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644060"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="94438-103">Dodatak za karticu klijenta (pregled)</span><span class="sxs-lookup"><span data-stu-id="94438-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="94438-104">Steknite pregled svojih klijenata od 360 stepeni direktno u Dynamics 365 aplikacijama.</span><span class="sxs-lookup"><span data-stu-id="94438-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="94438-105">Prikažite demografske podatke, uvide i vremenske rokove aktivnosti pomoću dodatka kartice klijenta.</span><span class="sxs-lookup"><span data-stu-id="94438-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94438-106">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="94438-106">Prerequisites</span></span>

- <span data-ttu-id="94438-107">Aplikacija Dynamics 365 (kao što je Čvorište za prodaju ili čvorište korisničke službe), verzije 9.0 i novije sa omogućenim objedinjenim interfejsom.</span><span class="sxs-lookup"><span data-stu-id="94438-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="94438-108">Profili klijenata [uneti iz aplikacije Dynamics 365 pomoću usluge Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="94438-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="94438-109">Korisnici Dodatka za karticu klijenta moraju biti [dodati kao korisnici](permissions.md) u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="94438-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="94438-110">[Konfigurisane mogućnosti pretraživanja i filtriranja](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="94438-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="94438-111">Demografska kontrola: Demografska polja, kao što su starost ili pol, dostupna su u objedinjenom profilu klijenata.</span><span class="sxs-lookup"><span data-stu-id="94438-111">Demographic control: Demographic fields, such as age or gender are available in the unified customer profile.</span></span>
- <span data-ttu-id="94438-112">Kontrola obogaćivanja: Zahteva da se aktivna [obogaćivanja](enrichment-hub.md) primene se na profile klijenata.</span><span class="sxs-lookup"><span data-stu-id="94438-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="94438-113">Kontrola obaveštavanja: Zahteva podatke generisane pomoću Azure mašinskog učenja ([predviđanja](predictions.md) ili [prilagođeni modeli](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="94438-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="94438-114">Kontrola mere: Zahteva [konfigurisane mere](measures.md).</span><span class="sxs-lookup"><span data-stu-id="94438-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="94438-115">Kontrola vremenske linije: Zahteva[ konfigurisane aktivnosti](activities.md).</span><span class="sxs-lookup"><span data-stu-id="94438-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="94438-116">Instalirajte i koristite dodatak za karticu klijenta</span><span class="sxs-lookup"><span data-stu-id="94438-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="94438-117">Programski dodatak za karticu klijenta je rešenje za Customer Engagement aplikacije u sistemu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="94438-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="94438-118">Da biste instalirali rešenje, idite na AppSource i potražite **Dynamics karticu klijenta**.</span><span class="sxs-lookup"><span data-stu-id="94438-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="94438-119">Izaberite [dodatak za karticu klijenta u usluzi AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i izaberite **Preuzmi odmah**.</span><span class="sxs-lookup"><span data-stu-id="94438-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="94438-120">Možda ćete morati da se prijavite pomoću akreditiva administratora za aplikaciju Dynamics 365 da biste instalirali rešenje.</span><span class="sxs-lookup"><span data-stu-id="94438-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="94438-121">Možda će biti potrebno neko vreme da se rešenje instalira u vaše okruženje.</span><span class="sxs-lookup"><span data-stu-id="94438-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="94438-122">Konfigurisanje dodatka klijentske kartice</span><span class="sxs-lookup"><span data-stu-id="94438-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="94438-123">Kao administrator, idite u odeljak **Podešavanja** u sistemu Dynamics 365 i izaberite **Rešenja**.</span><span class="sxs-lookup"><span data-stu-id="94438-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="94438-124">Izaberite vezu **Ime za prikaz** za rešenje **Dynamics 365 Customer Insights dodatak klijentske kartice (pregled)**.</span><span class="sxs-lookup"><span data-stu-id="94438-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="94438-125">![Izaberite ime za prikaz](media/select-display-name.png "Izaberite ime za prikaz")</span><span class="sxs-lookup"><span data-stu-id="94438-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="94438-126">Izaberite **Prijavljivanje** i unesite akreditive za nalog administratora koji koristite za konfigurisanje usluge Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="94438-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="94438-127">Proverite da li blokator iskačućih prozora pregledača ne blokira prozor za potvrdu identiteta kada izaberete dugme **Prijavljivanje**.</span><span class="sxs-lookup"><span data-stu-id="94438-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="94438-128">Izaberite okruženje iz kojeg želite da preuzmete podatke.</span><span class="sxs-lookup"><span data-stu-id="94438-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="94438-129">Definišite koje se mapiranje polja snima u aplikaciji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="94438-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="94438-130">Da biste mapirali kontakt, odaberite polje u entitetu klijenta koje se podudara sa ID-om vašeg entiteta kontakta.</span><span class="sxs-lookup"><span data-stu-id="94438-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="94438-131">Da biste mapirali poslovni kontakt, odaberite polje u entitetu klijenta koje se podudara sa ID-om vašeg entiteta poslovnog kontakta.</span><span class="sxs-lookup"><span data-stu-id="94438-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="94438-132">![Polje ID kontakta](media/contact-id-field.png "Polje ID kontakta")</span><span class="sxs-lookup"><span data-stu-id="94438-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="94438-133">Izaberite **Sačuvaj konfiguraciju** da biste sačuvali podešavanja.</span><span class="sxs-lookup"><span data-stu-id="94438-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="94438-134">Zatim treba da dodelite bezbednosne uloge u sistemu Dynamics 365 kako bi korisnici mogli da prilagođavaju i vide korisničku karticu.</span><span class="sxs-lookup"><span data-stu-id="94438-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="94438-135">U sistemu Dynamics 365, idite na **Podešavanja** > **Bezbednost** > **Korisnici**.</span><span class="sxs-lookup"><span data-stu-id="94438-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="94438-136">Izaberite korisnike da biste izmenili korisničke uloge i izaberite **Upravljaj ulogama**.</span><span class="sxs-lookup"><span data-stu-id="94438-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="94438-137">Dodelite ulogu **Stručnjak za prilagođavanje Customer Insights kartica** korisnicima koji će za celu organizaciju prilagođavati sadržaj prikazan na kartici.</span><span class="sxs-lookup"><span data-stu-id="94438-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="94438-138">Dodajte kontrole kartice klijenta u obrasce</span><span class="sxs-lookup"><span data-stu-id="94438-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="94438-139">Da biste dodali kontrole kartice klijenta u obrazac za kontakt, idite na **Podešavanja** > **Prilagođavanja** u Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="94438-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="94438-140">Izaberite **Prilagodi sistem**.</span><span class="sxs-lookup"><span data-stu-id="94438-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="94438-141">Dođite do entiteta **Kontakt**, proširite ga, a zatim izaberite **Obrasci**.</span><span class="sxs-lookup"><span data-stu-id="94438-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="94438-142">Izaberite obrazac kontakta na koji želite da dodate kontrole kartice klijenta.</span><span class="sxs-lookup"><span data-stu-id="94438-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="94438-143">![Izbor obrasca Kontakta](media/contact-active-forms.png "Izbor obrasca Kontakta")</span><span class="sxs-lookup"><span data-stu-id="94438-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="94438-144">Da biste dodali kontrolu, u uređivaču obrazaca prevucite bilo koje polje iz **Istraživača polja** tamo gde želite da se kontrola prikazuje.</span><span class="sxs-lookup"><span data-stu-id="94438-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="94438-145">Izaberite polje na obrascu koje ste upravo dodali, a zatim izaberite **Promeni svojstva**.</span><span class="sxs-lookup"><span data-stu-id="94438-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="94438-146">Idite do kartice **Kontrole** i izaberite **Dodaj kontrolu**.</span><span class="sxs-lookup"><span data-stu-id="94438-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="94438-147">Izaberite neku od dostupnih prilagođenih kontrola i izaberite **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="94438-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="94438-148">U dijalogu **Svojstva polja**, obrišite polje za potvrdu **Prikažite oznaku na obrascu**.</span><span class="sxs-lookup"><span data-stu-id="94438-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="94438-149">Izaberite opciju **Veb** za kontrolu.</span><span class="sxs-lookup"><span data-stu-id="94438-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="94438-150">Za kontrolu obogaćivanja izaberite tip obogaćivanja koji želite da prikažete konfigurisanjem polja **Tip obogaćivanja**.</span><span class="sxs-lookup"><span data-stu-id="94438-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="94438-151">Morate dodati posebnu kontrolu obogaćivanja za svaki tip obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="94438-151">You need to add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="94438-152">Izaberite **Sačuvaj** i **Objavi** da biste objavili ažurirani obrazac za kontakt.</span><span class="sxs-lookup"><span data-stu-id="94438-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="94438-153">Idite na objavljeni obrazac kontakta.</span><span class="sxs-lookup"><span data-stu-id="94438-153">Go to the published contact form.</span></span> <span data-ttu-id="94438-154">Videćete novododatu kontrolu.</span><span class="sxs-lookup"><span data-stu-id="94438-154">You'll see the newly added control.</span></span> <span data-ttu-id="94438-155">Možda ćete morati da se prijavite prilikom prvog korišćenja.</span><span class="sxs-lookup"><span data-stu-id="94438-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="94438-156">Da biste prilagodili šta želite da prikažete na prilagođenoj kontroli, izaberite dugme za uređivanje u gornjem desnom uglu.</span><span class="sxs-lookup"><span data-stu-id="94438-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>
