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
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315895"
---
# <a name="manage-predictions"></a><span data-ttu-id="1b95c-103">Upravljanje predviđanjima</span><span class="sxs-lookup"><span data-stu-id="1b95c-103">Manage predictions</span></span>

<span data-ttu-id="1b95c-104">Ovaj članak govori o nekim zadacima koje deli većina scenarija predviđanja.</span><span class="sxs-lookup"><span data-stu-id="1b95c-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="1b95c-105">Rešite problem sa neuspelim predviđanjem</span><span class="sxs-lookup"><span data-stu-id="1b95c-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="1b95c-106">Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="1b95c-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="1b95c-107">Izaberite vertikalne tri tačke pored predviđanja za koji želite da pregledate evidencije grešaka.</span><span class="sxs-lookup"><span data-stu-id="1b95c-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="1b95c-108">Izaberite **Evidencije**.</span><span class="sxs-lookup"><span data-stu-id="1b95c-108">Select **Logs**.</span></span>

1. <span data-ttu-id="1b95c-109">Pregledajte sve greške.</span><span class="sxs-lookup"><span data-stu-id="1b95c-109">Review all the errors.</span></span> <span data-ttu-id="1b95c-110">Može se pojaviti nekoliko vrsta grešaka i one opisuju uslov koji je doveo do greške.</span><span class="sxs-lookup"><span data-stu-id="1b95c-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="1b95c-111">Na primer, greška da nema dovoljno podataka za tačno predviđanje obično se rešava učitavanjem dodatnih podataka u Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1b95c-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="1b95c-112">Izveštaj o upotrebljivosti ulaznih podataka</span><span class="sxs-lookup"><span data-stu-id="1b95c-112">Input data usability report</span></span>

<span data-ttu-id="1b95c-113">Izveštaj o upotrebljivosti ulaznih podataka pruža konsolidovani prikaz grešaka i upozorenja koja mogu proizvesti vaša gotova predviđanja.</span><span class="sxs-lookup"><span data-stu-id="1b95c-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="1b95c-114">Takođe daje preporuke kako da poboljšate performanse modela.</span><span class="sxs-lookup"><span data-stu-id="1b95c-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="1b95c-115">Izveštaj je dostupan nakon što model završi svoj proces obuke.</span><span class="sxs-lookup"><span data-stu-id="1b95c-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="1b95c-116">Kreira se za svaki model posebno, bez obzira na to da li je uspešno završen ili ne.</span><span class="sxs-lookup"><span data-stu-id="1b95c-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="1b95c-117">Pogledajte izveštaj o upotrebljivosti ulaznih podataka</span><span class="sxs-lookup"><span data-stu-id="1b95c-117">View the input data usability report</span></span>

<span data-ttu-id="1b95c-118">Kada gotov model završi svoj korak obuke, pogledajte izveštaj:</span><span class="sxs-lookup"><span data-stu-id="1b95c-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="1b95c-119">Izaberite tri tačke pored naziva modela i odaberite **Izveštaj o upotrebljivosti ulaznih podataka**.</span><span class="sxs-lookup"><span data-stu-id="1b95c-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="1b95c-120">Izaberite status modela i izaberite **Pogledajte izveštaj o upotrebljivosti ulaznih podataka** u bočnom oknu.</span><span class="sxs-lookup"><span data-stu-id="1b95c-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="1b95c-121">Izaberite jedan od modela sa liste i izaberite **Izveštaj o upotrebljivosti ulaznih podataka** u komandnoj traci.</span><span class="sxs-lookup"><span data-stu-id="1b95c-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="1b95c-122">Otvorite stranicu rezultata modela i izaberite **Izveštaj o upotrebljivosti ulaznih podataka** u komandnoj traci.</span><span class="sxs-lookup"><span data-stu-id="1b95c-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="1b95c-123">Informacije u izveštaju o upotrebljivosti ulaznih podataka</span><span class="sxs-lookup"><span data-stu-id="1b95c-123">Information in the input data usability report</span></span>

<span data-ttu-id="1b95c-124">Sledeće kolone u izveštaju sadrže korisne informacije za poboljšanje podataka za model.</span><span class="sxs-lookup"><span data-stu-id="1b95c-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Primer izveštaja o upotrebljivosti ulaznih podataka koji prikazuje tabelu sa greškama, upozorenjima i preporukama.":::

- <span data-ttu-id="1b95c-126">Naziv: Opisni naziv greške, upozorenja ili preporuke.</span><span class="sxs-lookup"><span data-stu-id="1b95c-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="1b95c-127">Korak: Faza modela, obuke ili rezultata na koju se informacije odnose.</span><span class="sxs-lookup"><span data-stu-id="1b95c-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="1b95c-128">Status: Ozbiljnost informacija (greška, upozorenje, preporuka).</span><span class="sxs-lookup"><span data-stu-id="1b95c-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="1b95c-129">Naziv kolone: Kolona u entitetu koju treba izmeniti da bi se poboljšale performanse modela.</span><span class="sxs-lookup"><span data-stu-id="1b95c-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="1b95c-130">Naziv entiteta: Naziv entiteta koji treba izmeniti da bi se poboljšale performanse modela.</span><span class="sxs-lookup"><span data-stu-id="1b95c-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="1b95c-131">Detalji: Detalji o grešci, upozorenju ili preporuci.</span><span class="sxs-lookup"><span data-stu-id="1b95c-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="1b95c-132">Osvežavanje predviđanja</span><span class="sxs-lookup"><span data-stu-id="1b95c-132">Refresh a prediction</span></span>

<span data-ttu-id="1b95c-133">Predviđanja se automatski osvežavaju prema istom [rasporedu za osvežavanje podataka](system.md#schedule-tab), kao što je konfigurisano u podešavanjima.</span><span class="sxs-lookup"><span data-stu-id="1b95c-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="1b95c-134">Možete ih osvežiti i ručno.</span><span class="sxs-lookup"><span data-stu-id="1b95c-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="1b95c-135">Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="1b95c-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="1b95c-136">Odaberite uspravne tri tačke pored predviđanja koje želite da osvežite.</span><span class="sxs-lookup"><span data-stu-id="1b95c-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="1b95c-137">Izaberite **Osveži**.</span><span class="sxs-lookup"><span data-stu-id="1b95c-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="1b95c-138">Brisanje predviđanja</span><span class="sxs-lookup"><span data-stu-id="1b95c-138">Delete a prediction</span></span>

<span data-ttu-id="1b95c-139">Brisanjem predviđanja uklanja se i njegov izlazni entitet.</span><span class="sxs-lookup"><span data-stu-id="1b95c-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="1b95c-140">Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="1b95c-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="1b95c-141">Odaberite uspravne tri tačke pored predviđanja koje želite da izbrišete.</span><span class="sxs-lookup"><span data-stu-id="1b95c-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="1b95c-142">Izaberite **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="1b95c-142">Select **Delete**.</span></span>
