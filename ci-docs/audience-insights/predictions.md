---
title: Dopunite delimične podatke koristeći predviđanja
description: Koristite predviđanja za popunjavanje nepotpunih podataka o klijentima.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268289"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="0dae7-103">Popunite svoje delimične podatke predviđanjima</span><span class="sxs-lookup"><span data-stu-id="0dae7-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0dae7-104">Predviđanja vam omogućavaju da lako kreirate predviđene vrednosti koje mogu poboljšati razumevanje vašeg klijenta.</span><span class="sxs-lookup"><span data-stu-id="0dae7-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="0dae7-105">Na stranici **Obaveštavanje** > **Predviđanja** možete odabrati **Moja predviđanja** da biste videli predviđanja koja ste konfigurisali u drugim delovima uvida o korisnicima i dodatno ih prilagodili.</span><span class="sxs-lookup"><span data-stu-id="0dae7-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="0dae7-106">Ovu funkciju ne možete da koristite ako okruženje koristi Azure Data Lake Gen 2 prostor za skladištenje.</span><span class="sxs-lookup"><span data-stu-id="0dae7-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="0dae7-107">Funkcija predviđanja koristi automatizovano sredstvo za ocenjivanje podataka i pravljenje predviđanja na osnovu tih podataka i zbog toga ima mogućnost da se koristi kao metod profilisanja, jer je taj pojam definisan Opštom uredbom o zaštiti podataka („GDPR“).</span><span class="sxs-lookup"><span data-stu-id="0dae7-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="0dae7-108">Klijentovo korišćenje ove funkcije za obradu podataka može da bude podložno GDPR-u ili drugim zakonima ili propisima.</span><span class="sxs-lookup"><span data-stu-id="0dae7-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="0dae7-109">Odgovorni ste za to da koristite Dynamics 365 Customer Insights, uključujući predviđanja, u skladu sa svim važećim zakonima i propisima, uključujući zakone koji se odnose na privatnost, lične podatke, biometrijske podatke, zaštitu podataka i poverljivost komunikacija.</span><span class="sxs-lookup"><span data-stu-id="0dae7-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0dae7-110">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="0dae7-110">Prerequisites</span></span>

