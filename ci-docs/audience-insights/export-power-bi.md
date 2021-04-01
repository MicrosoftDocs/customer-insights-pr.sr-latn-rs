---
title: Power BI konektor
description: Saznajte kako da koristite Dynamics 365 Customer Insights konektor u usluzi Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596056"
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

   ![Navigator Power BI konektora](media/power-bi-navigator.png "Navigator Power BI konektora")

1. Označite polja za potvrdu pored entiteta koje treba da uključite i **Učitaj**. Možete da izaberete više entiteta, čak i iz više okruženja.

1. Videćete dijalog za učitavanje dok se entiteti učitavaju. Nakon što se učitaju svi izabrani entiteti, možete da koristite mogućnosti usluge Power BI za vizualizaciju podataka.

## <a name="large-data-sets"></a>Veliki skupovi podataka

Customer Insights konektor za Power BI je dizajniran da radi za skupove podataka koji sadrže do 1 milion korisničkih profila. Uvoz većih skupova podataka može da funkcioniše, ali to traje dugo. Pored toga, proces bi mogao naići na vremensko ograničenje zbog Power BI ograničenja. Za više informacija, pogledajte [Power BI: Preporuke za velike skupove podataka](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Rad sa podskupom podataka

Razmislite o radu sa podskupom podataka. Na primer, možete da kreirate[ segmente](segments.md) umesto da izveze sve evidencije klijenata u Power BI.

## <a name="troubleshooting"></a>Rešavanje problema

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights okruženje se ne prikazuje u usluzi Power BI

Okruženja koja imaju više od jedne [relacije](relationships.md) definisane između dva identična entiteta u uvidima o korisnicima neće biti dostupna u Power BI konektoru.

Možete identifikovati i ukloniti duplikate relacija.

1. U uvidima o korisnicima, idite na **Podaci** > **Relacije** na okruženje koje vam nedostaje u usluzi Power BI.
2. Identifikujte duplikate relacija:
   - Proverite da li postoji više relacija definisanih između ista dva entiteta.
   - Proverite da li postoji relacija kreirana između dva entiteta koja su oba uključena u proces objedinjavanja. Definisana je implicitna relacija između svih entiteta uključenih u proces ujedinjenja.
3. Uklonite sve prepoznate duplikate relacija.

Kada uklonite duplikate relacija, pokušajte da ponovo konfigurišete Power BI konektor. Okruženje bi trebalo da bude dostupno već sada.

[!INCLUDE[footer-include](../includes/footer-banner.md)]