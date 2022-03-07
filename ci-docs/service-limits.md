---
title: Ograničenja usluge u usluzi Dynamics 365 Customer Insights
description: Razumevanje ograničenja i restrikcija.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350424"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Ograničenja usluga u mogućnostima usluge Customer Insights

Ovaj članak opisuje ugrađena ograničenja za uslugu Customer Insights, koja su dizajnirana da osiguraju pouzdanost i stabilnost usluge. Svi zahtevi za promene mogu se uputiti preko [foruma ideja](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Uvidi u ciljnu grupu

| Oblasni grafikon  | Ograničenja  | Beleške |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, mere i predviđanja | 300  | Ukupan broj [segmenata](audience-insights/segments.md), [mera i](audience-insights/measures.md) predviđanja [zajedno](audience-insights/predictions.md) ne može da premaši 300.  |
| Relacije | 20 nivoa dubine u odnosima u putanjama entiteta. | Prilikom kreiranja [segmenata](audience-insights/segments.md) ili [mera](audience-insights/measures.md) koristeći interfejs za izradu, putanje entiteta mogu imati do 20 koraka odnosa između početnog entiteta i ciljnog entiteta.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