<span data-ttu-id="0dae7-111">Pre nego što organizacija bude mogla da koristi funkciju predviđanja, sledeći preduslovi moraju da budu ispunjeni:</span><span class="sxs-lookup"><span data-stu-id="0dae7-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="0dae7-112">Vaša organizacija ima instancu [postavljenu u usluzi Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) i u istoj je organizaciji kao i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0dae7-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="0dae7-113">Vaše okruženje je vezano za vašu Common Data Service instancu.</span><span class="sxs-lookup"><span data-stu-id="0dae7-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="0dae7-114">Ako [kreirate prvo okruženje](manage-environments.md), konfigurišite ga u dijalogu **Kreiranje okruženja** i izaberite stavku **Napredno**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="0dae7-115">Ako ste već kreirali okruženje, idite na njegova podešavanja i izaberite **Napredno**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="0dae7-116">U svakom slučaju, u odeljku **Koristite predviđanja** unesite URL Common Data Service instance na koji želite da prikačite svoje okruženje.</span><span class="sxs-lookup"><span data-stu-id="0dae7-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="0dae7-117">Kreiranje predviđanja u usluzi Customer entity</span><span class="sxs-lookup"><span data-stu-id="0dae7-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="0dae7-118">U uvidima o korisnicima idite na **Podaci** > **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="0dae7-119">Izaberite entitet **Klijent**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="0dae7-120">U entitetu **Klijent: CustomerInsights** izaberite stavku na kartici **Polja**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="0dae7-121">Pronađite ime atributa za koje želite da predvidite vrednosti, a zatim izaberite ikonu **Pregled** u koloni **Rezime**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0dae7-122">![Ikona „Pregled“](media/intelligence-overviewicon.png "Ikona „Pregled“")</span><span class="sxs-lookup"><span data-stu-id="0dae7-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="0dae7-123">Ako postoji visoka stopa nedostajućih vrednosti za atribut, izaberite **Predvidi nedostajuće vrednosti** da biste nastavili sa predviđanjem.</span><span class="sxs-lookup"><span data-stu-id="0dae7-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0dae7-124">![Prikaz statusa pregleda sa prikazanim dugmetom za vrednosti koje nedostaju](media/intelligence-overviewpredictmissingvalues.png "Prikaz statusa pregleda sa prikazanim dugmetom za vrednosti koje nedostaju")</span><span class="sxs-lookup"><span data-stu-id="0dae7-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="0dae7-125">Navedite **Ime za prikaz** i **Naziv izlaznog entiteta** za rezultate predviđanja.</span><span class="sxs-lookup"><span data-stu-id="0dae7-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="0dae7-126">Unapred popunjena lista opcija će pokazati gde možete da mapirate vrednosti u predviđenoj kategoriji.</span><span class="sxs-lookup"><span data-stu-id="0dae7-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="0dae7-127">U ovom slučaju, samo opcije kategorije će biti 0 ili 1 dok se mapiraju u tačno/netačno ili binarnu prirodu predviđanja.</span><span class="sxs-lookup"><span data-stu-id="0dae7-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="0dae7-128">U koloni „Kategorija“, vrednosti polja koje biste želeli da se klasifikuju kao „0“ u konačnom predviđanju mapirajte na „0“, a stavke koje biste želeli da se klasifikuju kao „1“ u konačnom predviđanju mapirajte na vrednost „1“.</span><span class="sxs-lookup"><span data-stu-id="0dae7-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0dae7-129">![Primer koji prikazuje mapirane vrednosti polja u kategorije](media/intelligence-categorymapping.png "Primer koji prikazuje mapirane vrednosti polja u kategorije")</span><span class="sxs-lookup"><span data-stu-id="0dae7-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="0dae7-130">Izaberite **Gotovo** i predviđanje će biti obrađeno.</span><span class="sxs-lookup"><span data-stu-id="0dae7-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="0dae7-131">Obrada će potrajati izvesno vreme, u zavisnosti od veličine i složenosti podataka.</span><span class="sxs-lookup"><span data-stu-id="0dae7-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="0dae7-132">Rezultati će biti dostupni u novom entitetu na osnovu **Naziva izlaznog entiteta** predviđanja koje ste kreirali.</span><span class="sxs-lookup"><span data-stu-id="0dae7-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="0dae7-133">Kreiranje predviđanja tokom kreiranja segmenta</span><span class="sxs-lookup"><span data-stu-id="0dae7-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="0dae7-134">Predviđanje nedostajućih vrednosti za određeni atribut izbora je moguće i prilikom kreiranja segmenta.</span><span class="sxs-lookup"><span data-stu-id="0dae7-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="0dae7-135">Posebno, kada brzo kreirate segment zasnovan na objedinjenom entitetu Klijent ili entitetu Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="0dae7-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="0dae7-136">U okviru ovog toka biraćete određeni atribut na kojem će zasnovati segment, kao što je zadovoljstvo klijenta ili iznos nabavke.</span><span class="sxs-lookup"><span data-stu-id="0dae7-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="0dae7-137">Nakon kreiranja segmenta, sistem će predložiti metod za predviđanje svih nedostajućih vrednosti za ovaj atribut.</span><span class="sxs-lookup"><span data-stu-id="0dae7-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="0dae7-138">U uvidima o klijentima idite na **Segmenti** i izaberite pločicu **Profili**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="0dae7-139">Odaberite **Polje** za kreiranje segmenta i izaberite **Operator**, a zatim izaberite stavku **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="0dae7-140">Navedite **Ime** i **Ime za prikaz** za segment.</span><span class="sxs-lookup"><span data-stu-id="0dae7-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="0dae7-141">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-141">Select **Save**.</span></span>

