---
title: Primeri OData za Dynamics 365 Customer Insights API-je
description: Često korišćeni primeri otvorenog protokola podataka (OData) za upit API-ja korisničkih uvida za redigovanje podataka.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cdadd72bfe4272d8d83d923baaa6fd40d008473b
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808478"
---
# <a name="odata-query-examples"></a>Primeri upita OData

Open Data Protocol (OData) je protokol za pristup podacima izgrađen na osnovnim protokolima kao što je HTTP. On koristi uobičajeno prihvaćene metodologije kao što je REST za Veb. Postoje razne vrste biblioteka i alatki koje se mogu koristiti za konzumiranje OData usluga.

Ovaj članak navodi neke često tražene primere upita koji vam pomažu u izradi sopstvenih implementacija na osnovu [API-ja uvida klijenata](apis.md).

Morate da izmenite uzorke upita da bi oni radili na ciljnim okruženjima: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` gde se {instanceId} nalazi GUID okruženja "Uvidi kupaca" koje želite da ispitate. Operacija [ListAllInstances vam](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) omogućava da pronađete pristup{InstanceId}.
- {CID}: GUID objedinjenog zapisa kupca. Primer: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identifikator primarnog ključa zapisa kupca u izvor podataka. Primer: `CNTID_1002`
- {DSname}: Niska sa imenom entiteta izvor podataka se unosi u uvid kupca. Primer: `Website_contacts`.
- {SegmentName}: Niska sa imenom izlaznog entiteta segmenta u uvidima kupaca. Primer: `Male_under_40`.

## <a name="customer"></a>klijentu

Sledeća tabela sadrži skup probnih upita za entitet *kupca*.

|Tip upita |Primer  | Belešku  |
|---------|---------|---------|
|ID jednog kupca     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Alternativni ključ    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Alternativni ključevi i dalje postoje u objedinjenom entitetu klijenta       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Za    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Alternativni ključ + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Pretražite  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Daje prvih 10 rezultata za nisku za traženje.      |
|Članstvo u segmentima  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Daje unapred određeni broj redova iz entiteta segmentacije.      |

## <a name="unified-activity"></a>Objedinjena aktivnost

Sledeća tabela sadrži skup probnih upita za entitet *objedinjeneaktivnosti*.

|Tip upita |Primer  | Belešku  |
|---------|---------|---------|
|Aktivnost CID-a     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Navodi aktivnosti određenog profila klijenta |
|Aktivnost vremenski okvir    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktivnosti profila kupca u vremenski okvir       |
|Tip aktivnosti    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktivnost po ime za prikaz     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Sortiranje aktivnosti    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Sortiranje aktivnosti po rastućem ili opadajućem redosledu       |
|Aktivnost proširena iz članstva u segmentima  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Drugi primeri

Sledeća tabela sadrži skup probnih upita za druge entitete.

|Tip upita |Primer  | Belešku  |
|---------|---------|---------|
|Mere CID-a    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Obogaćeni brendovi CID-a    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Obogaćena interesovanja CID-a    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + Expand     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Upiti za OData nisu podržani

Korisnički uvidi ne podržavaju sledeće upite:

- `$filter` na unetim izvornim entitetima. Upite za upite $filter možete da pokrenete samo na sistemskim entitetima koje kreira "Uvidi kupaca".
- `$expand``$search` iz upita. Primer: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` ako `$select` je izabran samo podskup atributa. Primer: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` obogaćenog brenda ili afiniteta interesovanja za datog kupca. Primer: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Upit predviđanje izlaznih entiteta po Alternativni ključ. Primer: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
