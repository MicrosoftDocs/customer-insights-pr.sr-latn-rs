---
title: Izvezite Customer Insights podatke u Dynamics 365 Marketing
description: Saznajte kako da konfigurišete vezu sa uslugom Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597620"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="b4bf1-103">Konektor za Dynamics 365 Marketing (pregled)</span><span class="sxs-lookup"><span data-stu-id="b4bf1-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b4bf1-104">Koristite [segmente](segments.md) da biste generisali kampanje i kontaktirali određene grupe klijenata pomoću usluge Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="b4bf1-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="b4bf1-105">Više informacija potražite u članku [Korišćenje segmenata iz usluga Dynamics 365 Customer Insights uz Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="b4bf1-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="b4bf1-106">Preduslov</span><span class="sxs-lookup"><span data-stu-id="b4bf1-106">Prerequisite</span></span>

- <span data-ttu-id="b4bf1-107">Zapisi kontakata moraju biti prisutni u usluzi Dynamics 365 Marketing da biste mogli da izvezete segment iz usluge Customer Insights u Marketing.</span><span class="sxs-lookup"><span data-stu-id="b4bf1-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="b4bf1-108">Pročitajte više o tome kako se unose kontakti u [Dynamics 365 Marketing pomoću usluge Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b4bf1-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="b4bf1-109">Izvoz segmenata iz uvida o korisnicima u Marketing neće kreirati nove zapise kontakata u instancama usluge Marketing.</span><span class="sxs-lookup"><span data-stu-id="b4bf1-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="b4bf1-110">Evidencija kontakata iz usluge Marketing mora se uneti u uvid o korisnicima i koristiti kao izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="b4bf1-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="b4bf1-111">Takođe ih treba uključiti u jedinstveni entitet klijenta da bi se ID-ovi klijenata mapirali u ID-ove kontakata da bi segmenti mogli da se izvezu.</span><span class="sxs-lookup"><span data-stu-id="b4bf1-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="b4bf1-112">Konfigurišite konektor za Marketing</span><span class="sxs-lookup"><span data-stu-id="b4bf1-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="b4bf1-113">U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="b4bf1-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b4bf1-114">U odeljku **Dynamics 365 Marketing** izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="b4bf1-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="b4bf1-115">Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="b4bf1-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b4bf1-116">Unesite URL organizacije za Marketing u polje **Adresa servera**.</span><span class="sxs-lookup"><span data-stu-id="b4bf1-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="b4bf1-117">U odeljku **Administratorski nalog na serveru**, izaberite **Prijavite se** i izaberite Dynamics 365 Marketing nalog.</span><span class="sxs-lookup"><span data-stu-id="b4bf1-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="b4bf1-118">Mapirajte polje korisničkog ID-a sa Dynamics 365 ID-om kontakta.</span><span class="sxs-lookup"><span data-stu-id="b4bf1-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="b4bf1-119">Izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="b4bf1-119">Select **Next**.</span></span>

1. <span data-ttu-id="b4bf1-120">Izaberite jedan ili više segmenata.</span><span class="sxs-lookup"><span data-stu-id="b4bf1-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="b4bf1-121">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="b4bf1-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b4bf1-122">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="b4bf1-122">Export the data</span></span>

<span data-ttu-id="b4bf1-123">Možete da [izvezete podatke na zahtev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b4bf1-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b4bf1-124">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b4bf1-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]