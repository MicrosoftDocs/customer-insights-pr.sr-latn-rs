---
title: Prilagođeni modeli mašinskog učenja | Microsoft Docs
description: Radite sa prilagođenim modelima iz Azure mašinskog učenja u usluzi Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609763"
---
# <a name="custom-machine-learning-models"></a>Prilagođeni modeli mašinskog učenja

> [!NOTE]
> Podrška za Mašinsko učenje Studio (klasika) završiće se 31. avgusta 2024. godine. Preporučujemo da pređete na [Azure Mašinsko učenje do](/azure/machine-learning/overview-what-is-azure-machine-learning) tog datuma.
>
> Počevši od 1. decembra 2021. godine, nećete moći da kreirate nove Mašinsko učenje Studio (klasične) resurse. Do 31. avgusta 2024. možete nastaviti da koristite postojeće Mašinsko učenje Studio (klasične) resurse. Više informacija potražite u članku [Migracija u Azure Mašinsko učenje](/azure/machine-learning/migrate-overview).

Prilagođeni modeli vam omogućava da upravljate tokovima posla zasnovanim na Azure Mašinsko učenje modelima. Tokovi posla pomažu vam da odaberete podatke od kojih želite da generišete uvid i da rezultate mapirate sa objedinjenim podacima o klijentima. Za više informacija o izradi prilagođenih ML modela pogledajte [Koristite modele zasnovane na Azure mašinskom učenju](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Preduslovi

- Web usluge objavljene preko [Azure Mašinsko učenje grupnih cevovoda](/azure/machine-learning/concept-ml-pipelines).
- Naftovod mora biti objavljen u okviru krajnja [tačka](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Azure [Data Lake Gen2 nalog za skladištenje povezan](/azure/storage/blobs/data-lake-storage-quickstart-create-account) sa instancom Azure studija.
- Za Azure Mašinsko učenje radne prostore sa dozvolama za Azure ili administratore korisničkog pristupa Azure Mašinsko učenje prostoru.

  > [!NOTE]
  > Podaci se prenose između Customer Insights instanci i izabranih Azure veb-usluga ili kanala u toku posla. Kada prenosite podatke u Azure uslugu, uverite se da je usluga konfigurisana da obrađuje podatke na način neophodan za poštovanje svih zakonskih ili regulatornih zahteva za te podatke za vašu organizaciju, kao i na lokaciji koja je za to neophodna.

## <a name="add-a-new-workflow"></a>Dodavanje novog toka posla

1. Idite na **Obaveštavanje** > **Prilagođeni modeli** i izaberite **Novi tok posla**.

1. Navedite prepoznatljivo **ime**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Snimak ekrana okna „Novi tok posla“.":::

1. Izaberite organizaciju koja sadrži veb-uslugu u **zakupcu koji sadrži vašu veb-uslugu**.

1. Ako je pretplata na Azure mašinsko učenje u drugom zakupcu u odnosu na Customer Insights, odaberite **Prijavite se** pomoću akreditiva za odabranu organizaciju.

1. Izaberite **Radne prostore** povezane sa vašom veb-uslugom.

1. Odaberite Azure Mašinsko učenje u Web usluzi **koja sadrži padajuću listu** modela. Zatim izaberite **Sledeće**.
   Saznajte više o [objavljivanju kanala u Azure mašinskom učenju pomoću dizajnera](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ili [ SDK-a](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Za svaki **Unos veb-usluge**, izaberite odgovarajući **Entitet** iz usluge Customer Insights. Zatim izaberite **Sledeće**.
   > [!NOTE]
   > Tok posla prilagođenog modela primenjivaće heuristiku za mapiranje polja za unos veb-usluga u atribute entiteta na osnovu imena i tipa podataka polja. Videćete grešku ako polje veb-usluge ne može da se preslika na entitet.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Konfigurisanje toka posla.":::

1. Za **parametre izlaznog modela** postavite sledeća svojstva:
   - **Ime entiteta za** rezultate proizvodnje gasovoda
   - **Izlazna skladište podataka ime parametra** vašeg grupnog cevovoda
   - **Ime parametra izlazne putanje** vašeg grupnog cevovoda

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Okno izlaznih parametara modela.":::

1. Izaberite odgovarajući atribut iz ID-a **kupca u rezultatima** koji identifikuju kupce i izaberite **Sačuvaj**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Povežite rezultate sa oknom podataka klijenata.":::

   Ekran " **Sačuvani tok** posla" prikazuje detalje o toku posla. Ako ste konfigurisali tok posla za Azure Mašinsko učenje, "Uvidi kupaca" se priključuje na radni prostor koji sadrži cevovod. Uvidi klijenata će dobiti **saradnik na** Azure radnom prostoru.

1. Izaberite **Gotovo**. Prikazaće **se stranica "** Prilagođeni modeli".

1. Izaberite vertikalnu elipsu () za&vellip; tok posla i izaberite **pokreni**. Tok posla se takođe automatski pokreće sa svakim planiranim [osvežavanje](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Upravljanje postojećim tokom posla

Idite na prilagođene **modele** > **obaveštajne** službe da biste prikazali tokove posla koje ste kreirali.

Izaberite tok posla da biste prikazali dostupne radnje.

- **Uređivanje** toka posla
- **Pokretanje** toka posla
- [**Brisanje**](#delete-a-workflow) toka posla

### <a name="edit-a-workflow"></a>Izmena toka posla

1. Idite na **obaveštajne** > **prilagođene modele**.

1. Pored toka posla koji želite da ažurirate izaberite vertikalnu elipsu () i izaberite&vellip; stavku **Uredi**.

1. Promenite **ime za prikaz** ako je potrebno i kliknite na dugme "**Dalje"**.

1. Za svaki **unos Web usluge** ažurirajte odgovarajući entitet iz **uvida** klijenata, ako je potrebno. Zatim izaberite **Sledeće**.

1. Za **izlazne parametre modela** promenite nešto od sledećeg:
   - **Ime entiteta za** rezultate proizvodnje gasovoda
   - **Izlazna skladište podataka ime parametra** vašeg grupnog cevovoda
   - **Ime parametra izlazne putanje** vašeg grupnog cevovoda

1. Promenite odgovarajući atribut iz ID-a **kupca u rezultatima da biste** identifikovali kupce. Odaberite atribut iz izlaza zaključka sa vrednostima sličnim koloni sa ID-om klijenta entiteta klijenta. Ako nemate takvu kolonu u skup podataka, odaberite atribut koji jedinstveno identifikuje red.

1. Izaberite stavku **Sačuvaj**

### <a name="delete-a-workflow"></a>Brisanje toka posla

1. Idite na **obaveštajne** > **prilagođene modele**.

1. Pored toka posla koji želite da izbrišete izaberite vertikalnu elipsu () i izaberite&vellip; stavku **Izbriši**.

1. Potvrdite brisanje.

Vaš tok posla će biti izbrisan. Entitet [koji je kreiran](entities.md) kada ste kreirali tok posla se nastavlja i može se prikazati sa stranice " **Entiteti** > **podataka** ".

## <a name="view-the-results"></a>Prikazivanje rezultata

Rezultati toka posla skladište se u imenu entiteta definisanom za parametre **izlaznog modela**. Pristupite ovim podacima sa stranice [**"Entiteti podataka** > **·**" ili sa](entities.md) API [pristupom](apis.md).

### <a name="api-access"></a>API pristup

Da bi određeni OData upit dobio podatke iz entiteta prilagođenog modela, koristite sledeći format:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Zamenite `<your instance id>` ID-om okruženja "Uvidi kupaca" koje se prikazuje na traci adresa pregledača kada pristupate uvidima klijenata.

1. Zamenite `<custom model output entity>` imem entiteta koje ste dali za parametre **izlaznog modela**.

1. Zamenite `<guid value>` ID-om kupca kome želite da pristupite. Ovaj ID se prikazuje na stranici [profila kupaca](customer-profiles.md) u polju ID kupca.

## <a name="frequently-asked-questions"></a>Najčešća pitanja

- Zašto ne mogu da vidim svoj kanal prilikom podešavanja toka posla prilagođenog modela?
  Ovaj problem je često uzrokovan problemom konfiguracije u kanalu. Uverite se da je [ulazni parametar konfigurisan](azure-machine-learning-experiments.md#dataset-configuration) i da su [izlazni parametri skladišta podataka i putanje](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) takođe konfigurisani.

- Šta znači greška „Ne mogu da sačuvam tok posla obaveštavanja“? 
  Korisnici obično vide ovu poruku o grešci ako u radnom prostoru nemaju administratorske privilegije pristupa za vlasnika ili korisnika. Korisniku je potreban viši nivo dozvola da omogući usluzi Customer Insights da obradi tok posla kao uslugu, umesto da koristi korisničke akreditive za naredna pokretanja toka posla.

- Da li je podržan krajnja tačka /privatni link za moj tok posla prilagođenog modela?
  Customer Insights trenutno ne podržava privatne krajnja tačka za prilagođene modele van okvira, ali je dostupno ručno zaobilazno rešenje. Za detalje se obratite podršci.

## <a name="responsible-ai"></a>Odgovorni AI

Predviđanja nude mogućnosti za stvaranje boljeg korisničkog iskustva, poboljšanje poslovnih prilika i tokova prihoda. Preporučujemo vam da uravnotežite vrednost predviđanja sa uticajem koji ima i odstupanjima koja se mogu uvesti na etičan način. Saznajte više o tome kako Microsoft [primenjuje odgovoran AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Takođe možete saznati o [tehnikama i procesima za odgovorno mašinsko učenje](/azure/machine-learning/concept-responsible-ml) specifičnim za Azure mašinsko učenje.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
