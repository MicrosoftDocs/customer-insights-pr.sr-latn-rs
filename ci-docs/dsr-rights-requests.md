---
title: Zahtevi na osnovu prava subjekta podataka (DSR) u okviru GDPR | Microsoft Docs
description: Odgovorite na zahteve teme podataka za Dynamics 365 Customer Insights korisnici uvida.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732697"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Zahtevi na osnovu prava subjekta podataka (DSR) u okviru GDPR

Opšta uredba o zaštiti podataka Evropske unije (GDPR) na snazi je od 25. maja 2018. Ona daje značajna prava pojedincima u pogledu njihovih podataka. GDPR se odnosi na zaštitu i omogućavanje prava na privatnost pojedinaca. Možete pročitati više o posvećenosti kompanije Microsoft bezbednosti i usklađenosti u [Microsoft centru za pouzdanost](https://www.microsoft.com/trust-center).

Posvećeni smo pomaganju našim klijentima da ispune zahteve GDPR-a. Obuhvata pravo na brisanje i izvoz podataka koji uključuju lične informacije kao što su korisnički ID-ovi, brojevi telefona i adrese e-pošte. Administratori mogu da primene zahteve korisnika za brisanje ili izvoz ličnih podataka.

## <a name="audience-insights"></a>Uvidi u ciljnu grupu

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Odgovaranje na GDPR podatke subjekat brise zahteve za Dynamics 365 Customer Insights korisnici uvida

„Pravo na brisanje“ uklanjanjem ličnih podataka iz podataka o klijentima organizacije predstavlja ključnu zaštitu u Opštoj uredbi o zaštiti podataka (GDPR). Uklanjanje ličnih podataka uključuje uklanjanje svih ličnih podataka i sistemski generisanih evidencija, osim informacija iz evidencije nadgledanja.

#### <a name="manage-data-subject-delete-requests"></a>Upravljanje zahtevima za brisanje subjekta podataka

Uvidi o korisnicima nude sledeće iskustvo u vezi sa proizvodom za brisanje ličnih podataka određenog klijenta ili Customer Insights korisnika:

- **Upravljajte zahtevima brisanje podataka o klijentu**: Podaci o klijentu u usluzi Customer Insights uneti su iz originalnih izvora podataka koji su spoljašnji za Customer Insights. Svi GDPR zahtevi za brisanje moraju se obaviti u originalnom izvoru podataka.
- **Upravljajte zahtevima za brisanje korisničkih podataka korisnika usluge Customer Insights**: Podatke za korisnike kreira Customer Insights. Svi GDPR zahtevi za brisanje moraju se obaviti u usluzi Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Upravljanje zahtevima za brisanje podataka o klijentima

Administrator usluge Customer Insights može da prati ove korake za uklanjanje podataka o klijentima koji su izbrisani u izvoru podataka:

1. Prijavljivanje u Dynamics 365 Customer Insights.
2. U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**
3. Za svaki izvor podataka na listi koji sadrži izbrisane podatke o klijentima:
   1. Izaberite (...), pa izaberite **Osveži**.
   2. Proverite status izvora podataka u odeljku **Status**. Znak potvrde znači da je osvežavanje bilo uspešno. Trokut upozorenja znači da nešto nije u redu. Ako se prikaže trougao upozorenja, kontaktirajte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Rukovanje GDPR zahtevima za brisanje podataka o klijentima.](audience-insights/media/gdpr-data-sources.png "Rukovanje GDPR zahtevima za brisanje podataka o klijentima")

##### <a name="manage-delete-requests-for-user-data"></a>Upravljanje zahtevima za brisanje podataka o korisnicima

Administrator usluge Customer Insights može da sledi sledeće korake za brisanje podataka o Customer Insights korisnicima:

1. Prijavljivanje u Dynamics 365 Customer Insights.
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

