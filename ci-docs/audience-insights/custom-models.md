---
title: Prilagođeni modeli mašinskog učenja | Microsoft Docs
description: Radite sa prilagođenim modelima iz Azure mašinskog učenja u usluzi Dynamics 365 Customer Insights.
ms.date: 12/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 8ca30193ae4f4ef3ed9c60f2d694cd11fad46c76
ms.sourcegitcommit: 15b1521041149716f8031cfa6d0dc61a56a5e2ff
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967672"
---
# <a name="custom-machine-learning-models"></a>Prilagođeni modeli mašinskog učenja

> [!NOTE]
> Podrška za Mašinsko učenje Studio (klasika) završiće se 31. avgusta 2024. godine. Preporučujemo da do tog [datuma pređete Mašinsko učenje](/azure/machine-learning/overview-what-is-azure-machine-learning) Azure.
>
> Počevši od 1. decembra 2021. godine, nećete moći da kreirate nove Mašinsko učenje Studio (klasične) resurse. Do 31. avgusta 2024. možete nastaviti da koristite postojeće Mašinsko učenje Studio (klasične) resurse. Više informacija potražite u [članku Migracija u Azure Mašinsko učenje](/azure/machine-learning/migrate-overview).


**Obaveštavanje** > **Prilagođeni modeli** vam omogućavaju upravljanje tokovima posla na osnovu Azure modela mašinskog učenja. Tokovi posla pomažu vam da odaberete podatke od kojih želite da generišete uvid i da rezultate mapirate sa objedinjenim podacima o klijentima. Za više informacija o izradi prilagođenih ML modela pogledajte [Koristite modele zasnovane na Azure mašinskom učenju](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Odgovorni AI

Predviđanja nude mogućnosti za stvaranje boljeg korisničkog iskustva, poboljšanje poslovnih prilika i tokova prihoda. Preporučujemo vam da uravnotežite vrednost predviđanja sa uticajem koji ima i odstupanjima koja se mogu uvesti na etičan način. Saznajte više o tome kako Microsoft [primenjuje odgovoran AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Takođe možete saznati o [tehnikama i procesima za odgovorno mašinsko učenje](/azure/machine-learning/concept-responsible-ml) specifičnim za Azure mašinsko učenje.

## <a name="prerequisites"></a>Preduslovi

- Ova funkcija podržava Veb usluge objavljene preko [Azure Mašinsko učenje grupnih cevovoda](/azure/machine-learning/concept-ml-pipelines).

- Da biste koristili ovu funkciju, potreban vam je Azure Data Lake Gen2 nalog za skladištenje povezan sa Azure Studio instancom. Za više informacija, pogledajte članak [Kreiranje Azure Data Lake Storage Gen2 naloga za skladištenje](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Za Azure radne prostore za mašinsko učenje sa kanalima, trebaju vam administratorske dozvole vlasnika ili korisnika da biste pristupili Azure radnom prostoru za mašinsko učenje.

   > [!NOTE]
   > Podaci se prenose između Customer Insights instanci i izabranih Azure veb-usluga ili kanala u toku posla. Kada prenosite podatke u Azure uslugu, uverite se da je usluga konfigurisana da obrađuje podatke na način neophodan za poštovanje svih zakonskih ili regulatornih zahteva za te podatke za vašu organizaciju, kao i na lokaciji koja je za to neophodna.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

## <a name="add-a-new-workflow"></a>Dodavanje novog toka posla

1. Idite na **Obaveštavanje** > **Prilagođeni modeli** i izaberite **Novi tok posla**.

1. Dajte prilagođenom modelu prepoznatljivo ime u polju **Ime**.

   > [!div class="mx-imgBorder"]
   > ![Snimak ekrana okna „Novi tok posla“.](media/new-workflowv2.png "Snimak ekrana okna „Novi tok posla“")

1. Izaberite organizaciju koja sadrži veb-uslugu u **zakupcu koji sadrži vašu veb-uslugu**.

1. Ako je pretplata na Azure mašinsko učenje u drugom zakupcu u odnosu na Customer Insights, odaberite **Prijavite se** pomoću akreditiva za odabranu organizaciju.

1. Izaberite **Radne prostore** povezane sa vašom veb-uslugom. 

1. Odaberite Azure Mašinsko učenje u **Web usluzi koja sadrži padajuću** listu modela. Zatim izaberite **Sledeće**.    
   Saznajte više o [objavljivanju kanala u Azure mašinskom učenju pomoću dizajnera](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ili [ SDK-a](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Vaš kanal mora biti objavljen pod [krajnjom tačkom kanala](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Za svaki **Unos veb-usluge**, izaberite odgovarajući **Entitet** iz uvida o korisnicima i izaberite **Dalje**.
   > [!NOTE]
   > Tok posla prilagođenog modela primenjivaće heuristiku za mapiranje polja za unos veb-usluga u atribute entiteta na osnovu imena i tipa podataka polja. Videćete grešku ako polje veb-usluge ne može da se preslika na entitet.

   > [!div class="mx-imgBorder"]
   > ![Konfigurisanje toka posla.](media/intelligence-screen2-updated.png "Konfigurisanje toka posla")

1. U koraku **Izlazni parametri modela** postavite sledeća svojstva:
      1. Unesite izlaz **Naziv entiteta** u koji želite da se prenose izlazni rezultati kanala.
      1. Izaberite **Naziv izlaznog parametra skladišta podataka** za grupni kanal iz padajućeg menija.
      1. Izaberite **Naziv izlaznog parametra putanje** za grupni kanal iz padajućeg menija.

      > [!div class="mx-imgBorder"]
      > ![Okno izlaznih parametara modela.](media/intelligence-screen3-outputparameters.png "Okno izlaznih parametara modela")

1. Izaberite odgovarajući atribut iz padajuće liste **ID klijenta u rezultatima** koja identifikuje klijente i izaberite **Sačuvaj**.

   > [!div class="mx-imgBorder"]
   > ![Povežite rezultate sa oknom podataka klijenata.](media/intelligence-screen4-relatetocustomer.png "Povežite rezultate sa oknom podataka klijenata")

1. Videćete ekran **Tok posla je sačuvan** sa detaljima o toku posla.    
   Ako ste konfigurisali tok posla za kanal Azure mašinskog učenja, uvidi o korisnicima će se priložiti u radni prostor koji sadrži kanal. Uvidi u publiku će dobiti ulogu **Saradnik** u Azure radnom prostoru.

1. Izaberite **Gotovo**.

1. Sada možete pokrenuti tok posla sa stranice **Prilagođeni modeli**.

## <a name="edit-a-workflow"></a>Izmena toka posla

1. Na stranici **Prilagođeni modeli** izaberite uspravne tri tačke u koloni **Radnje** pored toka posla koji ste prethodno kreirali i izaberite **Uredi**.

1. Prepoznatljivo ime toka posla možete ažurirati u polju **Ime za prikaz**, ali ne možete da promenite konfigurisanu veb-uslugu ili kanal. Izaberite **Sledeće**.

1. Za svaki **Unos veb-usluge**, možete da ažurirate odgovarajući **Entitet** iz uvida o korisnicima. Zatim izaberite **Sledeće**.

1. U koraku **Izlazni parametri modela** postavite sledeća svojstva:
      1. Unesite izlaz **Naziv entiteta** u koji želite da se prenose izlazni rezultati kanala.
      1. Izaberite **Naziv izlaznog parametra skladišta podataka** za probni kanal.
      1. Izaberite **Naziv izlaznog parametra putanje** za probni kanal.

1. Izaberite odgovarajući atribut iz padajuće liste **ID klijenta u rezultatima** koja identifikuje klijente i izaberite **Sačuvaj**.
   Odaberite atribut iz izlaza zaključka sa vrednostima sličnim koloni sa ID-om klijenta entiteta klijenta. Ako nemate takvu kolonu skupu podataka, odaberite atribut koji jedinstveno identifikuje red.

## <a name="run-a-workflow"></a>Pokretanje toka posla

1. Na stranici **Prilagođeni modeli** izaberite uspravne tri tačke u koloni **Radnje** pored toka posla koji ste prethodno kreirali.

1. Izaberite **Pokreni**.

Tok posla se takođe pokreće automatski sa svakim zakazanim osvežavanjem. Saznajte više o [postavljanju zakazanih osvežavanja](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Brisanje toka posla

1. Na stranici **Prilagođeni modeli** izaberite uspravne tri tačke u koloni **Radnje** pored toka posla koji ste prethodno kreirali.

1. Izaberite **Izbriši** i potvrdite brisanje.

Vaš tok posla će biti izbrisan. [Entitet](entities.md) koji je kreiran kada ste kreirali tok posla opstaje i može se pregledati sa stranice **Entiteti**.

## <a name="results"></a>Rezultati

Rezultati iz toka posla se čuvaju u entitetu konfigurisanom tokom faze izlaznih parametara modela. Ovim podacima možete pristupiti sa [stranice entiteta](entities.md) ili pomoću [API pristupa](apis.md).

### <a name="api-access"></a>API pristup

Da bi određeni OData upit dobio podatke iz entiteta prilagođenog modela, koristite sledeći format:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Zamenite `<your instance id>` sa ID-om vašeg Customer Insights okruženja, koji ćete pronaći u adresnoj traci svog pregledača kada pristupite usluzi Customer Insights.

1. Zamenite `<custom model output entity>` nazivom entiteta koje ste naveli tokom koraka parametara izlaznih parametara modela prilagođene konfiguracije modela.

1. Zamenite `<guid value>` ID-om klijenta čijem zapisu želite da pristupite. Taj ID obično možete pronaći na [stranica profila klijenta](customer-profiles.md) u polju CustomerID.

## <a name="frequently-asked-questions"></a>Najčešća pitanja

- Zašto ne mogu da vidim svoj kanal prilikom podešavanja toka posla prilagođenog modela?    
  Ovaj problem je često uzrokovan problemom konfiguracije u kanalu. Uverite se da je [ulazni parametar konfigurisan](azure-machine-learning-experiments.md#dataset-configuration) i da su [izlazni parametri skladišta podataka i putanje](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) takođe konfigurisani.

- Šta znači greška „Ne mogu da sačuvam tok posla obaveštavanja“?    
  Korisnici obično vide ovu poruku o grešci ako u radnom prostoru nemaju administratorske privilegije pristupa za vlasnika ili korisnika. Korisniku je potreban viši nivo dozvola da omogući usluzi Customer Insights da obradi tok posla kao uslugu, umesto da koristi korisničke akreditive za naredna pokretanja toka posla.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
