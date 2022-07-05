---
title: Power Automate linija spajanja (pregled) | Microsoft dokumenti
description: Kreirajte tokove u usluzi Microsoft Power Automate iz usluge Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29a861dad926072f6f849d738d868f0f3b9306be
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082456"
---
# <a name="power-automate-connector-preview"></a>Power Automate konektor (pregled)

Pokrenite određene događaje koji se pojavljuju automatski kada se promene podaci i upravljajte složenijim tokovima direktno u usluzi [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Poznata ograničenja

- Možete da uradite najviše 100 poziva na 60 sekundi. API možete da pozovete krajnja tačka više puta pomoću parametra $skip uređaja. [Saznajte više o $skip parametru](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Power Automate okidači

Koristite okidače da kreirate tokove u oblaku i automatizujete ponavljajuće zadatke, kao što su obaveštenja ili naprednije radnje.

- Pokrenite kada ne uspe osvežavanje izvora podataka.
- Pokrenite kada uspe osvežavanje izvora podataka.
- Pokrenite kada se pređe granična vrednost za segment. Okidač je ograničen na prekoračenje granične vrednosti.
- Pokrenite kada se pređe granična vrednost za poslovnu meru. Podržane su samo poslovne mere bez dimenzije. Okidač je ograničen na prekoračenje granične vrednosti.
- Aktivira se kada se završi potpuno osvežavanje (izvora podataka, segmenata, mera, ...).
- Aktiviraj kada se dovrši osvežavanje procesa ujedinjenja.

[Konfigurišite okidače u usluzi Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate radnje

Power Automate konektor pruža druge radnje osim dostupnih okidača. Za više informacija pogledajte [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Kreiranje Power Automate toka

1. Idite na **Administrator** > **Odredišta za izvoz**.

1. Na pločici **Power Automate** izaberite **Podesi**.

1. Otvara se Customer Insights konektor (pregled) u usluzi Power Automate. **Prijavite se** u Power Automate.

1. Izaberite jedan od dostupnih okidača i dodajte još koraka svom novom toku. Za više informacija pogledajte [Kreiranje toka u oblaku u usluzi Power Automate](/power-automate/get-started-logic-flow).

Primeri kako se koriste tokovi: 
- Pošaljite poruku na Microsoft Teams kanal ako osvežavanje izvora podataka ne uspe. 
- Pošaljite e-poruku vlasnicima podataka kada se pređe prag na segmentu.



[!INCLUDE [footer-include](includes/footer-banner.md)]
