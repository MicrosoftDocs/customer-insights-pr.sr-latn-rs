---
title: Customer Insights podaci u platformi Microsoft Dataverse
description: Koristite Customer Insights entitete kao tabele u platformi Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 7157ad930f3cea17c12bd4f95028d291483329d3
ms.sourcegitcommit: e5425f060c8d80f9510283dc610ce70a4e709b1e
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/15/2021
ms.locfileid: "6259208"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Rad sa Customer Insights podacima u platformi Microsoft Dataverse

Customer Insights pruža mogućnost omogućavanja dostupnosti izlaznih entiteta u platformi [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Ova integracija omogućava lako deljenje podataka i prilagođeni razvoj kroz pristup sa malo kodiranja / bez kodiranja. Izlazni entiteti biće dostupni kao tabele u platformi Dataverse. Ove tabele omogućavaju scenarije kao što su [automatizovani tokovi posla kroz Power Automate](/power-automate/getting-started), [aplikacije zasnovane na modelu](/powerapps/maker/model-driven-apps/) i [aplikacije sa podlogom](/powerapps/maker/canvas-apps/) kroz Power Apps. Podatke možete koristiti za bilo koju drugu aplikaciju zasnovanu na Dataverse tabelama. Trenutna primena uglavnom podržava pronalaženja gde se podaci iz dostupnih entiteta uvida u ciljne grupe mogu dobiti za dati ID klijenta.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Prilaganje Dataverse okruženja za Customer Insights

**Organizacije sa postojećim Dataverse okruženjem**

Organizacije koje već koriste Dataverse mogu da [koristi jedno od svojih postojećih Dataverse okruženja](manage-environments.md#create-an-environment-in-an-existing-organization) kada administrator postavi uvide u ciljne grupe. Navođenjem URL adrese za Dataverse okruženje, vezuje se za njihovo novo okruženje za uvide u ciljnu grupu. Da bi se obezbedile najbolje moguće performanse, Customer Insights i Dataverse okruženja moraju biti hostovani u istom regionu.

Da biste priložili Dataverse okruženje, proširite **Napredna podešavanja** prilikom kreiranja okruženja za uvide u ciljnu grupu. Navedite **URL adresu za Microsoft Dataverse okruženje** i označite polje za potvrdu **Omogući deljenje podataka**.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt":::

**Nova organizacija**

Ako napravite novu organizaciju kada podesite Customer Insights, automatski ćete dobiti novo Dataverse okruženje.

> [!NOTE]
> Ako vaše organizacije već koriste Dataverse kod svojih zakupaca, važno je da upamtite da [kreiranje Dataverse okruženja kontroliše administrator](/power-platform/admin/control-environment-creation.md). Na primer, ako postavljate novo okruženje za uvide u ciljnu grupu sa svojim organizacionim nalogom, a administrator je onemogućio kreiranje Dataverse probnih okruženja za sve osim administratora, ne možete kreirati novo probno okruženje.
> 
> Dataverse probna okruženja kreirana u usluzi Customer Insights imaju 3 GB prostora za skladištenje koji se neće računati u ukupni kapacitet koji ima pravo na zakupca. Plaćene pretplate dobijaju Dataverse pravo od 15 GB za bazu podataka i 20 GB za skladištenje datoteka.

## <a name="output-entities"></a>Izlazni entiteti

Neki izlazni entiteti iz uvida u ciljne grupe dostupni su kao tabele u usluzi Dataverse. Odeljci u nastavku opisuju očekivanu šemu ovih tabela.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obogaćivanje](#enrichment)
- [Predviđanje](#prediction)


### <a name="customerprofile"></a>CustomerProfile

Ova tabela sadrži objedinjeni profil klijenta iz usluge Customer Insights. Šema za objedinjeni profil klijenta zavisi od entiteta i atributa koji se koriste u procesu objedinjavanja. Šema profila klijenta obično sadrži podskup atributa iz [Common Data Model definicije profila klijenta](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabela AlternateKey sadrži ključeve entiteta koji su učestvovali u procesu objedinjavanja.

|Column  |Tip  |Opis  |
|---------|---------|---------|
|DataSourceName    |String         | Naziv izvora podataka. Na primer: `datasource5`        |
|EntityName        | String        | Naziv entiteta u uvidima u ciljnu grupu. Na primer: `contact1`        |
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
