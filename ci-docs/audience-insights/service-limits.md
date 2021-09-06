---
title: Ograničenja usluge
description: Razumevanje ograničenja i restrikcija.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034881"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Ograničenja usluge u Dynamics 365 Customer Insights mogućnosti uvida o korisnicima

Ovaj članak opisuje ugrađena ograničenja za uslugu Customer Insights, koja su dizajnirana da osiguraju pouzdanost i stabilnost usluge. Svi zahtevi za promene mogu se uputiti preko [foruma ideja](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Oblasni grafikon  | Ograničenja  | Beleške |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti i mere | 100 segmenata ili mera. | Ukupan broj aktivnih[ segmenata](segments.md) i[ mera](measures.md) kombinovano ne može preći 100.  |
| Relacije | 20 nivoa dubine u odnosima u putanjama entiteta. | Prilikom kreiranja [segmenata](segments.md) ili [mera](measures.md) koristeći interfejs za izradu, putanje entiteta mogu imati do 20 koraka odnosa između početnog entiteta i ciljnog entiteta.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]