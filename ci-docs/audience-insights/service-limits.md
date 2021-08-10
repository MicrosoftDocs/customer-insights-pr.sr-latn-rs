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
ms.openlocfilehash: 81253332cbea3110c0b3804db3a4d03b514f92d4
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604386"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Ograničenja usluge u Dynamics 365 Customer Insights mogućnosti uvida o korisnicima

Ovaj članak opisuje ugrađena ograničenja za uslugu Customer Insights, koja su dizajnirana da osiguraju pouzdanost i stabilnost usluge. Svi zahtevi za promene mogu se uputiti preko [foruma ideja](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Oblasni grafikon  | Ograničenja  | Beleške |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti i mere | 100 segmenata ili mera. | Ukupan broj aktivnih[ segmenata](segments.md) i[ mera](measures.md) kombinovano ne može preći 100.  |
| Relacije | 20 nivoa dubine u odnosima u putanjama entiteta. | Prilikom kreiranja [segmenata](segments.md) ili [mera](measures.md) koristeći interfejs za izradu, putanje entiteta mogu imati do 20 koraka odnosa između početnog entiteta i ciljnog entiteta.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]