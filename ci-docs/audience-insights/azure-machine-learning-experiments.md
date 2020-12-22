---
title: Eksperimenti Azure mašinskog učenja
description: Koristite modele zasnovane na Azure mašinskom učenju u usluzi Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: 6f00d3202dc29d810bdd218d06c7d04e551846e8
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668789"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="f37b9-103">Koristite modele zasnovane na Azure mašinskom učenju</span><span class="sxs-lookup"><span data-stu-id="f37b9-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="f37b9-104">Objedinjeni podaci u usluzi Dynamics 365 Customer Insights jesu izvor za izgradnju modela mašinskog učenja koji mogu stvoriti dodatne poslovne uvide.</span><span class="sxs-lookup"><span data-stu-id="f37b9-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="f37b9-105">Customer Insights se integriše sa Machine Learning Studio (klasični) i Azure mašinskim učenjem da bi koristio vaše prilagođene modele.</span><span class="sxs-lookup"><span data-stu-id="f37b9-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="f37b9-106">Pogledajte [Machine Learning Studio (klasični) eksperimente](machine-learning-studio-experiments.md) za primere eksperimenata izgrađenih na osnovu usluge Machine Learning Studio (klasičan).</span><span class="sxs-lookup"><span data-stu-id="f37b9-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f37b9-107">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="f37b9-107">Prerequisites</span></span>

