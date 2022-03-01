---
title: Power BI konektor
description: Saznajte kako da koristite Dynamics 365 Customer Insights konektor u usluzi Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406781"
---
# <a name="connector-for-power-bi-preview"></a>Konektor za Power BI (pregled)

Napravite vizuelizacije za svoje podatke pomoću usluge Power BI Desktop. Generišite dodatne uvide i pravite izveštaje pomoću objedinjenih podataka o klijentima.

## <a name="prerequisites"></a>Preduslovi

- Imate objedinjene profile klijenata.
- Najnovija verzija usluge [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je instalirana na vašem računaru. [Saznajte više o Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurišite konektor za Power BI

1. U programu Power BI Desktop, izaberite **Datoteka** > **Preuzmi podatke**.

1. Izaberite **Prikaži još** i potražite **Dynamics 365 Customer Insights**

1. Izaberite rezultat i izaberite **Poveži se**.

1. **Prijavite se** sa istim organizacionim nalogom koji koristite za Customer Insights i izaberite **Poveži se**.
   > [!NOTE]
   > Poslovni kontakt koji navedete u ovom koraku koristi se za preuzimanje podataka iz usluge Customer Insights i ne mora biti isti sa kojim ste prijavljeni na Power BI. Da biste resetovali nalog koji se koristi za preuzimanje podataka, otvorite Power BI i idite na **Datoteka** > **Opcije** > **Podešavanja** > **Podešavanja izvora podataka**. Na listi izvora podataka izaberite **Prijava na Dynamics 365 Customer Insights** i izaberite **Obriši dozvole**.  

1. U dijalogu **Navigator**. vidite listu svih okruženja kojima imate pristup. Proširite okruženje i otvorite bilo koju fasciklu (entiteti, mere, segmenti, obogaćivanja). Na primer, otvorite fasciklu **Entiteti** da vidite sve entitete koje možete da uvezete.

   ![Navigator Power BI konektora](media/power-bi-navigator.png "Navigator Power BI konektora")

1. Označite polja za potvrdu pored entiteta koje treba da uključite i **Učitaj**. Možete da izaberete više entiteta, čak i iz više okruženja.

1. Videćete dijalog za učitavanje dok se entiteti učitavaju. Nakon što se učitaju svi izabrani entiteti, možete da koristite mogućnosti usluge Power BI za vizualizaciju podataka.

## <a name="large-data-sets"></a>Veliki skupovi podataka

Customer Insights konektor za Power BI je dizajniran da radi za skupove podataka koji sadrže do 1 milion korisničkih profila. Uvoz većih skupova podataka može da funkcioniše, ali to traje dugo. Pored toga, proces bi mogao naići na vremensko ograničenje zbog Power BI ograničenja. Za više informacija, pogledajte [Power BI: Preporuke za velike skupove podataka](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Rad sa podskupom podataka

Razmislite o radu sa podskupom podataka. Na primer, možete da kreirate[ segmente](segments.md) umesto da izveze sve evidencije klijenata u Power BI.
