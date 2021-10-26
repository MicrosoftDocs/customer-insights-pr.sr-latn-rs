---
title: Izvoz Customer Insights podataka u Azure skladište blob objekta
description: Saznajte kako da konfigurišete vezu i izvezete sadržaj u skladište blob objekta.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d02c09a1869d0099db4861b65ac8ff006914873e
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605867"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Izvoz liste segmenata i drugih podataka u Azure skladište blob objekta (pregled)

Skladištite Customer Insights podatke u skladište blob objekta ili ih koristite za prenos podataka u druge aplikacije.

## <a name="known-limitations"></a>Poznata ograničenja

1. Za skladište Azure blob objekta možete birati između [nivoa standardnih performansi i premijum performansi](/azure/storage/blobs/storage-blob-performance-tiers). Ako odaberete nivo premijum performansi, izaberite [premijum ove blob objekata tip poslovnog kontakta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>Podesite vezu sa skladištem blob objekta

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **Azure skladište blob objekta** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **Naziv naloga**, **Ključ naloga** i **Kontejner** za svoj nalog skladišta blob objekta.
    - Da biste saznali više o tome kako da pronađete naziv naloga skladišta blob objekta i ključ naloga, pogledajte [Upravljanje podešavanjima naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).
    - Da biste saznali kako da kreirate kontejner, pogledajte članak [Kreiranje kontejnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Izaberite **Sačuvaj** da biste kreirali vezu. 

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Ako ste uključili podešavanje mekog brisanja za nalog Azure skladišta blob objekta, izvoz neće uspeti. Isključite meko brisanje za izvoz podataka u blob objekte. Za više informacija pogledajte [Omogućavanje mekog brisanja blob objekata](/azure/storage/blobs/soft-delete-blob-enable.md)

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Azure skladišta blob objekta. Ako ne vidite naziv ovog odeljka, tada vam nisu dostupne veze ovog tipa.

1. Izaberite polje pored svakog entiteta koji želite da izvezete na ovo odredište.

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).     

Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 

Izvezeni podaci se čuvaju u kontejneru skladišta blob objekta koji ste konfigurisali. Sledeće putanje fasciklu se automatski kreiraju u vašem kontejneru:

- Za izvorne entitete i entitete koje generiše sistem:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Primer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- Datoteka model.json za izvezene entitete biće na nivou %ExportDestinationName%.  
  - Primer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
