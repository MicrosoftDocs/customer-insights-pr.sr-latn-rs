---
title: Povezivanje izvor podataka Azure Synapse (pregled)
description: Koristite bazu podataka Azure Synapse kao izvor podataka u programu Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7bc0c3614e6dd39fbd65ae098ed679d95d09de9d
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259815"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Povezivanje izvor podataka Azure Synapse Analytics (pregled)

Azure Synapse Analytics je usluga analitike preduzeća koja ubrzava vreme na uvide u skladištima podataka i velikim sistemima podataka. Azure Synapse Analytics okuplja najbolje od SQL tehnologija koje se koriste u skladištu podataka preduzeća, Spark tehnologije koje se koriste za velike podatke, Data Explorer za analitiku evidencije i vremenskih serija, cevovode za integraciju podataka i ETL/ELT i duboku integraciju sa drugim Azure uslugama Power BI kao što su, Cosmos DB i AzureML.

Više informacija potražite u članku [Azure Synapse Pregled](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Preduslovi

> [!NOTE]
> Sinapsa radnih prostora kojima [je omogućen zaštitni](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) zid trenutno nije podržana.
> [!IMPORTANT]
> Obavezno podesite sve **dodele uloga** kao što je opisano.  

**U uvidima kupaca**:

* Imate ulogu administratora **u** "Uvidima klijenata". Saznajte više o korisničkim [dozvolama u fascikli "Uvidi klijenata"](permissions.md#add-users).

**U Azure:**

- Aktivna pretplata na uslugu Azure.

- Ako koristite novi Azure Data Lake Storage Gen2 nalog, *glavnicu usluge za uvide klijenata* koja je "Dynamics 365 AI za uvide klijenata" **potrebne su dozvole za skladištenje blob saradnik** podataka. Saznajte više o [povezivanju sa glavnim Azure Data Lake Storage servisom za uvide klijenata](connect-service-principal.md). Data Lake Storage Gen2 **mora da ima** omogućen [hijerarhijski prostor imena](/azure/storage/blobs/data-lake-storage-namespace).

- U grupi resursa radni Azure Synapse prostor se nalazi, *glavnicu usluge* koja je "Dynamics 365 AI za uvide klijenata" *i korisniku za uvide klijenata* potrebno je dodeliti **najmanje čitalac** dozvole. Za više informacija, pogledajte [Dodeljivanje Azure uloga pomoću Azure portala](/azure/role-based-access-control/role-assignments-portal).

- *Korisniku* su potrebne dozvole **saradnika za podatke skladišta blob objekta** na Azure Data Lake Storage Gen2 nalogu na kojem se podaci nalaze i povezani su sa Azure Synapse radnim prostorom. Saznajte više o [korišćenju Azure portala za dodeljivanje Azure uloge za pristup blob objektu i podacima u redu](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama saradnika za podatke skladišta blob objekta](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Upravljanom identitetu Azure Synapse radnog prostora](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* su potrebne dozvole **saradnika za podatke skladišta blob objekta** na Azure Data Lake Storage Gen2 nalogu na kojem se podaci nalaze i povezani su sa Azure Synapse radnim prostorom. Saznajte više o [korišćenju Azure portala za dodeljivanje Azure uloge za pristup blob objektu i podacima u redu](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama saradnika za podatke skladišta blob objekta](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Na radnom Azure Synapse prostoru, direktoru *usluge za uvide klijenata* koji je "Dynamics 365 AI za uvide klijenata" **potrebna je uloga administratora** sinapse. Za više informacija, pogledajte [Kako se postavlja kontrola pristupa za vaš Synapse radni prostor](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Ako vaše okruženje "Uvid u kupce" skladišti [podatke u sopstvenom Azure Data Lake Storage](own-data-lake-storage.md), korisniku koji podešavanje Azure Synapse Analytics veze treba barem ugrađenu **čitalac ulogu** na Data Lake Storage nalogu. Za više informacija, pogledajte [Dodeljivanje Azure uloga pomoću Azure portala](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Poveži se sa bazom podataka jezera u Azure Synapse Analytics

1. Idite na **Podaci** > **Izvori podataka**.

1. Izaberite **Dodaj izvor podataka**.

1. Odaberite **Azure Synapse Analytics metod (Pregled**).

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dijalog za povezivanje sa podacima sinapse Analitika":::
  
1. Unesite **ime** za izvor podataka i opcionalni **opis**.

1. Odaberite [dostupnu vezu](connections.md) sa Azure Synapse Analytics ili [kreirajte novu](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. Odaberite bazu **podataka** sa radnog prostora povezanog u izabranoj vezi i Azure Synapse Analytics kliknite na dugme " **Dalje"**. Trenutno podržavamo samo bazu podataka tipa Lake *baza podataka*.

1. Izaberite entitete koje želite da unestite iz povezane baze podataka i kliknite na dugme " **Dalje"**.

1. Opcionalno, odaberite entitete podataka da biste dozvolili profilisanje podataka.

1. Kliknite **na** dugme Sačuvaj da biste primenili selekciju i započeli unošenje podataka iz novokreiranog izvor podataka sa tabelama baze podataka jezera u programu Azure Synapse Analytics. Otvoriće **se stranica "Izvori podataka" koja prikazuje novu izvor podataka statusu "Osvežavanje** **·**".

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Učitavanje podataka može potrajati. Nakon uspešnog osvežavanja, uneti podaci se mogu redigovanje sa stranice [**"Entiteti**](entities.md) ".

[!INCLUDE [footer-include](includes/footer-banner.md)]
