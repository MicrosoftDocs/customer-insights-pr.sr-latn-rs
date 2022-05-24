---
title: Izvoz Customer Insights podataka u Azure Synapse Analytics
description: Saznajte kako da konfigurišete vezu sa programom Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 772fe0978362ccd829077a8133e2a3e74043f3f8
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741520"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Izvoz podataka u Azure Synapse Analytics (pregled)

Azure Synapse je analitička usluga koja ubrzava vreme za uvid u skladišta podataka i sisteme velikih podataka. Možete da unesete i koristite Customer Insights podatke u usluzi [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Preduslovi

Sledeći preduslovi moraju biti ispunjeni za konfigurisanje veze iz usluge Customer Insights u uslugu Azure Synapse.

> [!NOTE]
> Obavezno podesite sve **dodele uloga** kao što je opisano.  

## <a name="prerequisites-in-customer-insights"></a>Preduslovi u usluzi Customer Insights

* Vaš Azure Active Directory (AD) korisnički nalog ima ulogu administratora **u** uvidima klijenata. Saznajte više o [postavljanju korisničkih dozvola](permissions.md#assign-roles-and-permissions).

U usluzi Azure: 

- Aktivna pretplata na uslugu Azure.

- Ako koristite novi Azure Data Lake Storage Gen2 nalog, glavnoj usluzi *za uvide klijenata* potrebni **su podaci o skladištenju saradnik** dozvole. Saznajte više o [povezivanju sa Gen2 Azure Data Lake Storage nalogom pomoću direktora Azure usluge za uvide klijenata](connect-service-principal.md). Data Lake Storage Gen2 **mora da ima** omogućen [hijerarhijski prostor imena](/azure/storage/blobs/data-lake-storage-namespace).

- U grupi resursa u kojoj Azure Synapse se radni prostor nalazi, *direktoru usluge* *Azure AD i korisniku sa administratorske dozvole u uvidima* **korisnika potrebno je dodeliti najmanje čitalac** dozvole. Za više informacija, pogledajte [Dodeljivanje Azure uloga pomoću Azure portala](/azure/role-based-access-control/role-assignments-portal).

- Korisniku *Azure AD sa administratorske dozvole u uvidima klijenata* potrebne **su dozvole za skladištenje blob podataka saradnik** Azure Data Lake Storage na Gen2 nalogu gde se podaci nalaze i koji su povezani sa radnim Azure Synapse prostorom. Saznajte više o [korišćenju Azure portala za dodeljivanje Azure uloge za pristup blob objektu i podacima u redu](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama saradnika za podatke skladišta blob objekta](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Upravljanom identitetu Azure Synapse radnog prostora](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* su potrebne dozvole **saradnika za podatke skladišta blob objekta** na Azure Data Lake Storage Gen2 nalogu na kojem se podaci nalaze i povezani su sa Azure Synapse radnim prostorom. Saznajte više o [korišćenju Azure portala za dodeljivanje Azure uloge za pristup blob objektu i podacima u redu](/azure/storage/common/storage-auth-aad-rbac-portal) i [dozvolama saradnika za podatke skladišta blob objekta](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Na radnom Azure Synapse prostoru, direktoru *usluge za uvide klijenata* potrebna **je dodeljena uloga administratora** sinapse. Za više informacija, pogledajte [Kako se postavlja kontrola pristupa za vaš Synapse radni prostor](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Podesite vezu i izvoz u Azure Synapse

### <a name="configure-a-connection"></a>Konfigurisanje veze

Da biste kreirali vezu, glavnica usluge i korisnički nalog u okviru "Uvidi **klijenata" moraju čitalac dozvole** *za* grupu resursa u kojoj se nalazi radni prostor sinapse Analitika. Pored toga, direktoru usluge i korisniku na radnom prostoru Sinapse Analytics potrebne **su dozvole administratora sinapse**. 

1. Idite na **Administrator** > **Veze**.

1. Kliknite **na dugme Dodaj** vezu i **Azure Synapse Analytics** odaberite ili izaberite **stavku Podešavanje** na pločici **Azure Synapse Analytics** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju Ime za prikaz. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izaberite ili potražite pretplatu u kojoj želite da koristite Customer Insights podatke. Čim izaberete pretplatu, možete i da izaberete **Radni prostor**, **Nalog skladišta** i **Kontejner**.

1. Izaberite **Sačuvaj** da biste sačuvali vezu.

### <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Da biste konfigurisali izvoz sa deljenom vezom, potrebno vam je najmanje **saradnik** u fascikli "Uvidi kupaca". Za više informacija, pogledajte [dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odeljka **Azure Synapse Analytics**. Ako ne vidite naziv ovog odeljka, ne postoje [veze](connections.md) ovog tipa koje su vam dostupne.

1. Obezbedite prepoznatljivo **Ime za prikaz** za vaš izvoz i **Naziv baze podataka**.

1. Izaberite entitete u koje želite da izvezete Azure Synapse Analytics.
   > [!NOTE]
   > Izvori podataka na osnovu [Common Data Model fascikle](connect-common-data-model.md) nisu podržani.

2. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).

Da biste ispitali podatke koji su izvezeni u analitiku sinapse, **potrebni su vam podaci o skladištenju čitalac da biste** imali pristup odredišnom skladištu na radnom prostoru izvoza. 

### <a name="update-an-export"></a>Ažuriranje izvoza

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Uredi** na izvozu koji želite da promenite.

   - **Dodajte** ili **uklonite** entitete iz izbora. Ako se entiteti uklone iz izbora, neće se izbrisati iz Synapse Analytics baze podataka. Međutim, buduća osvežavanja podataka neće ažurirati uklonjene entitete u toj bazi podataka.

   - **Promena naziva baze podataka** kreira novu Synapse Analytics bazu podataka. Baza podataka sa imenom koje je prethodno bilo konfigurisano neće dobijati ažuriranja u budućim osvežavanjima.
