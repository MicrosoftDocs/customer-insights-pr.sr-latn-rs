---
title: Zahtevi na osnovu prava subjekta podataka (DSR) u okviru GDPR | Microsoft Docs
description: Odgovorite na zahteve subjekta podataka za Dynamics 365 Customer Insights mogućnost uvida o korisnicima.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e832fbbdfb59cb06d98715223edca438d2c3a7f2
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554364"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Zahtevi na osnovu prava subjekta podataka (DSR) u okviru GDPR

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Odgovaranje na zahteve za brisanje GDPR subjekta podataka za Dynamics 365 Customer Insights mogućnost uvida o korisnicima

„Pravo na brisanje“ uklanjanjem ličnih podataka iz podataka o klijentima organizacije predstavlja ključnu zaštitu u Opštoj uredbi o zaštiti podataka (GDPR). Uklanjanje ličnih podataka uključuje uklanjanje svih ličnih podataka i sistemski generisanih evidencija, osim informacija iz evidencije nadgledanja.

### <a name="manage-data-subject-delete-requests"></a>Upravljanje zahtevima za brisanje subjekta podataka

Uvidi o korisnicima nude sledeće iskustvo u vezi sa proizvodom za brisanje ličnih podataka određenog klijenta ili Customer Insights korisnika:

- **Upravljajte zahtevima brisanje podataka o klijentu**: Podaci o klijentu u usluzi Customer Insights uneti su iz originalnih izvora podataka koji su spoljašnji za Customer Insights. Svi GDPR zahtevi za brisanje moraju se obaviti u originalnom izvoru podataka.
- **Upravljajte zahtevima za brisanje korisničkih podataka korisnika usluge Customer Insights**: Podatke za korisnike kreira Customer Insights. Svi GDPR zahtevi za brisanje moraju se obaviti u usluzi Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Upravljanje zahtevima za brisanje podataka o klijentima

Administrator usluge Customer Insights može da prati ove korake za uklanjanje podataka o klijentima koji su izbrisani u izvoru podataka:

1. Prijavite se u Dynamics 365 Customer Insights.
2. U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**
3. Za svaki izvor podataka na listi koji sadrži izbrisane podatke o klijentima:
   1. Izaberite (...), pa izaberite **Osveži**.
   2. Proverite status izvora podataka u odeljku **Status**. Znak potvrde znači da je osvežavanje bilo uspešno. Trokut upozorenja znači da nešto nije u redu. Ako se prikaže trougao upozorenja, kontaktirajte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Rukovanje GDPR zahtevima za brisanje podataka o klijentima.](media/gdpr-data-sources.png "Rukovanje GDPR zahtevima za brisanje podataka o klijentima")

#### <a name="manage-delete-requests-for-user-data"></a>Upravljanje zahtevima za brisanje podataka o korisnicima

Administrator usluge Customer Insights može da sledi sledeće korake za brisanje podataka o Customer Insights korisnicima:

1. Prijavite se u Dynamics 365 Customer Insights.
2. U uvidima o korisnicima idite na **Administrator** > **Dozvole**.
3. Izaberite polje za potvrdu za korisnika kojeg želite da izbrišete.
4. Izaberite **Ukloni**.

> [!div class="mx-imgBorder"]
> ![Upravljanje GDPR zahtevima za brisanje podataka o korisnicima.](media/gdpr-permissions.png "Upravljanje GDPR zahtevima za brisanje podataka o korisnicima")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Odgovaranje na GDPR zahteve za izvoz subjekta podataka

Kao deo naše posvećenosti da zajedno sa vama sarađujemo na vašem putu do Opšte uredbe o zaštiti podataka (GDPR), razvili smo dokumentaciju koja će vam pomoći da se pripremite. Ova dokumentacija opisuje korake koje danas možete preduzeti da biste podržali poštovanje GDPR-a kada koristite uvide o korisnicima.

### <a name="manage-export-and-view-requests"></a>Upravljanje izvozom i prikaz zahteva

Pravo prenosivosti podataka omogućava subjektima podataka da zatraže kopiju svojih ličnih podataka u elektronskom formatu (definisanom kao "strukturirani, uobičajeno upotrebljiv, mašinski čitljiv i interoperabilni format") koji se može preneti na drugog kontrolora podataka.

#### <a name="export-customer-data-tenant-admin"></a>Izvoz podataka o klijentu (administrator zakupca)

Administrator zakupca može da prati ove korake za izvoz podataka:

1. Pošaljite e-poruku na D365CI@microsoft.com navodeći adresu e-pošte klijenta u zahtevu. Customer Insights tim će poslati e-poruku na registrovanu adresu e-pošte administratora registrovanog zakupca, tražeći potvrdu za izvoz podataka.
2. Potvrdite potvrdu za izvoz podataka za traženog klijenta.
3. Primite izvezene podatke putem e-adrese administratora zakupca.

#### <a name="export-user-data-tenant-admin"></a>Izvoz podataka o korisniku (administrator zakupca)

1. Pošaljite e-poruku na D365CI@microsoft.com navodeći adresu e-pošte korisnika u zahtevu. Customer Insights tim će poslati e-poruku na registrovanu adresu e-pošte administratora registrovanog zakupca, tražeći potvrdu za izvoz podataka.
2. Prihvatite potvrdu za izvoz podataka za traženog korisnika.
3. Primite izvezene podatke putem e-adrese administratora zakupca.


[!INCLUDE[footer-include](../includes/footer-banner.md)]