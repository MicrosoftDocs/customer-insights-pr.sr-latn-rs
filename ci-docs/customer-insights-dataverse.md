---
title: Rad sa Customer Insights podacima u platformi Microsoft Dataverse
description: Saznajte kako da povežete uvide klijenata Microsoft Dataverse i razumete izlazne entitete koji se izvoze u program Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9433c411a2c7eb0db137c6392578993d47be82a2
ms.sourcegitcommit: 8559ca47a22d1d7cd9be13531c2eaf0c1083942b
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/12/2022
ms.locfileid: "9671268"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Rad sa Customer Insights podacima u platformi Microsoft Dataverse

Customer Insights pruža mogućnost omogućavanja dostupnosti izlaznih entiteta u platformi [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ova integracija omogućava lako deljenje podataka i prilagođeni razvoj putem niskog koda/bez kodnog pristupa. Izlazni [entiteti su](#output-entities) dostupni kao tabele u okruženju Dataverse. Podatke možete da koristite za bilo koju drugu aplikaciju zasnovanu na Dataverse tabelama. Ove tabele omogućavaju scenarije kao što su automatizovani tokovi posla kroz Power Automate ili izradu aplikacija pomoću programa Power Apps.

Povezivanje sa okruženjem Dataverse vam takođe omogućava da unosite [podatke iz lokalni podataka pomoću Power Platform priliva podataka i mrežnih prolaza](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Preduslovi

- Uvidi klijenata Dataverse i okruženja moraju biti hostovana u istom regionu.
- Globalna uloga administratora postavljena u okruženju Dataverse. Proverite da [Dataverse li je ovo okruženje](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) povezano sa određenim bezbednosnim grupama i uverite se da ste dodati tim bezbednosnim grupama.
- Nijedno drugo okruženje "Uvidi kupaca" već nije povezano sa okruženjem Dataverse koje želite da povežete. Saznajte kako [da uklonite postojeću vezu sa okruženjem Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Okruženje Microsoft Dataverse povezano sa jednim nalogom za skladištenje ako konfigurišete okruženje tako [da koristi Azure Data Lake Storage](own-data-lake-storage.md) vaš.

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse pravo na skladišni kapacitet

Pretplata "Uvidi klijenata" vam daje pravo na dodatni kapacitet postojećeg kapaciteta skladištenja vaše [Dataverse organizacije](/power-platform/admin/capacity-storage). Dodatni kapacitet zavisi od broja profila koje vaša pretplata koristi.

**Primer:**

Pod pretpostavkom da dobijete skladište baze podataka od 15 GB i 20 GB skladišta datoteka na 100.000 profila klijenata. Ako pretplata uključuje 300.000 profila klijenata, ukupan kapacitet skladištenja je skladište baze podataka od 45 GB (3 x 15 GB) i skladište datoteka od 60 GB (3 x 20 GB). Slično tome, ako imate pretplatu na B-na-B sa 30K naloga, ukupan kapacitet skladištenja je skladište baze podataka od 45 GB (3 x 15 GB) i skladište datoteka od 60 GB (3 x 20 GB).

Kapacitet evidencije nije postepen i fiksiran za vašu organizaciju.

Više informacija o pravima na detaljne kapacitete potražite u Vodiču [za licenciranje za Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Povezivanje okruženja Dataverse sa uvidom klijenata

Ovaj **Microsoft Dataverse** korak vam omogućava da povežete uvide klijenata sa okruženjem Dataverse prilikom [kreiranja okruženja "Uvid u kupce"](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="deljenje podataka Microsoft Dataverse sa automatski omogućenim za nova okruženja.":::

1. Obezbedite URL adresu svom okruženju Dataverse ili ostavite praznu da bi ona bila kreirana za vas.

   > [!NOTE]
   > Nakon uspostavljanja veze između uvida klijenata i Dataverse, nemojte menjati ime organizacije za okruženje Dataverse. Ime organizacije se koristi u URL adresi i Dataverse promenjeno ime prekida vezu sa uvidom klijenta.

   [Power Platform administratori mogu da kontrolišu ko može da kreira nova Dataverse okruženja](/power-platform/admin/control-environment-creation). Ako pokušavate da podesite novo okruženje "Uvidi kupaca", a ne može, administrator je možda Dataverse onemogućio kreiranje okruženja za sve osim za administratore.

1. Ako koristite sopstveni Data Lake Storage nalog:
   1. Izaberite **opciju Omogući deljenje podataka** pomoću program Dataverse.
   1. Unesite **identifikator dozvola**. Da biste dobili identifikator dozvole, [omogućite deljenje podataka Dataverse sa sopstvenim Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Omogući deljenje podataka Dataverse sa sopstvenim Azure Data Lake Storage (pregled)

U [svom nalogu Azure Data Lake Storage](own-data-lake-storage.md) proverite da li korisnik koji podešava okruženje "Uvidi kupaca" ima **najmanje dozvole za skladištenje blob podataka čitalac** na `customerinsights` kontejneru u nalogu za skladištenje.

> [!NOTE]
> Deljenje podataka je primenljivo samo ako koristite sopstveni Azure Data Lake Storage nalog. Ova postavka nije dostupna ako okruženje "Uvidi kupaca" koristi podrazumevano Dataverse skladište.

### <a name="limitations"></a>Ograničenja

- Samo mapiranje jedan na jedan između organizacije Dataverse i naloga Azure Data Lake Storage. Kada je Dataverse organizacija povezana sa nalogom za skladištenje, ne može da se poveže sa drugim nalogom za skladištenje. Ovo ograničenje sprečava popunjavanje Dataverse više naloga za skladištenje.
- Deljenje podataka neće funkcionisati ako je za pristup nalogu potrebno Azure Data Lake Storage podešavanje Azure privatne veze jer se nalazi iza zaštitnog zida. Dataverse trenutno ne podržava vezu sa privatnim krajnjim tačkama putem privatne veze.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Sami podesite bezbednosne grupe Azure Data Lake Storage

1. Kreirajte dve bezbednosne grupe na Azure pretplati - **jednu čitalac bezbednosnu** **grupu i saradnik bezbednosnu** grupu i podesite Microsoft Dataverse uslugu kao vlasnika za obe bezbednosne grupe.

1. Upravljajte Listom kontrole pristupa (ACL) na kontejneru `customerinsights` u nalogu za skladištenje preko ovih bezbednosnih grupa.
   1. Dodajte uslugu Microsoft Dataverse i sve Dataverse poslovne aplikacije zasnovane na sistemu Dynamics 365 Marketing **u čitalac** grupu sa **dozvolama samo** za čitanje.
   1. Dodajte *samo* aplikaciju "Uvidi klijenata **" u saradnik grupu** da biste dodelili dozvole **za** čitanje i pisanje profila i uvida.

### <a name="set-up-powershell"></a>Podešavanje PowerShell-a

Podesite PowerShell da izvršava PowerShell skripte.

1. Instalirajte najnoviju verziju [Azure Active Directory programa PowerShell za Graph](/powershell/azure/active-directory/install-adv2).
   1. Na računaru izaberite taster Windows na tastaturi i potražite **Windows PowerShell** i izaberite **Pokreni kao administrator**.
   1. U PowerShell prozoru koji se otvori unesite `Install-Module AzureAD`.

1. Uvezi tri modula.
   1. U prozoru PowerShell unesite `Install-Module -Name Az.Accounts` i sledite korake.
   1. Ponovite za `Install-Module -Name Az.Resources` i `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Izvršavanje PowerShell skripti i dobijanje identifikatora dozvole

1. Preuzmite dve PowerShell skripte koje treba da pokrenete sa [GitHub repoa našeg inženjera](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: Potrebne su administratorske dozvole zakupca.
   - `ByolSetup.ps1`: Zahteva dozvole vlasnika podataka za skladištenje na nivou naloga/kontejnera za skladištenje. Ova skripta će kreirati dozvolu za vas. Dodeljivanje uloge može biti uklonjeno ručno nakon uspešnog pokretanja skripte.

1. Izvršite u programu Windows PowerShell tako što ćete obezbediti ID Azure pretplate `CreateSecurityGroups.ps1` koji sadrži vaš Azure Data Lake Storage. Otvorite PowerShell skriptu u uređivaču da biste pregledali dodatne informacije i primenjenu logiku.

   Ova skripta kreira dve bezbednosne grupe na Azure pretplati: jednu za čitalac grupu, a drugu za saradnik grupu. Microsoft Dataverse usluga je vlasnik obe ove bezbednosne grupe.

1. Sačuvajte ID vrednosti obe bezbednosne grupe koje generiše ova skripta da biste ih koristili u skripti `ByolSetup.ps1`.

   > [!NOTE]
   > Kreiranje bezbednosne grupe može biti onemogućeno vašem stanaru. U tom slučaju, biće potrebno ručno podešavanje i administrator će Azure AD morati da omogući kreiranje [bezbednosnih grupa](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Izvršite u `ByolSetup.ps1` programu Windows PowerShell tako što ćete obezbediti ID Azure Data Lake Storage Azure pretplate koji sadrži ime naloga za skladištenje, ime grupe resursa i čitalac i saradnik ID bezbednosne grupe. Otvorite PowerShell skriptu u uređivaču da biste pregledali dodatne informacije i primenjenu logiku.

   Ova skripta dodaje potrebnu kontrolu pristupa zasnovanu na ulozi za uslugu i Microsoft Dataverse sve poslovne aplikacije Dataverse zasnovane na ulozi. Takođe ažurira Listu kontrole pristupa (ACL) na kontejneru za bezbednosne `customerinsights` grupe kreirane pomoću skripte `CreateSecurityGroups.ps1`. Grupa saradnik dobila dozvolu *za rwx*, a grupa čitalaca samo *r-x* dozvolu.

1. Kopiraj izlaznu nisku koja izgleda kao: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Unesite kopiranu izlaznu nisku u **polje identifikatora dozvola** koraka konfiguracije okruženja za Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opcije konfiguracije da biste omogućili deljenje podataka iz sopstvenih sa Azure Data Lake Storage programom Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Uklanjanje postojeće veze sa okruženjem Dataverse

Kada se povezujete sa okruženjem Dataverse, poruka o grešci **Ova CDS organizacija je već priložena drugoj instanci uvida klijenata** znači Dataverse da se okruženje već koristi u okruženju "Uvidi kupaca". Postojeću vezu možete da uklonite kao globalni administrator u okruženju Dataverse. Može da potraje nekoliko sati da se promene nasele.

1. Idite na [Power Apps](https://make.powerapps.com).
1. Izaberite okruženje od birača okruženja.
1. Idite na **rešenja**.
1. Deinstalirajte ili izbrišite rešenje pod imenom **Dynamics 365 Customer Insights "Programski dodatak kartice kupca " (pregled)**.

ILI

1. Otvorite svoju Dataverse okolinu.
1. Idite na rešenja **za više opcija** > **za postavke**.
1. Deinstalirajte **CustomerInsightsCustomerCard** rešenje.

Ako uklanjanje veze ne uspe zbog zavisnosti, morate da uklonite i zavisnosti. Više informacija potražite u članku [Uklanjanje zavisnosti](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Izlazni entiteti

Neki izlazni entiteti iz "Uvida kupaca" dostupni su kao tabele u programu Dataverse. Odeljci u nastavku opisuju očekivanu šemu ovih tabela.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obogaćivanje](#enrichment)
- [Predviđanje](#prediction)
- [Članstvo u segmentima](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Ova tabela sadrži objedinjeni profil klijenta iz usluge Customer Insights. Šema za objedinjeni profil klijenta zavisi od entiteta i atributa koji se koriste u procesu ujedinjenja podataka. Šema profila klijenta obično sadrži podskup atributa iz [Common Data Model definicije profila klijenta](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Za scenario od B do B, profil kupca sadrži objedinjena konta, a šema obično sadrži podskup [atributa iz definicije uobičajenog modela podataka naloga](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

ContactProfile sadrži objedinjene informacije o kontaktu. Kontakti su [osobe koje su mapirane na nalog u](data-unification-contacts.md) scenariju B-na-B.

| Column                       | Tip                | Opis     |
| ---------------------------- | ------------------- | --------------- |
|  Datum rođenja            | Datum i vreme       |  Datum rođenja kontakta               |
|  Grad                 | Tekstualna poruka |  Grad kontakt adrese               |
|  ID kontakta            | Tekstualna poruka |  ID profila kontakta               |
|  IDprofile kontakta     | Jedinstveni identifikator   |  GUID za kontakt               |
|  ZemljaOrRegion      | Tekstualna poruka |  Zemlja/region kontakt adrese               |
|  CustomerId           | Tekstualna poruka |  ID poslovnog kontakta na koji je kontakt mapiran               |
|  EntityName           | Tekstualna poruka |  Entitet iz koga potiиu podaci                |
|  FirstName            | Tekstualna poruka |  Ime kontakta               |
|  Rod               | Tekstualna poruka |  Pol kontakta               |
|  ID                   | Tekstualna poruka |  Deterministički GUID zasnovan na`Identifier`               |
|  Identifier           | Tekstualna poruka |  Interni ID profila kontakta: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | Tekstualna poruka |  Radno mesto kontakta               |
|  LastName             | Tekstualna poruka |  Prezime kontakta               |
|  PostalCode           | Tekstualna poruka |  Poštanski broj adrese kontakta               |
|  PrimarnaEmail         | Tekstualna poruka |  E-adresa kontakta               |
|  Primarni telefon         | Tekstualna poruka |  Broj telefona kontakta               |
|  StateOrProvince      | Tekstualna poruka |  Država ili pokrajina kontakt adrese               |
|  Ulična adresa        | Tekstualna poruka |  Ulica kontakt adrese               |

### <a name="alternatekey"></a>AlternateKey

Tabela AlternateKey sadrži ključeve entiteta koji su učestvovali u procesu objedinjavanja.

|Column  |Tip  |Opis  |
|---------|---------|---------|
|DataSourceName    |Tekstualna poruka         | Naziv izvora podataka. Na primer: `datasource5`        |
|EntityName        | Tekstualna poruka        | Ime entiteta u uvidima kupaca. Na primer: `contact1`        |
|AlternateValue    |Tekstualna poruka         |Alternativni ID koji se preslikava na ID klijenta. Primer: `cntid_1078`         |
|KeyRing           | Tekstualna poruka        | JSON vrednost  </br> Primer: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | Tekstualna poruka        | ID objedinjenog profila klijenta.         |
|AlternateKeyId     | Jedinstveni identifikator        |  AlternateKey deterministički GUID zasnovan na`Identifier`      |
|Identifier |   Tekstualna poruka      |   `DataSourceName|EntityName|AlternateValue`  </br> Primer: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Ova tabela sadrži aktivnosti korisnika koje su dostupne u usluzi Customer Insights.

| Column            | Tip        | Opis                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Tekstualna poruka      | ID profila klijenta                                                                      |
| ActivityId        | Tekstualna poruka      | Interni ID korisničke aktivnosti (primarni ključ)                                       |
| SourceEntityName  | Tekstualna poruka      | Naziv izvornog entiteta                                                                |
| SourceActivityId  | Tekstualna poruka      | Primarni ključ iz izvornog entiteta                                                       |
| ActivityType      | Tekstualna poruka      | Tip semantičke aktivnosti ili naziv prilagođene aktivnosti                                        |
| ActivityTimeStamp | Datum i vreme    | Vremenska oznaka aktivnosti                                                                      |
| Titula             | Tekstualna poruka      | Naslov ili naziv aktivnosti                                                               |
| Opis       | Tekstualna poruka      | Opis aktivnosti                                                                     |
| URL adresa               | Tekstualna poruka      | Veza do spoljne URL adrese specifične za aktivnost                                         |
| SemanticData      | Tekstualna poruka | Sadrži listu parova vrednosti ključeva za polja semantičkog mapiranja specifična za vrstu aktivnosti |
| RangeIndex        | Tekstualna poruka      | Unix vremenska oznaka koja se koristi za sortiranje na vremenskoj osi aktivnosti i efikasnim upitima o opsegu |
| ID objedinjeneaktivnosti   | Jedinstveni identifikator | Interni ID korisničke aktivnosti (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Ova tabela sadrži izlazne podatke korisničkih mera zasnovanih na atributima.

| Column             | Tip             | Opis                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Tekstualna poruka           | ID profila klijenta        |
| Mere           | Tekstualna poruka      | Uključuje listu parova vrednosti ključeva za ime mere i vrednosti za datog klijenta |
| Identifier | Tekstualna poruka           | `Customer_Measure|CustomerId` |
| ID klijenta | Jedinstveni identifikator     | ID profila klijenta |

### <a name="enrichment"></a>Obogaćivanje

Ova tabela sadrži rezultate procesa obogaćivanja.

| Column               | Tip             |  Opis                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Tekstualna poruka           | ID profila klijenta                                 |
| EnrichmentProvider   | Tekstualna poruka           | Naziv dobavljača obogaćivanja                                  |
| EnrichmentType       | Tekstualna poruka           | Tip obogaćivanja                                      |
| Vrednosti               | Tekstualna poruka      | Lista atributa proizvedenih postupkom obogaćivanja |
| ID obogaćivanja | Jedinstveni identifikator            | Deterministički GUID generisan iz`Identifier` |
| Identifier   | Tekstualna poruka           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predviđanje

Ova tabela sadrži izlaz predviđanja modela.

| Column               | Tip        | Opis                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Tekstualna poruka      | ID profila klijenta                                  |
| ModelProvider        | Tekstualna poruka      | Naziv dobavljača modela                                      |
| Model                | Tekstualna poruka      | Naziv modela                                                |
| Vrednosti               | Tekstualna poruka | Lista atributa koje je napravio model |
| ID predviđanja | Jedinstveni identifikator       | Deterministički GUID generisan iz`Identifier` |
| Identifier   | Tekstualna poruka      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Članstvo u segmentima

Ova tabela sadrži informacije o članstvu u segmentu profila kupaca.

| Column        | Tip | Opis                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | Tekstualna poruka       | ID profila klijenta        |
| SegmentProvider      | Tekstualna poruka       | Aplikacija koja objavljuje segmente.      |
| SegmentMembershipType | Tekstualna poruka       | Vrsta kupca za ovaj zapis članstva u segmentima. Podržava više tipova kao što su "Kupac", "Kontakt" ili "Nalog". Podrazumevano: kupac  |
| Segmenti       | Tekstualna poruka  | Lista jedinstvenih segmenata u kojima je profil kupca član      |
| Identifier  | Tekstualna poruka   | Jedinstveni identifikator zapisa članstva u segmentu. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| ID segmentaMembership | Jedinstveni identifikator      | Deterministički GUID generisan iz`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