Da biste uklonili podatke o pristanku o određenim korisnicima, uklonite ih u izvorima podataka koji su uneti u mogućnost upravljanja pristankom. Nakon osvežavanja izvor podataka, uklonjeni podaci će takođe biti izbrisani u Centru za saglasnost. Aplikacije koje koriste entitet saglasnosti će takođe izbrisati podatke koji su uklonjeni na izvoru nakon [osvežavanja](audience-insights/system.md#refresh-processes). Preporučujemo brzo osvežavanje izvora podataka nakon odgovora na zahtev subjekta podataka za uklanjanje podataka korisnika iz svih drugih procesa i aplikacija.


## <a name="engagement-insights-preview"></a>Uvidi u angažovanje (verzija za pregled)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Brisanje i izvoz podataka o događajima koji sadrže informacije koje mogu identifikovati krajnjeg korisnika

Sledeći odeljci opisuju kako brisati i izvoziti podatke o događajima koji mogu sadržati lične podatke.

Da biste brisali ili izvezli podatke:

1. Označite svojstva događaja koja sadrže podatke sa ličnim informacijama.
2. Izbrišite ili izvezite podatke povezane sa određenim vrednostima (na primer: navedeni ID korisnika).

#### <a name="tag-and-update-event-properties"></a>Označavanje i ažuriranje svojstava događaja

Lični podaci su označeni na nivou svojstva događaja. Prvo označite svojstva koja se razmatraju za brisanje ili izvoz.

Da biste označili svojstvo događaja da sadrži lične informacije, sledite ove korake:

1. Otvorite radni prostor koji sadrži događaj.

1. Idite na **Podaci** > **Događaji** da biste videli listu događaja u izabranom radnom prostoru.
  
1. Izaberite događaj koji želite da označite.

1. Izaberite **Uredi svojstva** da biste otvorili okno sa spiskom svih svojstava izabranog događaja.
     
1. Izaberite **...**, a zatim izaberite **Uredi** da biste došli do dijaloga **Ažuriranje svojstva**.

   ![Uredite događaj.](engagement-insights/media/edit-event.png "Uredite događaj")

1. U prozoru **Ažuriranje svojstva**, odaberite **...** u gornjem desnom uglu, a zatim odaberite polje **Sadrži EUII**. Odaberite **Ažuriraj** da biste sačuvali promene.

   ![Sačuvajte promene.](engagement-insights/media/update-property.png "Sačuvajte promene")

   > [!NOTE]
   > Svaki put kada se šema događaja promeni ili kreirate novi događaj, preporučujemo da procenite pridružena svojstva događaja i po potrebi ih označite ili poništite oznaku da sadrže lične podatke.

#### <a name="delete-or-export-tagged-event-data"></a>Brisanje ili izvoz označenih podataka o događajima

Ako su sva svojstva događaja označena na odgovarajući način kako je opisano u prethodnom koraku, administrator okruženja može izdati zahtev za brisanje označenih podataka o događaju.

Za upravljanje zahtevima za brisanje ili izvoz EUII

1. Idite na stavku **Administrator** > **Okruženje** > **Podešavanja**.

1. U odeljku **Upravljanje informacijama koje mogu identifikovati krajnjeg korisnika (EUII)**, izaberite **Upravljanje EUII**.

##### <a name="deletion"></a>Brisanje

Da biste ih izbrisali, možete uneti listu korisničkih ID-ova razdvojenih zarezom u odeljku **Brisanje podataka koji mogu identifikovati krajnjeg korisnika (EUII)**. Ovi ID-ovi će se zatim upoređivati sa svim označenim svojstvima događaja svih projekata u trenutnom okruženju putem tačnog podudaranja niski. 

Ako se vrednost svojstva podudara sa jednim od navedenih ID-ova, povezani događaj biće trajno izbrisan. Zbog nepovratnosti ove radnje, morate da potvrdite brisanje nakon što izaberete **Izbriši**.

##### <a name="export"></a>Export

Proces izvoza identičan je procesu brisanja kada je u pitanju definisanje vrednosti svojstava događaja u odeljku **Izvoz podataka koji mogu identifikovati krajnjeg korisnika (EUII)**. Osim toga, moraćete da navedete **URL adresu skladišta Azure blob objekta** da biste naveli odredište za izvoz. URL adresa Azure blob objekta mora da sadrži [Potpis deljenog pristupa (SAS)](/azure/storage/common/storage-sas-overview).

Nakon što izaberete **Izvoz**, svi događaji trenutnog tima koji sadrže odgovarajuća označena svojstva biće izvezeni u CSV formatu u odredište za izvoz.

### <a name="good-practices"></a>Dobre prakse

* Pokušajte da izbegnete slanje događaja koji sadrže lične podatke.
* Ako je potrebno da pošaljete događaje koji sadrže EUII podatke, ograničite broj događaja i svojstava događaja koji sadrže EUII podatke. U idealnom slučaju, ograničite se na jedan takav događaj.
* Uverite se da što manje ljudi ima pristup poslatim ličnim podacima.
* Za događaje koji sadrže lične podatke, uverite se da ste postavili jedno svojstvo da emituje jedinstveni identifikator koji se lako može povezati sa određenim korisnikom (na primer, ID korisnika). Ovo olakšava razdvajanje podataka i izvoz ili brisanje pravih podataka.
* Označite samo jedno svojstvo po događaju da sadrži lične podatke. Idealno onaj koji sadrži samo jedinstveni identifikator.
* Nemojte označavati svojstva koja sadrže detaljne vrednosti (na primer, celo telo zahteva). Mogućnost uvida u angažovanje koristi tačno podudaranje niski kada odlučuje koje događaje će izbrisati ili izvesti.

[!INCLUDE[footer-include](includes/footer-banner.md)]