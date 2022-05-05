---
title: Power BI konektor
description: Saznajte kako da koristite Dynamics 365 Customer Insights konektor u usluzi Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e901114703a43b4b4e751e0a93eb4876d7636c00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643636"
---
# <a name="connector-for-power-bi-preview"></a>Konektor za Power BI (pregled)

Napravite vizuelizacije za svoje podatke pomoću usluge Power BI Desktop. Generišite dodatne uvide i pravite izveštaje pomoću objedinjenih podataka o klijentima.

## <a name="prerequisites"></a>Preduslovi

- Imate objedinjene profile klijenata.
- Najnovija verzija aplikacije [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je instalirana na vašem računaru. [Saznajte više o Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurišite konektor za Power BI

1. U programu Power BI Desktop, izaberite **Datoteka** > **Preuzmi podatke**.

1. Izaberite **Prikaži još** i potražite **Dynamics 365 Customer Insights**

1. Izaberite **Poveži se**.

1. **Prijavite se** sa istim organizacionim nalogom koji koristite za Customer Insights i izaberite **Poveži se**.
   > [!NOTE]
   > Poslovni kontakt koji navedete u ovom koraku koristi se za preuzimanje podataka iz usluge Customer Insights i ne mora biti isti sa kojim ste prijavljeni na Power BI. Da biste resetovali nalog koji se koristi za preuzimanje podataka, otvorite Power BI i idite na **Datoteka** > **Opcije** > **Podešavanja** > **Podešavanja izvora podataka**. Na listi izvora podataka izaberite **Prijava na Dynamics 365 Customer Insights** i izaberite **Obriši dozvole**.  

1. U dijalogu **Navigator**. vidite listu svih okruženja kojima imate pristup. Proširite okruženje i otvorite bilo koju fasciklu (entiteti, mere, segmenti, obogaćivanja). Na primer, otvorite fasciklu **Entiteti** da vidite sve entitete koje možete da uvezete.

   ![Navigator Power BI konektora.](media/power-bi-navigator.png "Navigator Power BI konektora")

1. Označite polja za potvrdu pored entiteta koje treba da uključite i **Učitaj**. Možete da izaberete više entiteta, čak i iz više okruženja.

1. Videćete dijalog za učitavanje dok se entiteti učitavaju. Nakon što se učitaju svi izabrani entiteti, možete da koristite mogućnosti usluge Power BI za vizualizaciju podataka.

## <a name="large-data-sets"></a>Veliki skupovi podataka

Customer Insights konektor za Power BI je dizajniran da radi za skupove podataka koji sadrže do 1 milion korisničkih profila. Uvoz većih skupova podataka može da funkcioniše, ali to traje dugo. Pored toga, proces bi mogao naići na vremensko ograničenje zbog Power BI ograničenja. Za više informacija, pogledajte [Power BI: Preporuke za velike skupove podataka](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Rad sa podskupom podataka

Razmislite o radu sa podskupom podataka. Na primer, možete da kreirate[ segmente](segments.md) umesto da izveze sve evidencije klijenata u Power BI.

## <a name="troubleshooting"></a>Rešavanje problema

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights okruženje se ne prikazuje u usluzi Power BI

Okruženja koja imaju više od jedne relacije [definisane](relationships.md) između dva identična entiteta u uvidima klijenata neće biti dostupna u konektoru Power BI.

Možete identifikovati i ukloniti duplikate relacija.

1. Idite na **odnosi** > **podaci** o okruženju u kojem nedostajete Power BI.
2. Identifikujte duplikate relacija:
   - Proverite da li postoji više relacija definisanih između ista dva entiteta.
   - Proverite da li postoji relacija kreirana između dva entiteta koja su oba uključena u proces objedinjavanja. Definisana je implicitna relacija između svih entiteta uključenih u proces ujedinjenja.
3. Uklonite sve prepoznate duplikate relacija.

Kada uklonite duplikate relacija, pokušajte da ponovo konfigurišete Power BI konektor. Okruženje bi trebalo da bude dostupno već sada.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Greške u poljima datuma pri učitavanju entiteta u usluzi Power BI Desktop

Prilikom učitavanja entiteta koji sadrže polja sa formatom datuma poput MM/DD/GGGG, možete naići na greške zbog neusklađenih formata za lokalni standard. Do ovog nepodudaranja se dešava kada je Power BI Desktop datoteka postavljena na drugi lokalni standard od engleskog (SAD), jer se polja datuma u uvidima kupaca čuvaju u američkom formatu.

Power BI Desktop datoteka ima jedno podešavanje lokalnog standarda, koja se primenjuje pri preuzimanju podataka. Da biste ispravno protumačili ova polja datuma, postavite lokalni standard .BPI datoteke na engleski (Sjedinjene Države). [Saznajte kako da promenite lokalni standard Power BI Desktop datoteke](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE [footer-include](includes/footer-banner.md)]
