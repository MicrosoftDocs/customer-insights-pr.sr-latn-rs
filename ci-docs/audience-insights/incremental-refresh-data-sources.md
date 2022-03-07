---
title: Postepeno osvežavanje za izvore Power Query podataka zasnovane na podacima
description: Osvežite nove i ažurirane podatke za velike izvore podataka na osnovu Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 62632efda3c0c7e53fcdd8864b053ba93e2918bc
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353722"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Postepeno osvežavanje izvora podataka na osnovu Power Query

Ovaj članak govori o konfigurisanju postepenog osvežavanja izvora podataka na osnovu Power Query.

Inkrementalno osvežavanje izvora podataka pruža sledeće prednosti:

- **Brža osvežavanja** – Osvežavaju se samo podaci koji su promenjeni. Na primer, možete da osvežite samo proteklih pet dana skupa podataka iz prethodnog perioda.
- **Povećana pouzdanost** – Uz manje osvežavanja, ne morate dugo da održavate veze sa sistemima sa promenljivim izvorima, smanjujući rizik od problema sa povezivanjem.
- **Smanjena potrošnja resursa** – Osvežavanje samo podskupa ukupnih podataka dovodi do efikasnijeg korišćenja računarskih resursa i smanjenja uticaja na životnu sredinu.

## <a name="configure-incremental-refresh"></a>Konfigurisanje postepenog osvežavanja

Korisnici omogućava postepeno osvežavanje izvora podataka uvezenih Power Query putem te podrške postepenom unošenjem. Na primer, Azure SQL baze podataka sa poljima datuma i vremena, koja pokazuju kada su zapisi datuma poslednji put ažurirani.

1. [Kreirajte novi izvor podataka zasnovan na Power Query](connect-power-query.md).

1. Navedite **ime** za izvor podataka.

1. Izaberite izvor podataka podržava postepeno osvežavanje, kao što je [Azure SQL baza podataka](/power-query/connectors/azuresqldatabase).

1. Izaberite entitete ili tabele za unos.

1. Dovršite korake transformacije i izaberite **Sledeće**.

1. U dijalogu **Podesite postepeno osvežavanje** izaberite **Podesi** da otvorite **Podešavanja postepenog osvežavanja**. Ako izaberete **Preskoči**, izvor podataka će osvežiti celokupni skup podataka.
   > [!TIP]
   > Kasnije možete primeniti i postepeno osvežavanje uređivanjem postojećeg izvora podataka.

1. U **podešavanjima postepenog osvežavanja**, konfigurisaćete postepeno osvežavanje za sve entitete koje ste izabrali prilikom kreiranja izvora podataka.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurisanje entiteta u izvoru podataka za postepeno osvežavanje.":::

1. Izaberite entitet i navedite sledeće detalje:

   - **Definišite primarni ključ**: Izaberite primarni ključ entiteta ili tabele.
   - **Definišite polje „poslednji put ažurirano“**: Ovo polje će prikazivati samo atribute tipa datuma ili vremena. Izaberite atribut koji pokazuje kada su zapisi poslednji put ažurirani. Koristiće se za identifikaciju zapisa koji spadaju u vremenski okvir za inkrementalno osvežavanje.
   - **Proveri da li postoje ispravke na svakih**: Navedite koliko dug vremenski okvir za postepeno osvežavanje želite da bude.

1. Izaberite **Sačuvaj** da biste dovršili kreiranje izvora podataka. Početno osvežavanje podataka biće potpuno osveženje. Nakon toga, inkrementalno osvežavanje podataka dešava se kao što je konfigurisano u prethodnom koraku.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
