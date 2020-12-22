---
title: Izvezite Customer Insights podatke u Dynamics 365 Sales
description: Saznajte kako da konfigurišete vezu sa uslugom Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643835"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="7e343-103">Konektor za Dynamics 365 Sales (pregled)</span><span class="sxs-lookup"><span data-stu-id="7e343-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="7e343-104">Koristite podatke o klijentima da biste kreirali marketinške spiskove, pratili tokove posla i slali promocije sa uslugom Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="7e343-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="7e343-105">Preduslov</span><span class="sxs-lookup"><span data-stu-id="7e343-105">Prerequisite</span></span>

<span data-ttu-id="7e343-106">Zapisi kontakata [iz Dynamics 365 Sales unetih pomoću usluge Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="7e343-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="7e343-107">Konfigurišite konektor za Sales</span><span class="sxs-lookup"><span data-stu-id="7e343-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="7e343-108">U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="7e343-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7e343-109">U odeljku **Dynamics 365 Sales** izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="7e343-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="7e343-110">Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="7e343-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7e343-111">Unesite URL organizacije za Sales u polje **Adresa servera**.</span><span class="sxs-lookup"><span data-stu-id="7e343-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="7e343-112">U odeljku **Administratorski nalog na serveru**, izaberite **Prijavite se** i izaberite Dynamics 365 Sales nalog.</span><span class="sxs-lookup"><span data-stu-id="7e343-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="7e343-113">Mapirajte polje korisničkog ID-a sa Dynamics 365 ID-om kontakta.</span><span class="sxs-lookup"><span data-stu-id="7e343-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="7e343-114">Izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="7e343-114">Select **Next**.</span></span>

1. <span data-ttu-id="7e343-115">Izaberite jedan ili više segmenata.</span><span class="sxs-lookup"><span data-stu-id="7e343-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="7e343-116">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="7e343-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7e343-117">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="7e343-117">Export the data</span></span>

<span data-ttu-id="7e343-118">Možete da [izvezete podatke na zahtev](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="7e343-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="7e343-119">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7e343-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
