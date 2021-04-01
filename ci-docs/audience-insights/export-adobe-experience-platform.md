---
title: Izvoz Customer Insights podataka u Adobe platformu iskustva
description: Saznajte kako se koriste segmenti uvida o korisnicima u Adobe platformi iskustva.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596286"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Korišćenje Customer Insights segmenata u Adobe platformi iskustva (verzija za pregled)

Kao korisnik uvida o korisnicima za Dynamics 365 Customer Insights, možda ste kreirali segmente da biste marketinške kampanje učinili efikasnijim tako što ćete ciljati relevantne ciljne grupe. Da biste koristili segment iz uvida o korisnicima u Adobe platformi iskustva i aplikacijama poput Adobe Campaign Standard, potrebno je da sledite nekoliko koraka navedenih u ovom članku.

:::image type="content" source="media/AEP-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a>Preduslovi

-   Dynamics 365 Customer Insights licenca
-   Licenca za Adobe platformu iskustva
-   Licenca za Adobe Campaign Standard
-   Nalog Azure skladišta blob objekta

## <a name="campaign-overview"></a>Pregled kampanje

Da biste bolje razumeli kako možete da koristite segmente iz uvida o korisnicima u Adobe platformi iskustva, pogledajmo fiktivni primer kampanje.

Pretpostavimo da vaše preduzeće nudi mesečnu uslugu zasnovanu na pretplati za klijente u Sjedinjenim Državama. Želite da identifikujete klijente koji treba da obnove pretplate u narednih osam dana, ali još uvek nisu obnovili pretplatu. Da biste zadržali ove klijente, treba da im pošaljete promotivnu ponudu putem e-pošte, koristeći Adobe platformu iskustva.

U ovom primeru želimo da jednom pokrenemo promotivnu kampanju e-pošte. Ovaj članak ne pokriva slučaj korišćenja sa više pokretanja kampanje.

## <a name="identify-your-target-audience"></a>Identifikujte svoju ciljnu grupu

U našem scenarij,u pretpostavljamo da su adrese e-pošte klijenata dostupne u uvidima o korisnicima i da su analizirane njihove promotivne željene opcije kako bi se identifikovali članovi segmenta.

[Segment koji ste definisali uvidom o korisnicima](segments.md) se zove **ChurnProneCustomers** i planirate da ovim klijentima pošaljete e-poruku sa promocijom.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimak ekrana stranice segmenata sa kreiranim segmentom ChurnProneCustomers.":::

E-poruka sa ponudom koju želite da pošaljete sadrži ime, prezime i datum završetka pretplate klijenta. Poruka obaveštava klijente o popustu koji će dobiti ako obnove pretplatu pre nego što se završi.

## <a name="export-your-target-audience"></a>Izvezite svoju ciljnu grupu

Kada je identifikovana ciljna grupa, možemo da konfigurišemo izvoz iz uvida o korisnicima na nalog Azure skladišta blob objekta.

1. U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.

1. Na pločici **Azure skladište blob objekta** izaberite **Podesi**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Pločica za konfiguraciju za Azure skladište blob objekta.":::

1. Navedite **ime za prikaz** za ovo novo odredište za izvoz, a zatim unesite **Naziv naloga**, **Ključ naloga** i **Kontejner** naloga Azure skladišta blob objekta u koji želite da izvezete segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimak ekrana konfiguracije naloga skladišta. "::: 

   - Da biste saznali više o pronalaženju imena i ključa naloga za Azure skladište blob objekta, pogledajte [Upravljajte podešavanjima naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).

   - Da biste saznali kako da kreirate kontejner, pogledajte članak [Kreiranje kontejnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Izaberite **Sledeće**.

1. Odaberite segment koje želite da izvezete. U ovom primeru, to je **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimak ekrana korisničkog interfejsa za odabir segmenta sa izabranim segmentom ChurnProneCustomers.":::

1. Izaberite stavku **Sačuvaj**.

Kada sačuvate odredište za izvoz, pronaći ćete ga na listi **Administrator** > **Izvozi** > **Moja odredišta za izvoz**.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Snimak ekrana sa istaknutom listom izvoza i uzorkom segmenta.":::

Sada možete da [izvozite segment na zahtev](export-destinations.md#export-data-on-demand). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md).

> [!NOTE]
> Uverite se da je broj zapisa u izvezenom segmentu unutar dozvoljenog ograničenja vaše Adobe Campaign Standard licence.

Izvezeni podaci se čuvaju u kontejneru Azure skladišta blob objekta koji ste ranije konfigurisali. Sledeća putanja do fascikle se automatski kreira u vašem kontejneru:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Datoteka *model.json* za izvezene entitete nalazi se na nivou *%ExportDestinationName%*.

Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definišite model podataka o iskustvu (XDM) na Adobe platformi iskustva

Pre nego što budemo mogli da koristimo izvezene podatke iz uvida o korisnicima na Adobe platformi iskustva, moramo da definišemo šemu modela podataka iskustva i [konfigurišemo podatke za profil klijenta u realnom vremenu](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Saznajte [šta je to XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) i razjasnite [osnove sastavljanja šeme](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Uvezite podatke u Adobe platformu iskustva

Sada kada je sve na svom mestu, treba da uvezemo podatke o ciljnoj grupi iz uvida o korisnicima u Adobe platformi iskustva.

Prvo [kreirajte izvornu vezu sa Azure skladištem blob objekta](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Kada definišete izvornu vezu, [konfigurišite tok podataka](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) za grupno povezivanje sa skladištem u oblaku radi uvoza izlaza segmenta iz uvida o korisnicima u Adobe platformu iskustva.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Kreiranje korisnika u usluzi Adobe Campaign Standard

Da bismo poslali e-poruku za ovu kampanju, koristićemo Adobe Campaign Standard. Nakon uvoza podataka u Adobe platformu iskustva, treba da [kreiramo ciljnu grupu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) u usluzi Adobe Campaign Standard koristeći podatke na Adobe platformi iskustva.

Saznajte kako da [koristite alatku za pravljenje segmenata](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) u usluzi Adobe Campaign Standard da biste definisali ciljnu grupu na osnovu podataka u Adobe platformi iskustva.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Kreirajte i pošaljite e-poruku koristeći Adobe Campaign Standard

Kreirajte sadržaj e-poruke, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poruku.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Primer e-poruke sa ponudom obnove pretplate iz usluge Adobe Campaign Standard.":::