---
title: Izvoz podataka u Azure skladište bloba (pregled)
description: Saznajte kako da konfigurišete vezu i izvezete sadržaj u skladište blob objekta.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195721"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Izvoz podataka u Azure skladište bloba (pregled)

Skladištite Customer Insights podatke u skladište blob objekta ili ih koristite za prenos podataka u druge aplikacije.

## <a name="prerequisites"></a>Preduslovi

- Ime [Azure Blob Storage naloga](/azure/storage/blobs/create-data-lake-storage-account) i ključ naloga. Da biste pronašli ime i ključ, pogledajte članak Upravljanje [postavkama naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).
- Azure [Blob skladišni kontejner](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Poznata ograničenja

- Za Azure Blob Storage odaberite između standardnih [performansi i premium performansi](/azure/storage/blobs/storage-blob-performance-tiers). Ako odaberete nivo premijum performansi, izaberite [premijum ove blob objekata tip poslovnog kontakta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Podešavanje veze sa skladištem bloba

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i odaberite **Azure skladište bloba**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **Naziv naloga**, **Ključ naloga** i **Kontejner** za svoj nalog skladišta blob objekta.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Da biste konfigurisali ovaj izvoz, morate imati [dozvolu](export-destinations.md#set-up-a-new-export) za ovaj tip veze.

> [!IMPORTANT]
> Ako ste uključili postavku [mekog brisanja](/azure/storage/blobs/soft-delete-blob-enable) za Azure Blob Storage nalog, izvoz neće uspeti. Isključite meko brisanje za izvoz podataka u blob objekte.

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Azure skladišta blob objekta. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Unesite ime fascikle za skladište bloba.

1. Izaberite polje pored svakog entiteta koji želite da izvezete na ovo odredište.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Izvezeni podaci se čuvaju u kontejneru skladišta blob objekta koji ste konfigurisali. Sledeće putanje fasciklu se automatski kreiraju u vašem kontejneru:

- Za izvorne entitete i entitete koje generiše sistem:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Primer: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Izvoz entiteta koji sadrže veliku količinu podataka može dovesti do više CSV datoteka u istoj fascikli za svaki izvoz. Deljenje izvoza se dešava iz razloga performansi da bi se umanjilo vreme potrebno za dovršavanje izvoza.

- Model.json za izvezene entitete se nalazi na nivou *%ExportDestinationName%*.  
  
  Primer: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
