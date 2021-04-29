---
title: Izvezite Customer Insights podatke u Dynamics 365 Marketing
description: Saznajte kako da konfigurišete vezu i izvezete u Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759654"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="86a37-103">Korišćenje segmenata u usluzi Dynamics 365 Marketing (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="86a37-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="86a37-104">Koristite [segmente](segments.md) da biste generisali kampanje i kontaktirali određene grupe klijenata pomoću usluge Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="86a37-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="86a37-105">Više informacija potražite u članku [Korišćenje segmenata iz usluga Dynamics 365 Customer Insights uz Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="86a37-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="86a37-106">Preduslov za vezu</span><span class="sxs-lookup"><span data-stu-id="86a37-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="86a37-107">Zapisi kontakata moraju biti prisutni u usluzi Dynamics 365 Marketing da biste mogli da izvezete segment iz usluge Customer Insights u Marketing.</span><span class="sxs-lookup"><span data-stu-id="86a37-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="86a37-108">Pročitajte više o tome kako se unose kontakti u [Dynamics 365 Marketing pomoću usluge Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="86a37-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="86a37-109">Izvoz segmenata iz uvida o korisnicima u Marketing neće kreirati nove zapise kontakata u instancama usluge Marketing.</span><span class="sxs-lookup"><span data-stu-id="86a37-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="86a37-110">Evidencija kontakata iz usluge Marketing mora se uneti u uvid o korisnicima i koristiti kao izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="86a37-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="86a37-111">Takođe ih treba uključiti u jedinstveni entitet klijenta da bi se ID-ovi klijenata mapirali u ID-ove kontakata da bi segmenti mogli da se izvezu.</span><span class="sxs-lookup"><span data-stu-id="86a37-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="86a37-112">Podešavanje veze za Marketing</span><span class="sxs-lookup"><span data-stu-id="86a37-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="86a37-113">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="86a37-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="86a37-114">Izaberite **Dodaj vezu** i birajte **Dynamics 365 Marketing** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="86a37-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="86a37-115">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="86a37-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="86a37-116">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="86a37-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="86a37-117">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="86a37-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="86a37-118">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="86a37-118">Choose who can use this connection.</span></span> <span data-ttu-id="86a37-119">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="86a37-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="86a37-120">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="86a37-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="86a37-121">Unesite URL organizacije za Marketing u polje **Adresa servera**.</span><span class="sxs-lookup"><span data-stu-id="86a37-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="86a37-122">U odeljku **Administratorski nalog na serveru**, izaberite **Prijavite se** i izaberite Dynamics 365 Marketing nalog.</span><span class="sxs-lookup"><span data-stu-id="86a37-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="86a37-123">Mapirajte polje korisničkog ID-a sa Dynamics 365 ID-om kontakta.</span><span class="sxs-lookup"><span data-stu-id="86a37-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="86a37-124">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="86a37-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="86a37-125">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="86a37-125">Configure an export</span></span>

<span data-ttu-id="86a37-126">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="86a37-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="86a37-127">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="86a37-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="86a37-128">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="86a37-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="86a37-129">Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.</span><span class="sxs-lookup"><span data-stu-id="86a37-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="86a37-130">U polju **Veza za izvoz**, odaberite vezu iz odeljka Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="86a37-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="86a37-131">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="86a37-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="86a37-132">Izaberite jedan ili više segmenata.</span><span class="sxs-lookup"><span data-stu-id="86a37-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="86a37-133">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="86a37-133">Select **Save**.</span></span>

<span data-ttu-id="86a37-134">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="86a37-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="86a37-135">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="86a37-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="86a37-136">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="86a37-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
