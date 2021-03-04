---
title: Izvezite Customer Insights podatke u Dynamics 365 Marketing
description: Saznajte kako da konfigurišete vezu sa uslugom Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269071"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="c6910-103">Konektor za Dynamics 365 Marketing (pregled)</span><span class="sxs-lookup"><span data-stu-id="c6910-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c6910-104">Koristite [segmente](segments.md) da biste generisali kampanje i kontaktirali određene grupe klijenata pomoću usluge Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="c6910-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="c6910-105">Više informacija potražite u članku [Korišćenje segmenata iz usluga Dynamics 365 Customer Insights uz Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="c6910-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="c6910-106">Preduslov</span><span class="sxs-lookup"><span data-stu-id="c6910-106">Prerequisite</span></span>

- <span data-ttu-id="c6910-107">Zapisi kontakata moraju biti prisutni u usluzi Dynamics 365 Marketing da biste mogli da izvezete segment iz usluge Customer Insights u Marketing.</span><span class="sxs-lookup"><span data-stu-id="c6910-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="c6910-108">Pročitajte više o tome kako se unose kontakti u [Dynamics 365 Marketing pomoću usluge Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="c6910-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="c6910-109">Izvoz segmenata iz uvida o korisnicima u Marketing neće kreirati nove zapise kontakata u instancama usluge Marketing.</span><span class="sxs-lookup"><span data-stu-id="c6910-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="c6910-110">Evidencija kontakata iz usluge Marketing mora se uneti u uvid o korisnicima i koristiti kao izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="c6910-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="c6910-111">Takođe ih treba uključiti u jedinstveni entitet klijenta da bi se ID-ovi klijenata mapirali u ID-ove kontakata da bi segmenti mogli da se izvezu.</span><span class="sxs-lookup"><span data-stu-id="c6910-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="c6910-112">Konfigurišite konektor za Marketing</span><span class="sxs-lookup"><span data-stu-id="c6910-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="c6910-113">U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="c6910-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c6910-114">U odeljku **Dynamics 365 Marketing** izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="c6910-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="c6910-115">Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="c6910-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c6910-116">Unesite URL organizacije za Marketing u polje **Adresa servera**.</span><span class="sxs-lookup"><span data-stu-id="c6910-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="c6910-117">U odeljku **Administratorski nalog na serveru**, izaberite **Prijavite se** i izaberite Dynamics 365 Marketing nalog.</span><span class="sxs-lookup"><span data-stu-id="c6910-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="c6910-118">Mapirajte polje korisničkog ID-a sa Dynamics 365 ID-om kontakta.</span><span class="sxs-lookup"><span data-stu-id="c6910-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="c6910-119">Izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="c6910-119">Select **Next**.</span></span>

1. <span data-ttu-id="c6910-120">Izaberite jedan ili više segmenata.</span><span class="sxs-lookup"><span data-stu-id="c6910-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="c6910-121">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="c6910-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c6910-122">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="c6910-122">Export the data</span></span>

<span data-ttu-id="c6910-123">Možete da [izvezete podatke na zahtev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c6910-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c6910-124">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c6910-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]