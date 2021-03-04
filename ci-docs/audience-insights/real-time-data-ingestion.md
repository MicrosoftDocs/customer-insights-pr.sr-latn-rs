---
title: Unošenje podataka u realnom vremenu i ograničenja
description: Opšte informacije o mogućnostima u realnom vremenu u uvidima o korisnicima.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270297"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="97a8e-103">Unos podataka u realnom vremenu (pregled)</span><span class="sxs-lookup"><span data-stu-id="97a8e-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="97a8e-104">Funkcionalnost koja je skoro sasvim u stvarnom vremenu omogućava vam da u roku od nekoliko sekundi vidite najnovije interakcije koje su izvršili vaši klijenti sa vašim proizvodima ili uslugama.</span><span class="sxs-lookup"><span data-stu-id="97a8e-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="97a8e-105">[Zakazana osvežavanja](system.md#schedule-tab) uključuju veliki broj zapisa i nekoliko složenih operacija.</span><span class="sxs-lookup"><span data-stu-id="97a8e-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="97a8e-106">Prvo se podaci uzimaju iz izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="97a8e-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="97a8e-107">Zatim se podaci objedinjuju, a zatim obogaćuju dodatnim informacijama.</span><span class="sxs-lookup"><span data-stu-id="97a8e-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="97a8e-108">Svako pokretanje ovog postupka može trajati od nekoliko minuta do nekoliko sati.</span><span class="sxs-lookup"><span data-stu-id="97a8e-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="97a8e-109">Funkcionalnost u realnom vremenu pruža podatke koji se odmah mogu koristiti, sve dok naknadno planirano osvežavanje ne povuče ove podatke iz izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="97a8e-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="97a8e-110">Ažuriranja u realnom vremenu imaju vreme isteka nakon čega više ne menjaju vrednost iz izvora podataka:</span><span class="sxs-lookup"><span data-stu-id="97a8e-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="97a8e-111">Ažuriranja profila čuvaće se 4 sata</span><span class="sxs-lookup"><span data-stu-id="97a8e-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="97a8e-112">Aktivnosti će se čuvati 30 dana</span><span class="sxs-lookup"><span data-stu-id="97a8e-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="97a8e-113">Te vrednosti su parametri API poziva koje možete promeniti.</span><span class="sxs-lookup"><span data-stu-id="97a8e-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="97a8e-114">Oni imaju za cilj da osiguraju da vaši izvorni podaci ostanu vaš izvor istine.</span><span class="sxs-lookup"><span data-stu-id="97a8e-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="97a8e-115">Ako želite da ažuriranja u realnom vremenu budu duže uključena, morate ih dodati u izvor podataka kako bi se povukla tokom sledećeg zakazanog osvežavanja.</span><span class="sxs-lookup"><span data-stu-id="97a8e-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="97a8e-116">Ažuriranje polja objedinjenog profila klijenta u realnom vremenu</span><span class="sxs-lookup"><span data-stu-id="97a8e-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="97a8e-117">Ažurirani profili će se prikazati u prikazu kartice klijenta ili bilo kojoj drugoj vizuelizaciji u roku od nekoliko sekundi.</span><span class="sxs-lookup"><span data-stu-id="97a8e-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="97a8e-118">Pošto se operacije u realnom vremenu odvijaju nakon što se desilo objedinjavanje podataka, one se primenjuju samo na objedinjene profile korisnika.</span><span class="sxs-lookup"><span data-stu-id="97a8e-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="97a8e-119">Stoga promene profila u realnom vremenu neće ažurirati mere, članstvo u segmentima ili obogaćivanja.</span><span class="sxs-lookup"><span data-stu-id="97a8e-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="97a8e-120">Ograničenja</span><span class="sxs-lookup"><span data-stu-id="97a8e-120">Limitations</span></span>

- <span data-ttu-id="97a8e-121">Profili korisnika se mogu ažurirati, ali ne i kreirati ili brisati.</span><span class="sxs-lookup"><span data-stu-id="97a8e-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="97a8e-122">Izvoz ažuriranja u realnom vremenu u spoljne sisteme, kao što je Power BI, trenutno nije moguće.</span><span class="sxs-lookup"><span data-stu-id="97a8e-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="97a8e-123">Kreiranje aktivnosti u realnom vremenu</span><span class="sxs-lookup"><span data-stu-id="97a8e-123">Real-time creation of activities</span></span>

