---
title: Koristite modele zasnovane na Azure mašinskom učenju
description: Koristite modele zasnovane na Azure mašinskom učenju u usluzi Dynamics 365 Customer Insights.
ms.date: 09/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d9c9324ea4840b585b9af1a58d505ccaea6f18e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609842"
---
# <a name="use-azure-machine-learning-based-models"></a>Koristite modele zasnovane na Azure mašinskom učenju

Objedinjeni podaci u usluzi Dynamics 365 Customer Insights jesu izvor za izgradnju modela mašinskog učenja koji mogu stvoriti dodatne poslovne uvide. Customer Insights se integriše sa Azure mašinskim učenjem kako bi koristio vaše sopstvene prilagođene modele.

## <a name="prerequisites"></a>Preduslovi

- Pristup u Customer Insights
- Aktivna Azure Enterprise pretplata
- [Objedinjeni profil klijenta](data-unification.md)
- [Izvoz entiteta u Azure skladište blob objekata](export-azure-blob-storage.md) je konfigurisan

## <a name="set-up-azure-machine-learning-workspace"></a>Podesite radni prostor za Azure mašinsko učenje

1. Pogledajte [kreiranje radnog prostora za Azure mašinsko učenje](/azure/machine-learning/concept-workspace#-create-a-workspace) za različite opcije za kreiranje radnog prostora. Za najbolje performanse napravite radni prostor u Azure regionu koji je geografski najbliži vašem Customer Insights okruženju.

1. Pristupite svom radnom prostoru putem [usluge Azure Machine Learning Studio](https://ml.azure.com/). Ima nekoliko [načina interakcije](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) sa radnim prostorom.

## <a name="work-with-azure-machine-learning-designer"></a>Radite sa dizajnerom za Azure mašinsko učenje

Azure Mašinsko učenje obezbeđuje vizuelnu podlogu na kojoj možete da prevlačite i otpustite grupe podataka i module. Grupni kanal kreiran iz dizajnera može se integrisati u Customer Insights ako su konfigurisani u skladu s tim. 

## <a name="working-with-azure-machine-learning-sdk"></a>Rad sa SDK-om za Azure mašinsko učenje

Naučnici za podatke i AI programeri koriste [SDK za Azure mašinsko učenje](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) za izgradnju tokova posla mašinskog učenja. Trenutno modeli obučeni pomoću SDK-a ne mogu direktno da se integrišu sa uslugom Customer Insights. Grupni kanal za zaključivanje koji koristi taj model potreban je za integraciju sa uslugom Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Zahtevi za grupni kanal za integraciju sa uslugom Customer Insights

### <a name="dataset-configuration"></a>Konfiguracija skupa podataka

Kreirajte grupe podataka da biste koristili podatke entiteta iz okvira "Uvidi kupaca" za cevovod za zaključivač grupnih zaključaka. Registrujte ove grupe podataka u radnom prostoru. Trenutno podržavamo samo [tabelarne skupove podataka](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) u .csv formatu. Parametrizujte grupe podataka koje odgovaraju entitetskim podacima kao parametru cevovoda.

- Parametri skupa podataka u dizajneru

  U dizajneru otvorite **Izaberite kolone u skupu podataka** i izaberite **Postavi kao parametar kanala** gde dajete ime za parametar.

  :::image type="content" source="media/intelligence-designer-dataset-parameters.png" alt-text="Određivanje parametara skupa podataka u dizajneru.":::

- Parametar skupa podataka u SDK-u (Python)

   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Grupni kanal za zaključivanje
  
- U dizajneru koristite cevovod za obuku da biste kreirali ili ažurirali cevovod za zaključivanje. Trenutno su podržani samo grupni kanali za zaključivanje.

- Koristeći SDK, objavite gasovod na krajnja tačka. Trenutno se Customer Insights integriše sa podrazumevanim kanalom u krajnjoj tački grupnog kanala u radnom prostoru za mašinsko učenje.

   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Uvezite podatke o kanalu u Customer Insights

- Dizajner obezbeđuje [modul za izvoz podataka](/azure/machine-learning/algorithm-module-reference/export-data) koji omogućava izvoz izlaza kanala u Azure skladište. Trenutno modul mora da koristi tip skladišta podataka **Azure skladište blob objekata** i da odredi parametre ta **skladište podataka** i relativnu **putanju**. Customer Insights zamenjuje oba ova parametra tokom izvršavanja kanala pomoću skladišta podataka i putanje koja je dostupna proizvodu.

  :::image type="content" source="media/intelligence-designer-importdata.png" alt-text="Izvoz konfiguracije modula podataka.":::

- Kada upisujete izlaz zaključka koristeći kôd, otpremite izlaz na putanju *unutar registrovane lokacije podataka* u radnom prostoru. Ako su za putanju i skladište podataka određeni parametri u kanalu, Customer insights moći će da pročita i uveze izlaz zaključka. Trenutno je podržan jedan tabelarni izlaz u csv formatu. Putanja mora da sadrži direktorijum i ime datoteke.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]