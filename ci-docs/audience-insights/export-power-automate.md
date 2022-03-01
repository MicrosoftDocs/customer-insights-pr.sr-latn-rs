---
title: Power Automate konektor | Microsoft Docs
description: Kreirajte tokove u usluzi Microsoft Power Automate iz usluge Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406776"
---
# <a name="power-automate-connector-preview"></a>Power Automate konektor (pregled)

Pokrenite određene događaje koji se pojavljuju automatski kada se promene podaci i upravljajte složenijim tokovima direktno u usluzi [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate okidači

Možete koristiti razne okidače koji vam omogućavaju da kreirate tokove za automatizaciju zadataka koji se ponavljaju, poput obaveštenja ili naprednijih radnji. 

- Pokrenite kada ne uspe osvežavanje izvora podataka. 
- Pokrenite kada uspe osvežavanje izvora podataka.
- Pokrenite kada se pređe granična vrednost za segment. Okidač je ograničen na prekoračenje granične vrednosti.
- Pokrenite kada se pređe granična vrednost za poslovnu meru. Okidač je ograničen na prekoračenje granične vrednosti.
- Aktivira se kada se završi potpuno osvežavanje (izvora podataka, segmenata, mera...).
- Pokrenite kada se završi osvežavanje procesa objedinjavanja (mapiranje, podudaranje, spajanje).

[Konfigurisanje okidača u usluzi Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate radnje
Power Automate konektor pruža druge radnje osim dostupnih okidača. Za više informacija pogledajte [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Kreirajte Power Automate tok u uvidima o korisnicima

1. U uvidima o korisnicima idite na **Administrator** > **Sistem**.

1. Na stranici **Sistem** izaberite karticu **Status**.

1. U odeljku **Izvori podataka** izaberite **Tokovi** i izaberite **Kreiranje toka** iz padajuće liste.
   > [!div class="mx-imgBorder"]
   > ![Power Automate konektor koji prikazuje radnju „Kreiraj tok“](media/power-automate-connector-create-flow.png "Power Automate konektor koji prikazuje radnju „Kreiraj tok“")

1. U usluzi Power Automate, izaberite jedan od dostupnih okidača da biste kreirali željeni tok. Ako kreirate prvi tok, prvo ćete morati da potvrdite identitet pomoću Power Automate konektora.
