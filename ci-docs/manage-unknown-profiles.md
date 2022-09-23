---
title: Upravljanje nepoznatim profilima pomoću uvida klijenata
description: Radite sa nepoznatim profilima klijenata koji se kreiraju i upravljaju u programu Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: d7e5050ee5832df5ecf40a352f7ea8d42830fa45
ms.sourcegitcommit: f6b6a4c4ce9cf12e449488b24aab80a2cbfe0c47
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/21/2022
ms.locfileid: "9556413"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Upravljanje nepoznatim profilima pomoću uvida klijenata

Korisnici Interneta su često neidentifikovani i anonimni na mreži. Ako nisu prijavljeni zato što koriste različite uređaje ili kanale, to čak važi i za najlojalnije kupce. S tim što će kolačići nezavisnih proizvođača verovatno uskoro nestati, upravljanje željenim opcijama korisnika na osnovu podataka prvog proizvođača je od ključnog značaja za postizanje različitih personalizovanih iskustava. Za mnoge brendove, poznati ili autentifikacijski korisnici su manjina uprkos rastućim očekivanjima kupaca oko personalizacije. Sjajno je za preduzeća da znaju ko su njihovi klijenti, na osnovu pouzdanih, detaljnih i objedinjenih podataka.

Pamćenje personalizacije zavisi od bogatstva i potpunosti vaših podataka o korisnicima i Uvidi klijenata vam pomažu da ostvarite ove ciljeve. Ne morate da ograničavate ili zaustavljate korišćenje podataka prikupljenih na početku put koji pređe korisnik. Uvidi klijenata vam omogućava da donesete sopstvene podatke da biste kreirali korisnički profil za nepoznate korisnike. Zatim možete da koristite taj profil za dalje radnje, uprkos tome što nedostaju kontakt informacije. Uvezite podatke prve strane iz izvora kao što su Veb, mobilni ili CRM sistemi u uvide klijenata da biste neprekidno obogatili profile klijenata. Dok ujedinjujete više interakcija, pretvorite [nepoznatog *kupca* u poznatog *kupca*](unknown-to-known.md).

## <a name="sample-scenario"></a>Uzorak scenarija

E-trgovina je najbrže rastući kanal u poslednjoj deceniji. Pretpostavimo da korisnik koristi mobilni uređaj za pregledanje vaše lokacije za e-trgovinu. Veb lokacija dodeljuje posetiocu "mobile_guest123" kao jedinstveni identifikator i počinjete da prikupljate aktivnosti ponašanja na osnovu njihove aktivnosti na mreži. Na primer, koje stranice su posetili, koliko su vremena potrošili na te stranice ili na koje veze su kliknuli. Ne znate njihovo ime ili e-adresu, ali ti podaci mogu da pomognu brendovima da pruže smislen uvid u vezi sa ovim određenim korisnikom. Zauzvrat, te uvide možete da stavite na posao sledeći put kada korisnik poseti sajt. Query Customer Insights for "mobile_guest123" to retrieve the user's segment list, such as "organic", "mobile pre-order customers", "high-value customers" itd., or retrieve the profile to create personalized web experiences. Podatke možete da izvezete i u bilo koji sistem aktivacije da biste uradili isto.

## <a name="prerequisites"></a>Preduslovi

- Ingest first-party data into Customer Insights
- Svaki entitet ima jedinstveni ID koji je postavljen kao primarni ključ
- Svaki entitet sa primarnim ključem za personalizaciju je objedinjen
- Sistem za upravljanje sadržajem Vaše Web lokacije je sposoban da koristi API(za personalizaciju veba na osnovu direktne komunikacije sa Customer Insights)

Sledeća tabela prikazuje pojednostavljeni primer kako Web događaji visoke vrednosti mogu biti uhvaćeni.

|ID događaja|EventTimeStamp|ID korisnika|Primarni ključ|Ime događaja|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Prikaz proizvoda|
|2|09-18-2022 10:05:00|abc123|CookieID1|Prikaz proizvoda|
|3|09-18-2022 10:10:00|abc123|CookieID1|Dodaj u korpu|
|4|09-21-2022 09:05:00|abc123|CookieID1|Prikaz proizvoda|

## <a name="data-ingestion"></a>Unos podataka

Više informacija o dostupnim opcijama za unos podataka potražite u pregledu [izvora podataka](data-sources.md).

## <a name="data-unification"></a>Ujednačavanje podataka

Više informacija o ujedinjenju profila klijenata potražite u članku [Pregled ujedinjenja podataka](data-unification.md).

## <a name="get-insights"></a>Ostvarite uvide

[Obogatite](enrichment-hub.md) podatke, izgradite [mere i](measures.md) kreirajte [segmente za dalju](segments.md) aktivaciju.

Na primer, možete da kreirate segmente nepoznatih korisnika koji su pregledali iste stranice proizvoda, ali nikada nisu dovršili odjavu.

## <a name="activation"></a>Aktivacija

Sa vašim podacima u uvidima klijenata i vašim uvidima spremnim za posao, možete koristiti uvide klijenata za personalizaciju:

1. Koristite [OData API da biste preuzeli](apis.md) članstvo u segmentu ili profil kupca Za više primera pogledajte [primere upita OData za API-je korisničkih uvida](odata-examples.md).

1. [Izvezite](export-destinations.md) podatke u sisteme za aktivaciju.

Primer: Nepoznati korisnik posećuje Veb lokaciju više puta i posećuje stranice proizvoda za različite modele kožnih cipela. Sa tim podacima dostupnim u "Uvidima kupaca", nepoznatog korisnika možete uključiti u segment osoba koje su zainteresovane za kožne cipele. Koristite ovaj segment da biste obavestili vašu Web lokaciju o personalizaciji za povratak posetilaca. U sledećoj poseti sajt prepoznaje nepoznatog korisnika i mogao bi da im ponudi kupon od 10% na kožne cipele.

[!INCLUDE [footer-include](includes/footer-banner.md)]