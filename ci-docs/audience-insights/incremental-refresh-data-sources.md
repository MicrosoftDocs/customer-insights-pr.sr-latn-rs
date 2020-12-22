---
title: Inkrementalno osvežavanje za izvore podataka zasnovane na usluzi Power Query
description: Osvežite nove i ažurirane podatke za velike izvore podataka na osnovu usluge Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406811"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Inkrementalno osvežavanje za izvore podataka zasnovane na usluzi Power Query

Inkrementalno osvežavanje izvora podataka pruža sledeće prednosti:

- **Brža osvežavanja** – Osvežavaju se samo podaci koji su promenjeni. Na primer, možete da osvežite samo proteklih pet dana skupa podataka iz prethodnog perioda.
- **Povećana pouzdanost** – Uz manje osvežavanja, ne morate dugo da održavate veze sa sistemima sa promenljivim izvorima, smanjujući rizik od problema sa povezivanjem.
- **Smanjena potrošnja resursa** – Osvežavanje samo podskupa ukupnih podataka dovodi do efikasnijeg korišćenja računarskih resursa i smanjenja uticaja na životnu sredinu.

## <a name="configure-incremental-refresh"></a>Konfigurisanje postepenog osvežavanja

Uvidi o korisnicima omogućavaju inkrementalno osvežavanje za izvore podataka uvezene preko usluge Power Query koja podržava inkrementalni unos. Na primer, Azure SQL baze podataka sa poljima datuma i vremena, koja pokazuju kada su zapisi datuma poslednji put ažurirani.

1. [Napravite novi izvor podataka na osnovu usluge Power Query](connect-power-query.md).

1. Navedite naziv za izvor podataka.

1. Izaberite izvor podataka koji podržava postepeno osvežavanje, kao što je Azure SQL baza podataka.

1. Izaberite entitete ili tabele za unos.

1. Dovršite korake transformacije i izaberite **Sledeće**.

1. U dijalogu **Podesite postepeno osvežavanje** izaberite **Podesi** da otvorite **Podešavanja postepenog osvežavanja**. Ako izaberete **Preskoči**, izvor podataka će osvežiti celokupni skup podataka.
   > [!TIP]
   > Kasnije možete primeniti i postepeno osvežavanje uređivanjem postojećeg izvora podataka.

1. U **podešavanjima postepenog osvežavanja**, konfigurisaćete postepeno osvežavanje za sve entitete koje ste izabrali prilikom kreiranja izvora podataka.

   > [!div class="mx-imgBorder"]
   > ![Konfigurisanje entiteta u izvoru podataka za postepeno osvežavanje](media/incremental-refresh-settings.png "Konfigurisanje entiteta u izvoru podataka za postepeno osvežavanje")

1. Izaberite entitet i navedite sledeće detalje:

   - **Definišite primarni ključ**: Izaberite primarni ključ entiteta ili tabele.
   - **Definišite polje „poslednji put ažurirano“**: Ovo polje će prikazivati samo atribute tipa datuma ili vremena. Izaberite atribut koji pokazuje kada su zapisi poslednji put ažurirani. Koristiće se za identifikaciju zapisa koji spadaju u vremenski okvir za inkrementalno osvežavanje.
   - **Proveri da li postoje ispravke na svakih**: Navedite koliko dug vremenski okvir za postepeno osvežavanje želite da bude.

1. Izaberite **Sačuvaj** da biste dovršili kreiranje izvora podataka. Početno osvežavanje podataka biće potpuno osveženje. Nakon toga, inkrementalno osvežavanje podataka dešava se kao što je konfigurisano u prethodnom koraku.
