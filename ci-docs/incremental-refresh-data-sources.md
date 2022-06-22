---
title: Postepeno osvežavanje za Power Query i Azure Data Lake izvore podataka
description: Osvežite nove i ažurirane podatke za velike izvore podataka zasnovane na Power Query ili Azure izvorima podataka u jezeru podataka.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: bff27bf7fec2bcb741846ae76bb1f616f459136c
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012042"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Postepeno osvežavanje za Power Query i Azure Data Lake izvore podataka

Ovaj članak govori o tome kako da konfigurišete postepeno osvežavanje za izvore podataka zasnovane na Power Query Azure Data Lake ili Azure Data Lake.

Inkrementalno osvežavanje izvora podataka pruža sledeće prednosti:

- **Brža osvežavanja** – Osvežavaju se samo podaci koji su promenjeni. Na primer, možete da osvežite samo proteklih pet dana skupa podataka iz prethodnog perioda.
- **Povećana pouzdanost** – Uz manje osvežavanja, ne morate dugo da održavate veze sa sistemima sa promenljivim izvorima, smanjujući rizik od problema sa povezivanjem.
- **Smanjena potrošnja resursa** – Osvežavanje samo podskupa ukupnih podataka dovodi do efikasnijeg korišćenja računarskih resursa i smanjenja uticaja na životnu sredinu.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Konfigurisanje postepenog osvežavanja za izvore podataka na osnovu Power Query

Uvidi klijenata omogućavaju postepeno osvežavanje izvora podataka uvezenih Power Query putem te podrške postepenog unošenja. Na primer, Azure SQL baze podataka sa poljima datuma i vremena, koja pokazuju kada su zapisi datuma poslednji put ažurirani.

1. [Kreirajte novi izvor podataka zasnovan na Power Query](connect-power-query.md).

1. Izaberite izvor podataka podržava postepeno osvežavanje, kao što je [Azure SQL baza podataka](/power-query/connectors/azuresqldatabase).

1. Izaberite entitete ili tabele za unos.

1. Dovršite korake transformacije i izaberite **Sledeće**.

1. U dijalogu **Podesite postepeno osvežavanje** izaberite **Podesi** da otvorite **Podešavanja postepenog osvežavanja**. Ako izaberete **Preskoči**, izvor podataka će osvežiti celokupni skup podataka.
   > [!TIP]
   > Kasnije možete primeniti i postepeno osvežavanje uređivanjem postojećeg izvora podataka.

1. U **podešavanjima postepenog osvežavanja**, konfigurisaćete postepeno osvežavanje za sve entitete koje ste izabrali prilikom kreiranja izvora podataka.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurišite postepene postavke osvežavanja.":::

1. Izaberite entitet i navedite sledeće detalje:

   - **Definišite primarni ključ**: Izaberite primarni ključ entiteta ili tabele.
   - **Definišite polje „poslednji put ažurirano“**: Ovo polje će prikazivati samo atribute tipa datuma ili vremena. Izaberite atribut koji pokazuje kada su zapisi poslednji put ažurirani. Koristiće se za identifikaciju zapisa koji spadaju u vremenski okvir za inkrementalno osvežavanje.
   - **Proveri da li postoje ispravke na svakih**: Navedite koliko dug vremenski okvir za postepeno osvežavanje želite da bude.

1. Izaberite **Sačuvaj** da biste dovršili kreiranje izvora podataka. Početno osvežavanje podataka biće potpuno osveženje. Nakon toga, inkrementalno osvežavanje podataka dešava se kao što je konfigurisano u prethodnom koraku.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Konfigurisanje postepenog osvežavanja za Azure Data Lake izvore podataka

Uvidi klijenata omogućavaju postepeno osvežavanje izvora podataka povezanih sa programom Azure Data Lake Storage. Da biste koristili postepeno unošenje i osvežavanje za entitet, konfigurišite taj entitet prilikom dodavanja Azure izvor podataka podataka ili kasnije prilikom uređivanja izvor podataka. Fascikla sa podacima entiteta mora da sadrži sledeće fascikle:

- **FullData: fascikla** sa datotekama sa podacima koje sadrže početne zapise
- **IncrementalData: Fascikla** sa fasciklama hijerarhije datuma/vremena **u yyyy/mm/dd/hh** formatu koja sadrži postepene ispravke. **hh** predstavlja UTC sat ispravki i sadrži fascikle **Upserts** and **Deletes**. **Upserts sadrži datoteke** sa podacima sa ispravkama postojećih zapisa ili novih zapisa. **Brisanja sadrže** datoteke sa podacima koje treba ukloniti.

1. Kada dodajete ili uređujete izvor podataka, dođite do **okna** atributa za entitet.

1. Redigujte atribute. Uverite se da je atribut kreiranog ili poslednje ažuriranog datuma podešen *sa formatom* **podataka dateTime** *i kalendarom.Datum* **semantičkog tipa.** Uredite atribut ako je potrebno i izaberite **Gotovo**.

1. U oknu **"Izbor entiteta** " uredite entitet. Potvrđen **je izbor u polju za potvrdu** Postepeno ingestion.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Konfigurisanje entiteta u izvoru podataka za postepeno osvežavanje.":::

   1. Potražite osnovnu fasciklu koja sadrži datoteke .csv ili .parketa za potpune podatke, postepene uvećavanje podataka i brisanje postepenih podataka.
   1. Unesite oznaku tipa datoteke za sve podatke i postepene datoteke (\. csv ili \. parket).
   1. Izaberite **Sačuvaj**.

1. Za **poslednji put ažurirano** izaberite atribut date timestamp.

1. Ako primarni **ključ nije** izabran, izaberite primarni ključ. Primarni ključ je atribut jedinstven za entitet. Da bi atribut bio važeći primarni ključ, ne bi trebalo da sadrži duplirane vrednosti, nedostajuće vrednosti ili prazne vrednosti. Atributi tipa niska, ceo broj i GUID tip podataka su podržani kao primarni ključevi.

1. Kliknite na **dugme** "Zatvori" da biste sačuvali i zatvorili okno.

1. Nastavite sa dodavanjem ili uređivanjem izvor podataka.

[!INCLUDE [footer-include](includes/footer-banner.md)]
