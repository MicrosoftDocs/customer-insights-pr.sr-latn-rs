---
title: Izvezite Customer Insights podatke u Azure Data Lake Storage Gen2
description: Saznajte kako da konfigurišete vezu sa uslugom Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22eee11666752459a1750d728c4e254ab0c59e58
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947247"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Izvoz liste segmenata i drugih podataka u Azure Data Lake Storage Gen2 (verzija za pregled)

Skladištite podatke iz usluge Customer Insights u Data Lake Storage Gen2 nalog ili ih koristite za prenos podataka u druge aplikacije.

## <a name="known-limitations"></a>Poznata ograničenja

1. Za Azure Data Lake Storage Gen2 možete birati između [nivoa standardnih performansi i premijum performansi](/azure/storage/blobs/create-data-lake-storage-account) kada kreirate nalog za skladištenje za svoje jezero podataka. Ako odaberete nivo premijum performansi, izaberite premijum ove blob objekata tip poslovnog kontakta.

## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Podešavanje veze sa Azure Data Lake Storage Gen2

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **Azure Data Lake Gen 2** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **Naziv poslovnog kontakta**, **Ključ poslovnog kontakta** i **Kontejner** za vaš Azure Data Lake Storage Gen2.
    - Da biste saznali kako da napravite nalog za skladištenje sa kojim ćete koristiti Azure Data Lake Storage Gen2, pogledajte članak [Kreiranje naloga za skladištenje](/azure/storage/blobs/create-data-lake-storage-account). 
    - Da biste saznali više o nazivu naloga Azure Data Lake Gen2 skladišta i ključu skladišta, pogledajte [Upravljanje podešavanjima naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka **Azure Data Lake**. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. Izaberite polje pored svakog entiteta koji želite da izvezete na ovo odredište.

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).
Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).

Izvezeni podaci se čuvaju u Azure Data Lake Gen 2 kontejneru za skladištenje koji ste konfigurisali.

> [!TIP]
> Izvoz entiteta koji sadrže veliku količinu podataka može dovesti do više CSV datoteka u istoj fascikli za svaki izvoz. Deljenje izvoza se dešava iz razloga performansi da bi se umanjilo vreme potrebno za dovršavanje izvoza.

[!INCLUDE [footer-include](includes/footer-banner.md)]
