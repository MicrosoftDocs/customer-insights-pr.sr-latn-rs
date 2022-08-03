---
title: Power BI konektor (pregled)
description: Saznajte kako da koristite Dynamics 365 Customer Insights konektor u usluzi Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196687"
---
# <a name="power-bi-connector-preview"></a>Power BI konektor (pregled)

Kreirajte vizuelizacije za podatke pomoću radne površine Microsoft Power BI. Generišite dodatne uvide i pravite izveštaje pomoću objedinjenih podataka o klijentima.

## <a name="prerequisites"></a>Preduslovi

- Objedinjeni profili klijenata.
- Najnovija verzija aplikacije [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je instalirana na vašem računaru. [Saznajte više o Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurišite konektor za Power BI

1. U programu Power BI Desktop, izaberite **Datoteka** > **Preuzmi podatke**.

1. Izaberite **Prikaži još** i potražite **Dynamics 365 Customer Insights**

1. Izaberite **Poveži se**.

1. **Prijavite se** sa istim organizacionim nalogom koji koristite za Customer Insights i izaberite **Poveži se**.
   > [!NOTE]
   > Poslovni kontakt koji navedete u ovom koraku koristi se za preuzimanje podataka iz usluge Customer Insights i ne mora biti isti sa kojim ste prijavljeni na Power BI. Da biste resetovali nalog koji se koristi za preuzimanje podataka, otvorite Power BI i idite na **Datoteka** > **Opcije** > **Podešavanja** > **Podešavanja izvora podataka**. Na listi izvora podataka izaberite **Prijava na Dynamics 365 Customer Insights** i izaberite **Obriši dozvole**.  

1. U dijalogu **"Navigator** " prikažite listu svih okruženja kojima imate pristup. Proširite okruženje i otvorite bilo koju fasciklu (entiteti, mere, segmenti, obogaćivanja). Na primer, otvorite fasciklu **Entiteti** da vidite sve entitete koje možete da uvezete.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Navigator Power BI konektora.":::

1. Označite polja za potvrdu pored entiteta koje treba da uključite i **Učitaj**. Možete da izaberete više entiteta, čak i iz više okruženja.

   Prikazaće se dijalog za učitavanje dok su entiteti učitani. Kada učitate sve izabrane entitete, koristite mogućnosti vizuelizacije Power BI podataka.

## <a name="large-data-sets"></a>Veliki skupovi podataka

Customer Insights konektor za Power BI je dizajniran da radi za skupove podataka koji sadrže do 1 milion korisničkih profila. Uvoz većih skupova podataka može da funkcioniše, ali dugo traje i može da potraje zbog Power BI ograničenja. Za više informacija, pogledajte [Power BI: Preporuke za velike skupove podataka](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Rad sa podskupom podataka

Razmislite o radu sa podskupom podataka. Na primer, kreirajte [segmente umesto](segments.md) da izvezete sve zapise kupaca u Power BI.

## <a name="troubleshooting"></a>Rešavanje problema

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights okruženje se ne prikazuje u usluzi Power BI

Okruženja koja imaju više od jedne relacije [definisane](relationships.md) između dva identična entiteta u uvidima klijenata neće biti dostupna u konektoru Power BI.

Identifikujte i uklonite duplirani odnosi.

1. Idite na **odnosi** > **podaci** o okruženju u kojem nedostajete Power BI.
1. Identifikujte duplikate relacija:
   - Proverite da li postoji više relacija definisanih između ista dva entiteta.
   - Proverite da li postoji relacija kreirana između dva entiteta koja su oba uključena u proces objedinjavanja. Definisana je implicitna relacija između svih entiteta uključenih u proces ujedinjenja.
1. Uklonite sve prepoznate duplikate relacija.

Kada uklonite duplikate relacija, pokušajte da ponovo konfigurišete Power BI konektor.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Greške u poljima datuma pri učitavanju entiteta u usluzi Power BI Desktop

Prilikom učitavanja entiteta koji sadrže polja sa formatom datuma kao što je MM/DD/YYYY, može doći do grešaka zbog nepodudarnih lokalnih formata. Do ovog nepodudaranja se dešava kada je Power BI Desktop datoteka postavljena na drugi lokalni standard od engleskog (SAD), jer se polja datuma u uvidima kupaca čuvaju u američkom formatu.

Power BI Desktop datoteka ima jedno podešavanje lokalnog standarda, koja se primenjuje pri preuzimanju podataka. Da biste otklonili greške datuma, [podesite lokalni standard . BPI datoteka na](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) engleski (Sjedinjene Države).

[!INCLUDE [footer-include](includes/footer-banner.md)]
