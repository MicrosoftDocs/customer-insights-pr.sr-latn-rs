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
# <a name="custom-machine-learning-models"></a>Prilagođeni modeli mašinskog učenja

**Obaveštavanje** > **Prilagođeni modeli** vam omogućavaju upravljanje tokovima posla na osnovu Azure modela mašinskog učenja. Tokovi posla pomažu vam da odaberete podatke od kojih želite da generišete uvid i da rezultate mapirate sa objedinjenim podacima o klijentima. Za više informacija o izradi prilagođenih ML modela pogledajte [Koristite modele zasnovane na Azure mašinskom učenju](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Odgovorni AI

Predviđanja nude mogućnosti za stvaranje boljeg korisničkog iskustva, poboljšanje poslovnih prilika i tokova prihoda. Preporučujemo vam da uravnotežite vrednost predviđanja sa uticajem koji ima i odstupanjima koja se mogu uvesti na etičan način. Saznajte više o tome kako Microsoft [primenjuje odgovoran AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Takođe možete saznati o [tehnikama i procesima za odgovorno mašinsko učenje](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specifičnim za Azure mašinsko učenje.

## <a name="prerequisites"></a>Preduslovi

- Trenutno ova funkcija podržava veb-usluge objavljene putem [Machine Learning Studio (klasičnog)](https://studio.azureml.net) i [grupnih kanala Azure mašinskog učenja](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Da biste koristili ovu funkciju, potreban vam je Azure Data Lake Gen2 nalog za skladištenje povezan sa Azure Studio instancom. Za više informacija pogledajte [Napravite Azure Data Lake Storage Gen2 nalog za skladištenje podataka](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Dodavanje novog toka posla

1. Idite na **Obaveštavanje** > **Prilagođeni modeli** i izaberite **Novi tok posla**.

1. Dajte prilagođenom modelu prepoznatljivo ime u polju **Ime**.

   > [!div class="mx-imgBorder"]
   > ![Snimak ekrana okna „Novi tok posla“](media/new-workflowv2.png "Snimak ekrana okna „Novi tok posla“")

1. Izaberite organizaciju koja sadrži veb-uslugu u **zakupcu koji sadrži vašu veb-uslugu**.

1. Ako je pretplata na Azure mašinsko učenje u drugom zakupcu u odnosu na Customer Insights, odaberite **Prijavite se** pomoću akreditiva za odabranu organizaciju.

1. Izaberite **Radne prostore** povezane sa vašom veb-uslugom. Navedena su dva odeljka, jedan za Azure mašinsko učenje v1 (Machine Learning Studio (klasični)) i Azure mašinsko učenje v2 (Azure mašinsko učenje). Ako niste sigurni koji je radni prostor pravi za vašu Machine Learning Studio (klasičan) veb-uslugu, izaberite **Bilo koji**.

1. Izaberite Machine Learning Studio (klasična) veb-uslugu ili kanal Azure mašinskog učenja u padajućem meniju **Veb-usluga koja sadrži vaš model**. Zatim izaberite **Sledeće**.
   - Saznajte više o [objavljivanju veb-usluge u Machine Learning Studio (klasičnom)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Saznajte više o [objavljivanju kanala u Azure mašinskom učenju pomoću dizajnera](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ili [ SDK-a](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). 
     > [!NOTE]
     > Vaš kanal mora biti objavljen pod [krajnjom tačkom kanala](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Za svaki **Unos veb-usluge**, izaberite odgovarajući **Entitet** iz uvida o korisnicima i izaberite **Dalje**.

   > [!div class="mx-imgBorder"]
   > ![Konfigurisanje toka posla](media/intelligence-screen2-updated.png "Konfigurisanje toka posla")

1. U koraku **Izlazni parametri modela** postavite sledeća svojstva:
   - Machine Learning Studio (klasični)
      1. Unesite izlaz **Naziv entiteta** u koji želite da se prenose izlazni rezultati veb-usluga.
   - Azure mašinsko učenje
      1. Unesite izlaz **Naziv entiteta** u koji želite da se prenose izlazni rezultati kanala.
      1. Izaberite **Naziv izlaznog parametra skladišta podataka** za grupni kanal iz padajućeg menija.
      1. Izaberite **Naziv izlaznog parametra putanje** za grupni kanal iz padajućeg menija.
      
      > [!div class="mx-imgBorder"]
      > ![Okno izlaznih parametara modela](media/intelligence-screen3-outputparameters.png "Okno izlaznih parametara modela")

1. Izaberite odgovarajući atribut iz padajuće liste **ID klijenta u rezultatima** koja identifikuje klijente i izaberite **Sačuvaj**.
   
   > [!div class="mx-imgBorder"]
   > ![Povežite rezultate sa oknom podataka klijenata](media/intelligence-screen4-relatetocustomer.png "Povežite rezultate sa oknom podataka klijenata")

1. Videćete ekran **Tok posla je sačuvan** sa detaljima o toku posla.    
   Ako ste konfigurisali tok posla za kanal Azure mašinskog učenja, uvidi o korisnicima će se priložiti u radni prostor koji sadrži kanal. Uvidi u publiku će dobiti ulogu **Saradnik** u Azure radnom prostoru.

1. Izaberite **Gotovo**.

1. Sada možete pokrenuti tok posla sa stranice **Prilagođeni modeli**.

## <a name="edit-a-workflow"></a>Izmena toka posla

1. Na stranici **Prilagođeni modeli** izaberite uspravne tri tačke u koloni **Radnje** pored toka posla koji ste prethodno kreirali i izaberite **Uredi**.

1. Prepoznatljivo ime toka posla možete ažurirati u polju **Ime za prikaz**, ali ne možete da promenite konfigurisanu veb-uslugu ili kanal. Izaberite **Sledeće**.

1. Za svaki **Unos veb-usluge**, možete da ažurirate odgovarajući **Entitet** iz uvida o korisnicima. Zatim izaberite **Sledeće**.

1. U koraku **Izlazni parametri modela** postavite sledeća svojstva:
   - Machine Learning Studio (klasični)
      1. Unesite izlaz **Naziv entiteta** u koji želite da se prenose izlazni rezultati veb-usluga.
   - Azure mašinsko učenje
      1. Unesite izlaz **Naziv entiteta** u koji želite da se prenose izlazni rezultati kanala.
      1. Izaberite **Naziv izlaznog parametra skladišta podataka** za probni kanal.
      1. Izaberite **Naziv izlaznog parametra putanje** za probni kanal.

1. Izaberite odgovarajući atribut iz padajuće liste **ID klijenta u rezultatima** koja identifikuje klijente i izaberite **Sačuvaj**.
   Morate da odaberete atribut iz izlaza zaključka sa vrednostima sličnim koloni sa ID-om klijenta entiteta klijenta. Ako nemate takvu kolonu skupu podataka, odaberite atribut koji jedinstveno identifikuje red.

## <a name="run-a-workflow"></a>Pokretanje toka posla

1. Na stranici **Prilagođeni modeli** izaberite uspravne tri tačke u koloni **Radnje** pored toka posla koji ste prethodno kreirali.

1. Izaberite **Pokreni**.

Tok posla se takođe pokreće automatski sa svakim zakazanim osvežavanjem. Saznajte više o [postavljanju zakazanih osvežavanja](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Brisanje toka posla

1. Na stranici **Prilagođeni modeli** izaberite uspravne tri tačke u koloni **Radnje** pored toka posla koji ste prethodno kreirali.

1. Izaberite **Izbriši** i potvrdite brisanje.

Vaš tok posla će biti izbrisan. [Entitet](entities.md) koji je kreiran kada ste kreirali tok posla opstaje i može se pregledati sa stranice **Entiteti**.