<span data-ttu-id="97a8e-124">API u realnom vremenu omogućava vam objavljivanje nove aktivnosti iz vašeg izvornog sistema (pojedinačni izvorni zapis) na objedinjenom profilu klijenta.</span><span class="sxs-lookup"><span data-stu-id="97a8e-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="97a8e-125">Nova aktivnost će biti dostupna kao objedinjena aktivnost na vremenskoj osi tog objedinjenog klijenta u roku od nekoliko sekundi.</span><span class="sxs-lookup"><span data-stu-id="97a8e-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="97a8e-126">Vremensku liniju možete videti u prikazu kartice klijenta ili bilo kojoj drugoj integraciji vremenske linije koju ste konfigurisali.</span><span class="sxs-lookup"><span data-stu-id="97a8e-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="97a8e-127">Aktivnosti su nepromenljive.</span><span class="sxs-lookup"><span data-stu-id="97a8e-127">Activities are immutable.</span></span> <span data-ttu-id="97a8e-128">Ne menjaju se jednom kada ih kreirate.</span><span class="sxs-lookup"><span data-stu-id="97a8e-128">They don't change once created.</span></span>
> - <span data-ttu-id="97a8e-129">Trenutno se segmenti i mere neće ažurirati na osnovu nove aktivnosti.</span><span class="sxs-lookup"><span data-stu-id="97a8e-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="97a8e-130">Aktivnosti dodate samo putem API-ja u realnom vremenu nisu deo izvoza i neće se prikazati u usluzi PowerBI.</span><span class="sxs-lookup"><span data-stu-id="97a8e-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="97a8e-131">Postoje dva načina za povezivanje sa API-jem u realnom vremenu:</span><span class="sxs-lookup"><span data-stu-id="97a8e-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="97a8e-132">[indirektno](#connect-via-the-dynamics-365-customer-insights-connector), pomoću [Dynamics 365 Customer Insights konektora](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="97a8e-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="97a8e-133">[direktno](#connect-directly-to-the-real-time-api), sa kodom</span><span class="sxs-lookup"><span data-stu-id="97a8e-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="97a8e-134">Oba načina dele sledeće preduslove:</span><span class="sxs-lookup"><span data-stu-id="97a8e-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="97a8e-135">Customer Insights okruženje</span><span class="sxs-lookup"><span data-stu-id="97a8e-135">A Customer Insights environment</span></span>
- <span data-ttu-id="97a8e-136">Objedinjeni profil klijenta</span><span class="sxs-lookup"><span data-stu-id="97a8e-136">Unified customer profiles</span></span>
- <span data-ttu-id="97a8e-137">Aktivnosti se konfigurišu i pokreću</span><span class="sxs-lookup"><span data-stu-id="97a8e-137">Activities configured and run</span></span>
- <span data-ttu-id="97a8e-138">Dozvole saradnika ili administratora za potvrdu identiteta naloga</span><span class="sxs-lookup"><span data-stu-id="97a8e-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="97a8e-139">Povežite se putem Dynamics 365 Customer Insights konektora</span><span class="sxs-lookup"><span data-stu-id="97a8e-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="97a8e-140">API u realnom vremenu može da unosi podatke sa namenskog Power Platform konektora, po imenu [Dynamics 365 Customer Insights konektor](https://docs.microsoft.com/connectors/customerinsights/), bez potrebe za pisanjem i primenom bilo kakvog koda.</span><span class="sxs-lookup"><span data-stu-id="97a8e-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="97a8e-141">Konektor može da obavlja iste radnje u realnom vremenu kao i API.</span><span class="sxs-lookup"><span data-stu-id="97a8e-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="97a8e-142">Potrebna vam je važeća licenca za premijum konektore.</span><span class="sxs-lookup"><span data-stu-id="97a8e-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="97a8e-143">Za više informacija, pogledajte članak [Najčešća pitanja o Power Apps i Power Automate licenciranju](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="97a8e-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="97a8e-144">Power Platform [Power Apps i/ili Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="97a8e-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="97a8e-145">Azure [logičke aplikacije](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="97a8e-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="97a8e-146">Za detalje o kreiranju tokova, pogledajte [Power Automate dokumentaciju](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="97a8e-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="97a8e-147">Povežite se direktno sa API-jem u realnom vremenu</span><span class="sxs-lookup"><span data-stu-id="97a8e-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="97a8e-148">Mogućnosti u realnom vremenu možete da koristite izgradnjom sopstvenog kanala i direktnim povezivanjem sa API-jem u realnom vremenu.</span><span class="sxs-lookup"><span data-stu-id="97a8e-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="97a8e-149">Aktivnost možete objaviti u formatu vašeg izvornog sistema ili u formatu UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="97a8e-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="97a8e-150">Preuzmite format upućivanjem API poziva u /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="97a8e-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="97a8e-151">Detalji ovog API-ja, uključujući parametre i odgovore, mogu se naći u odeljku **Podaci o entitetima** u [Referenci Customer Insights API-ja](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="97a8e-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="97a8e-152">Za više informacija pogledajte [Radite sa Customer Insights API-jima](apis.md).</span><span class="sxs-lookup"><span data-stu-id="97a8e-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="97a8e-153">Objašnjenje upotrebe u realnom vremenu pomoću telemetrije</span><span class="sxs-lookup"><span data-stu-id="97a8e-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="97a8e-154">Dobijte pregled obima zahteva za API u realnom vremenu i informacije o problemima sa kojima se sistem može susresti.</span><span class="sxs-lookup"><span data-stu-id="97a8e-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="97a8e-155">Možete [pristupati telemetriji u realnom vremenu](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="97a8e-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]