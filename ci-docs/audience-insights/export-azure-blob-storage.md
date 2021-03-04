---
title: Izvezite Customer Insights podatke u Azure skladište blob objekata
description: Saznajte kako da konfigurišete vezu sa Azure skladištem blob objekata.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269209"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Konektor za Azure skladište blob objekata (pregled)

Uskladištite Customer Insights podatke u Azure skladište blob objekata ili ih koristite za prenos podataka u druge aplikacije.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Konfigurisanje konektora za Azure skladište blob objekata

1. U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.

1. U odeljku **Azure skladište blob objekata** izaberite **Podesi**.

1. Unesite **Naziv naloga**, **Ključ naloga** i **Kontejner** za vaš nalog za Azure skladište blob objekata.
    - Da biste saznali više o pronalaženju imena i ključa naloga za Azure skladište blob objekta, pogledajte [Upravljajte podešavanjima naloga za skladištenje na Azure portalu](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Da biste saznali kako da kreirate kontejner, pogledajte članak [Kreiranje kontejnera](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Dajte odredištu prepoznatljivo ime u polju **Ime za prikaz**.

1. Izaberite **Sledeće**.

1. Izaberite polje pored svakog entiteta koji želite da izvezete na ovo odredište.

1. Izaberite stavku **Sačuvaj**.

Izvezeni podaci se čuvaju u kontejneru Azure skladišta blob objekata koji ste konfigurisali. Sledeće putanje fasciklu se automatski kreiraju u vašem kontejneru:

- Za izvorne entitete i entitete koje generiše sistem: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Primer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model.json za izvezene entitete će se nalazi na nivou %ExportDestinationName%
  - Primer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Izvoz podataka

Možete da [izvezete podatke na zahtev](export-destinations.md#export-data-on-demand). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]