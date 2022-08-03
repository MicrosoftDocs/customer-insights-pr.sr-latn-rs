---
title: Izvoz segmenata u Adobe Experience Platform (pregled)
description: Saznajte kako da koristite segmente "Uvid kupca" u Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195307"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Izvoz segmenata u Adobe Experience Platform (pregled)

Izvezi segmente koji ciljaju relevantne grupe korisnika lokacije u Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a>Preduslovi

- Dozvola Adobe Experience Platform.
- Licenca Adobe za standard kampanje.
- Ime [Azure Blob Storage naloga](/azure/storage/blobs/create-data-lake-storage-account) i ključ naloga. Da biste pronašli ime i ključ, pogledajte članak Upravljanje [postavkama naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).
- Azure [Blob skladišni kontejner](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Pregled kampanje

Da bismo bolje razumeli kako možete da koristite segmente iz "Uvida kupaca" Adobe Experience Platform u, pogledajmo fiktivnu probnu kampanju.

Pretpostavimo da vaše preduzeće nudi mesečnu uslugu zasnovanu na pretplati za klijente u Sjedinjenim Državama. Želite da identifikujete klijente koji treba da obnove pretplate u narednih osam dana, ali još uvek nisu obnovili pretplatu. Da biste zadržali ove klijente, treba da im pošaljete promotivnu ponudu putem e-pošte koristeći Adobe Experience Platform.

U ovom primeru želimo da jednom pokrenemo promotivnu kampanju e-pošte. Ovaj članak ne pokriva slučaj korišćenja sa više pokretanja kampanje.

## <a name="identify-your-target-audience"></a>Identifikujte svoju ciljnu grupu

U našem scenariju, pretpostavljamo da su e-adrese klijenata dostupne u uvidima klijenata i da su njihove promotivne preferencije analizirane kako bi se identifikovali članovi segmenta.

Segment [koji ste definisali u "Uvidima kupaca"](segments.md) zove se **ChurnProneCustomers i planirate** da ovim korisnicima pošaljete promociju e-pošte.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimak ekrana stranice segmenata sa kreiranim segmentom ChurnProneCustomers.":::

E-poruka sa ponudom koju želite da pošaljete sadrži ime, prezime i datum završetka pretplate klijenta. Poruka obaveštava klijente o popustu koji će dobiti ako obnove pretplatu pre nego što se završi.

## <a name="export-your-target-audience"></a>Izvezite svoju ciljnu grupu

Konfigurisaćemo izvoz iz uvida kupaca u Azure Blob Storage nalog.

### <a name="set-up-connection-to-azure-blob-storage"></a>Podešavanje veze sa skladištem Azure blob

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i odaberite **Azure skladište bloba**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **Naziv naloga**, **Ključ naloga** i **Kontejner** za vaš nalog za skladište blob objekta u koji želite da izvezete segment.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimak ekrana konfiguracije naloga skladišta. ":::

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

### <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Azure skladišta blob objekta. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Odaberite segment koje želite da izvezete. U ovom primeru, to je **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimak ekrana korisničkog interfejsa za odabir segmenta sa izabranim segmentom ChurnProneCustomers.":::

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Uverite se da je broj zapisa u izvezenom segmentu unutar dozvoljenog ograničenja vaše licence za uslugu Adobe Campaign Standard.

Izvezeni podaci se skladište u kontejneru Azure blob skladišta koji ste konfigurisali. Sledeće putanje fasciklu se automatski kreiraju u vašem kontejneru:

- Za izvorne entitete i entitete koje generiše sistem:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- Datoteka *model.json* za izvezene entitete nalazi se na nivou *%ExportDestinationName%*.

  Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definisanje model podataka o iskustvu (XDM) u usluzi Adobe Experience Platform

Pre nego što se izvezeni podaci iz uvida klijenata mogu koristiti u okviru Adobe Experience Platform, definišite šemu modela podataka iskustva i konfigurišite podatke [za profil kupca u realnom vremenu](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Saznajte [šta je to XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) i razjasnite [osnove sastavljanja šeme](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Uvoz podataka u Adobe Experience Platform

Uvezite pripremljene korisnici podataka iz uvida kupaca u Adobe Experience Platform.

1. [Kreirajte Azure blob storage izvornu vezu](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Konfigurišite tok podataka za](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) grupnu vezu skladišta u oblaku da biste uvezli izlaz segmenta iz uvida kupaca u Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Kreiranje ciljne grupe u usluzi Adobe Campaign Standard

Da bismo poslali e-poštu za ovu kampanju, koristićemo uslugu Adobe Campaign Standard.

1. [Kreirajte korisnici standardu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission)Adobe kampanje koristeći podatke u programu Adobe Experience Platform.

1. [Koristite izradu segmenta](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) u Adobe standardnoj kampanji da biste definisali korisnici na osnovu podataka u programu Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Kreiranje i slanje e-pošte u usluzi Adobe Campaign Standard

Kreirajte sadržaj e-poruke, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poruku.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Primer e-poruke sa ponudom za obnovu iz usluge Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
