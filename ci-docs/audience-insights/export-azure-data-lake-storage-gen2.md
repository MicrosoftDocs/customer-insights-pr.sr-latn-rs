---
title: Izvezite Customer Insights podatke u Azure Data Lake Storage Gen2
description: Saznajte kako da konfigurišete vezu sa uslugom Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596655"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Konektor za Azure Data Lake Storage Gen2 (pregled)

Skladištite podatke Customer Insights podataka u uslugu Azure Data Lake Storage Gen2 ili ih koristite za prenos podataka u druge aplikacije.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Konfigurišite konektor za Azure Data Lake Storage Gen2

1. U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.

1. Uz odeljku **Azure Data Lake Storage Gen2** izaberite **Podesi**.

1. Dajte odredištu prepoznatljivo ime u polju **Ime za prikaz**.

1. Unesite **Naziv poslovnog kontakta**, **Ključ poslovnog kontakta** i **Kontejner** za vaš Azure Data Lake Storage Gen2.
    - Da biste saznali kako da napravite nalog za skladištenje sa kojim ćete koristiti Azure Data Lake Storage Gen2, pogledajte članak [Kreiranje naloga za skladištenje](/azure/storage/blobs/create-data-lake-storage-account). 
    - Da biste saznali više o tome kako da pronađete ime poslovnog kontakta za Azure Data Lake Gen2 skladište, pogledajte članak [Upravljanje podešavanjima naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).

1. Izaberite **Sledeće**.

1. Izaberite polje pored svakog entiteta koji želite da izvezete na ovo odredište.

1. Izaberite stavku **Sačuvaj**.

## <a name="export-the-data"></a>Izvoz podataka

Možete da [izvezete podatke na zahtev](export-destinations.md#export-data-on-demand). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).