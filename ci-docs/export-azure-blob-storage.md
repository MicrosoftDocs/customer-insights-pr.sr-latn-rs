---
title: Izvoz podataka u Azure skladište bloba (pregled)
description: Saznajte kako da konfigurišete vezu i izvezete sadržaj u skladište blob objekta.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 059c8364ca0f3740bc0e4ffeeeba94246c9e5696
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055507"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Izvoz podataka u Azure skladište bloba (pregled)

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
> Ako ste uključili podešavanje mekog brisanja za nalog Azure skladišta blob objekta, izvoz neće uspeti. Isključite meko brisanje za izvoz podataka u blob objekte. Za više informacija pogledajte [Omogućavanje mekog brisanja blob objekata](/azure/storage/blobs/soft-delete-blob-enable)

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
  
  > [!TIP]
  > Izvoz entiteta koji sadrže veliku količinu podataka može dovesti do više CSV datoteka u istoj fascikli za svaki izvoz. Deljenje izvoza se dešava iz razloga performansi da bi se umanjilo vreme potrebno za dovršavanje izvoza.

- Datoteka model.json za izvezene entitete biće na nivou %ExportDestinationName%.  
  - Primer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]