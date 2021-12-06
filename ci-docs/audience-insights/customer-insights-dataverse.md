---
title: Podaci o uvidu klijenata u Microsoft Dataverse
description: Koristite entitete uvida kupaca kao tabele u Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866951"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Rad sa podacima uvida klijenata u Microsoft Dataverse

Uvidi klijenata pružaju opciju da izlazni entiteti budu dostupni [u Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Ova integracija omogućava lako deljenje podataka i prilagođeni razvoj kroz pristup sa malo kodiranja / bez kodiranja. Izlazni entiteti će biti dostupni kao tabele u Dataverse. Ove tabele omogućavaju scenarije kao što [su automatizovani tokovi posla Power Automate](/power-automate/getting-started), aplikacije sa [modelima i aplikacije na](/powerapps/maker/model-driven-apps/)[platnu](/powerapps/maker/canvas-apps/) putem Power Apps. Podatke možete da koristite za bilo koju drugu aplikaciju koja se zasniva na Dataverse tabele. Trenutna primena uglavnom podržava pronalaženja gde se podaci iz dostupnih entiteta uvida u ciljne grupe mogu dobiti za dati ID klijenta.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Prilaganje Dataverse okruženja uz uvide klijenata

**Organizacije sa postojećim Dataverse okruženjima**

Organizacije koje već koriste Dataverse mogu [da koriste jedno od postojećih Dataverse okruženja kada administrator korisnici](create-environment.md) uvide. Obezbeđivanjem URL adrese Dataverse okruženju, ona se pridaje njihovom novom okruženju korisnici uvida. Da biste obezbedili najbolje moguće performanse, korisnički uvidi i Dataverse okruženja moraju biti hostovana u istom regionu.

**Nova organizacija**

Ako prilikom podešavanja uvida kupaca kreirate novu organizaciju, automatski ćete dobiti novi Dataverse okruženja.

> [!NOTE]
> Ako vaše organizacije već Dataverse u svom zakupu, važno [je da zapamtite da Dataverse okruženja kontroliše administrator](/power-platform/admin/control-environment-creation.md) . Na primer, ako podešavate novo okruženje za korisnici uvide sa organizacionim nalogom, a administrator je onemogućio kreiranje Dataverse probnih okruženja za sve osim za administratore, ne možete da kreirate novo probno okruženje.
> 
> Probna Dataverse okruženja kreirana u uvidima klijenata imaju 3 GB prostora za skladištenje koje se neće računati u odnosu na ukupne kapacitete koji imaju pravo na stanara. Plaćene pretplate dobijaju Dataverse od 15 GB za bazu podataka i 20 GB za skladištenje datoteka.

## <a name="output-entities"></a>Izlazni entiteti

Neki izlazni entiteti iz korisnici dostupni su kao tabele u Dataverse. Odeljci u nastavku opisuju očekivanu šemu ovih tabela.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obogaćivanje](#enrichment)
- [Predviđanje](#prediction)
- [Članstvo u segmentima](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Ova tabela sadrži objedinjeni profil klijenta iz usluge Customer Insights. Šema za objedinjeni profil klijenta zavisi od entiteta i atributa koji se koriste u procesu objedinjavanja. Šema profila klijenta obično sadrži podskup atributa iz [Common Data Model definicije profila klijenta](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabela AlternateKey sadrži ključeve entiteta koji su učestvovali u procesu objedinjavanja.

|Column  |Tip  |Opis  |
|---------|---------|---------|
|DataSourceName    |String         | Naziv izvora podataka. Na primer: `datasource5`        |
|EntityName        | String        | Naziv entiteta u uvidima u ciljnu grupu. Na primer: `contact1`        |
|AlternateValue    |String         |Alternativni ID koji se preslikava na ID klijenta. Primer: `cntid_1078`         |
|KeyRing           | Tekst u više redova        | JSON vrednost  </br> Uzorak: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
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
| SegmentProvider      | String       | Aplikacija koja objavljuje segmente. Podrazumevano: korisnici uvidi         |
| SegmentMembershipType | String       | Tip kupca ovaj zapis članstva u segmentima. Podržava više tipova kao što su "Kupac", "Kontakt" ili "Nalog". Podrazumevano: kupac  |
| Segmenti       | JSON niska  | Lista jedinstvenih segmenata u kojima je profil kupca član      |
| msdynci_identifier  | String   | Jedinstveni identifikator zapisa članstva u segmentu. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministički GUID generisan iz`msdynci_identifier`          |
