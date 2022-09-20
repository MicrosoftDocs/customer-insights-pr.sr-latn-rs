---
title: Ograničenja usluge u uvidima klijenata
description: Razumevanje ograničenja i ograničenja u saaS usluzi "Uvidi kupaca".
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c3863b1a72fd92ddc87755699feda11371ec9214
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463236"
---
# <a name="service-limits-in-customer-insights"></a>Ograničenja usluge u uvidima klijenata

 Customer Insights ima ugrađena ograničenja dizajnirana da obezbede pouzdanost i stabilnost usluge. Svi zahtevi za promene mogu se uputiti preko [foruma ideja](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Oblasni grafikon  | Ograničenja  | Beleške |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, mere i predviđanja | 300  | Ukupan broj [segmenata](segments.md), [mera i](measures.md) predviđanja [zajedno](predictions-overview.md) ne može da premaši 300.  |
| Relacije | 20 nivoa dubine u odnosima u putanjama entiteta. | Prilikom kreiranja [segmenata](segments.md) ili [mera](measures.md) koristeći interfejs za izradu, putanje entiteta mogu imati do 20 koraka odnosa između početnog entiteta i ciljnog entiteta.  |
|Unos podataka| Uporedne procene za izvore Power Query podataka su ograničene. | Customer Insights ima ista ograničenja [za osvežavanje kao Dataflows u PowerBI.com](/power-query/power-query-online-limits#refresh-limits). |

## <a name="fair-scheduling-of-jobs"></a>Pošteno zakazivanje poslova

Customer Insights je SaaS servis koji koristi deljene Azure resurse. Kupci imaju tendenciju da imaju opterećenje promenljivog intenziteta i po različitim rasporedima. Da bismo obezbedili fer pristup osnovnim resursima, osiguravamo da sistemski procesi budu izvedeni fer redosledom. Primeri sistemskih procesa su poslovi vezani za ujedinjenje podataka, ažuriranje segmenta ili izračunavanje mera. Sajamskog zakazivanja vas štiti od čekanja u redu za resurse ako dođe do porasta traženih poslova. Istovremeno, uvidi klijenata ne garantuju da se svi poslovi koje čekate u redu obrađuju paralelno.

[!INCLUDE [footer-include](includes/footer-banner.md)]
