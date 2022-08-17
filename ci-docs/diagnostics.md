---
title: Izvoz dijagnostičkih evidencija (pregled)
description: Saznajte kako da pošaljete evidencije na monitor Microsoft Azure.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 60b039173fd938482c782c7394420d4951c222a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245942"
---
# <a name="export-diagnostic-logs-preview"></a>Izvoz dijagnostičkih evidencija (pregled)

Prosledite evidencije iz uvida klijenata pomoću Azure monitora. Evidencije resursa Azure monitora vam omogućava da nadgledate i šaljete evidencije [u Azure skladište](https://azure.microsoft.com/services/storage/), [Azure analitiku evidencije](/azure/azure-monitor/logs/log-analytics-overview) ili da ih strimujete [u Azure čvorišta događaja](https://azure.microsoft.com/services/event-hubs/).

Uvidi kupaca šalju sledeće evidencije događaja:

- **Događaji nadgledanja**
  - **APIEvent** - omogućava praćenje promena putem UI Dynamics 365 Customer Insights.
- **Operativni događaji**
  - **WorkflowEvent** - omogućava vam da podesite izvore podataka [, ujedinite](data-sources.md), [obogatite](data-unification.md) i [izvezete](enrichment-hub.md)[podatke](export-destinations.md) u druge sisteme. Ovi koraci mogu da se urade pojedinačno (na primer, da se pokrene jedan izvoz). Oni takođe mogu da pokrenu orkestrirano (na primer, osvežavanje podataka iz izvora podataka koji pokreću proces ujedinjenja, koji će povući bogaćenja i izvesti podatke u drugi sistem). Više informacija potražite u šemi [WorkflowEvent](#workflow-event-schema).
  - **APIEvent** - šalje sve API pozive instance klijenata na Dynamics 365 Customer Insights. Više informacija potražite u apievent [šemi](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Podešavanje dijagnostičkih postavki

### <a name="prerequisites"></a>Preduslovi

- Aktivna [Azure pretplata](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Administratorske](permissions.md#admin) dozvole u uvidima klijenata.
- [saradnik administratora i administratora korisničkog pristupa](/azure/role-based-access-control/role-assignments-portal) na odredišnom resursu na Azure. Resurs može biti nalog Azure Data Lake Storage, čvorište Azure događaja ili radni prostor Azure analitike evidencije. Ova dozvola je neophodna tokom konfigurisanja dijagnostičkih postavki u programu Customer Insights, ali se može promeniti nakon uspešnog podešavanja.
- [Ispunjeni su](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) odredišni zahtevi za Azure skladište, Azure čvorište događaja ili analitiku evidencije Azure.
- Barem uloga **čitalac** resursa kojoj resurs pripada.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Podešavanje dijagnostike pomoću Azure monitora

1. U fascikli "Uvidi kupaca" idite na **administratorski** > **sistem i** izaberite karticu **Dijagnostika**.

1. Izaberite **stavku Dodaj odredište**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Dijagnostička veza.":::

1. Navedite ime u odredišnom **polju Ime za dijagnostiku**.

1. Izaberite tip **resursa** (Nalog skladišta, Čvorište događaja ili Analitika evidencije).

1. Izaberite **pretplatu**, **grupu resursa** i resurs **za** odredišni resurs. Više informacija [o dozvoli i evidenciji potražite u članku](#configuration-on-the-destination-resource) Konfiguracija odredišnog resursa.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Izaberite opciju **Poveži se sa sistemom** da biste se povezali sa odredišnim resursom. Evidencije počinju da se pojavljuju na odredištu posle 15 minuta, ako je API u upotrebi i generiše događaje.

## <a name="configuration-on-the-destination-resource"></a>Konfiguracija odredišnog resursa

Na osnovu vašeg izbora tipa resursa, automatski dolazi do sledećih promena:

### <a name="storage-account"></a>Nalog skladišta

Direktor usluge "Uvidi kupaca" dobija **dozvolu saradnik za** skladištenje na izabranom resursu i kreira dva kontejnera pod izabranim prostorom za ime:

- `insight-logs-audit` koji sadrže događaje **nadgledanja**
- `insight-logs-operational` koji sadrže operativne **događaje**

### <a name="event-hub"></a>Čvorište događaja

Direktor usluge "Uvid u korisnike **" dobija dozvolu čvorišta događaja Azure vlasnika** podataka za resurs i kreira dva čvorišta događaja pod izabranim prostorom za ime:

- `insight-logs-audit` koji sadrže događaje **nadgledanja**
- `insight-logs-operational` koji sadrže operativne **događaje**

### <a name="log-analytics"></a>Evidentiraj analitiku

Direktor usluge "Uvidi korisnika" dobija dozvolu **za saradnik evidencije** o resursu. Evidencije su dostupne u okviru evidencije **Tabela** > **za evidenciju** > **na** izabranom radnom prostoru analitike evidencije. Razvijte rešenje **za upravljanje evidencijom** i pronađite tabele `CIEventsAudit``CIEventsOperational` i tabele.

- `CIEventsAudit` koji sadrže događaje **nadgledanja**
- `CIEventsOperational` koji sadrže operativne **događaje**

U prozoru **Upiti** proširite rešenje **nadzora** i pronađite primer upita navedenih pretraživanjem `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>Uklanjanje odredišta dijagnostike

1. Idite na **administratorski** > **sistem i** izaberite karticu **Dijagnostika**.

1. Izaberite odredište dijagnostike sa liste.

   > [!TIP]
   > Uklanjanje odredišta zaustavlja prosleđivanje evidencije, ali ne briše resurs na Azure pretplati. Da biste izbrisali resurs u Azure, izaberite vezu u koloni **Radnje** da biste otvorili portal Azure za izabrani resurs i tamo ga izbrisali. Zatim izbrišite odredište dijagnostike.

1. U koloni **Radnje** izaberite ikonu **"Izbriši** ".

1. Potvrdite brisanje da biste uklonili odredište i zaustavili prosleđivanje evidencije.

## <a name="log-categories-and-event-schemas"></a>Evidentiraj kategorije i šeme događaja

Trenutno su [podržani API](apis.md) događaji i događaji toka posla i primenjuju se sledeće kategorije i šeme.
Šema evidencije prati zajedničku šemu [Azure monitora](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorije

Uvidi kupaca obezbeđuju dve kategorije:

- **Događaji nadgledanja**: [API događaji](#api-event-schema) za praćenje promena konfiguracije na usluzi. `POST|PUT|DELETE|PATCH` operacije idu u ovu kategoriju.
- **Operativni događaji**: [API događaji ili događaji](#api-event-schema) toka [posla](#workflow-event-schema) generisani tokom korišćenja usluge.  Na primer, zahtevi `GET` ili događaji izvršavanja toka posla.

## <a name="event-schemas"></a>Šeme događaja

API događaji i događaji toka posla imaju zajedničku strukturu, ali uz nekoliko razlika. Više informacija potražite u apI [šemi događaja ili šemi](#api-event-schema) događaja [toka posla](#workflow-event-schema).

### <a name="api-event-schema"></a>Šema API događaja

| Polje             | Tippodataka  | Obavezno/opcionalno | Opis       | Primer        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Vremenska oznaka | Zahtevano          | Timestamp događaja (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Zahtevano          | ID resursa instance koja je emigrirao događaj         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Zahtevano          | Ime operacije predstavljene ovim događajem.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Zahtevano          | Evidentiraj kategoriju događaja. Ili `Operational` ili `Audit`. All POST/PUT/PATCH/DELETE HTTP Requests are tagged with `Audit`, sve ostalo sa`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Zahtevano          | Status događaja. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Opcionalno          | Status rezultata događaja. Ako operacija odgovara pozivu REST API, to je HTTP statusni kôd.        | `200`             |
| `durationMs`      | Dugačak      | Opcionalno          | Trajanje operacije u milisekundama.     | `133`     |
| `callerIpAddress` | String    | Opcionalno          | IP adresa pozivaoca, ako operacija odgovara API pozivu koji dolazi sa javno dostupne IP adrese.                                                 | `144.318.99.233`         |
| `identity`        | String    | Opcionalno          | JSON objekat koji opisuje identitet korisnika ili aplikacije koja je uradila operaciju.       | Pogledajte [odeljak](#identity-schema) Identitet.     |  
| `properties`      | String    | Opcionalno          | JSON objekat sa više svojstava prema određenoj kategoriji događaja.      | Pogledajte [odeljak Svojstva](#api-properties-schema).    |
| `level`           | String    | Zahtevano          | Nivo ozbiljnosti događaja.    | `Informational`, `Warning`,, `Error` ili `Critical`.           |
| `uri`             | String    | Opcionalno          | Apsolutni zahtev URI.    |               |

#### <a name="identity-schema"></a>Šema identiteta

JSON `identity` objekat ima sledeću strukturu

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Polje                         | Opis                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Dodeljena uloga za korisnika ili aplikaciju. Više informacija potražite u korisničkim [dozvolama](permissions.md).                                     |
| `Authorization.RequiredRoles` | Potrebne uloge za operaciju. `Admin` uloga je dozvoljena za sve operacije.                                                    |
| `Claims`                      | Tvrdnje korisnika ili aplikacije JSON Web token (JWT). Svojstva zahteva se razlikuju po organizaciji i Azure Active Directory konfiguraciji. |

#### <a name="api-properties-schema"></a>Šema API svojstava

[API događaji imaju](apis.md) sledeća svojstva.

| Polje                        | Opis                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | `ApiEvent` Uvek, označavanje događaja evidencije kao API događaja.                                                                 |
| `properties.userAgent`       | Agent pregledača šalje zahtev ili `unknown`.                                                                        |
| `properties.method`          | HTTP metod:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Relativna putanja zahteva.                                                                                          |
| `properties.origin`          | URI koji pokazuje odakle dolazi dopremanje ili `unknown`.                                                                  |
| `properties.operationStatus` | `Success` za HTTP statusni kôd < 400 <br> `ClientError` za HTTP statusni kôd < 500 <br> `Error` za HTTP Status >= 500 |
| `properties.tenantId`        | ID organizacije                                                                                                        |
| `properties.tenantName`      | Naziv organizacije.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ID objekta pozivaoca.                                                                         |
| `properties.instanceId`      | Uvidi kupaca`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Šema događaja toka posla

Tok posla sadrži više koraka. [Unesti izvori podataka, ujedinite](data-sources.md), [obogatite](data-unification.md)[i](enrichment-hub.md) izvezite [podatke](export-destinations.md). Svi ti koraci mogu da se pokreću pojedinačno ili da se orkestrira sa sledećim procesima.

#### <a name="operation-types"></a>Tipovi operacija

| OperationType     | Grupiši                                     |
| ----------------- | ----------------------------------------- |
| Ingestion         | [Izvori podataka](data-sources.md)           |
| Prespremanje podataka   | [Izvori podataka](data-sources.md)           |
| Mapiranje               | [Ujednačavanje podataka](data-unification.md)   |
| Podudaranje             | [Ujednačavanje podataka](data-unification.md)   |
| Objedini             | [Ujednačavanje podataka](data-unification.md)   |
| Istorija profila      | [Profili klijenata](customer-profiles.md) |
| Pretražite            | [Profili klijenata](customer-profiles.md) |
| Aktivnost          | [Aktivnosti](activities.md)                  |
| AtributMeasures | [Segmenti i mere](segments.md)      |
| EntitetMeasures    | [Segmenti i mere](segments.md)      |
| Mere          | [Segmenti i mere](segments.md)      |
| Segmentacija      | [Segmenti i mere](segments.md)      |
| Obogaćivanje        | [Obogaćivanje](enrichment-hub.md)                                          |
| Informacije      | [Predviđanja](predictions-overview.md)                                          |
| AiBuilder         | [Predviđanja](predictions-overview.md)                                          |
| Uvidi          | [Predviđanja](predictions-overview.md)                                          |
| Export            | [Izvozi](export-destinations.md)                                          |
| ModelManagement   | [Predviđanja](custom-models.md)                                           |
| Relacija      | [Ujednačavanje podataka](relationships.md)                                           |

#### <a name="field-description"></a>Opis polja

| Polje           | Tippodataka  | Obavezno/opcionalno | Opis                                                                                                                                                   | Primer                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Vremenska oznaka | Zahtevano          | Timestamp događaja (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Zahtevano          | ID resursa instance koja je emituje događaj.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Zahtevano          | Ime operacije predstavljene ovim događajem. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Pogledajte [tipove operacija](#operation-types) za referencu. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Zahtevano          | Evidentiraj kategoriju događaja. Uvek `Operational` za događaje toka posla                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Zahtevano          | Status događaja. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Dugačak      | Opcionalno          | Trajanje operacije u milisekundama.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Opcionalno          | JSON objekat sa više svojstava prema određenoj kategoriji događaja.                                                                                        | Pogledajte podse odsek " [Svojstva toka posla"](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Zahtevano          | Nivo ozbiljnosti događaja.                                                                                                                                  | `Informational`, `Warning` ili `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Šema svojstava toka posla

Događaji toka posla imaju sledeća svojstva.

| Polje              | Workflow | Zadatak | Opis            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Da      | Da  | Uvek `WorkflowEvent`, označavanje događaja kao događaja toka posla.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Da      | Da  | Identifikator toka posla. Svi događaji toka posla i zadataka u okviru izvršavanja toka posla imaju isti `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Da      | Da  | Identifikator operacije, pogledajte tipove [operacija](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Da      | No   | Samo tok posla. Broj zadataka koje tok posla pokreće.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Da      | No   | Opcionalno. Samo događaji toka posla. ID Azure Active Directory [objekta korisnika koji je aktivirao](/azure/marketplace/find-tenant-object-id#find-user-object-id) tok posla, pogledajte takođe `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Da      | No   | `full` ili osvežiti `incremental`.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Da      | No   | `OnDemand` ili `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Da      | No   | `Running` ili `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Da      | Da  | UTC Timestamp`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Da      | Da  | UTC Timestamp`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Da      | Da  | UTC Timestamp`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Da      | Da  | Uvidi kupaca`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Da  | - Za OperationType = `Export`, identifikator je guid konfiguracije izvoza. <br> - Za OperationType = `Enrichment`, to je guid bogaćenja <br> - Za OperationType `Measures``Segmentation` i, identifikator je ime entiteta. |
| `properties.friendlyName`                    | No       | Da  | Korisnički prilagođeno ime izvoza ili entiteta koji se obrađuje.                                                                                                                                                                                           |
| `properties.error`                           | No       | Da  | Opcionalno. Poruka o grešci sa više detalja.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Da  | Opcionalno. Samo za OperationType `Export`. Identifikuje tip izvoza. Više informacija potražite u [pregledu izvoznih odredišta](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Da  | Opcionalno. Samo za OperationType `Export`. Sadrži listu konfigurisanih entiteta u izvozu.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Da  | Opcionalno. Samo za OperationType `Export`. Detaljna poruka za izvoz.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Da  | Opcionalno. Samo za OperationType `Segmentation`. Označava ukupan broj članova koje segment ima.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
