---
title: Segmenti zasnovani na izlazu predviđanja
description: Kreirajte segmente na osnovu izlaznog entiteta modela predviđanja.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b89754aea2b0da33f27dea5b26d212920f0c090885f951a37cf42ff11c7b6e93
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036436"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Kreiranje segmenta na osnovu modela predviđanja (pregled)

Rezultati predviđanja ponekad se odnose samo na podskup vaših klijenata. Povećajte personalizaciju preporuka kreiranjem segmenata od rezultata modela predviđanja. Na primer, možda ćete želeti da date konkretne preporuke klijentima koji viže vole određenu vrstu usluge. 

## <a name="prerequisites"></a>Preduslovi

- Barem [dozvole saradnika](permissions.md) u usluzi Customer Insights.

- Model preporuke proizvoda, gubitka transakcija, gubitka pretplata ili trajne vrednosti klijenta konfigurisan je u usluzi Customer Insights. Pregledajte zahteve za postavljanje različitih modela:

  - [Model preporuke proizvoda](predict-product-recommendation.md)
  - [Model gubitka pretplata](predict-subscription-churn.md)
  - [Model gubitka transakcija](predict-transactional-churn.md)
  - [Model trajne vrednosti klijenta](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Kreiranje segmenata klijenata zasnovanih na predviđanjima

1. Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.

1. Izaberite uspravne tri tačke pored modela koji želite da pregledate i izaberite **Prikaz**.

1. Na stranici rezultata, izaberite **Napravi segment**. Za više informacija o stranici rezultata, pogledajte članak o modelu.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Snimak ekrana stranice rezultata predviđanja sa isticanjem radnje „Napravi segment“.":::

1. Kreirajte novi segment na osnovu izlaznog entiteta izabranog modela. Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).