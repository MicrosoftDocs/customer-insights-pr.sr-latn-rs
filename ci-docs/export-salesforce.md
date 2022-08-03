---
title: Izvoz podataka u Salesforce Marketing Cloud (pregled)
description: Saznajte kako da konfigurišete vezu i izvezete je u Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197055"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Izvoz podataka u Salesforce Marketing Cloud (pregled)

Koristite podatke o klijentima u usluzi Salesforce Marketing Cloud tako što ćete ih izvesti putem lokacije protokola sigurnog prenosa datoteka (SFTP).

## <a name="prerequisites"></a>Preduslovi

- SFTP [domaćin za Salesforce Marketing Cloud i](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) odgovarajuće administrativne akreditive.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Podešavanje veze sa Salesforce marketinškim oblakom

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **dodaj vezu** i odaberite **Salesforce Marketing Cloud**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite **korisničko ime**, **lozinku**, **ime hosta** i **fasciklu za izvoz** za SFTP nalog.

1. Izaberite **Verifikuj** da testirate vezu.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka SFTP. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Odaberite da li želite da izvezete podatke **spakovano** ili **raspakovano** i **separator polja** za izvezene datoteke.

1. Izaberite entitete, npr.

   > [!NOTE]
   > Svaki izabrani entitet će biti podeljen na najviše pet izlaznih datoteka kada se izveze.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Izvezite Customer Insights podatke u sa SFTP lokacije Salesforce Marketing Cloud

1. Kreirajte [proširenja podataka u usluzi Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) za uvoz Customer Insights datoteke podataka sa SFTP lokacije.

2. [Uvezite podatke sa SFTP lokacije](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) u Salesforce Marketing Cloud proširenje podataka.

3. Podesite automatizaciju za uvoz podataka u proširenja podataka. Saznajte više o [automatizacijama otpuštanja datoteka i zakazanim automatizacijama](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definišite [automatizaciju otpuštanja datoteka](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ili [zakazanu automatizaciju](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Evo primera [automatizacije sa SFTP-om](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
