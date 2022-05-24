---
title: Customer Insights podaci u platformi Microsoft Dataverse
description: Koristite Customer Insights entitete kao tabele u platformi Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 1e629cd218b104b115f74f59a53a14e9d60fcc8a
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741382"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Rad sa Customer Insights podacima u platformi Microsoft Dataverse

Customer Insights pruža mogućnost omogućavanja dostupnosti izlaznih entiteta u platformi [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ova integracija omogućava lako deljenje podataka i prilagođeni razvoj putem niskog koda/bez kodnog pristupa. Izlazni [entiteti su](#output-entities) dostupni kao tabele u okruženju Dataverse. Podatke možete da koristite za bilo koju drugu aplikaciju zasnovanu na Dataverse tabelama. Ove tabele omogućavaju scenarije kao što su automatizovani tokovi posla kroz Power Automate ili izradu aplikacija pomoću programa Power Apps. Trenutna implementacija uglavnom podržava prikaze u kojima se podaci iz dostupnih entiteta Uvidi klijenata mogu preneti za dati ID kupca.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Prilaganje Dataverse okruženja za Customer Insights

**Postojeća organizacija**

Administratori mogu da konfigurišu uvide klijenata [tako da koriste postojeće Dataverse](create-environment.md) okruženje kada kreiraju okruženje "Uvidi kupaca". Obezbeđivanjem URL adrese okruženju Dataverse, ona se prilaže njihovom novom okruženju "Uvidi kupaca". Uvidi klijenata Dataverse i okruženja moraju biti hostovana u istom regionu. 

Ako ne želite da koristite postojeće okruženje Dataverse, sistem kreira novo okruženje za podatke o uvidima klijenata u zakupca. 

> [!NOTE]
> Ako vaše organizacije već koriste Dataverse kod svog zakupca, važno je da zapamtite da [Dataverse kreiranje okruženja kontroliše administrator](/power-platform/admin/control-environment-creation). Na primer, ako podešavate novo okruženje "Uvidi klijenata" sa organizacionim nalogom, a administrator je onemogućio Dataverse kreiranje probnih okruženja za sve osim za administratore, ne možete da kreirate novo probno okruženje.
> 
> Dataverse probna okruženja kreirana u usluzi Customer Insights imaju 3 GB prostora za skladištenje koji se neće računati u ukupni kapacitet koji ima pravo na zakupca. Plaćene pretplate dobijaju Dataverse pravo od 15 GB za bazu podataka i 20 GB za skladištenje datoteka.

**Nova organizacija**

Ako prilikom podešavanja uvida klijenata kreirate novu organizaciju, sistem automatski kreira novo okruženje Dataverse u vašoj organizaciji.

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
