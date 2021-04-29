---
title: Segmenti zasnovani na izlazu predviđanja
description: Kreirajte segmente na osnovu izlaznog entiteta modela predviđanja.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741446"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="fcd6c-103">Kreiranje segmenta na osnovu modela predviđanja (pregled)</span><span class="sxs-lookup"><span data-stu-id="fcd6c-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="fcd6c-104">Rezultati predviđanja ponekad se odnose samo na podskup vaših klijenata.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="fcd6c-105">Povećajte personalizaciju preporuka kreiranjem segmenata od rezultata modela predviđanja.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="fcd6c-106">Na primer, možda ćete želeti da date konkretne preporuke klijentima koji viže vole određenu vrstu usluge.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="fcd6c-107">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="fcd6c-107">Prerequisites</span></span>

- <span data-ttu-id="fcd6c-108">Barem [dozvole saradnika](permissions.md) u usluzi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="fcd6c-109">Model preporuke proizvoda, gubitka transakcija, gubitka pretplata ili trajne vrednosti klijenta konfigurisan je u usluzi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="fcd6c-110">Pregledajte zahteve za postavljanje različitih modela:</span><span class="sxs-lookup"><span data-stu-id="fcd6c-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="fcd6c-111">Model preporuke proizvoda</span><span class="sxs-lookup"><span data-stu-id="fcd6c-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="fcd6c-112">Model gubitka pretplata</span><span class="sxs-lookup"><span data-stu-id="fcd6c-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="fcd6c-113">Model gubitka transakcija</span><span class="sxs-lookup"><span data-stu-id="fcd6c-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="fcd6c-114">Model trajne vrednosti klijenta</span><span class="sxs-lookup"><span data-stu-id="fcd6c-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="fcd6c-115">Kreiranje segmenata klijenata zasnovanih na predviđanjima</span><span class="sxs-lookup"><span data-stu-id="fcd6c-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="fcd6c-116">Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="fcd6c-117">Izaberite uspravne tri tačke pored modela koji želite da pregledate i izaberite **Prikaz**.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="fcd6c-118">Na stranici rezultata, izaberite **Napravi segment**.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="fcd6c-119">Za više informacija o stranici rezultata, pogledajte članak o modelu.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Snimak ekrana stranice rezultata predviđanja sa isticanjem radnje „Napravi segment“.":::

1. <span data-ttu-id="fcd6c-121">Kreirajte novi segment na osnovu izlaznog entiteta izabranog modela.</span><span class="sxs-lookup"><span data-stu-id="fcd6c-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="fcd6c-122">Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).</span><span class="sxs-lookup"><span data-stu-id="fcd6c-122">For more information, see [Create and manage segments](segments.md).</span></span>