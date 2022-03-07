---
title: Predloženi segmenti zasnovani na aktivnosti.
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
ms.openlocfilehash: 9c10a32b770ea110a1166f20f72116a3a12cb92e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354480"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Predloženi segmenti zasnovani na podacima o aktivnosti (pregled)

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
Ako se bavite zdravstvenom delatnošću koja pruža javnu zdravstvenu zaštitu i vaš cilj je da smanjite troškove za pojedinačne pacijente. Moguć način za to bi bilo smanjenje ponovljenih poseta pružanjem najbolje moguće nege u što manje poseta. U ovom slučaju, vaš cilj je da učestalost poseta bude niska i da minimizujete ponovljene troškove za pacijente. Ili možete identifikovati segmente pacijenata koji imaju česte preglede i visoke troškove koji se ponavljaju, pa analizirati ove slučajeve kako biste poboljšali lečenje pojedinca. 

## <a name="required-data"></a>Obavezni podaci

Predlozi se generišu na osnovu izabranih ulaznih podataka. 

- Korisnički profili: Svi klijenti ili članovi određenog segmenta. 

- Vremenski period: Prošli mesec, prošla godina ili bilo koji prilagođeni vremenski okvir.

- Tip aktivnosti: kupovine, maloprodajne transakcije, transakcije na mreži, slučajevi korisničke podrške, pretplate itd.  

- Entitet u usluzi Customer Insights koji sadrži podatke o aktivnosti: entitet ujednačene aktivnosti ili entitet za određenu aktivnost. 

- Dimenzije koje treba da obuhvate: Nedavna aktivnost, učestalost ili novčana dimenzija, u zavisnosti od vaših poslovnih zahteva.

## <a name="generate-suggested-segments"></a>Generišite predložene segmente

1. Idite na **Segmenti**.

1. Izaberite karticu **Predlozi (pregled)**.

1. Izaberite **Pronađite nove predloge** i odaberite **Pogledajte ili predvidite ponašanje klijenata**. Izaberite **Početak** za pokretanje vođenog iskustva.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Prvi korak čarobnjaka za konfiguraciju za predloženi segment na osnovu aktivnosti.":::

1. Navedite potrebne ulazne podatke i izaberite **Sledeće** i nastavite.

   - Odaberite klijente: Uključite sve klijente ili određeni segment.
   - Odaberite aktivnost: Izaberite vrstu aktivnosti i entitete koji opisuju aktivnost.
   - Željene postavke: Postavite vremenski period koji treba uzeti u obzir, faktore za predloge i mapirajte atribute.

1. Pregledajte svoj unos i izaberite **Pokreni** da biste pokrenuli model i generisali predloge.

1. U zavisnosti od broja korisničkih profila i izabranih aktivnosti, može potrajati nekoliko minuta. 

Nakon generisanja predloga, možete ih filtrirati prema dimenziji ili vrednosti koja vas najviše zanima. 

## <a name="view-details-of-a-suggested-segment"></a>Prikaz detalja predloženog segmenta

Kada se predlozi generišu, naći ćete ih na spisku **Segmenti** > **Predlozi (pregled)** u odeljku **Predlozi zasnovani na aktivnostima**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Prošireno bočno okno koje prikazuje detaljne podatke o predloženom segmentu.":::

Izaberite **Pogledajte predlog** na predloženom segmentu da biste videli detalje o tom segmentu. Bočno okno pruža detalje poput obima svake dimenzije u poređenju sa ciljnom grupom. Takođe naglašava broj potencijalnih članova u segmentu i odgovarajući procenat od ukupnog broja klijenata. Ako želite da predlog zadržite kao segment, izaberite **Napravi segment**.    

## <a name="save-a-suggestion-as-a-segment"></a>Čuvanje predloga kao segmenta

1. Idite na **Segmenti** > **Predlozi (pregled)**.

1. Izaberite segment koji želite da sačuvate. 

1. U bočnom oknu, izaberite **Napravi segment**. 

1. Kada sačuvate segment, prikazaće se na listi segmenata na kartici **Svi segmenti**. Sad može biti [osvežen ili izbrisan kao i bilo koji drugi segment](segments.md). Ne možete da uređujete detalje segmenta. Međutim, možete promeniti kriterijume unosa za predloge i generisati različite predloge.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Osvežite ili izmenite skup predloga

1. Idite na **Segmenti** > **Predlozi (pregled)** i potražite segment u odeljku **Predlozi zasnovani na aktivnostima**.

1. Izaberite **Osveži predloge** da biste osvežili predloge uz zadržavanje konfigurisanih atributa. Ili izaberite **Izmeni predloge** da biste izmenili konfigurisane atribute. Sistem će ponovo pokrenuti postupak, generisati predloge za segmente na osnovu najnovijih podataka i zameniti trenutne predloge.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
