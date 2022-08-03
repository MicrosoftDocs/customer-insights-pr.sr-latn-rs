---
title: Izvezi podatke Azure Data Lake Storage u Gen2 (pregled)
description: Saznajte kako da konfigurišete vezu sa uslugom Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196457"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Izvezi podatke Azure Data Lake Storage u Gen2 (pregled)

Skladištite podatke iz usluge Customer Insights u Data Lake Storage Gen2 nalog ili ih koristite za prenos podataka u druge aplikacije.

## <a name="prerequisites"></a>Preduslovi

- Nalog za [skladištenje koji će se koristiti sa Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Da biste pronašli ime i ključ naloga za skladištenje, pogledajte članak [Upravljanje postavkama naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).
- Azure [Blob skladišni kontejner](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Poznata ograničenja

- Za Azure Data Lake Storage Gen2 odaberite između standardnih [performansi i premium performansi](/azure/storage/blobs/create-data-lake-storage-account). Ako odaberete nivo premijum performansi, izaberite [premijum ove blob objekata tip poslovnog kontakta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Podešavanje veze sa gen2 Azure Data Lake Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i odaberite **Azure Data Lake Gen 2**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **Naziv poslovnog kontakta**, **Ključ poslovnog kontakta** i **Kontejner** za vaš Azure Data Lake Storage Gen2.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odeljka Azure jezero sa podacima. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Unesite ime fascikle za Azure Data Lake Storage Gen2 skladište.

1. Izaberite polje pored svakog entiteta koji želite da izvezete na ovo odredište.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Izvezeni podaci se čuvaju u Azure Data Lake Gen 2 kontejneru za skladištenje koji ste konfigurisali.

> [!TIP]
> Izvoz entiteta koji sadrže veliku količinu podataka može dovesti do više CSV datoteka u istoj fascikli za svaki izvoz. Deljenje izvoza se dešava iz razloga performansi da bi se umanjilo vreme potrebno za dovršavanje izvoza.

[!INCLUDE [footer-include](includes/footer-banner.md)]
