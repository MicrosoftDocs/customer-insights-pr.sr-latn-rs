---
title: Ograničenja usluge u usluzi Dynamics 365 Customer Insights
description: Razumevanje ograničenja i restrikcija.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483703"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Ograničenja usluga u mogućnostima usluge Customer Insights

Ovaj članak opisuje ugrađena ograničenja za uslugu Customer Insights, koja su dizajnirana da osiguraju pouzdanost i stabilnost usluge. Svi zahtevi za promene mogu se uputiti preko [foruma ideja](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Uvidi u ciljnu grupu

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Ograničenja usluge u Dynamics 365 Customer Insights mogućnosti uvida o korisnicima

| Oblasni grafikon  | Ograničenja  | Beleške |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti i mere | 100 segmenata ili mera. | Ukupan broj aktivnih[ segmenata](audience-insights/segments.md) i[ mera](audience-insights/measures.md) kombinovano ne može preći 100.  |
| Relacije | 20 nivoa dubine u odnosima u putanjama entiteta. | Prilikom kreiranja [segmenata](audience-insights/segments.md) ili [mera](audience-insights/measures.md) koristeći interfejs za izradu, putanje entiteta mogu imati do 20 koraka odnosa između početnog entiteta i ciljnog entiteta.  |


## <a name="engagement-insights"></a>Uvidi u angažovanje

### <a name="workspace-and-event-quotas"></a>Kvote za radni prostor i događaje

Uvidi o angažovanje je izuzetno skalabilna aplikacija koja može podržati milione događaja u sekundi. Tokom verzije za javni pregled, događaji imaju ograničenje obima. Takođe postoji ograničenje broja radnih prostora u organizaciji.

### <a name="engagement-insights-limits"></a>Ograničenja uvida u angažovanje

- Maksimalni obim događaja po radnom prostoru = 100 događaja u sekundi

- Maksimalan broj radnih prostora po organizaciji = 100

Kada događaji pređu ograničenje, to može dovesti do gubitka podataka u izveštajima zasnovanim na tim događajima. Možete da [kontaktirate podršku](https://go.microsoft.com/fwlink/?linkid=2145734) kako biste zatražili povećanje obima pre nego što prekoračite ograničenja. Radićemo sa vama kako bismo utvrdili vašu potrebu za povećanjem obima i podržali vaš zahtev.


[!INCLUDE[footer-include](includes/footer-banner.md)]