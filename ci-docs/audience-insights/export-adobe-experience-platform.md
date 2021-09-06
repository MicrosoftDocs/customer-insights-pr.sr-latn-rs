---
title: Izvoz Customer Insights podataka u Adobe Experience Platform
description: Saznajte kako da koristite segmente uvida u ciljnu grupu u usluzi Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fac976a49b1b5c5485b75e1262135738c913bd2230be7df8aa0ec12c59734053
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032134"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Korišćenje Customer Insights segmenata u usluzi Adobe Experience Platform (verzija za pregled)

Kao korisnik uvida u ciljnu grupu u usluzi Dynamics 365 Customer Insights, možda ste kreirali segmente da biste marketinške kampanje učinili efikasnijim ciljajući relevantne ciljne grupe. Da biste koristili segment iz uvida u ciljnu grupu u usluzi Adobe Experience Platform i aplikacijama poput Adobe Campaign Standard, morate da sledite nekoliko koraka opisanih u ovom članku.

:::image type="content" source="media/AEP-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a>Preduslovi

-   Dynamics 365 Customer Insights licenca
-   Adobe Experience Platform licenca
-   Licenca za Adobe Campaign Standard
-   Nalog Azure skladišta blob objekta

## <a name="campaign-overview"></a>Pregled kampanje

Da biste bolje razumeli kako možete da koristite segmente iz uvida u ciljnu grupu u usluzi Adobe Experience Platform, pogledajmo izmišljeni primer kampanje.

Pretpostavimo da vaše preduzeće nudi mesečnu uslugu zasnovanu na pretplati za klijente u Sjedinjenim Državama. Želite da identifikujete klijente koji treba da obnove pretplate u narednih osam dana, ali još uvek nisu obnovili pretplatu. Da biste zadržali ove klijente, treba da im pošaljete promotivnu ponudu putem e-pošte koristeći Adobe Experience Platform.

U ovom primeru želimo da jednom pokrenemo promotivnu kampanju e-pošte. Ovaj članak ne pokriva slučaj korišćenja sa više pokretanja kampanje.

## <a name="identify-your-target-audience"></a>Identifikujte svoju ciljnu grupu

U našem scenarij,u pretpostavljamo da su adrese e-pošte klijenata dostupne u uvidima o korisnicima i da su analizirane njihove promotivne željene opcije kako bi se identifikovali članovi segmenta.

[Segment koji ste definisali uvidom o korisnicima](segments.md) se zove **ChurnProneCustomers** i planirate da ovim klijentima pošaljete e-poruku sa promocijom.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimak ekrana stranice segmenata sa kreiranim segmentom ChurnProneCustomers.":::

E-poruka sa ponudom koju želite da pošaljete sadrži ime, prezime i datum završetka pretplate klijenta. Poruka obaveštava klijente o popustu koji će dobiti ako obnove pretplatu pre nego što se završi.

## <a name="export-your-target-audience"></a>Izvezite svoju ciljnu grupu

Kada je identifikovana ciljna grupa, možemo da konfigurišemo izvoz iz uvida o korisnicima na nalog Azure skladišta blob objekta.

### <a name="configure-a-connection"></a>Konfigurisanje veze

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **Azure skladište blob objekta** ili izaberite **Podesi** na pločici **Azure skladište blob objekta** da biste konfigurisali vezu.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Pločica za konfiguraciju za Azure skladište blob objekta."::: 

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **Naziv naloga**, **Ključ naloga** i **Kontejner** za vaš nalog za skladište blob objekta u koji želite da izvezete segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimak ekrana konfiguracije naloga skladišta. "::: 
   
    - Da biste saznali više o tome kako da pronađete naziv naloga skladišta blob objekta i ključ naloga, pogledajte [Upravljanje podešavanjima naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).
    - Da biste saznali kako da kreirate kontejner, pogledajte članak [Kreiranje kontejnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Izaberite **Sačuvaj** da biste kreirali vezu. 

### <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Azure skladišta blob objekta. Ako ne vidite naziv ovog odeljka, tada vam nisu dostupne veze ovog tipa.

1. Odaberite segment koje želite da izvezete. U ovom primeru, to je **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimak ekrana korisničkog interfejsa za odabir segmenta sa izabranim segmentom ChurnProneCustomers.":::

1. Izaberite stavku **Sačuvaj**.

Kada sačuvate odredište za izvoz, pronaći ćete ga u dijalogu **Podaci** > **Izvozi**.

Sada možete da [izvozite segment na zahtev](export-destinations.md#run-exports-on-demand). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md).

> [!NOTE]
> Uverite se da je broj zapisa u izvezenom segmentu unutar dozvoljenog ograničenja vaše licence za uslugu Adobe Campaign Standard.

Izvezeni podaci se čuvaju u kontejneru Azure skladišta blob objekta koji ste ranije konfigurisali. Sledeća putanja do fascikle se automatski kreira u vašem kontejneru:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Datoteka *model.json* za izvezene entitete nalazi se na nivou *%ExportDestinationName%*.

Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definisanje model podataka o iskustvu (XDM) u usluzi Adobe Experience Platform

Pre nego što se izvezeni podaci iz uvida u ciljnu grupu mogu koristiti unutar usluge Adobe Experience Platform, potrebno je da definišemo šemu modela podataka o iskustvu i [konfigurišemo podatke za profil klijenta u realnom vremenu](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Saznajte [šta je to XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) i razjasnite [osnove sastavljanja šeme](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Uvoz podataka u Adobe Experience Platform

Sada kada je sve na svom mestu, moramo da uvezemo pripremljene podatke o ciljnoj grupi iz uvida o ciljnoj grupi u uslugu Adobe Experience Platform.

Prvo [kreirajte izvornu vezu sa Azure skladištem blob objekta](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Kada definišete izvornu vezu, [konfigurišite tok podataka](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) za paketnu vezu za skladištenje u oblaku da biste uvezli izlaz segmenta iz uvida u ciljnu grupu u uslugu Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Kreiranje ciljne grupe u usluzi Adobe Campaign Standard

Da bismo poslali e-poštu za ovu kampanju, koristićemo uslugu Adobe Campaign Standard. Nakon uvoza podataka u Adobe Experience Platform, treba da [napravimo ciljnu grupu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) u usluzi Adobe Campaign Standard koristeći podatke u usluzi Adobe Experience Platform.


Saznajte kako da [koristite alatku za kreiranje segmenata](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) u usluzi Adobe Campaign Standard da biste definisali ciljnu grupu na osnovu podataka u usluzi Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Kreiranje i slanje e-pošte u usluzi Adobe Campaign Standard

Kreirajte sadržaj e-poruke, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poruku.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Primer e-poruke sa ponudom za obnovu iz usluge Adobe Campaign Standard.":::
