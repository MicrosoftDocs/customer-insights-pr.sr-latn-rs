---
title: Zajednički zadaci za scenarije predviđanja
description: Naučite kako da upravljate predviđanjima, rešavate ih i precizirate.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095746"
---
# <a name="manage-predictions"></a><span data-ttu-id="a8c86-103">Upravljanje predviđanjima</span><span class="sxs-lookup"><span data-stu-id="a8c86-103">Manage predictions</span></span>

<span data-ttu-id="a8c86-104">Ovaj članak govori o nekim zadacima koje deli većina scenarija predviđanja.</span><span class="sxs-lookup"><span data-stu-id="a8c86-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="a8c86-105">Rešite problem sa neuspelim predviđanjem</span><span class="sxs-lookup"><span data-stu-id="a8c86-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="a8c86-106">Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="a8c86-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="a8c86-107">Izaberite vertikalne tri tačke pored predviđanja za koji želite da pregledate evidencije grešaka.</span><span class="sxs-lookup"><span data-stu-id="a8c86-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="a8c86-108">Izaberite **Evidencije**.</span><span class="sxs-lookup"><span data-stu-id="a8c86-108">Select **Logs**.</span></span>

1. <span data-ttu-id="a8c86-109">Pregledajte sve greške.</span><span class="sxs-lookup"><span data-stu-id="a8c86-109">Review all the errors.</span></span> <span data-ttu-id="a8c86-110">Može se pojaviti nekoliko vrsta grešaka i one opisuju uslov koji je doveo do greške.</span><span class="sxs-lookup"><span data-stu-id="a8c86-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="a8c86-111">Na primer, greška da nema dovoljno podataka za tačno predviđanje obično se rešava učitavanjem dodatnih podataka u Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a8c86-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="a8c86-112">Izveštaj o upotrebljivosti ulaznih podataka</span><span class="sxs-lookup"><span data-stu-id="a8c86-112">Input data usability report</span></span>

<span data-ttu-id="a8c86-113">Izveštaj o upotrebljivosti ulaznih podataka pruža konsolidovani prikaz grešaka i upozorenja koja mogu proizvesti vaša gotova predviđanja.</span><span class="sxs-lookup"><span data-stu-id="a8c86-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="a8c86-114">Takođe daje preporuke kako da poboljšate performanse modela.</span><span class="sxs-lookup"><span data-stu-id="a8c86-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="a8c86-115">Izveštaj je dostupan nakon što model završi svoj proces obuke.</span><span class="sxs-lookup"><span data-stu-id="a8c86-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="a8c86-116">Kreira se za svaki model posebno, bez obzira na to da li je uspešno završen ili ne.</span><span class="sxs-lookup"><span data-stu-id="a8c86-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="a8c86-117">Trenutno, ova funkcija radi samo za model gubitka transakcija.</span><span class="sxs-lookup"><span data-stu-id="a8c86-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="a8c86-118">Pogledajte izveštaj o upotrebljivosti ulaznih podataka</span><span class="sxs-lookup"><span data-stu-id="a8c86-118">View the input data usability report</span></span>

<span data-ttu-id="a8c86-119">Kada gotov model završi svoj korak obuke, pogledajte izveštaj:</span><span class="sxs-lookup"><span data-stu-id="a8c86-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="a8c86-120">Izaberite tri tačke pored naziva modela i odaberite **Izveštaj o upotrebljivosti ulaznih podataka**.</span><span class="sxs-lookup"><span data-stu-id="a8c86-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="a8c86-121">Izaberite status modela i izaberite **Pogledajte izveštaj o upotrebljivosti ulaznih podataka** u bočnom oknu.</span><span class="sxs-lookup"><span data-stu-id="a8c86-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="a8c86-122">Izaberite jedan od modela sa liste i izaberite **Izveštaj o upotrebljivosti ulaznih podataka** u komandnoj traci.</span><span class="sxs-lookup"><span data-stu-id="a8c86-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="a8c86-123">Otvorite stranicu rezultata modela i izaberite **Izveštaj o upotrebljivosti ulaznih podataka** u komandnoj traci.</span><span class="sxs-lookup"><span data-stu-id="a8c86-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="a8c86-124">Informacije u izveštaju o upotrebljivosti ulaznih podataka</span><span class="sxs-lookup"><span data-stu-id="a8c86-124">Information in the input data usability report</span></span>

<span data-ttu-id="a8c86-125">Sledeće kolone u izveštaju sadrže korisne informacije za poboljšanje podataka za model.</span><span class="sxs-lookup"><span data-stu-id="a8c86-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Primer izveštaja o upotrebljivosti ulaznih podataka koji prikazuje tabelu sa greškama, upozorenjima i preporukama.":::

- <span data-ttu-id="a8c86-127">Naziv: Opisni naziv greške, upozorenja ili preporuke.</span><span class="sxs-lookup"><span data-stu-id="a8c86-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="a8c86-128">Korak: Faza modela, obuke ili rezultata na koju se informacije odnose.</span><span class="sxs-lookup"><span data-stu-id="a8c86-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="a8c86-129">Status: Ozbiljnost informacija (greška, upozorenje, preporuka).</span><span class="sxs-lookup"><span data-stu-id="a8c86-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="a8c86-130">Naziv kolone: Kolona u entitetu koju treba izmeniti da bi se poboljšale performanse modela.</span><span class="sxs-lookup"><span data-stu-id="a8c86-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="a8c86-131">Naziv entiteta: Naziv entiteta koji treba izmeniti da bi se poboljšale performanse modela.</span><span class="sxs-lookup"><span data-stu-id="a8c86-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="a8c86-132">Detalji: Detalji o grešci, upozorenju ili preporuci.</span><span class="sxs-lookup"><span data-stu-id="a8c86-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="a8c86-133">Osvežavanje predviđanja</span><span class="sxs-lookup"><span data-stu-id="a8c86-133">Refresh a prediction</span></span>

<span data-ttu-id="a8c86-134">Predviđanja se automatski osvežavaju prema istom [rasporedu za osvežavanje podataka](system.md#schedule-tab), kao što je konfigurisano u podešavanjima.</span><span class="sxs-lookup"><span data-stu-id="a8c86-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="a8c86-135">Možete ih osvežiti i ručno.</span><span class="sxs-lookup"><span data-stu-id="a8c86-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="a8c86-136">Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="a8c86-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="a8c86-137">Odaberite uspravne tri tačke pored predviđanja koje želite da osvežite.</span><span class="sxs-lookup"><span data-stu-id="a8c86-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="a8c86-138">Izaberite **Osveži**.</span><span class="sxs-lookup"><span data-stu-id="a8c86-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="a8c86-139">Brisanje predviđanja</span><span class="sxs-lookup"><span data-stu-id="a8c86-139">Delete a prediction</span></span>

<span data-ttu-id="a8c86-140">Brisanjem predviđanja uklanja se i njegov izlazni entitet.</span><span class="sxs-lookup"><span data-stu-id="a8c86-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="a8c86-141">Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="a8c86-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="a8c86-142">Odaberite uspravne tri tačke pored predviđanja koje želite da izbrišete.</span><span class="sxs-lookup"><span data-stu-id="a8c86-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="a8c86-143">Izaberite **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="a8c86-143">Select **Delete**.</span></span>
