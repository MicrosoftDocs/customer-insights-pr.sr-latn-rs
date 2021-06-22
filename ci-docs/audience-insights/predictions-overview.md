---
title: Pregled podržanih scenarija predviđanja
description: Scenariji i opcije predviđanja pokriveni su aplikacijom Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095745"
---
# <a name="predictions-overview"></a><span data-ttu-id="349fd-103">Pregled predviđanja</span><span class="sxs-lookup"><span data-stu-id="349fd-103">Predictions overview</span></span>

<span data-ttu-id="349fd-104">Dynamics 365 Customer Insights dolazi sa raznim opcijama koje koriste veštačka inteligencija i mašinsko učenje za predviđanje podataka.</span><span class="sxs-lookup"><span data-stu-id="349fd-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="349fd-105">Gotovi modeli</span><span class="sxs-lookup"><span data-stu-id="349fd-105">Out-of-box models</span></span>

<span data-ttu-id="349fd-106">Najlakši način da započnete sa predviđanjem podataka su unapred definisani modeli, koji se često nazivaju „gotovi modeli“.</span><span class="sxs-lookup"><span data-stu-id="349fd-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="349fd-107">Oni samo zahtevaju određene podatke i strukturu da bi brzo stekli uvid.</span><span class="sxs-lookup"><span data-stu-id="349fd-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="349fd-108">Trenutno su dostupni sledeći modeli:</span><span class="sxs-lookup"><span data-stu-id="349fd-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="349fd-109">[Trajna vrednost klijenta](predict-customer-lifetime-value.md): Predviđa potencijalni prihod klijenta tokom čitave interakcije sa preduzećem.</span><span class="sxs-lookup"><span data-stu-id="349fd-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="349fd-110">[Preporuka proizvoda](predict-product-recommendation.md): Predlaže skupove prediktivnih preporuka za proizvode na osnovu ponašanja u kupovini i klijenata sa sličnim obrascima kupovine.</span><span class="sxs-lookup"><span data-stu-id="349fd-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="349fd-111">[Gubitak pretplate](predict-subscription-churn.md): Predviđa da li je klijent ugrožen zbog toga što više ne koristi pretplaćene proizvode ili usluge vašeg preduzeća.</span><span class="sxs-lookup"><span data-stu-id="349fd-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="349fd-112">[Gubitak transakcija](predict-transactional-churn.md): Predvidite da li klijent više neće kupovati vaše proizvode ili usluge u određenom vremenskom okviru.</span><span class="sxs-lookup"><span data-stu-id="349fd-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="349fd-113">Integracija Azure mašinskog učenja</span><span class="sxs-lookup"><span data-stu-id="349fd-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="349fd-114">Ako organizacija već koristi scenarije mašinskog učenja zasnovane na eksperimentima Azure mašinskog učenja, funkcija prilagođenih modela u usluzi Customer Insights pomaže u povezivanju tačaka.</span><span class="sxs-lookup"><span data-stu-id="349fd-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="349fd-115">Napravite tokove posla koji vam pomažu da odaberete podatke od kojih želite da generišete uvide i mapirate rezultate u svoje objedinjene profile klijenata.</span><span class="sxs-lookup"><span data-stu-id="349fd-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="349fd-116">Za više informacija pogledajte [Prilagođeni modeli mašinskog učenja](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="349fd-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="349fd-117">AI Builder predviđanje</span><span class="sxs-lookup"><span data-stu-id="349fd-117">AI Builder prediction</span></span>

<span data-ttu-id="349fd-118">Ponekad su skupovi podataka nepotpuni, a neke vrednosti nedostaju.</span><span class="sxs-lookup"><span data-stu-id="349fd-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="349fd-119">Customer Insights može pomoći u predviđanju vrednosti koje nedostaju za entitet i segmente klijenta.</span><span class="sxs-lookup"><span data-stu-id="349fd-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="349fd-120">Za više informacija, pogledajte [Dopunite svoje delimične podatke predviđanjima](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="349fd-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
