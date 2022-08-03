---
title: Power Automate linija spajanja (pregled) | Microsoft dokumenti
description: Kreirajte tokove u usluzi Microsoft Power Automate iz usluge Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196135"
---
# <a name="power-automate-connector-preview"></a>Power Automate konektor (pregled)

Pokrenite određene događaje koji se pojavljuju automatski kada se promene podaci i upravljajte složenijim tokovima direktno u usluzi [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Poznata ograničenja

- Najviše 100 poziva na 60 sekundi. Koristite [parametar $skip za](/connectors/customerinsights/#get-items-from-an-entity) pozivanje API krajnja tačka više puta.

## <a name="power-automate-triggers"></a>Power Automate okidači

Koristite okidače da kreirate tokove u oblaku i automatizujete ponavljajuće zadatke, kao što su obaveštenja ili naprednije radnje. Koristi okidače kada:

- Osvežavanje izvor podataka ne uspe.
- Osvežavanje izvor podataka uspe.
- Prag se prelazi na segmentu. Okidač je ograničen na prekoračenje granične vrednosti.
- Prag se prelazi na poslovnoj meri. Podržane su samo poslovne mere bez dimenzije. Okidač je ograničen na prekoračenje granične vrednosti.
- Kompletno planirano osvežavanje je dovršeno. Ovaj okidač ne radi za ručno započeto osvežavanje.
- Osvežavanje procesa ujedinjenja je dovršeno.

[Konfigurišite okidače u usluzi Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate radnje

Power Automate konektor pruža druge radnje osim dostupnih okidača. Za više informacija pogledajte [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Kreiranje Power Automate toka

1. Idite na **Administrator** > **Veze**.

1. Na pločici **Power Automate** izaberite **Podesi**.

1. Otvara se Customer Insights konektor (pregled) u usluzi Power Automate. **Prijavite se** u Power Automate.

1. Izaberite jedan od dostupnih okidača i dodajte još koraka svom novom toku. Za više informacija pogledajte [Kreiranje toka u oblaku u usluzi Power Automate](/power-automate/get-started-logic-flow).

Primeri kako se koriste tokovi: 
- Pošaljite poruku na Microsoft Teams kanal ako osvežavanje izvora podataka ne uspe. 
- Pošaljite e-poruku vlasnicima podataka kada se pređe prag na segmentu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
