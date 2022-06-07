---
title: Zahtevi na osnovu prava subjekta podataka (DSR) u okviru GDPR | Microsoft Docs
description: Odgovorite na zahteve subjekta podataka za Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: af2583295627f98e980adbca4f216b9c34c3cad8
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808578"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Zahtevi na osnovu prava subjekta podataka (DSR) u okviru GDPR

Opšta uredba o zaštiti podataka Evropske unije (GDPR) na snazi je od 25. maja 2018. Ona daje značajna prava pojedincima u pogledu njihovih podataka. GDPR se odnosi na zaštitu i omogućavanje prava na privatnost pojedinaca. Možete pročitati više o posvećenosti kompanije Microsoft bezbednosti i usklađenosti u [Microsoft centru za pouzdanost](https://www.microsoft.com/trust-center).

Posvećeni smo pomaganju našim klijentima da ispune zahteve GDPR-a. Obuhvata pravo na brisanje i izvoz podataka koji uključuju lične informacije kao što su korisnički ID-ovi, brojevi telefona i adrese e-pošte. Administratori mogu da primene zahteve korisnika za brisanje ili izvoz ličnih podataka.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Odgovaranje na zahteve za brisanje GDPR subjekta podataka za Dynamics 365 Customer Insights

„Pravo na brisanje“ uklanjanjem ličnih podataka iz podataka o klijentima organizacije predstavlja ključnu zaštitu u Opštoj uredbi o zaštiti podataka (GDPR). Uklanjanje ličnih podataka uključuje uklanjanje svih ličnih podataka i sistemski generisanih evidencija, osim informacija iz evidencije nadgledanja.

#### <a name="manage-data-subject-delete-requests"></a>Upravljanje zahtevima za brisanje subjekta podataka

Customer Insights nudi sledeća iskustva u radu sa proizvodima za brisanje ličnih podataka za određenog klijenta ili korisnika:

- **Upravljajte zahtevima brisanje podataka o klijentu**: Podaci o klijentu u usluzi Customer Insights uneti su iz originalnih izvora podataka koji su spoljašnji za Customer Insights. Svi GDPR zahtevi za brisanje moraju se obaviti u originalnom izvoru podataka.
- **Upravljajte zahtevima za brisanje korisničkih podataka korisnika usluge Customer Insights**: Podatke za korisnike kreira Customer Insights. Svi GDPR zahtevi za brisanje moraju se obaviti u usluzi Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Upravljanje zahtevima za brisanje podataka o klijentima

Administrator usluge Customer Insights može da prati ove korake za uklanjanje podataka o klijentima koji su izbrisani u izvoru podataka:

1. Prijavite se u Dynamics 365 Customer Insights.
2. Idi na **izvore** > **podataka**
3. Za svaki izvor podataka na listi koji sadrži izbrisane podatke o klijentima:
   1. Izaberite vertikalnu elipsu () i izaberite stavku&vellip; Osveži **·**.
   2. Proverite status izvora podataka u odeljku **Status**. Znak potvrde znači da je osvežavanje bilo uspešno. Trokut upozorenja znači da nešto nije u redu. Ako se prikaže trougao upozorenja, kontaktirajte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Rukovanje GDPR zahtevima za brisanje podataka o klijentima.](media/gdpr-data-sources.png "Rukovanje GDPR zahtevima za brisanje podataka o klijentima")

##### <a name="manage-delete-requests-for-user-data"></a>Upravljanje zahtevima za brisanje podataka o korisnicima

Administrator usluge Customer Insights može da sledi sledeće korake za brisanje podataka o Customer Insights korisnicima:

1. Prijavite se u Dynamics 365 Customer Insights.
2. Idite na **bezbednosne** > **dozvole** > **administratora**.
3. Izaberite polje za potvrdu za korisnika kojeg želite da izbrišete.
4. Izaberite **Ukloni**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odgovaranje na GDPR zahteve za izvoz subjekta podataka

Kao deo naše posvećenosti partnerstvu sa Vama na vašem putu ka Opštoj uredbi o zaštiti podataka (GDPR), razvili smo dokumentaciju koja će vam pomoći da odgovorite na zahteve subjekata podataka.

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

Da biste uklonili podatke o pristanku o određenim korisnicima, uklonite ih u izvorima podataka koji su uneti u mogućnost upravljanja pristankom. Nakon osvežavanja izvor podataka, uklonjeni podaci će biti izbrisani i u Centru za saglasnost. Aplikacije koje koriste entitet saglasnosti će takođe izbrisati podatke koji su uklonjeni na izvoru nakon [osvežavanja](system.md#refresh-processes). Preporučujemo brzo osvežavanje izvora podataka nakon odgovora na zahtev subjekta podataka za uklanjanje podataka korisnika iz svih drugih procesa i aplikacija.

[!INCLUDE [footer-include](includes/footer-banner.md)]