---
title: Izvezite Customer Insights podatke u Dynamics 365 Sales
description: Saznajte kako da konfigurišete vezu sa uslugom Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598126"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="e488d-103">Konektor za Dynamics 365 Sales (pregled)</span><span class="sxs-lookup"><span data-stu-id="e488d-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e488d-104">Koristite podatke o klijentima da biste kreirali marketinške spiskove, pratili tokove posla i slali promocije sa uslugom Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="e488d-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="e488d-105">Preduslov</span><span class="sxs-lookup"><span data-stu-id="e488d-105">Prerequisite</span></span>

1. <span data-ttu-id="e488d-106">Zapisi kontakata moraju biti prisutni u usluzi Dynamics 365 Sales da biste mogli da izvezete segment iz usluge Customer Insights u Sales.</span><span class="sxs-lookup"><span data-stu-id="e488d-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="e488d-107">Pročitajte više o tome kako se unose kontakti u [Dynamics 365 Sales pomoću usluge Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="e488d-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="e488d-108">Izvoz segmenata iz uvida o korisnicima u Sales neće kreirati nove zapise kontakata u instancama usluge Sales.</span><span class="sxs-lookup"><span data-stu-id="e488d-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="e488d-109">Evidencija kontakata iz usluge Sales mora se uneti u uvid o korisnicima i koristiti kao izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="e488d-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="e488d-110">Takođe ih treba uključiti u jedinstveni entitet klijenta da bi se ID-ovi klijenata mapirali u ID-ove kontakata da bi segmenti mogli da se izvezu.</span><span class="sxs-lookup"><span data-stu-id="e488d-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="e488d-111">Konfigurišite konektor za Sales</span><span class="sxs-lookup"><span data-stu-id="e488d-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="e488d-112">U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="e488d-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e488d-113">U odeljku **Dynamics 365 Sales** izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="e488d-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="e488d-114">Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="e488d-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e488d-115">Unesite URL organizacije za Sales u polje **Adresa servera**.</span><span class="sxs-lookup"><span data-stu-id="e488d-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="e488d-116">U odeljku **Administratorski nalog na serveru**, izaberite **Prijavite se** i izaberite Dynamics 365 Sales nalog.</span><span class="sxs-lookup"><span data-stu-id="e488d-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="e488d-117">Mapirajte polje korisničkog ID-a sa Dynamics 365 ID-om kontakta.</span><span class="sxs-lookup"><span data-stu-id="e488d-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="e488d-118">Izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="e488d-118">Select **Next**.</span></span>

1. <span data-ttu-id="e488d-119">Izaberite jedan ili više segmenata.</span><span class="sxs-lookup"><span data-stu-id="e488d-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="e488d-120">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="e488d-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e488d-121">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="e488d-121">Export the data</span></span>

<span data-ttu-id="e488d-122">Možete da [izvezete podatke na zahtev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e488d-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e488d-123">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e488d-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]