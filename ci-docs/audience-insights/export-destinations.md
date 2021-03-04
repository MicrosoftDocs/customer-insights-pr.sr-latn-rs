---
title: Odrdišta za izvoz
description: Izvezite podatke i upravljajte odredištima za izvoz.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 63caa2ebdd7d637d14ac9c9cc7972095803aee2f
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477150"
---
# <a name="export-destinations-preview-overview"></a>Pregled odredišta za izvoz (pregled)

Stranica **Odredišta za izvoz** prikazuje sve lokacije na koje ste postavili izvoz podataka. Takođe možete dodati nova odredišta za izvoz. Pored toga, prikazuje izvoz trenutno dostupnih opcija. Preuzmite brzi pregled, opis i saznajte šta možete uraditi sa svakom opcijom proširivosti. Izvezite objedinjene profile, mere i segmente u podržane aplikacije relevantne za vaše poslovanje.

Idite na **Administrator** > **Izvoz odredišta** da biste pronašli sledeće opcije proširenja:

- [Dynamics 365 programski dodatak za karticu klijenta](customer-card-add-in.md)
- [Facebook Ads Manager konektor](export-facebook.md)
- [Power Automate konektor](export-power-automate.md)
- [Power Apps konektor](export-power-apps.md)
- [Power BI konektor](export-power-bi.md)
- [Autopilot](export-autopilot.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Azure skladište blob objekta](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [SendGrid](export-sendgrid.md)
- [LiveRamp&reg; konektor](export-liveramp.md)
- [Robot za Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [Customer Insights API](apis.md)

## <a name="add-a-new-export-destination"></a>Dodavanje novog odredišta za izvoz

Da biste dodali odredišta za izvoz, imate [administratorske dozvole](permissions.md). Ako izvozite u Microsoft usluge, pretpostavljamo da su obe usluge u istoj organizaciji.

1. Idite na **Administrator** > **Odredišta za izvoz**.

1. Prebacite se na karticu **Moja odredišta za izvoz**.

1. Izaberite **Dodavanje odredišta** da biste kreirali novo odredište za izvoz.

1. U oknu **Dodavanje odredišta**, izaberite **Tip** odredišta za izvoz u padajućoj listi.

1. Navedite potrebne detalje i izaberite **Sledeće** da kreirate odredište za izvoz.

Takođe možete da izaberete **Podešavanje** na pločici na kartici **Otkrivanje**.

## <a name="view-export-destinations"></a>Prikaz odredišta za izvoz

Kada kreirate odredišta za izvoz, naći ćete ih u tabeli na kartici **Moja odredišta za izvoz**. Ova tabela ima tri kolone:

- **Ime za prikaz**: Ime koje ste uneli prilikom kreiranja odredišta.
- **Tip**: Vrsta odredišta za izvoz koju ste postavili prilikom kreiranja odredišta.
- **Kreirano**: Datum kad ste kreirali odredište.

## <a name="edit-an-export-destination"></a>Uređivanje odredišta za izvoz

1. Izaberite vertikalne tri tačke za odredište za izvoz koje želite da uređujete.

   > [!div class="mx-imgBorder"]
   > ![Vertikalne tri tačke](media/export-destinations-page-ellipsis.png "Vertikalne tri tačke")

1. Izaberite **Uređuj** iz padajućeg menija.

1. Promenite vrednosti za koje je potrebno ažuriranje i izaberite **Sačuvaj**.

## <a name="export-data-on-demand"></a>Izvoz podataka na zahtev

Nakon konfigurisanja konektora za odredište za izvoz, izvozi će se pokrenuti sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).

Da biste izvezli podatke bez čekanja na zakazano osvežavanje, idite na karticu **Moja odredišta za izvoz** u dijalogu **Administrator** > **Odredišta za izvoz**.

> [!div class="mx-imgBorder"]
> ![Vertikalne tri tačke](media/export-destinations-page-ellipsis.png "Vertikalne tri tačke")

- Izaberite **Izvezi** iznad liste da biste istovremeno pokrenuli izvoz u sva odredišta za izvoz.
- Izaberite tri tačke (...) nakon stavke liste, a zatim odaberite opciju **Izvezi** za pokretanje izvoza za jedno odredište za izvoz.

## <a name="remove-an-export-destination"></a>Uklanjanje odredište za izvoz

Da biste uklonili odredište za izvoz, počnite iz glavne stranice **Odredišta za izvoz**.

1. Odaberite vertikalne tri tačke za odredište za izvoz koje želite da uklonite.

   > [!div class="mx-imgBorder"]
   > ![Vertikalne tri tačke](media/export-destinations-page-ellipsis.png "Vertikalne tri tačke")

2. Izaberite **Ukloni** iz padajućeg menija.

3. Potvrdite uklanjanje odabirom **Ukloni** na ekranu za potvrdu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]