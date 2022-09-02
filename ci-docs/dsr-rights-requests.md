---
title: Zahtevi na osnovu prava subjekta podataka (DSR) u okviru GDPR | Microsoft Docs
description: Odgovorite na zahteve subjekta podataka za Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387128"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Zahtevi na osnovu prava subjekta podataka (DSR) u okviru GDPR

Opšta uredba o zaštiti podataka Evropske unije (GDPR) na snazi je od 25. maja 2018. Ona daje značajna prava pojedincima u pogledu njihovih podataka. GDPR se odnosi na zaštitu i omogućavanje prava na privatnost pojedinaca. Više o posvećenosti korporacije Microsoft bezbednosti i usaglašenosti pročitajte u [Microsoft centru za pouzdanost](https://www.microsoft.com/trust-center).

Posvećeni smo pomaganju našim klijentima da ispune zahteve GDPR-a. On uključuje pravo brisanja ili izvoza podataka koji uključuju lične informacije kao što su korisnički ID-ovi, brojevi telefona i e-adrese. Administratori mogu da primene zahteve korisnika za brisanje ili izvoz ličnih podataka.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Odgovaranje na GDPR podatke tema brisanja zahteva za uvid u kupce

„Pravo na brisanje“ uklanjanjem ličnih podataka iz podataka o klijentima organizacije predstavlja ključnu zaštitu u Opštoj uredbi o zaštiti podataka (GDPR). Uklanjanje ličnih podataka uključuje uklanjanje svih ličnih podataka i sistemski generisanih evidencija, osim informacija iz evidencije nadgledanja.

### <a name="manage-data-subject-delete-requests"></a>Upravljanje zahtevima za brisanje subjekta podataka

Customer Insights nudi sledeća iskustva u radu sa proizvodima za brisanje ličnih podataka za određenog klijenta ili korisnika:

- **Upravljajte zahtevima brisanje podataka o klijentu**: Podaci o klijentu u usluzi Customer Insights uneti su iz originalnih izvora podataka koji su spoljašnji za Customer Insights. Prvo izvršite GDPR brisanje zahteva u originalnom izvor podataka nalogu.
- **Upravljajte zahtevima za brisanje korisničkih podataka korisnika usluge Customer Insights**: Podatke za korisnike kreira Customer Insights. Izvršite sve GDPR zahteve za brisanje u uvidima kupaca.

#### <a name="manage-requests-to-delete-customer-data"></a>Upravljanje zahtevima za brisanje podataka o klijentima

Kao administrator uvida klijenta, uklonite podatke o klijentima "Uvidi kupaca" koji su izbrisani u izvor podataka. Proverite da li su GDPR zahtevi za brisanje izvršeni u originalnom izvor podataka.

1. Prijavite se u Dynamics 365 Customer Insights.

1. Idite na **Podaci** > **Izvori podataka**.

1. Za svaki izvor podataka na listi koji sadrži izbrisane podatke o klijentima:
   1. Izaberite stavku izvor podataka a zatim izaberite stavku **Osveži**.
   1. Proverite status izvora podataka u odeljku **Status**. Znak potvrde znači da je osvežavanje bilo uspešno. Trokut upozorenja znači da nešto nije u redu. Ako se prikaže trougao upozorenja, kontaktirajte D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Rukovanje GDPR zahtevima za brisanje podataka o klijentima.":::

1. Nakon uspešnog osvežavanja izvora podataka, pokrenite i nizvodno osvežavanje. Naročito ako nemate planirano potpuno osvežavanje uvida kupaca u ponavljanje.

   > [!IMPORTANT]
   > Statički segmenti nisu uključeni u potpuno osvežavanje ili pokretanje nizvodno osvežavanje nakon zahteva za brisanje. Da biste se uverili da su i podaci klijenata uklonjeni iz statičnih segmenata, ponovo kreirajte statične segmente sa osveženim izvornim podacima.

#### <a name="manage-delete-requests-for-user-data"></a>Upravljanje zahtevima za brisanje podataka o korisnicima

Kao administrator korisničkih uvida, izbrišite korisničke podatke korisničkih uvida korisnika.

1. Prijavite se u Dynamics 365 Customer Insights.

1. Idite na **lokaciju** > **administratorske** > i izaberite karticu **"Korisnici**".

1. Potvrdite izbor u polju za potvrdu za korisnike koje želite da izbrišete.

1. Izaberite **Ukloni**.

1. Potvrdite brisanje.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Odgovaranje na GDPR zahteve za izvoz subjekta podataka

Pravo prenosivosti podataka omogućava subjektima podataka da zatraže kopiju svojih ličnih podataka u elektronskom formatu (definisanom kao "strukturirani, uobičajeno upotrebljiv, mašinski čitljiv i interoperabilni format") koji se može preneti na drugog kontrolora podataka.

### <a name="manage-export-and-view-requests"></a>Upravljanje izvozom i prikaz zahteva

Upravljajte zahtevima za izvoz podataka kupaca ili korisnika.

#### <a name="export-customer-data-tenant-admin"></a>Izvoz podataka o klijentu (administrator zakupca)

Kao administrator zakupca, izvezite podatke o kupcima.

1. Pošaljite e-poruku na D365CI@microsoft.com navodeći adresu e-pošte klijenta u zahtevu. Customer Insights tim će poslati e-poruku na registrovanu adresu e-pošte administratora registrovanog zakupca, tražeći potvrdu za izvoz podataka.
2. Potvrdite potvrdu za izvoz podataka za traženog klijenta.
3. Primite izvezene podatke putem e-adrese administratora zakupca.

#### <a name="export-user-data-tenant-admin"></a>Izvoz podataka o korisniku (administrator zakupca)

Kao administrator zakupca, izvezite korisničke podatke.

1. Pošaljite e-poruku na D365CI@microsoft.com navodeći adresu e-pošte korisnika u zahtevu. Tim "Uvidi kupaca" šalje e-poruku na adresu administratora registrovanog zakupca, tražeći potvrdu za izvoz podataka.
1. Prihvatite potvrdu za izvoz podataka za traženog korisnika.
1. Primite izvezene podatke putem e-adrese administratora zakupca.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Rukovanje brisanjem podataka u Dynamics 365 Customer Insights

Podaci se brišu (particije podataka i snimci podataka) ako su particije sa podacima i snimci podataka neaktivni duže od 30 dana, što znači da su zamenjeni novom particijom podataka i snimkom kroz osvežavanje izvora podataka.

Ne brišu se svi podaci i snimci. Najnovija particija sa podacima i snimak podataka su aktivni zato što se koriste u programu "Uvid korisnika". Za najnovije podatke nije važno da li izvori podataka nisu osveženi u poslednjih 30 dana.

[!INCLUDE [footer-include](includes/footer-banner.md)]
