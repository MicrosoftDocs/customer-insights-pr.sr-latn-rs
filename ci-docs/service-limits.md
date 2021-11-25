---
title: Ograničenja usluge u Dynamics 365 Customer Insights
description: Razumevanje ograničenja i restrikcija.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/10/2021
ms.locfileid: "7818788"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Ograničenja usluga u mogućnostima usluge Customer Insights

Ovaj članak opisuje ugrađena ograničenja za uslugu Customer Insights, koja su dizajnirana da osiguraju pouzdanost i stabilnost usluge. Svi zahtevi za promene mogu se uputiti preko [foruma ideja](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Uvidi u ciljnu grupu

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Ograničenja usluge u Dynamics 365 Customer Insights korisnici uvida

| Oblasni grafikon  | Ograničenja  | Beleške |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, mere i predviđanja | 300  | Ukupan broj [segmenata](audience-insights/segments.md), [mera](audience-insights/measures.md) i [predviđanja](audience-insights/predictions.md) zajedno ne može da premaši 300.  |
| Relacije | 20 nivoa dubine u odnosima u putanjama entiteta. | Prilikom kreiranja [segmenata](audience-insights/segments.md) ili [mera](audience-insights/measures.md) koristeći interfejs za izradu, putanje entiteta mogu imati do 20 koraka odnosa između početnog entiteta i ciljnog entiteta.  |


## <a name="engagement-insights"></a>Uvidi u angažovanje

### <a name="workspace-and-event-quotas"></a>Kvote za radni prostor i događaje

Uvidi o angažovanje je izuzetno skalabilna aplikacija koja može podržati milione događaja u sekundi. Tokom verzije za javni pregled, događaji imaju ograničenje obima. Takođe postoji ograničenje broja radnih prostora u organizaciji.

### <a name="engagement-insights-limits"></a>Ograničenja uvida u angažovanje

- Maksimalni obim događaja po radnom prostoru = 100 događaja u sekundi

- Maksimalan broj radnih prostora po organizaciji = 100

Kada događaji pređu ograničenje, to može dovesti do gubitka podataka u izveštajima zasnovanim na tim događajima. Možete da [kontaktirate podršku](https://go.microsoft.com/fwlink/?linkid=2145734) kako biste zatražili povećanje obima pre nego što prekoračite ograničenja. Radićemo sa vama kako bismo utvrdili vašu potrebu za povećanjem obima i podržali vaš zahtev.


[!INCLUDE[footer-include](includes/footer-banner.md)]