- <span data-ttu-id="f37b9-108">Pristup u Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f37b9-108">Access to Customer Insights</span></span>
- <span data-ttu-id="f37b9-109">Aktivna Azure Enterprise pretplata</span><span class="sxs-lookup"><span data-stu-id="f37b9-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="f37b9-110">Objedinjeni profil klijenta</span><span class="sxs-lookup"><span data-stu-id="f37b9-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="f37b9-111">[Izvoz entiteta u Azure skladište blob objekata](export-azure-blob-storage.md) je konfigurisan</span><span class="sxs-lookup"><span data-stu-id="f37b9-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="f37b9-112">Podesite radni prostor za Azure mašinsko učenje</span><span class="sxs-lookup"><span data-stu-id="f37b9-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="f37b9-113">Pogledajte [kreiranje radnog prostora za Azure mašinsko učenje](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) za različite opcije za kreiranje radnog prostora.</span><span class="sxs-lookup"><span data-stu-id="f37b9-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="f37b9-114">Za najbolje performanse napravite radni prostor u Azure regionu koji je geografski najbliži vašem Customer Insights okruženju.</span><span class="sxs-lookup"><span data-stu-id="f37b9-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="f37b9-115">Pristupite svom radnom prostoru putem [usluge Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="f37b9-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="f37b9-116">Ima nekoliko [načina interakcije](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) sa radnim prostorom.</span><span class="sxs-lookup"><span data-stu-id="f37b9-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="f37b9-117">Radite sa dizajnerom za Azure mašinsko učenje</span><span class="sxs-lookup"><span data-stu-id="f37b9-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="f37b9-118">Dizajner za Azure mašinsko učenje pruža vizuelnu podlogu po kojoj možete prevlačiti i otpuštati skupove podataka i module, slično kao Machine Learning Studio (klasični).</span><span class="sxs-lookup"><span data-stu-id="f37b9-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="f37b9-119">Grupni kanal kreiran iz dizajnera može se integrisati u Customer Insights ako su konfigurisani u skladu s tim.</span><span class="sxs-lookup"><span data-stu-id="f37b9-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="f37b9-120">Rad sa SDK-om za Azure mašinsko učenje</span><span class="sxs-lookup"><span data-stu-id="f37b9-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="f37b9-121">Naučnici za podatke i AI programeri koriste [SDK za Azure mašinsko učenje](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) za izgradnju tokova posla mašinskog učenja.</span><span class="sxs-lookup"><span data-stu-id="f37b9-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="f37b9-122">Trenutno modeli obučeni pomoću SDK-a ne mogu direktno da se integrišu sa uslugom Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f37b9-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="f37b9-123">Grupni kanal za zaključivanje koji koristi taj model potreban je za integraciju sa uslugom Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f37b9-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="f37b9-124">Zahtevi za grupni kanal za integraciju sa uslugom Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f37b9-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="f37b9-125">Konfiguracija skupa podataka</span><span class="sxs-lookup"><span data-stu-id="f37b9-125">Dataset Configuration</span></span>

<span data-ttu-id="f37b9-126">Morate da kreirate skupove podataka da biste koristili podatke entiteta od usluge Customer Insights do grupnog kanala za zaključivanje.</span><span class="sxs-lookup"><span data-stu-id="f37b9-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="f37b9-127">Ove skupove podataka treba registrovati u radnom prostoru.</span><span class="sxs-lookup"><span data-stu-id="f37b9-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="f37b9-128">Trenutno podržavamo samo [tabelarne skupove podataka](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) u .csv formatu.</span><span class="sxs-lookup"><span data-stu-id="f37b9-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="f37b9-129">Za skupove podataka koji odgovaraju podacima entiteta moraju se odrediti parametri kao parametar kanala.</span><span class="sxs-lookup"><span data-stu-id="f37b9-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="f37b9-130">Parametri skupa podataka u dizajneru</span><span class="sxs-lookup"><span data-stu-id="f37b9-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="f37b9-131">U dizajneru otvorite **Izaberite kolone u skupu podataka** i izaberite **Postavi kao parametar kanala** gde dajete ime za parametar.</span><span class="sxs-lookup"><span data-stu-id="f37b9-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="f37b9-132">![Određivanje parametara skupa podataka u dizajneru](media/intelligence-designer-dataset-parameters.png "Određivanje parametara skupa podataka u dizajneru")</span><span class="sxs-lookup"><span data-stu-id="f37b9-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="f37b9-133">Parametar skupa podataka u SDK-u (Python)</span><span class="sxs-lookup"><span data-stu-id="f37b9-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="f37b9-134">Grupni kanal za zaključivanje</span><span class="sxs-lookup"><span data-stu-id="f37b9-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="f37b9-135">U dizajneru se kanal za obuku može koristiti za stvaranje ili ažuriranje kanala za zaključivanje.</span><span class="sxs-lookup"><span data-stu-id="f37b9-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="f37b9-136">Trenutno su podržani samo grupni kanali za zaključivanje.</span><span class="sxs-lookup"><span data-stu-id="f37b9-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="f37b9-137">Korišćenjem SDK-a možete objaviti kanal na krajnjoj tački.</span><span class="sxs-lookup"><span data-stu-id="f37b9-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="f37b9-138">Trenutno se Customer Insights integriše sa podrazumevanim kanalom u krajnjoj tački grupnog kanala u radnom prostoru za mašinsko učenje.</span><span class="sxs-lookup"><span data-stu-id="f37b9-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="f37b9-139">Uvezite podatke o kanalu u Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f37b9-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="f37b9-140">Dizajner obezbeđuje [modul za izvoz podataka](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) koji omogućava izvoz izlaza kanala u Azure skladište.</span><span class="sxs-lookup"><span data-stu-id="f37b9-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="f37b9-141">Trenutno modul mora da koristi tip skladišta podataka **Azure skladište blob objekata** i da odredi parametre ta **skladište podataka** i relativnu **putanju**.</span><span class="sxs-lookup"><span data-stu-id="f37b9-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="f37b9-142">Customer Insights zamenjuje oba ova parametra tokom izvršavanja kanala pomoću skladišta podataka i putanje koja je dostupna proizvodu.</span><span class="sxs-lookup"><span data-stu-id="f37b9-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f37b9-143">![Izvoz konfiguracije modula podataka](media/intelligence-designer-importdata.png "Izvoz konfiguracije modula podataka")</span><span class="sxs-lookup"><span data-stu-id="f37b9-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="f37b9-144">Kada zapisujete izlaz zaključka pomoću koda, možete otpremiti izlaz na putanju unutar *registrovanog skladišta podataka* u radnom prostoru.</span><span class="sxs-lookup"><span data-stu-id="f37b9-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="f37b9-145">Ako su za putanju i skladište podataka određeni parametri u kanalu, Customer insights moći će da pročita i uveze izlaz zaključka.</span><span class="sxs-lookup"><span data-stu-id="f37b9-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="f37b9-146">Trenutno je podržan jedan tabelarni izlaz u csv formatu.</span><span class="sxs-lookup"><span data-stu-id="f37b9-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="f37b9-147">Putanja mora da sadrži direktorijum i ime datoteke.</span><span class="sxs-lookup"><span data-stu-id="f37b9-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```
