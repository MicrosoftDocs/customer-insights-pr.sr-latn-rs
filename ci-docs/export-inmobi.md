---
title: Izvezi podatke o uvidima kupaca u InMobi
description: Saznajte kako da konfigurišete vezu i izvezete u InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059617"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Izvoz liste segmenata i drugih podataka u InMobi (pregled)

Izvezite liste segmenata ili druge podatke iz instance "Uvidi kupaca" [u InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Preduslovi

1. Imate [InMobi nalog i](https://www.inmobi.com/) administrativne akreditive.
1. Imate ime Azure Blob naloga za skladištenje i odgovarajući ključ naloga. Više informacija potražite u članku [Upravljanje postavkama naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage). Postoji kontejner na računu za skladištenje u koji treba izvesti InMobi podatke. Više informacija potražite u članku [Kreiranje kontejnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi će kreirati direktnu vezu sa vašim Blob skladištem i konfigurisati automatski uvoz vaših podataka u InMobi. Obratite se predstavniku InMobija da pokrenete proces.

## <a name="known-limitations"></a>Poznata ograničenja

1. Za Azure skladište bloba možete birati između standardnih [performansi i premium performansi](/azure/storage/blobs/storage-blob-performance-tiers). Ako odaberete nivo premijum performansi, izaberite [premijum ove blob objekata tip poslovnog kontakta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Podešavanje veze sa Azure skladištem bloba i konfigurisanje izvoza

1. Sledite uputstva da [biste podešavanju veze sa skladištem Azure bloba](export-azure-blob-storage.md).
2. Sledite uputstva da biste [konfigurisali izvoz](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
