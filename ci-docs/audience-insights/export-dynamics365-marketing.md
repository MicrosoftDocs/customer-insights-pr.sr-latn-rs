---
title: Izvezite Customer Insights podatke u Dynamics 365 Marketing
description: Saznajte kako da konfigurišete vezu sa uslugom Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643790"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="c59d9-103">Konektor za Dynamics 365 Marketing (pregled)</span><span class="sxs-lookup"><span data-stu-id="c59d9-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c59d9-104">Koristite [segmente](segments.md) da biste generisali kampanje i kontaktirali određene grupe klijenata pomoću usluge Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="c59d9-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="c59d9-105">Više informacija potražite u članku [Korišćenje segmenata iz usluga Dynamics 365 Customer Insights uz Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="c59d9-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="c59d9-106">Preduslov</span><span class="sxs-lookup"><span data-stu-id="c59d9-106">Prerequisite</span></span>

<span data-ttu-id="c59d9-107">Zapisi kontakata [iz Dynamics 365 Marketing uneti pomoću usluge Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="c59d9-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="c59d9-108">Konfigurišite konektor za Marketing</span><span class="sxs-lookup"><span data-stu-id="c59d9-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="c59d9-109">U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="c59d9-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c59d9-110">U odeljku **Dynamics 365 Marketing** izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="c59d9-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="c59d9-111">Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="c59d9-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c59d9-112">Unesite URL organizacije za Marketing u polje **Adresa servera**.</span><span class="sxs-lookup"><span data-stu-id="c59d9-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="c59d9-113">U odeljku **Administratorski nalog na serveru**, izaberite **Prijavite se** i izaberite Dynamics 365 Marketing nalog.</span><span class="sxs-lookup"><span data-stu-id="c59d9-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="c59d9-114">Mapirajte polje korisničkog ID-a sa Dynamics 365 ID-om kontakta.</span><span class="sxs-lookup"><span data-stu-id="c59d9-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="c59d9-115">Izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="c59d9-115">Select **Next**.</span></span>

1. <span data-ttu-id="c59d9-116">Izaberite jedan ili više segmenata.</span><span class="sxs-lookup"><span data-stu-id="c59d9-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="c59d9-117">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="c59d9-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c59d9-118">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="c59d9-118">Export the data</span></span>

<span data-ttu-id="c59d9-119">Možete da [izvezete podatke na zahtev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c59d9-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c59d9-120">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c59d9-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
