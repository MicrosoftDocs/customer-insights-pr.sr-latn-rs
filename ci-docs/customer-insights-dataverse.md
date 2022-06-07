---
title: Rad sa Customer Insights podacima u platformi Microsoft Dataverse
description: Saznajte kako da povežete uvide klijenata Microsoft Dataverse i razumete izlazne entitete koji se izvoze u program Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833693"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Rad sa Customer Insights podacima u platformi Microsoft Dataverse

Uvidi klijenata pružaju opciju da izlazni entiteti budu dostupni kao [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ova integracija omogućava lako deljenje podataka i prilagođeni razvoj putem niskog koda/bez kodnog pristupa. Izlazni [entiteti su](#output-entities) dostupni kao tabele u okruženju Dataverse. Podatke možete da koristite za bilo koju drugu aplikaciju zasnovanu na Dataverse tabelama. Ove tabele omogućavaju scenarije kao što su automatizovani tokovi posla kroz Power Automate ili izradu aplikacija pomoću programa Power Apps.

Povezivanje sa okruženjem Dataverse vam takođe omogućava da unosite [podatke iz lokalni podataka pomoću Power Platform priliva podataka i mrežnih prolaza](data-sources.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Preduslovi

- Uvidi klijenata Dataverse i okruženja moraju biti hostovana u istom regionu.
- Morate imati ulogu globalnog administratora u okruženju Dataverse. Proverite da [Dataverse li je ovo okruženje](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) povezano sa određenim bezbednosnim grupama i uverite se da ste dodati tim bezbednosnim grupama.
- Nijedno drugo okruženje "Uvid u kupce" već nije povezano sa okruženjem Dataverse koje želite da povežete. Saznajte kako [da uklonite postojeću vezu sa okruženjem Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Okruženje Microsoft Dataverse može da se poveže samo sa jednim nalogom za skladištenje. Primenjuje se samo ako konfigurišete okruženje tako [da koristi vaš Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Povezivanje okruženja Dataverse sa uvidom klijenata

Ovaj **Microsoft Dataverse** korak vam omogućava da povežete uvide klijenata sa okruženjem Dataverse prilikom [kreiranja okruženja "Uvid u kupce"](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="deljenje podataka Microsoft Dataverse sa automatski omogućenim za neto nova okruženja.":::

Administratori mogu da konfigurišu uvide klijenata da povežu postojeće Dataverse okruženje. Obezbeđivanjem URL adrese okruženju Dataverse, ona se prilaže njihovom novom okruženju "Uvidi kupaca".

Ako ne želite da koristite postojeće okruženje Dataverse, sistem kreira novo okruženje za podatke o uvidima klijenata u zakupca. [Power Platform administratori mogu da kontrolišu ko može da kreira okruženja](/power-platform/admin/control-environment-creation). Kada podešavate novo okruženje "Uvidi kupaca", a administrator je onemogućio Dataverse kreiranje okruženja za sve osim za administratore, možda nećete moći da kreirate novo okruženje.

**Omogućite deljenje podataka** tako što Dataverse ćete potvrditi izbor u polju za potvrdu za deljenje podataka.

Ako koristite sopstveni nalog za skladištenje u jezeru Sa podacima, potreban vam je **i identifikator dozvola**. Za više informacija o tome kako da nabavite identifikator dozvole redigujte sledeći odeljak.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Omogući deljenje podataka Dataverse sa sopstvenim Azure Data Lake Storage (Pregled)

Za omogućavanje deljenja podataka Microsoft Dataverse kada okruženje koristi [sopstveni nalog potrebna Azure Data Lake Storage je](own-data-lake-storage.md) dodatna konfiguracija. Korisnik koji podešava okruženje "Uvid u korisnike" mora da ima najmanje **dozvole za skladištenje blob čitalac** *na kontejneru CustomerInsights* u nalogu Azure Data Lake Storage.

1. Kreirajte dve bezbednosne grupe na Azure pretplati - **jednu čitalac bezbednosnu** **grupu i saradnik bezbednosnu** grupu i podesite Microsoft Dataverse uslugu kao vlasnika za obe bezbednosne grupe.
2. Upravljajte listom kontrole pristupa (ACL) na kontejneru CustomerInsights u nalogu za skladištenje putem ovih bezbednosnih grupa. Dodajte uslugu Microsoft Dataverse i sve Dataverse poslovne aplikacije zasnovane na sistemu Dynamics 365 Marketing **u čitalac** grupu sa **dozvolama samo** za čitanje. Dodajte *samo* aplikaciju "Uvidi klijenata **" u saradnik grupu** da biste dodelili dozvole **za** čitanje i pisanje profila i uvida.

### <a name="limitations"></a>Ograničenja

Postoje dva ograničenja prilikom korišćenja Dataverse sa sopstvenim nalogom Azure Data Lake Storage:

- Postoji mapiranje jedan na jedan između organizacije Dataverse i naloga Azure Data Lake Storage. Kada je Dataverse organizacija povezana sa nalogom za skladištenje, ne može da se poveže sa drugim nalogom za skladištenje. Ovo ograničenje sprečava popunjavanje Dataverse više naloga za skladištenje.
- Deljenje podataka neće funkcionisati ako je potrebno podešavanje Azure privatne veze za pristup Azure Data Lake nalogu za skladištenje jer se nalazi iza zaštitnog zida. Dataverse trenutno ne podržava vezu sa privatnim krajnjim tačkama putem privatne veze.

### <a name="set-up-powershell"></a>Podešavanje PowerShell-a

Da biste izvršili PowerShell skripte, prvo morate da podesite PowerShell u skladu sa tim.

1. Instalirajte najnoviju verziju [Azure Active Directory programa PowerShell za Graph](/powershell/azure/active-directory/install-adv2).
   1. Na računaru izaberite taster Windows na tastaturi i potražite **Windows PowerShell** i izaberite **Pokreni kao administrator**.
   1. U PowerShell prozoru koji se otvori unesite `Install-Module AzureAD`.
2. Uvezi tri modula.
    1. U prozoru PowerShell unesite `Install-Module -Name Az.Accounts` i sledite korake.
    1. Ponovite za `Install-Module -Name Az.Resources` i `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Koraci konfiguracije

1. Preuzmite dve PowerShell skripte koje treba da pokrenete sa [GitHub repoa našeg inženjera](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Potrebne su vam *administratorske dozvole* zakupca da biste pokrenuli ovu PowerShell skriptu.
       - Ova PowerShell skripta kreira dve bezbednosne grupe na Azure pretplati. Jedan za čitalac grupu i drugi za saradnik grupu i učiniće Microsoft Dataverse uslugu kao vlasnik obe ove bezbednosne grupe.
       - Izvršite ovu PowerShell skriptu u programu Windows PowerShell tako što ćete obezbediti ID Azure pretplate koji sadrži vaš Azure Data Lake Storage. Otvorite PowerShell skriptu u uređivaču da biste pregledali dodatne informacije i primenjenu logiku.
       - Sačuvajte vrednosti ID-a obe bezbednosne grupe koje generiše ova skripta jer ćemo ih koristiti u skripti `ByolSetup.ps1`.

        > [!NOTE]
        > Kreiranje bezbednosne grupe može biti onemogućeno vašem stanaru. U tom slučaju, biće potrebno ručno podešavanje i administrator će Azure AD morati da omogući kreiranje [bezbednosnih grupa](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Potrebne su vam *dozvole vlasnika podataka za skladištenje* na nalogu/kontejneru za skladištenje da biste pokrenuli ovu skriptu ili će ova skripta kreirati jednu za vas. Dodeljivanje uloge može biti uklonjeno ručno nakon uspešnog pokretanja skripte.
        - Ova PowerShell skripta dodaje potrebnu kontrolu pristupa zasnovanu na tolima (RBAC) za Microsoft Dataverse uslugu i sve poslovne Dataverse aplikacije zasnovane na tome. Takođe ažurira Listu kontrole pristupa (ACL) na kontejneru CustomerInsights za bezbednosne grupe kreirane pomoću skripte `CreateSecurityGroups.ps1`. Grupa saradnik će imati rwx *dozvolu* i grupa čitalaca će imati samo *r-x* dozvolu.
        - Izvršite ovu PowerShell skriptu u programu Windows PowerShell tako što ćete obezbediti ID Azure Data Lake Storage Azure pretplate koji sadrži vaše ime naloga za skladištenje, ime grupe resursa i ID čitalac i saradnik bezbednosne grupe. Otvorite PowerShell skriptu u uređivaču da biste pregledali dodatne informacije i primenjenu logiku.
        - Kopirajte izlaznu nisku nakon uspešnog pokretanja skripte. Izlazna niska izgleda ovako: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Unesite izlaznu nisku kopiranu odozgo u **polje identifikatora** dozvola koraka konfiguracije okruženja za Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opcije konfiguracije da biste omogućili deljenje podataka iz sopstvenih sa Azure Data Lake Storage programom Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Uklanjanje postojeće veze sa okruženjem Dataverse

Kada se povezujete sa okruženjem Dataverse, poruka o grešci **Ova CDS organizacija je već priložena drugoj instanci uvida klijenata** znači Dataverse da se okruženje već koristi u okruženju "Uvidi kupaca". Postojeću vezu možete da uklonite kao globalni administrator u okruženju Dataverse. Može da potraje nekoliko sati da se promene nasele.

1. Idite na [Power Apps](https://make.powerapps.com).
1. Izaberite okruženje od birača okruženja.
1. Idi na **rešenja**
1. Deinstalirajte ili izbrišite rešenje pod imenom **Dynamics 365 Customer Insights "Programski dodatak kartice kupca " (pregled)**.

ILI

1. Otvorite svoju Dataverse okolinu.
1. Idite na rešenja **za više opcija** > **za postavke**.
1. Deinstalirajte **CustomerInsightsCustomerCard** rešenje.

Ako uklanjanje veze ne uspe zbog zavisnosti, morate da uklonite i zavisnosti. Više informacija potražite u članku [Uklanjanje zavisnosti](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Izlazni entiteti

Neki izlazni entiteti iz "Uvida kupaca" dostupni su kao tabele u programu Dataverse. Odeljci u nastavku opisuju očekivanu šemu ovih tabela.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obogaćivanje](#enrichment)
- [Predviđanje](#prediction)
- [Članstvo u segmentima](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Ova tabela sadrži objedinjeni profil klijenta iz usluge Customer Insights. Šema za objedinjeni profil klijenta zavisi od entiteta i atributa koji se koriste u procesu ujedinjenja podataka. Šema profila klijenta obično sadrži podskup atributa iz [Common Data Model definicije profila klijenta](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabela AlternateKey sadrži ključeve entiteta koji su učestvovali u procesu objedinjavanja.

|Column  |Tip  |Opis  |
|---------|---------|---------|
|DataSourceName    |String         | Naziv izvora podataka. Na primer: `datasource5`        |
|EntityName        | String        | Ime entiteta u uvidima kupaca. Na primer: `contact1`        |
|AlternateValue    |String         |Alternativni ID koji se preslikava na ID klijenta. Primer: `cntid_1078`         |
|KeyRing           | Tekst u više redova        | JSON vrednost  </br> Primer: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | ID objedinjenog profila klijenta.         |
|AlternateKeyId     | GUID         |  AlternateKey određeni GUID zasnovan na parametru msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Primer: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Ova tabela sadrži aktivnosti korisnika koje su dostupne u usluzi Customer Insights.

| Column            | Tip        | Opis                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | ID profila klijenta                                                                      |
| ActivityId        | String      | Interni ID korisničke aktivnosti (primarni ključ)                                       |
| SourceEntityName  | String      | Naziv izvornog entiteta                                                                |
| SourceActivityId  | String      | Primarni ključ iz izvornog entiteta                                                       |
| ActivityType      | String      | Tip semantičke aktivnosti ili naziv prilagođene aktivnosti                                        |
| ActivityTimeStamp | DATETIME    | Vremenska oznaka aktivnosti                                                                      |
| Naziv             | String      | Naslov ili naziv aktivnosti                                                               |
| Opis       | String      | Opis aktivnosti                                                                     |
| URL adresa               | String      | Veza do spoljne URL adrese specifične za aktivnost                                         |
| SemanticData      | JSON niska | Sadrži listu parova vrednosti ključeva za polja semantičkog mapiranja specifična za vrstu aktivnosti |
| RangeIndex        | String      | Unix vremenska oznaka koja se koristi za sortiranje na vremenskoj osi aktivnosti i efikasnim upitima o opsegu |
| mydynci_unifiedactivityid   | GUID | Interni ID korisničke aktivnosti (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Ova tabela sadrži izlazne podatke korisničkih mera zasnovanih na atributima.

| Column             | Tip             | Opis                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | ID profila klijenta        |
| Mere           | JSON niska      | Uključuje listu parova vrednosti ključeva za ime mere i vrednosti za datog klijenta | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID profila klijenta |


### <a name="enrichment"></a>Obogaćivanje

Ova tabela sadrži rezultate procesa obogaćivanja.

| Column               | Tip             |  Opis                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | ID profila klijenta                                 |
| EnrichmentProvider   | String           | Naziv dobavljača obogaćivanja                                  |
| EnrichmentType       | String           | Tip obogaćivanja                                      |
| Vrednosti               | JSON niska      | Lista atributa proizvedenih postupkom obogaćivanja |
| msdynci_enrichmentid | GUID             | Deterministički GUID generisan iz parametra msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predviđanje

Ova tabela sadrži izlaz predviđanja modela.

| Column               | Tip        | Opis                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | ID profila klijenta                                  |
| ModelProvider        | String      | Naziv dobavljača modela                                      |
| Model                | String      | Naziv modela                                                |
| Vrednosti               | JSON niska | Lista atributa koje je napravio model |
| msdynci_predictionid | GUID        | Deterministički GUID generisan iz parametra msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Članstvo u segmentima

Ova tabela sadrži informacije o članstvu u segmentu profila kupaca.

| Column        | Tip | Opis                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ID profila klijenta        |
| SegmentProvider      | String       | Aplikacija koja objavljuje segmente.      |
| SegmentMembershipType | String       | Tip kupca ovaj zapis članstva u segmentima. Podržava više tipova kao što su "Kupac", "Kontakt" ili "Nalog". Podrazumevano: kupac  |
| Segmenti       | JSON niska  | Lista jedinstvenih segmenata u kojima je profil kupca član      |
| msdynci_identifier  | String   | Jedinstveni identifikator zapisa članstva u segmentu. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministički GUID generisan iz`msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
