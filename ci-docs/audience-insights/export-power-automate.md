---
title: Power Automate konektor | Microsoft Docs
description: Kreirajte tokove u usluzi Microsoft Power Automate iz usluge Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976105"
---
# <a name="power-automate-connector-preview"></a>Power Automate konektor (pregled)

Pokrenite određene događaje koji se pojavljuju automatski kada se promene podaci i upravljajte složenijim tokovima direktno u usluzi [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate okidači

Koristite okidače da kreirate tokove u oblaku i automatizujete ponavljajuće zadatke, kao što su obaveštenja ili naprednije radnje. 

- Pokrenite kada ne uspe osvežavanje izvora podataka. 
- Pokrenite kada uspe osvežavanje izvora podataka.
- Pokrenite kada se pređe granična vrednost za segment. Okidač je ograničen na prekoračenje granične vrednosti.
- Pokrenite kada se pređe granična vrednost za poslovnu meru. Podržane su samo poslovne mere bez dimenzije. Okidač je ograničen na prekoračenje granične vrednosti.
- Aktivira se kada se završi potpuno osvežavanje (izvora podataka, segmenata, mera...).
- Pokrenite kada se završi osvežavanje procesa objedinjavanja (mapiranje, podudaranje, spajanje).

[Konfigurisanje okidača u usluzi Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate radnje
Power Automate konektor pruža druge radnje osim dostupnih okidača. Za više informacija pogledajte [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Kreiranje Power Automate toka

1. U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.

1. Na pločici **Power Automate** izaberite **Podesi**.

1. Otvara se Customer Insights konektor (pregled) u usluzi Power Automate. **Prijavite se** u Power Automate.

1. Izaberite jedan od dostupnih okidača i dodajte još koraka svom novom toku. Za više informacija pogledajte [Kreiranje toka u oblaku u usluzi Power Automate](/power-automate/get-started-logic-flow).

Primeri korišćenja tokova: 
- Pošaljite poruku na Microsoft Teams kanal ako osvežavanje izvora podataka ne uspe. 
- Pošaljite e-poruku vlasnicima podataka kada se pređe prag na segmentu.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
