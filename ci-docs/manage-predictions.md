---
title: Upravljanje predviđanjima
description: Naučite kako da upravljate predviđanjima, rešavate ih i precizirate.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 42abfb305efaccaeef48e32f2cc69f3d36fbe73d
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245482"
---
# <a name="manage-predictions"></a>Upravljanje predviđanjima

Ovaj članak govori o nekim zadacima koje deli većina scenarija predviđanja.

## <a name="troubleshoot-a-failed-prediction"></a>Rešite problem sa neuspelim predviđanjem

1. Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.

1. Izaberite vertikalne tri tačke pored predviđanja za koji želite da pregledate evidencije grešaka.

1. Izaberite **Evidencije**.

1. Pregledajte sve greške. Može se pojaviti nekoliko vrsta grešaka i one opisuju uslov koji je doveo do greške. Na primer, greška da nema dovoljno podataka za tačno predviđanje obično se rešava učitavanjem dodatnih podataka u Customer Insights.

## <a name="input-data-usability-report"></a>Izveštaj o upotrebljivosti ulaznih podataka

Izveštaj o upotrebljivosti ulaznih podataka pruža konsolidovani prikaz grešaka i upozorenja koja mogu proizvesti vaša gotova predviđanja. Takođe daje preporuke kako da poboljšate performanse modela.

Izveštaj je dostupan nakon što model završi svoj proces obuke. Kreira se za svaki model posebno, bez obzira na to da li je uspešno završen ili ne.

### <a name="view-the-input-data-usability-report"></a>Pogledajte izveštaj o upotrebljivosti ulaznih podataka

Kada gotov model završi svoj korak obuke, pogledajte izveštaj:
- Izaberite tri tačke pored naziva modela i odaberite **Izveštaj o upotrebljivosti ulaznih podataka**.
- Izaberite status modela i izaberite **Pogledajte izveštaj o upotrebljivosti ulaznih podataka** u bočnom oknu.
- Izaberite jedan od modela sa liste i izaberite **Izveštaj o upotrebljivosti ulaznih podataka** u komandnoj traci.
- Otvorite stranicu rezultata modela i izaberite **Izveštaj o upotrebljivosti ulaznih podataka** u komandnoj traci.

### <a name="information-in-the-input-data-usability-report"></a>Informacije u izveštaju o upotrebljivosti ulaznih podataka

Sledeće kolone u izveštaju sadrže korisne informacije za poboljšanje podataka za model.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Primer izveštaja o upotrebljivosti ulaznih podataka koji prikazuje tabelu sa greškama, upozorenjima i preporukama.":::

- **Ime:** Opisno ime greške, upozorenja ili preporuke.
- **Korak:** Model faza, voz ili rezultat, informacije se odnose na njih.
- **Stanje:** Ozbiljnost informacija (greška, upozorenje, preporuka).
- **Ime kolone:** Kolona u entitetu koju treba izmeniti da bi se poboljšale performanse modela.
- **Ime entiteta:** Ime entiteta koje treba izmeniti da bi se poboljšale performanse modela.
- **Detalji:** Detalji o grešci, upozorenju ili preporuci.

## <a name="refresh-a-prediction"></a>Osvežavanje predviđanja

Predviđanja se automatski osvežavaju prema istom [rasporedu za osvežavanje podataka](schedule-refresh.md), kao što je konfigurisano u podešavanjima. Možete ih osvežiti i ručno.

1. Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.

1. Odaberite uspravne tri tačke pored predviđanja koje želite da osvežite.

1. Izaberite **Osveži**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Brisanje predviđanja

Brisanjem predviđanja uklanja se i njegov izlazni entitet.

1. Idite na **Obaveštavanje** > **Predviđanja** i izaberite karticu **Moja predviđanja**.

1. Odaberite uspravne tri tačke pored predviđanja koje želite da izbrišete.

1. Izaberite **Izbriši**.