5. <span data-ttu-id="0dae7-142">Ako segment koji ste upravo kreirali nema potpune podatke u izvornom polju, možete da izaberete da predvidite vrednosti koje nedostaju.</span><span class="sxs-lookup"><span data-stu-id="0dae7-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0dae7-143">![Dugme predviđanja](media/segments-predictoption.png "Dugme predviđanja")</span><span class="sxs-lookup"><span data-stu-id="0dae7-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="0dae7-144">Navedite **Ime za prikaz** i **Naziv izlaznog entiteta** za rezultate predviđanja.</span><span class="sxs-lookup"><span data-stu-id="0dae7-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="0dae7-145">Izaberite **Gotovo**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-145">Select **Done**.</span></span> <span data-ttu-id="0dae7-146">Predviđanje će se uskoro generisati u novom entitetu sa imenom koje ste naveli za **Ime izlaznog entiteta**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="0dae7-147">Prikaz predviđanja</span><span class="sxs-lookup"><span data-stu-id="0dae7-147">View a prediction</span></span>

1. <span data-ttu-id="0dae7-148">U uvidima o korisnicima idite na **Obaveštavanje** > **Predviđanja** > **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="0dae7-149">Izaberite predviđanje koje želite da pregledate.</span><span class="sxs-lookup"><span data-stu-id="0dae7-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="0dae7-150">Izaberite tri tačke u koloni **Radnje** i izaberite stavku **Prikaz**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="0dae7-151">Videćete broj tačaka podataka u prikazu predviđanja.</span><span class="sxs-lookup"><span data-stu-id="0dae7-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0dae7-152">![Stranica predviđanja](media/intelligence-predictionsviewpage.png "Stranica predviđanja")</span><span class="sxs-lookup"><span data-stu-id="0dae7-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="0dae7-153">**Predviđene vrednosti** prikazuju mapiranje koje ste kreirali tokom faze mapiranja vrednosti polja u kategoriju.</span><span class="sxs-lookup"><span data-stu-id="0dae7-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="0dae7-154">Ovo su vrednosti u vašem skupu podataka koje su mapirane u određenu kategoriju.</span><span class="sxs-lookup"><span data-stu-id="0dae7-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="0dae7-155">-**Najuticajniji faktori** su faktori u vašem skupu podataka koji najverovatnije najviše utiču na poverenje predviđanja vaše vrednosti polja koja se mapiraju u određenu kategoriju.</span><span class="sxs-lookup"><span data-stu-id="0dae7-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="0dae7-156">**Performanse** ukazuju na način na koji se prognoze obavljaju.</span><span class="sxs-lookup"><span data-stu-id="0dae7-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="0dae7-157">Izaberite vezu da biste saznali više.</span><span class="sxs-lookup"><span data-stu-id="0dae7-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="0dae7-158">**Pregled** prikazuje uzorke izlaznih grupa podataka iz predviđanja i verovatnoću, ili naše poverenje, predviđene vrednosti, gde je 0 neizvesno, a 1 je sigurno.</span><span class="sxs-lookup"><span data-stu-id="0dae7-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="0dae7-159">Ažuriranje predviđanja</span><span class="sxs-lookup"><span data-stu-id="0dae7-159">Update a prediction</span></span>

1. <span data-ttu-id="0dae7-160">U uvidima o korisnicima idite na **Obaveštavanje** > **Predviđanja** > **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="0dae7-161">Izaberite predviđanje koje želite da ažurirate i izaberite ikonu **Ažuriraj**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="0dae7-162">Predviđanje će biti zakazano za obradu.</span><span class="sxs-lookup"><span data-stu-id="0dae7-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="0dae7-163">Vreme kad je poslednji put ažurirano možete da vidite u koloni **Ažurirano** na stranici **Predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="0dae7-164">Uređivanje predviđanja</span><span class="sxs-lookup"><span data-stu-id="0dae7-164">Edit a prediction</span></span>

