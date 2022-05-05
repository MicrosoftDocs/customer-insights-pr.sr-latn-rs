---
title: Ingest podaci iz Azure Synapse Analytics
description: Koristite bazu podataka Azure Synapse kao izvor podataka u programu Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643342"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Povezivanje izvor podataka Azure Synapse (pregled)

Azure Synapse Analytics je usluga analitike preduzeća koja ubrzava vreme na uvide u skladištima podataka i velikim sistemima podataka. Azure Synapse Analytics okuplja najbolje od SQL tehnologija koje se koriste u skladištu podataka preduzeća, Spark tehnologije koje se koriste za velike podatke, Data Explorer za analitiku evidencije i vremenskih serija, cevovode za integraciju podataka i ETL/ELT i duboku integraciju sa drugim Azure uslugama Power BI kao što su, Cosmos DB i AzureML.

Više informacija potražite u članku [Azure Synapse Pregled](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Preduslovi

Da biste konfigurisali vezu od Dynamics 365 Customer Insights Azure Synapse.

> [!IMPORTANT]
> Obavezno podesite sve **dodele uloga** kao što je opisano.  

## <a name="prerequisites-in-customer-insights"></a>Preduslovi u usluzi Customer Insights

* Imate ulogu administratora **u** "Uvidima klijenata". Saznajte više o korisničkim [dozvolama u fascikli "Uvidi klijenata"](permissions.md#assign-roles-and-permissions).

U usluzi Azure: 

- Aktivna pretplata na uslugu Azure.

- Ako koristite novi Azure Data Lake Storage Gen2 nalog, glavnoj usluzi *za uvide klijenata* potrebni **su podaci o skladištenju saradnik** dozvole. Saznajte više o [povezivanju sa glavnim Azure Data Lake Storage servisom za uvide klijenata](connect-service-principal.md). Data Lake Storage Gen2 **mora da ima** omogućen [hijerarhijski prostor imena](/azure/storage/blobs/data-lake-storage-namespace).

- U grupi resursa radni Azure Synapse prostor se nalazi, *direktoru usluge* *i korisniku za uvide klijenata* potrebno je dodeliti **najmanje čitalac** dozvole. Za više informacija, pogledajte [Dodeljivanje Azure uloga pomoću Azure portala](/azure/role-based-access-control/role-assignments-portal).

- *Korisniku* su potrebne dozvole **saradnika za podatke skladišta blob objekta** na Azure Data Lake Storage Gen2 nalogu na kojem se podaci nalaze i povezani su sa Azure Synapse radnim prostorom. Saznajte više o [korišćenju Azure portala za dodeljivanje Azure uloge za pristup blob objektu i podacima u redu](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama saradnika za podatke skladišta blob objekta](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Upravljanom identitetu Azure Synapse radnog prostora](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* su potrebne dozvole **saradnika za podatke skladišta blob objekta** na Azure Data Lake Storage Gen2 nalogu na kojem se podaci nalaze i povezani su sa Azure Synapse radnim prostorom. Saznajte više o [korišćenju Azure portala za dodeljivanje Azure uloge za pristup blob objektu i podacima u redu](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama saradnika za podatke skladišta blob objekta](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Na radnom Azure Synapse prostoru, direktoru *usluge za uvide klijenata* potrebna **je dodeljena uloga administratora** sinapse. Za više informacija, pogledajte [Kako se postavlja kontrola pristupa za vaš Synapse radni prostor](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Poveži se sa bazama podataka jezera u Azure Synapse Analytics

1. Idite na **Podaci** > **Izvori podataka**.

1. Izaberite **Dodaj izvor podataka**.

1. Odaberite **Azure Synapse Analytics metod (Pregled**).

1. Navedite **Naziv** za izvor podataka, pa izaberite **Sledeće** kako biste kreirali izvor podataka. 

1. Odaberite [dostupnu vezu](connections.md) sa Azure Synapse Analytics ili kreirajte novu.

1. Odaberite bazu **podataka jezera** sa radnog prostora povezanog u izabranoj vezi i Azure Synapse Analytics kliknite na dugme " **Dalje"**.

1. Izaberite entitete koje želite da unestite iz povezane baze podataka. 

1. Opcionalno, odaberite entitete podataka da biste dozvolili profilisanje podataka. 

1. Kliknite **na** dugme Sačuvaj da biste primenili selekciju i započeli unošenje podataka iz novokreiranog izvor podataka sa tabelama baze podataka jezera u programu Azure Synapse Analytics.
