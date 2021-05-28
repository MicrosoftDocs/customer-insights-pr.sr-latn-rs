---
title: Izvezite Customer Insights podatke u Dynamics 365 Sales
description: Saznajte kako da konfigurišete vezu i izvezete u Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976243"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="52c66-103">Korišćenje segmenata u usluzi Dynamics 365 Sales (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="52c66-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="52c66-104">Koristite podatke o klijentima da biste kreirali marketinške spiskove, pratili tokove posla i slali promocije sa uslugom Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="52c66-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="52c66-105">Preduslov za vezu</span><span class="sxs-lookup"><span data-stu-id="52c66-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="52c66-106">Zapisi kontakata moraju biti prisutni u usluzi Dynamics 365 Sales da biste mogli da izvezete segment iz usluge Customer Insights u Sales.</span><span class="sxs-lookup"><span data-stu-id="52c66-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="52c66-107">Pročitajte više o tome kako se unose kontakti u [Dynamics 365 Sales pomoću usluge Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="52c66-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="52c66-108">Izvoz segmenata iz uvida o korisnicima u Sales neće kreirati nove zapise kontakata u instancama usluge Sales.</span><span class="sxs-lookup"><span data-stu-id="52c66-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="52c66-109">Evidencija kontakata iz usluge Sales mora se uneti u uvid o korisnicima i koristiti kao izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="52c66-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="52c66-110">Takođe ih treba uključiti u jedinstveni entitet klijenta da bi se ID-ovi klijenata mapirali u ID-ove kontakata da bi segmenti mogli da se izvezu.</span><span class="sxs-lookup"><span data-stu-id="52c66-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="52c66-111">Podešavanje veze sa uslugom Sales</span><span class="sxs-lookup"><span data-stu-id="52c66-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="52c66-112">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="52c66-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="52c66-113">Izaberite **Dodaj vezu** i birajte **Dynamics 365 Sales** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="52c66-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="52c66-114">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="52c66-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="52c66-115">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="52c66-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="52c66-116">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="52c66-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="52c66-117">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="52c66-117">Choose who can use this connection.</span></span> <span data-ttu-id="52c66-118">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="52c66-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="52c66-119">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="52c66-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="52c66-120">Unesite URL organizacije za Sales u polje **Adresa servera**.</span><span class="sxs-lookup"><span data-stu-id="52c66-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="52c66-121">U odeljku **Administratorski nalog na serveru**, izaberite **Prijavite se** i izaberite Dynamics 365 Sales nalog.</span><span class="sxs-lookup"><span data-stu-id="52c66-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="52c66-122">Mapirajte polje korisničkog ID-a sa Dynamics 365 ID-om kontakta.</span><span class="sxs-lookup"><span data-stu-id="52c66-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="52c66-123">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="52c66-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="52c66-124">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="52c66-124">Configure an export</span></span>

<span data-ttu-id="52c66-125">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="52c66-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="52c66-126">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="52c66-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="52c66-127">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="52c66-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="52c66-128">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="52c66-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="52c66-129">U polju **Veza za izvoz**, odaberite vezu iz odeljka Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="52c66-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="52c66-130">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="52c66-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="52c66-131">Izaberite jedan ili više segmenata.</span><span class="sxs-lookup"><span data-stu-id="52c66-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="52c66-132">Izaberite stavku **Sačuvaj**</span><span class="sxs-lookup"><span data-stu-id="52c66-132">Select **Save**</span></span>

<span data-ttu-id="52c66-133">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="52c66-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="52c66-134">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="52c66-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="52c66-135">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="52c66-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
