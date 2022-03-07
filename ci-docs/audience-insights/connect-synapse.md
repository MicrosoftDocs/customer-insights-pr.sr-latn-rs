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
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356053"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Povezivanje izvor podataka Azure Synapse (pregled)

Azure Synapse Analytics je usluga analitike preduzeća koja ubrzava vreme na uvide u skladištima podataka i velikim sistemima podataka. Azure Synapse Analytics okuplja najbolje od SQL tehnologija koje se koriste u skladištu podataka preduzeća, Spark tehnologije koje se koriste za velike podatke, Data Explorer za analitiku evidencije i vremenskih serija, cevovode za integraciju podataka i ETL/ELT i duboku integraciju sa drugim Azure uslugama Power BI kao što su, Cosmos DB i AzureML.

Više informacija potražite u članku [Azure Synapse Pregled](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Preduslovi

Sledeći preduslovi moraju biti ispunjeni za konfigurisanje veze iz usluge Customer Insights u uslugu Azure Synapse.

> [!IMPORTANT]
> Obavezno podesite sve **dodele uloga** kao što je opisano.  

## <a name="prerequisites-in-customer-insights"></a>Preduslovi u usluzi Customer Insights

* Imate ulogu administratora **u** "Uvidima klijenata". Saznajte više o [korisničkim dozvolama u uvidima u ciljnu grupu](permissions.md#assign-roles-and-permissions).

U usluzi Azure: 

- Aktivna pretplata na uslugu Azure.

- Ako koristite novi Azure Data Lake Storage Gen2 nalog, *principalu usluge za uvide u ciljnu grupu* su potrebne dozvole **saradnika za podatke skladišta blob objekta**. Saznajte više [o povezivanju sa Azure Data Lake Storage direktorom usluge za korisnici uvide](connect-service-principal.md). Data Lake Storage Gen2 **mora da ima** omogućen [hijerarhijski prostor imena](/azure/storage/blobs/data-lake-storage-namespace).

- U grupi resursa u kojoj se nalazi Azure Synapse radni prostor, *principalu usluge* i *korisniku za uvide u ciljnu grupu* treba dodeliti barem dozvole **čitaoca**. Za više informacija, pogledajte [Dodeljivanje Azure uloga pomoću Azure portala](/azure/role-based-access-control/role-assignments-portal).

- *Korisniku* su potrebne dozvole **saradnika za podatke skladišta blob objekta** na Azure Data Lake Storage Gen2 nalogu na kojem se podaci nalaze i povezani su sa Azure Synapse radnim prostorom. Saznajte više o [korišćenju Azure portala za dodeljivanje Azure uloge za pristup blob objektu i podacima u redu](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama saradnika za podatke skladišta blob objekta](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Upravljanom identitetu Azure Synapse radnog prostora](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* su potrebne dozvole **saradnika za podatke skladišta blob objekta** na Azure Data Lake Storage Gen2 nalogu na kojem se podaci nalaze i povezani su sa Azure Synapse radnim prostorom. Saznajte više o [korišćenju Azure portala za dodeljivanje Azure uloge za pristup blob objektu i podacima u redu](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama saradnika za podatke skladišta blob objekta](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- U Azure Synapse radnom prostoru, *principalu usluge za uvide u ciljnu grupu* je potrebna dodeljena uloga **Synapse administratora**. Za više informacija, pogledajte [Kako se postavlja kontrola pristupa za vaš Synapse radni prostor](/azure/synapse-analytics/security/how-to-set-up-access-control).

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
