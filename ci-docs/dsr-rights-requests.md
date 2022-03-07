---
title: Zahtevi na osnovu prava subjekta podataka (DSR) u okviru GDPR | Microsoft Docs
description: Odgovorite na zahteve subjekta podataka za Dynamics 365 Customer Insights mogućnost uvida o korisnicima.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350286"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Zahtevi na osnovu prava subjekta podataka (DSR) u okviru GDPR

Opšta uredba o zaštiti podataka Evropske unije (GDPR) na snazi je od 25. maja 2018. Ona daje značajna prava pojedincima u pogledu njihovih podataka. GDPR se odnosi na zaštitu i omogućavanje prava na privatnost pojedinaca. Možete pročitati više o posvećenosti kompanije Microsoft bezbednosti i usklađenosti u [Microsoft centru za pouzdanost](https://www.microsoft.com/trust-center).

Posvećeni smo pomaganju našim klijentima da ispune zahteve GDPR-a. Obuhvata pravo na brisanje i izvoz podataka koji uključuju lične informacije kao što su korisnički ID-ovi, brojevi telefona i adrese e-pošte. Administratori mogu da primene zahteve korisnika za brisanje ili izvoz ličnih podataka.

## <a name="audience-insights"></a>Uvidi u ciljnu grupu

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Odgovaranje na zahteve za brisanje GDPR subjekta podataka za Dynamics 365 Customer Insights mogućnost uvida o korisnicima

„Pravo na brisanje“ uklanjanjem ličnih podataka iz podataka o klijentima organizacije predstavlja ključnu zaštitu u Opštoj uredbi o zaštiti podataka (GDPR). Uklanjanje ličnih podataka uključuje uklanjanje svih ličnih podataka i sistemski generisanih evidencija, osim informacija iz evidencije nadgledanja.

#### <a name="manage-data-subject-delete-requests"></a>Upravljanje zahtevima za brisanje subjekta podataka

Uvidi o korisnicima nude sledeće iskustvo u vezi sa proizvodom za brisanje ličnih podataka određenog klijenta ili Customer Insights korisnika:

- **Upravljajte zahtevima brisanje podataka o klijentu**: Podaci o klijentu u usluzi Customer Insights uneti su iz originalnih izvora podataka koji su spoljašnji za Customer Insights. Svi GDPR zahtevi za brisanje moraju se obaviti u originalnom izvoru podataka.
- **Upravljajte zahtevima za brisanje korisničkih podataka korisnika usluge Customer Insights**: Podatke za korisnike kreira Customer Insights. Svi GDPR zahtevi za brisanje moraju se obaviti u usluzi Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Upravljanje zahtevima za brisanje podataka o klijentima

Administrator usluge Customer Insights može da prati ove korake za uklanjanje podataka o klijentima koji su izbrisani u izvoru podataka:

1. Prijavite se u Dynamics 365 Customer Insights.
2. U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**
3. Za svaki izvor podataka na listi koji sadrži izbrisane podatke o klijentima:
   1. Izaberite (...), pa izaberite **Osveži**.
   2. Proverite status izvora podataka u odeljku **Status**. Znak potvrde znači da je osvežavanje bilo uspešno. Trokut upozorenja znači da nešto nije u redu. Ako se prikaže trougao upozorenja, kontaktirajte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Rukovanje GDPR zahtevima za brisanje podataka o klijentima.](audience-insights/media/gdpr-data-sources.png "Rukovanje GDPR zahtevima za brisanje podataka o klijentima")

##### <a name="manage-delete-requests-for-user-data"></a>Upravljanje zahtevima za brisanje podataka o korisnicima

Administrator usluge Customer Insights može da sledi sledeće korake za brisanje podataka o Customer Insights korisnicima:

1. Prijavite se u Dynamics 365 Customer Insights.
2. U uvidima o korisnicima idite na **Administrator** > **Dozvole**.
3. Izaberite polje za potvrdu za korisnika kojeg želite da izbrišete.
4. Izaberite **Ukloni**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odgovaranje na GDPR zahteve za izvoz subjekta podataka

Kao deo naše posvećenosti da zajedno sa vama sarađujemo na vašem putu do Opšte uredbe o zaštiti podataka (GDPR), razvili smo dokumentaciju koja će vam pomoći da se pripremite. Ova dokumentacija opisuje korake koje danas možete preduzeti da biste podržali poštovanje GDPR-a kada koristite uvide o korisnicima.

#### <a name="manage-export-and-view-requests"></a>Upravljanje izvozom i prikaz zahteva

Pravo prenosivosti podataka omogućava subjektima podataka da zatraže kopiju svojih ličnih podataka u elektronskom formatu (definisanom kao "strukturirani, uobičajeno upotrebljiv, mašinski čitljiv i interoperabilni format") koji se može preneti na drugog kontrolora podataka.

##### <a name="export-customer-data-tenant-admin"></a>Izvoz podataka o klijentu (administrator zakupca)

Administrator zakupca može da prati ove korake za izvoz podataka:

1. Pošaljite e-poruku na D365CI@microsoft.com navodeći adresu e-pošte klijenta u zahtevu. Customer Insights tim će poslati e-poruku na registrovanu adresu e-pošte administratora registrovanog zakupca, tražeći potvrdu za izvoz podataka.
2. Potvrdite potvrdu za izvoz podataka za traženog klijenta.
3. Primite izvezene podatke putem e-adrese administratora zakupca.

##### <a name="export-user-data-tenant-admin"></a>Izvoz podataka o korisniku (administrator zakupca)

1. Pošaljite e-poruku na D365CI@microsoft.com navodeći adresu e-pošte korisnika u zahtevu. Customer Insights tim će poslati e-poruku na registrovanu adresu e-pošte administratora registrovanog zakupca, tražeći potvrdu za izvoz podataka.
2. Prihvatite potvrdu za izvoz podataka za traženog korisnika.
3. Primite izvezene podatke putem e-adrese administratora zakupca.

## <a name="consent-management-preview"></a>Upravljanje saglasnostima (pregled)

Mogućnost upravljanja pristankom ne prikuplja direktno korisničke podatke. On uvozi i obrađuje samo podatke o saglasnosti koje korisnici obezbeđuju u drugim aplikacijama.

Da biste uklonili podatke o pristanku o određenim korisnicima, uklonite ih u izvorima podataka koji su uneti u mogućnost upravljanja pristankom. Nakon osvežavanja izvor podataka, uklonjeni podaci će biti izbrisani i u Centru za saglasnost. Aplikacije koje koriste entitet saglasnosti će takođe izbrisati podatke koji su uklonjeni na izvoru nakon [osvežavanja](audience-insights/system.md#refresh-processes). Preporučujemo brzo osvežavanje izvora podataka nakon odgovora na zahtev subjekta podataka za uklanjanje podataka korisnika iz svih drugih procesa i aplikacija.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]