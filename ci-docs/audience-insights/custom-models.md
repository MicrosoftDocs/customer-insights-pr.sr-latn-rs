---
title: Prilagođeni modeli mašinskog učenja | Microsoft Docs
description: Radite sa prilagođenim modelima iz Azure mašinskog učenja u usluzi Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 82f6f363497f8f1b45fa84acd49bcaed332e60e8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305665"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="1e5ea-103">Prilagođeni modeli mašinskog učenja</span><span class="sxs-lookup"><span data-stu-id="1e5ea-103">Custom machine learning models</span></span>

<span data-ttu-id="1e5ea-104">**Obaveštavanje** > **Prilagođeni modeli** vam omogućavaju upravljanje tokovima posla na osnovu Azure modela mašinskog učenja.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="1e5ea-105">Tokovi posla pomažu vam da odaberete podatke od kojih želite da generišete uvid i da rezultate mapirate sa objedinjenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="1e5ea-106">Za više informacija o izradi prilagođenih ML modela pogledajte [Koristite modele zasnovane na Azure mašinskom učenju](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="1e5ea-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="1e5ea-107">Odgovorni AI</span><span class="sxs-lookup"><span data-stu-id="1e5ea-107">Responsible AI</span></span>

<span data-ttu-id="1e5ea-108">Predviđanja nude mogućnosti za stvaranje boljeg korisničkog iskustva, poboljšanje poslovnih prilika i tokova prihoda.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="1e5ea-109">Preporučujemo vam da uravnotežite vrednost predviđanja sa uticajem koji ima i odstupanjima koja se mogu uvesti na etičan način.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="1e5ea-110">Saznajte više o tome kako Microsoft [primenjuje odgovoran AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="1e5ea-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="1e5ea-111">Takođe možete saznati o [tehnikama i procesima za odgovorno mašinsko učenje](/azure/machine-learning/concept-responsible-ml) specifičnim za Azure mašinsko učenje.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1e5ea-112">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="1e5ea-112">Prerequisites</span></span>

- <span data-ttu-id="1e5ea-113">Trenutno ova funkcija podržava veb-usluge objavljene putem [Machine Learning Studio (klasičnog)](https://studio.azureml.net) i [grupnih kanala Azure mašinskog učenja](/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="1e5ea-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="1e5ea-114">Da biste koristili ovu funkciju, potreban vam je Azure Data Lake Gen2 nalog za skladištenje povezan sa Azure Studio instancom.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="1e5ea-115">Za više informacija, pogledajte članak [Kreiranje Azure Data Lake Storage Gen2 naloga za skladištenje](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span><span class="sxs-lookup"><span data-stu-id="1e5ea-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="1e5ea-116">Za Azure radne prostore za mašinsko učenje sa kanalima, trebaju vam administratorske dozvole vlasnika ili korisnika da biste pristupili Azure radnom prostoru za mašinsko učenje.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1e5ea-117">Podaci se prenose između Customer Insights instanci i izabranih Azure veb-usluga ili kanala u toku posla.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="1e5ea-118">Kada prenosite podatke u Azure uslugu, uverite se da je usluga konfigurisana da obrađuje podatke na način neophodan za poštovanje svih zakonskih ili regulatornih zahteva za te podatke za vašu organizaciju, kao i na lokaciji koja je za to neophodna.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="1e5ea-119">Dodavanje novog toka posla</span><span class="sxs-lookup"><span data-stu-id="1e5ea-119">Add a new workflow</span></span>

1. <span data-ttu-id="1e5ea-120">Idite na **Obaveštavanje** > **Prilagođeni modeli** i izaberite **Novi tok posla**.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="1e5ea-121">Dajte prilagođenom modelu prepoznatljivo ime u polju **Ime**.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1e5ea-122">![Snimak ekrana okna „Novi tok posla“](media/new-workflowv2.png "Snimak ekrana okna „Novi tok posla“")</span><span class="sxs-lookup"><span data-stu-id="1e5ea-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="1e5ea-123">Izaberite organizaciju koja sadrži veb-uslugu u **zakupcu koji sadrži vašu veb-uslugu**.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="1e5ea-124">Ako je pretplata na Azure mašinsko učenje u drugom zakupcu u odnosu na Customer Insights, odaberite **Prijavite se** pomoću akreditiva za odabranu organizaciju.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="1e5ea-125">Izaberite **Radne prostore** povezane sa vašom veb-uslugom.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="1e5ea-126">Navedena su dva odeljka, jedan za Azure mašinsko učenje v1 (Machine Learning Studio (klasični)) i Azure mašinsko učenje v2 (Azure mašinsko učenje).</span><span class="sxs-lookup"><span data-stu-id="1e5ea-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="1e5ea-127">Ako niste sigurni koji je radni prostor pravi za vašu Machine Learning Studio (klasičan) veb-uslugu, izaberite **Bilo koji**.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="1e5ea-128">Izaberite Machine Learning Studio (klasična) veb-uslugu ili kanal Azure mašinskog učenja u padajućem meniju **Veb-usluga koja sadrži vaš model**.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="1e5ea-129">Zatim izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="1e5ea-130">Saznajte više o [objavljivanju veb-usluge u Machine Learning Studio (klasičnom)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="1e5ea-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="1e5ea-131">Saznajte više o [objavljivanju kanala u Azure mašinskom učenju pomoću dizajnera](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ili [ SDK-a](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="1e5ea-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="1e5ea-132">Vaš kanal mora biti objavljen pod [krajnjom tačkom kanala](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="1e5ea-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="1e5ea-133">Za svaki **Unos veb-usluge**, izaberite odgovarajući **Entitet** iz uvida o korisnicima i izaberite **Dalje**.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="1e5ea-134">Tok posla prilagođenog modela primenjivaće heuristiku za mapiranje polja za unos veb-usluga u atribute entiteta na osnovu imena i tipa podataka polja.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="1e5ea-135">Videćete grešku ako polje veb-usluge ne može da se preslika na entitet.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1e5ea-136">![Konfigurisanje toka posla](media/intelligence-screen2-updated.png "Konfigurisanje toka posla")</span><span class="sxs-lookup"><span data-stu-id="1e5ea-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="1e5ea-137">U koraku **Izlazni parametri modela** postavite sledeća svojstva:</span><span class="sxs-lookup"><span data-stu-id="1e5ea-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="1e5ea-138">Machine Learning Studio (klasični)</span><span class="sxs-lookup"><span data-stu-id="1e5ea-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="1e5ea-139">Unesite izlaz **Naziv entiteta** u koji želite da se prenose izlazni rezultati veb-usluga.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="1e5ea-140">Azure mašinsko učenje</span><span class="sxs-lookup"><span data-stu-id="1e5ea-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="1e5ea-141">Unesite izlaz **Naziv entiteta** u koji želite da se prenose izlazni rezultati kanala.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="1e5ea-142">Izaberite **Naziv izlaznog parametra skladišta podataka** za grupni kanal iz padajućeg menija.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="1e5ea-143">Izaberite **Naziv izlaznog parametra putanje** za grupni kanal iz padajućeg menija.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="1e5ea-144">![Okno izlaznih parametara modela](media/intelligence-screen3-outputparameters.png "Okno izlaznih parametara modela")</span><span class="sxs-lookup"><span data-stu-id="1e5ea-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="1e5ea-145">Izaberite odgovarajući atribut iz padajuće liste **ID klijenta u rezultatima** koja identifikuje klijente i izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-145">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1e5ea-146">![Povežite rezultate sa oknom podataka klijenata](media/intelligence-screen4-relatetocustomer.png "Povežite rezultate sa oknom podataka klijenata")</span><span class="sxs-lookup"><span data-stu-id="1e5ea-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="1e5ea-147">Videćete ekran **Tok posla je sačuvan** sa detaljima o toku posla.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="1e5ea-148">Ako ste konfigurisali tok posla za kanal Azure mašinskog učenja, uvidi o korisnicima će se priložiti u radni prostor koji sadrži kanal.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="1e5ea-149">Uvidi u publiku će dobiti ulogu **Saradnik** u Azure radnom prostoru.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="1e5ea-150">Izaberite **Gotovo**.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-150">Select **Done**.</span></span>

1. <span data-ttu-id="1e5ea-151">Sada možete pokrenuti tok posla sa stranice **Prilagođeni modeli**.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="1e5ea-152">Izmena toka posla</span><span class="sxs-lookup"><span data-stu-id="1e5ea-152">Edit a workflow</span></span>

1. <span data-ttu-id="1e5ea-153">Na stranici **Prilagođeni modeli** izaberite uspravne tri tačke u koloni **Radnje** pored toka posla koji ste prethodno kreirali i izaberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="1e5ea-154">Prepoznatljivo ime toka posla možete ažurirati u polju **Ime za prikaz**, ali ne možete da promenite konfigurisanu veb-uslugu ili kanal.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="1e5ea-155">Izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-155">Select **Next**.</span></span>

1. <span data-ttu-id="1e5ea-156">Za svaki **Unos veb-usluge**, možete da ažurirate odgovarajući **Entitet** iz uvida o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="1e5ea-157">Zatim izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="1e5ea-158">U koraku **Izlazni parametri modela** postavite sledeća svojstva:</span><span class="sxs-lookup"><span data-stu-id="1e5ea-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="1e5ea-159">Machine Learning Studio (klasični)</span><span class="sxs-lookup"><span data-stu-id="1e5ea-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="1e5ea-160">Unesite izlaz **Naziv entiteta** u koji želite da se prenose izlazni rezultati veb-usluga.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="1e5ea-161">Azure mašinsko učenje</span><span class="sxs-lookup"><span data-stu-id="1e5ea-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="1e5ea-162">Unesite izlaz **Naziv entiteta** u koji želite da se prenose izlazni rezultati kanala.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="1e5ea-163">Izaberite **Naziv izlaznog parametra skladišta podataka** za probni kanal.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="1e5ea-164">Izaberite **Naziv izlaznog parametra putanje** za probni kanal.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="1e5ea-165">Izaberite odgovarajući atribut iz padajuće liste **ID klijenta u rezultatima** koja identifikuje klijente i izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-165">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="1e5ea-166">Odaberite atribut iz izlaza zaključka sa vrednostima sličnim koloni sa ID-om klijenta entiteta klijenta.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="1e5ea-167">Ako nemate takvu kolonu skupu podataka, odaberite atribut koji jedinstveno identifikuje red.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="1e5ea-168">Pokretanje toka posla</span><span class="sxs-lookup"><span data-stu-id="1e5ea-168">Run a workflow</span></span>

1. <span data-ttu-id="1e5ea-169">Na stranici **Prilagođeni modeli** izaberite uspravne tri tačke u koloni **Radnje** pored toka posla koji ste prethodno kreirali.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="1e5ea-170">Izaberite **Pokreni**.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-170">Select **Run**.</span></span>

<span data-ttu-id="1e5ea-171">Tok posla se takođe pokreće automatski sa svakim zakazanim osvežavanjem.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="1e5ea-172">Saznajte više o [postavljanju zakazanih osvežavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1e5ea-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="1e5ea-173">Brisanje toka posla</span><span class="sxs-lookup"><span data-stu-id="1e5ea-173">Delete a workflow</span></span>

1. <span data-ttu-id="1e5ea-174">Na stranici **Prilagođeni modeli** izaberite uspravne tri tačke u koloni **Radnje** pored toka posla koji ste prethodno kreirali.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="1e5ea-175">Izaberite **Izbriši** i potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="1e5ea-176">Vaš tok posla će biti izbrisan.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-176">Your workflow will be deleted.</span></span> <span data-ttu-id="1e5ea-177">[Entitet](entities.md) koji je kreiran kada ste kreirali tok posla opstaje i može se pregledati sa stranice **Entiteti**.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="1e5ea-178">Rezultati</span><span class="sxs-lookup"><span data-stu-id="1e5ea-178">Results</span></span>

<span data-ttu-id="1e5ea-179">Rezultati iz toka posla se čuvaju u entitetu konfigurisanom tokom faze izlaznih parametara modela.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="1e5ea-180">Ovim podacima možete pristupiti sa [stranice entiteta](entities.md) ili pomoću [API pristupa](apis.md).</span><span class="sxs-lookup"><span data-stu-id="1e5ea-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="1e5ea-181">API pristup</span><span class="sxs-lookup"><span data-stu-id="1e5ea-181">API Access</span></span>

<span data-ttu-id="1e5ea-182">Da bi određeni OData upit dobio podatke iz entiteta prilagođenog modela, koristite sledeći format:</span><span class="sxs-lookup"><span data-stu-id="1e5ea-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="1e5ea-183">Zamenite `<your instance id>` sa ID-om vašeg Customer Insights okruženja, koji ćete pronaći u adresnoj traci svog pregledača kada pristupite usluzi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="1e5ea-184">Zamenite `<custom model output entity>` nazivom entiteta koje ste naveli tokom koraka parametara izlaznih parametara modela prilagođene konfiguracije modela.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="1e5ea-185">Zamenite `<guid value>` ID-om klijenta čijem zapisu želite da pristupite.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="1e5ea-186">Taj ID obično možete pronaći na [stranica profila klijenta](customer-profiles.md) u polju CustomerID.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="1e5ea-187">Najčešća pitanja</span><span class="sxs-lookup"><span data-stu-id="1e5ea-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="1e5ea-188">Zašto ne mogu da vidim svoj kanal prilikom podešavanja toka posla prilagođenog modela?</span><span class="sxs-lookup"><span data-stu-id="1e5ea-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="1e5ea-189">Ovaj problem je često uzrokovan problemom konfiguracije u kanalu.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="1e5ea-190">Uverite se da je [ulazni parametar konfigurisan](azure-machine-learning-experiments.md#dataset-configuration) i da su [izlazni parametri skladišta podataka i putanje](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) takođe konfigurisani.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="1e5ea-191">Šta znači greška „Ne mogu da sačuvam tok posla obaveštavanja“?</span><span class="sxs-lookup"><span data-stu-id="1e5ea-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="1e5ea-192">Korisnici obično vide ovu poruku o grešci ako u radnom prostoru nemaju administratorske privilegije pristupa za vlasnika ili korisnika.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="1e5ea-193">Korisniku je potreban viši nivo dozvola da omogući usluzi Customer Insights da obradi tok posla kao uslugu, umesto da koristi korisničke akreditive za naredna pokretanja toka posla.</span><span class="sxs-lookup"><span data-stu-id="1e5ea-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