<span data-ttu-id="0dae7-165">Kada kreirate predviđanje, možete da prilagodite model u programu AI Builder da biste povećali efikasnost vašeg modela.</span><span class="sxs-lookup"><span data-stu-id="0dae7-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="0dae7-166">U uvidima o korisnicima idite na **Obaveštavanje** > **Predviđanja** > **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="0dae7-167">Izaberite predviđanje koje želite da uredite.</span><span class="sxs-lookup"><span data-stu-id="0dae7-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="0dae7-168">Izaberite tri tačke u koloni **Radnje** i izaberite stavku **Prikaz**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="0dae7-169">Izaberite **Prilagodite u usluzi AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="0dae7-170">Ažurirajte model u programu AI Builder.</span><span class="sxs-lookup"><span data-stu-id="0dae7-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="0dae7-171">[Saznajte više o upravljanju modelima u programu AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="0dae7-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="0dae7-172">Sledeće pokretanje predviđanja koristiće ažurirani model koji ste kreirali.</span><span class="sxs-lookup"><span data-stu-id="0dae7-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="0dae7-173">Novi modeli napravljeni u AI Builder-u neće se prikazivati u uvidima o korisnicima, osim ako model nije napravljen na osnovu gorenavedenih iskustava.</span><span class="sxs-lookup"><span data-stu-id="0dae7-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="0dae7-174">Uklanjanje predviđanja</span><span class="sxs-lookup"><span data-stu-id="0dae7-174">Remove a prediction</span></span>

1. <span data-ttu-id="0dae7-175">U uvidima o korisnicima idite na **Obaveštavanje** > **Predviđanja** > **Moja predviđanja**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="0dae7-176">Izaberite predviđanje koje želite da izbrišete.</span><span class="sxs-lookup"><span data-stu-id="0dae7-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="0dae7-177">Izaberite tri tačke u koloni **Radnje** i izaberite stavku **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="0dae7-178">Potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="0dae7-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0dae7-179">Rešavanje problema</span><span class="sxs-lookup"><span data-stu-id="0dae7-179">Troubleshooting</span></span>

<span data-ttu-id="0dae7-180">Ako ne možete da dovršite prilaganje Common Data Service procesa zbog greške, možete pokušati da dovršite postupak ručno.</span><span class="sxs-lookup"><span data-stu-id="0dae7-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="0dae7-181">Postoje dva poznata problema koja se mogu pojaviti u procesu prilaganja:</span><span class="sxs-lookup"><span data-stu-id="0dae7-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="0dae7-182">Rešenje Dodatak za karticu klijenta nije instalirano.</span><span class="sxs-lookup"><span data-stu-id="0dae7-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="0dae7-183">Dovršite uputstva za [instaliranje i konfigurisanje rešenja](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="0dae7-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="0dae7-184">Dozvole za aplikacije nisu dodeljene.</span><span class="sxs-lookup"><span data-stu-id="0dae7-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="0dae7-185">Idite na [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="0dae7-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="0dae7-186">Izaberite **Okruženja**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="0dae7-187">Izaberite tri tačke pored okruženja kojem želite da dodate dozvolu i izaberite **Podešavanja**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="0dae7-188">Proširite odeljak **Korisnici + dozvole** i izaberite **Korisnici**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="0dae7-189">Izaberite **+ Novo** i izaberite **Korisnik**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="0dae7-190">Izaberite opciju **Korisnik aplikacije** ako nije već izabrana i unesite sledeće informacije:</span><span class="sxs-lookup"><span data-stu-id="0dae7-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="0dae7-191">**Korisničko ime:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0dae7-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="0dae7-192">**ID aplikacije** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="0dae7-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="0dae7-193">**Ime:** Klijent</span><span class="sxs-lookup"><span data-stu-id="0dae7-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="0dae7-194">**Prezime:** Uvidi</span><span class="sxs-lookup"><span data-stu-id="0dae7-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="0dae7-195">**Primarna e-adresa:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0dae7-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="0dae7-196">Izaberite stavku **Sačuvaj i zatvori**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="0dae7-197">Izaberite korisnika kojeg ste upravo kreirali.</span><span class="sxs-lookup"><span data-stu-id="0dae7-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="0dae7-198">Izaberite **Upravljaj ulogama** u gornjoj traci menija.</span><span class="sxs-lookup"><span data-stu-id="0dae7-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="0dae7-199">Izaberite **Sistemski administrator**, a zatim izaberite **U redu**.</span><span class="sxs-lookup"><span data-stu-id="0dae7-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]