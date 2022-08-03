---
title: Izvoz podataka u Azure Synapse Analytics (pregled)
description: Saznajte kako da konfigurišete vezu sa programom Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196411"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Izvoz podataka u Azure Synapse Analytics (pregled)

Azure Synapse je analitička usluga koja ubrzava vreme za uvid u skladišta podataka i sisteme velikih podataka. Možete da unesete i koristite Customer Insights podatke u usluzi [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Preduslovi

> [!NOTE]
> Obavezno podesite sve **dodele uloga** kao što je opisano.

- U fascikli "Uvidi klijenata", Azure Active Directory vaš (AD) korisnički nalog mora da ima ulogu [administratora](permissions.md#assign-roles-and-permissions).

U usluzi Azure:

- Aktivna pretplata na uslugu Azure.

- Ako koristite novi Azure Data Lake Storage Gen2 nalog, glavnica [usluge za uvide klijenata ima](connect-service-principal.md)**dozvole za skladištenje blob saradnik** podataka. Data Lake Storage Gen2 **mora da ima** omogućen [hijerarhijski prostor imena](/azure/storage/blobs/data-lake-storage-namespace).

- U grupi resursa u kojoj Azure Synapse se radni prostor nalazi, *direktoru usluge i* *Azure AD korisniku sa administratorske dozvole u "Uvidima* **korisnika" mora biti dodeljeno najmanje čitalac**[dozvole.](/azure/role-based-access-control/role-assignments-portal)

- Korisnik *Azure AD sa administratorskim dozvolama u programu Customer Insights* ima **dozvole za skladištenje blob podataka saradnik** Azure Data Lake Storage na Gen2 nalogu gde se podaci nalaze i koji su povezani sa radnim Azure Synapse prostorom. Saznajte više o [korišćenju Azure portala za dodeljivanje Azure uloge za pristup blob objektu i podacima u redu](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama saradnika za podatke skladišta blob objekta](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Upravljani *[Azure Synapse identitet radnog prostora](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* ima **uslugu Storage Blob Data saradnik** za opšte dozvole Azure Data Lake Storage na Gen2 nalogu gde se podaci nalaze i koji su povezani sa radnim Azure Synapse prostorom. Saznajte više o [korišćenju Azure portala za dodeljivanje Azure uloge za pristup blob objektu i podacima u redu](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama saradnika za podatke skladišta blob objekta](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Na radnom Azure Synapse prostoru, glavnina *usluge za uvide klijenata* **ima dodeljenu ulogu administratora**[sinapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-connection-to-azure-synapse"></a>Podesi vezu sa Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu i** odaberite **Azure Synapse Analytics**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izaberite ili potražite pretplatu u kojoj želite da koristite Customer Insights podatke. Čim izaberete pretplatu, možete i da izaberete **Radni prostor**, **Nalog skladišta** i **Kontejner**.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)] Da biste konfigurisali izvoz sa deljenom vezom, potrebno vam je najmanje **saradnik** u fascikli "Uvidi kupaca".

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odeljka Azure Synapse Analytics. Ako veza nije dostupna, obratite se administratoru.

1. Obezbedite prepoznatljivo **Ime za prikaz** za vaš izvoz i **Naziv baze podataka**. Izvoz će stvoriti novu bazu podataka [Azure Synapse jezera](/azure/synapse-analytics/database-designer/concepts-lake-database) u radnom prostoru definisanom u vezi.

1. Izaberite entitete u koje želite da izvezete Azure Synapse Analytics.
   > [!NOTE]
   > Izvori podataka na osnovu [Common Data Model fascikle](connect-common-data-model.md) nisu podržani.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Da biste ispitali podatke koji su izvezeni u analitiku sinapse, **potrebni su vam podaci o skladištenju čitalac da biste** imali pristup odredišnom skladištu na radnom prostoru izvoza.

## <a name="update-an-export"></a>Ažuriranje izvoza

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Uredi** na izvozu koji želite da promenite.

   - **Dodajte** ili **uklonite** entitete iz izbora. Ako se entiteti uklone iz izbora, neće se izbrisati iz Synapse Analytics baze podataka. Međutim, buduća osvežavanja podataka neće ažurirati uklonjene entitete u toj bazi podataka.

   - **Promena naziva baze podataka** kreira novu Synapse Analytics bazu podataka. Baza podataka sa imenom koje je prethodno bilo konfigurisano neće dobijati ažuriranja u budućim osvežavanjima.

[!INCLUDE [footer-include](includes/footer-banner.md)]
