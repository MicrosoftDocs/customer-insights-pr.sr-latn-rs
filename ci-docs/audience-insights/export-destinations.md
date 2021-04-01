---
title: Odrdišta za izvoz
description: Izvezite podatke i upravljajte odredištima za izvoz.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596103"
---
# <a name="export-destinations-preview-overview"></a>Pregled odredišta za izvoz (pregled)

Stranica **Odredišta za izvoz** prikazuje sve lokacije na koje ste postavili izvoz podataka. Takođe možete dodati nova odredišta za izvoz. Pored toga, prikazuje izvoz trenutno dostupnih opcija. Preuzmite brzi pregled, opis i saznajte šta možete uraditi sa svakom opcijom proširivosti. Izvezite objedinjene profile, mere i segmente u podržane aplikacije relevantne za vaše poslovanje.

Idite na **Administrator** > **Izvoz odredišta** da biste pronašli sledeće opcije proširenja:

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Adobe platforma iskustva](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [Autopilot](export-autopilot.md)
- [Azure skladište blob objekta](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [Robot za Microsoft Teams](export-teams-bot.md)
- [Customer Insights API](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service (programski dodatak za karticu klijenta)](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 čvorište za prodaju (programski dodatak za karticu klijenta)](customer-card-add-in.md)
- [Facebook menadžer oglasa](export-facebook.md)
- [Google oglasi](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [Mailchimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

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