---
title: Predloženi segmenti zasnovani na aktivnosti (pregled)
description: Neka vam mašinsko učenje pomogne da pronađete nove i zanimljive segmente na osnovu aktivnosti klijenata.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170606"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Predloženi segmenti zasnovani na aktivnosti (pregled)

Otkrijte zanimljive segmente svojih klijenata na osnovu podataka o aktivnostima klijenata koji se unose u Customer Insights. Primeri podataka o aktivnostima su transakcije, trajanje poziva za podršku, kupovine ili povraćaji. Da bi predložili segmente, podaci o aktivnostima se analiziraju na osnovu nedavnosti, učestalosti i novčane vrednosti (ili trajanja). Možete i da generišete [predložene segmente za poboljšanje mere ili za bolje razumevanje uticaja na atribut](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Kartica Predloženi segmenti prikazuje predloge segmenata za segmente zasnovane na aktivnostima i segmente zasnovane na atributima.":::

## <a name="categorize-customers-by-activity"></a>Kategorizacija klijenata prema aktivnostima

Sa [podacima o aktivnostima](activities.md) dostupnim u usluzi Customer Insights, možemo da generišemo predloge koji predstavljaju grupe klijenata:

- najaktivniji klijenti 
- klijenti koji su obavili najviše kupovina 
- klijenti koji su ostvarili najviše prihoda 
- klijenti koji u poslednje vreme nisu bili aktivni 
- klijenti koji često komuniciraju sa vašim preduzećem  

Ako imate maloprodaju, mogli biste da saznate koji klijenti ostvaruju najviše prihoda i nagradite ih kuponom. Ili možete da identifikujete povremene klijente i ponudite im da se pridruže programu nagrađivanja kako bi češće posećivali vaše preduzeće.
Ako obezbedite javno zdravstvo, a vaš cilj je da smanjite troškove za pojedinačne pacijente, mogli biste da pokušate da smanjite periodične posete pružajući najbolju moguću negu u što manje poseta. U ovom slučaju, vaš cilj je da učestalost poseta bude niska i da minimizujete ponovljene troškove za pacijente. Ili možete identifikovati segmente pacijenata koji imaju česte preglede i visoke troškove koji se ponavljaju, pa analizirati ove slučajeve kako biste poboljšali lečenje pojedinca.

## <a name="required-data"></a>Obavezni podaci

Predlozi se generišu na osnovu izabranih ulaznih podataka.

- Korisnički profili: Svi klijenti ili članovi određenog segmenta.

- Vremenski period: Prošli mesec, prošla godina ili bilo koji prilagođeni vremenski okvir.

- Tip aktivnosti: kupovine, maloprodajne transakcije, transakcije na mreži, slučajevi korisničke podrške, pretplate itd.  

- Entitet u usluzi Customer Insights koji sadrži podatke o aktivnosti: entitet ujednačene aktivnosti ili entitet za određenu aktivnost.

- Dimenzije koje treba da obuhvate: Nedavna aktivnost, učestalost ili novčana dimenzija, u zavisnosti od vaših poslovnih zahteva.

## <a name="generate-suggested-segments"></a>Generišite predložene segmente

1. Idite na **karticu Segmenti** i izaberite **karticu Predlozi (pregled**).

1. Izaberite **Pronađite nove predloge** i odaberite **Pogledajte ili predvidite ponašanje klijenata**. Izaberite **početni ekran**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Prvi korak čarobnjaka za konfiguraciju za predloženi segment na osnovu aktivnosti.":::

1. Navedite potrebne ulazne podatke i kliknite na dugme " **Dalje"**.

   - Odaberite klijente: Uključite sve klijente ili određeni segment.
   - Odaberite aktivnost: Izaberite vrstu aktivnosti i entitete koji opisuju aktivnost.
   - Željene postavke: Postavite vremenski period koji treba uzeti u obzir, faktore za predloge i mapirajte atribute.

1. Pregledajte svoj unos i izaberite **Pokreni** da biste pokrenuli model i generisali predloge.

U zavisnosti od broja korisničkih profila i izabranih aktivnosti, može potrajati nekoliko minuta.

Nakon generisanja predloga, možete ih filtrirati prema dimenziji ili vrednosti koja vas najviše zanima.

## <a name="manage-suggested-segments"></a>Upravljanje predloženim segmentima

Idite na **karticu Segmenti** i izaberite **karticu Predlozi (pregled**). U odeljku **Predlozi zasnovani na aktivnostima** izaberite predloženi segment da biste prikazali dostupne radnje.

- **Pogledajte predlog** da biste videli detalje tog segmenta kao obim svake dimenzije u poređenju sa ciljnom grupom. Takođe naglašava broj potencijalnih članova u segmentu i odgovarajući procenat od ukupnog broja klijenata.
- **Kreirajte segment** da biste sačuvali predloženo kao segment. Prikazuje se na kartici **"Svi segmenti** " i može se [osvežiti ili izbrisati](segments.md). Ne možete da uređujete detalje segmenta. Međutim, možete promeniti kriterijume unosa za predloge i generisati različite predloge.
- **Uredite predloge** da biste izmenili konfigurisane atribute koji će zameniti trenutne predloge.
- **Osvežite predloge** da biste osvežili predloge zadržavajući konfigurisane atribute.

[!INCLUDE [footer-include](includes/footer-banner.md)]
