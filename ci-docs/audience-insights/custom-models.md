---
title: Prilagođeni modeli mašinskog učenja | Microsoft Docs
description: Radite sa prilagođenim modelima iz Azure mašinskog učenja u usluzi Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668920"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="cb754-103">Prilagođeni modeli mašinskog učenja</span><span class="sxs-lookup"><span data-stu-id="cb754-103">Custom machine learning models</span></span>

<span data-ttu-id="cb754-104">**Obaveštavanje** > **Prilagođeni modeli** vam omogućavaju upravljanje tokovima posla na osnovu Azure modela mašinskog učenja.</span><span class="sxs-lookup"><span data-stu-id="cb754-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="cb754-105">Tokovi posla pomažu vam da odaberete podatke od kojih želite da generišete uvid i da rezultate mapirate sa objedinjenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="cb754-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="cb754-106">Za više informacija o izradi prilagođenih ML modela pogledajte [Koristite modele zasnovane na Azure mašinskom učenju](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="cb754-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="cb754-107">Odgovorni AI</span><span class="sxs-lookup"><span data-stu-id="cb754-107">Responsible AI</span></span>

<span data-ttu-id="cb754-108">Predviđanja nude mogućnosti za stvaranje boljeg korisničkog iskustva, poboljšanje poslovnih prilika i tokova prihoda.</span><span class="sxs-lookup"><span data-stu-id="cb754-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="cb754-109">Preporučujemo vam da uravnotežite vrednost predviđanja sa uticajem koji ima i odstupanjima koja se mogu uvesti na etičan način.</span><span class="sxs-lookup"><span data-stu-id="cb754-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="cb754-110">Saznajte više o tome kako Microsoft [primenjuje odgovoran AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="cb754-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="cb754-111">Takođe možete saznati o [tehnikama i procesima za odgovorno mašinsko učenje](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specifičnim za Azure mašinsko učenje.</span><span class="sxs-lookup"><span data-stu-id="cb754-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cb754-112">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="cb754-112">Prerequisites</span></span>

- <span data-ttu-id="cb754-113">Trenutno ova funkcija podržava veb-usluge objavljene putem [Machine Learning Studio (klasičnog)](https://studio.azureml.net) i [grupnih kanala Azure mašinskog učenja](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="cb754-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="cb754-114">Da biste koristili ovu funkciju, potreban vam je Azure Data Lake Gen2 nalog za skladištenje povezan sa Azure Studio instancom.</span><span class="sxs-lookup"><span data-stu-id="cb754-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="cb754-115">Za više informacija pogledajte [Napravite Azure Data Lake Storage Gen2 nalog za skladištenje podataka](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="cb754-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="cb754-116">Dodavanje novog toka posla</span><span class="sxs-lookup"><span data-stu-id="cb754-116">Add a new workflow</span></span>

1. <span data-ttu-id="cb754-117">Idite na **Obaveštavanje** > **Prilagođeni modeli** i izaberite **Novi tok posla**.</span><span class="sxs-lookup"><span data-stu-id="cb754-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="cb754-118">Dajte prilagođenom modelu prepoznatljivo ime u polju **Ime**.</span><span class="sxs-lookup"><span data-stu-id="cb754-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cb754-119">![Snimak ekrana okna „Novi tok posla“](media/new-workflowv2.png "Snimak ekrana okna „Novi tok posla“")</span><span class="sxs-lookup"><span data-stu-id="cb754-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="cb754-120">Izaberite organizaciju koja sadrži veb-uslugu u **zakupcu koji sadrži vašu veb-uslugu**.</span><span class="sxs-lookup"><span data-stu-id="cb754-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="cb754-121">Ako je pretplata na Azure mašinsko učenje u drugom zakupcu u odnosu na Customer Insights, odaberite **Prijavite se** pomoću akreditiva za odabranu organizaciju.</span><span class="sxs-lookup"><span data-stu-id="cb754-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="cb754-122">Izaberite **Radne prostore** povezane sa vašom veb-uslugom.</span><span class="sxs-lookup"><span data-stu-id="cb754-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="cb754-123">Navedena su dva odeljka, jedan za Azure mašinsko učenje v1 (Machine Learning Studio (klasični)) i Azure mašinsko učenje v2 (Azure mašinsko učenje).</span><span class="sxs-lookup"><span data-stu-id="cb754-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="cb754-124">Ako niste sigurni koji je radni prostor pravi za vašu Machine Learning Studio (klasičan) veb-uslugu, izaberite **Bilo koji**.</span><span class="sxs-lookup"><span data-stu-id="cb754-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="cb754-125">Izaberite Machine Learning Studio (klasična) veb-uslugu ili kanal Azure mašinskog učenja u padajućem meniju **Veb-usluga koja sadrži vaš model**.</span><span class="sxs-lookup"><span data-stu-id="cb754-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="cb754-126">Zatim izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="cb754-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="cb754-127">Saznajte više o [objavljivanju veb-usluge u Machine Learning Studio (klasičnom)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="cb754-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="cb754-128">Saznajte više o [objavljivanju kanala u Azure mašinskom učenju pomoću dizajnera](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ili [ SDK-a](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="cb754-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="cb754-129">Vaš kanal mora biti objavljen pod [krajnjom tačkom kanala](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="cb754-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="cb754-130">Za svaki **Unos veb-usluge**, izaberite odgovarajući **Entitet** iz uvida o korisnicima i izaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="cb754-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cb754-131">![Konfigurisanje toka posla](media/intelligence-screen2-updated.png "Konfigurisanje toka posla")</span><span class="sxs-lookup"><span data-stu-id="cb754-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="cb754-132">U koraku **Izlazni parametri modela** postavite sledeća svojstva:</span><span class="sxs-lookup"><span data-stu-id="cb754-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="cb754-133">Machine Learning Studio (klasični)</span><span class="sxs-lookup"><span data-stu-id="cb754-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="cb754-134">Unesite izlaz **Naziv entiteta** u koji želite da se prenose izlazni rezultati veb-usluga.</span><span class="sxs-lookup"><span data-stu-id="cb754-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="cb754-135">Azure mašinsko učenje</span><span class="sxs-lookup"><span data-stu-id="cb754-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="cb754-136">Unesite izlaz **Naziv entiteta** u koji želite da se prenose izlazni rezultati kanala.</span><span class="sxs-lookup"><span data-stu-id="cb754-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="cb754-137">Izaberite **Naziv izlaznog parametra skladišta podataka** za grupni kanal iz padajućeg menija.</span><span class="sxs-lookup"><span data-stu-id="cb754-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="cb754-138">Izaberite **Naziv izlaznog parametra putanje** za grupni kanal iz padajućeg menija.</span><span class="sxs-lookup"><span data-stu-id="cb754-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="cb754-139">![Okno izlaznih parametara modela](media/intelligence-screen3-outputparameters.png "Okno izlaznih parametara modela")</span><span class="sxs-lookup"><span data-stu-id="cb754-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="cb754-140">Izaberite odgovarajući atribut iz padajuće liste **ID klijenta u rezultatima** koja identifikuje klijente i izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="cb754-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cb754-141">![Povežite rezultate sa oknom podataka klijenata](media/intelligence-screen4-relatetocustomer.png "Povežite rezultate sa oknom podataka klijenata")</span><span class="sxs-lookup"><span data-stu-id="cb754-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="cb754-142">Videćete ekran **Tok posla je sačuvan** sa detaljima o toku posla.</span><span class="sxs-lookup"><span data-stu-id="cb754-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="cb754-143">Ako ste konfigurisali tok posla za kanal Azure mašinskog učenja, uvidi o korisnicima će se priložiti u radni prostor koji sadrži kanal.</span><span class="sxs-lookup"><span data-stu-id="cb754-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="cb754-144">Uvidi u publiku će dobiti ulogu **Saradnik** u Azure radnom prostoru.</span><span class="sxs-lookup"><span data-stu-id="cb754-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="cb754-145">Izaberite **Gotovo**.</span><span class="sxs-lookup"><span data-stu-id="cb754-145">Select **Done**.</span></span>

1. <span data-ttu-id="cb754-146">Sada možete pokrenuti tok posla sa stranice **Prilagođeni modeli**.</span><span class="sxs-lookup"><span data-stu-id="cb754-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="cb754-147">Izmena toka posla</span><span class="sxs-lookup"><span data-stu-id="cb754-147">Edit a workflow</span></span>

1. <span data-ttu-id="cb754-148">Na stranici **Prilagođeni modeli** izaberite uspravne tri tačke u koloni **Radnje** pored toka posla koji ste prethodno kreirali i izaberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="cb754-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="cb754-149">Prepoznatljivo ime toka posla možete ažurirati u polju **Ime za prikaz**, ali ne možete da promenite konfigurisanu veb-uslugu ili kanal.</span><span class="sxs-lookup"><span data-stu-id="cb754-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="cb754-150">Izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="cb754-150">Select **Next**.</span></span>

1. <span data-ttu-id="cb754-151">Za svaki **Unos veb-usluge**, možete da ažurirate odgovarajući **Entitet** iz uvida o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="cb754-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="cb754-152">Zatim izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="cb754-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="cb754-153">U koraku **Izlazni parametri modela** postavite sledeća svojstva:</span><span class="sxs-lookup"><span data-stu-id="cb754-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="cb754-154">Machine Learning Studio (klasični)</span><span class="sxs-lookup"><span data-stu-id="cb754-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="cb754-155">Unesite izlaz **Naziv entiteta** u koji želite da se prenose izlazni rezultati veb-usluga.</span><span class="sxs-lookup"><span data-stu-id="cb754-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="cb754-156">Azure mašinsko učenje</span><span class="sxs-lookup"><span data-stu-id="cb754-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="cb754-157">Unesite izlaz **Naziv entiteta** u koji želite da se prenose izlazni rezultati kanala.</span><span class="sxs-lookup"><span data-stu-id="cb754-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="cb754-158">Izaberite **Naziv izlaznog parametra skladišta podataka** za probni kanal.</span><span class="sxs-lookup"><span data-stu-id="cb754-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="cb754-159">Izaberite **Naziv izlaznog parametra putanje** za probni kanal.</span><span class="sxs-lookup"><span data-stu-id="cb754-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="cb754-160">Izaberite odgovarajući atribut iz padajuće liste **ID klijenta u rezultatima** koja identifikuje klijente i izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="cb754-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="cb754-161">Morate da odaberete atribut iz izlaza zaključka sa vrednostima sličnim koloni sa ID-om klijenta entiteta klijenta.</span><span class="sxs-lookup"><span data-stu-id="cb754-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="cb754-162">Ako nemate takvu kolonu skupu podataka, odaberite atribut koji jedinstveno identifikuje red.</span><span class="sxs-lookup"><span data-stu-id="cb754-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="cb754-163">Pokretanje toka posla</span><span class="sxs-lookup"><span data-stu-id="cb754-163">Run a workflow</span></span>

1. <span data-ttu-id="cb754-164">Na stranici **Prilagođeni modeli** izaberite uspravne tri tačke u koloni **Radnje** pored toka posla koji ste prethodno kreirali.</span><span class="sxs-lookup"><span data-stu-id="cb754-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="cb754-165">Izaberite **Pokreni**.</span><span class="sxs-lookup"><span data-stu-id="cb754-165">Select **Run**.</span></span>

<span data-ttu-id="cb754-166">Tok posla se takođe pokreće automatski sa svakim zakazanim osvežavanjem.</span><span class="sxs-lookup"><span data-stu-id="cb754-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="cb754-167">Saznajte više o [postavljanju zakazanih osvežavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cb754-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="cb754-168">Brisanje toka posla</span><span class="sxs-lookup"><span data-stu-id="cb754-168">Delete a workflow</span></span>

1. <span data-ttu-id="cb754-169">Na stranici **Prilagođeni modeli** izaberite uspravne tri tačke u koloni **Radnje** pored toka posla koji ste prethodno kreirali.</span><span class="sxs-lookup"><span data-stu-id="cb754-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="cb754-170">Izaberite **Izbriši** i potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="cb754-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="cb754-171">Vaš tok posla će biti izbrisan.</span><span class="sxs-lookup"><span data-stu-id="cb754-171">Your workflow will be deleted.</span></span> <span data-ttu-id="cb754-172">[Entitet](entities.md) koji je kreiran kada ste kreirali tok posla opstaje i može se pregledati sa stranice **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="cb754-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
