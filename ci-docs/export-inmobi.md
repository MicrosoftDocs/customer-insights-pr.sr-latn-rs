---
title: Izvezi podatke o uvidima kupaca u InMobi
description: Saznajte kako da konfigurišete vezu i izvezete u InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195905"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Izvezi podatke o uvidima klijenata u InMobi (pregled)

Izvezite liste segmenata ili druge podatke iz instance "Uvidi kupaca" [u InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Preduslovi

- InMobi [nalog i](https://www.inmobi.com/) administrativni akreditivi.
- Ime [Azure Blob Storage naloga](/azure/storage/blobs/create-data-lake-storage-account) i ključ naloga. Da biste pronašli ime i ključ, pogledajte članak Upravljanje [postavkama naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).
- Azure [Blob Storage kontejner u koji ćete](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) izvoziti InMobi podatke.
- InMobi će kreirati direktnu vezu sa vašim Blob skladištem i konfigurisati automatski uvoz vaših podataka u InMobi. Obratite se predstavniku InMobija da pokrenete proces.

## <a name="known-limitations"></a>Poznata ograničenja

- Za Azure Blob Storage odaberite između standardnih [performansi i premium performansi](/azure/storage/blobs/storage-blob-performance-tiers). Ako odaberete nivo premijum performansi, izaberite [premijum ove blob objekata tip poslovnog kontakta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Podešavanje veze sa skladištem Azure blob

[Podesite vezu sa Azure skladištem bloba](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[Konfigurišite izvoz](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
