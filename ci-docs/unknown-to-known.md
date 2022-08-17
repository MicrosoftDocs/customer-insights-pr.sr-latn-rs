---
title: Personalizovanje iskustava sa podacima o poznatim i nepoznatim korisnicima
description: Uključite informacije o nekada nepoznatim korisnicima kada znate njihov identitet.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224312"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Personalizovanje iskustava sa podacima o poznatim i nepoznatim korisnicima

Upravljanje podacima o korisnicima nije novi izazov, ali postaje sve teži kako se korisnici kreću kroz različite digitalne kanale koje brendovi nude. Korisnik koji je poznat (potvrđena verodostojnost) u jednom kanalu postaje nepoznat (neautorizovan) u drugom ako nije prijavljen. Problem je često u tome što neautorizovani (nepoznati) korisnici nemaju uobičajeni ID. Može se koristiti za povezivanje smislenih atributa profila i generisanje objedinjenih profila klijenata. Uvidi klijenata pomažu u rešavanju ovog problema tako što unose podatke iz metoda praćenja na izvornim sistemima. Konsolidovanje nepoznatih i poznatih profila obezbeđuje organizacijama kompletan prikaz akušerskih profila i njihovih istorijskih transakcija, ponašanja i demografije. Ona čak ide i korak dalje obezbeđivanjem rešenja identiteta koje vam omogućava da ujedinite aktivnost klijenata preko više kanala, uključujući Veb lokaciju, kupovinu u prodavnici, programe lojalnosti itd.

## <a name="sample-scenario"></a>Primer scenarija

Razmislimo o lancu kafe, koji ima široku bazu kupaca koji kupuje kafu i hranu u prodavnicama i naručuje proizvode preko interneta. Često se posetiocima na mreži ne daje verodostojnost prilikom pregledanja proizvoda, što ih čini "nepoznatim korisnicima". Lancu kafe je teško da dostavi personalizovane ponude i iskustva ako su korisnici nepoznati. Sa druge strane, kupci mogu da se prijave na svoj nalog i postanu "poznati korisnici" kompaniji tako što će se pridružiti sistemu lojalnosti, što zauzvrat omogućava personalizovanija iskustva. Customer Insights može pomoći lancu kafe da dobije uvid u poznate i ranije nepoznate korisnike.

Sa uvidom klijenta, preduzeće može da kombinuje profile klijenata sa podacima o aktivnostima iz neautorizovanih (nepoznatih) sesija nakon što se korisnik ukaћe i postane poznat. Lanac kafe može da donese podatke iz drugih izvora podataka koristeći ugrađene konektore u korisničke uvide kako bi objedinio identitete za kupce sa različitih kanala.

## <a name="prerequisites"></a>Preduslovi

- Web podaci se prikupljaju i sadrže "ID-ove posetilaca" za sve posetioce.
- Web podaci sadrže "identitetizovane korisničke ID-ove" za prijavljene posetioce. Ove ID-ove su povezane sa sistemom lojalnosti.
- Podaci o događajima visoke vrednosti kao što su "Prikaz proizvoda" i "Odjavljivanje" definisani su i uključeni u izvorne podatke zajedno sa tajm-osom događaja i ID-om događaja.

Sledeća tabela prikazuje pojednostavljeni primer koliko Web događaji visoke vrednosti mogu biti uhvaćeni.

|ID događaja|EventTimeStamp|ID korisnika|ID lojalnosti|Ime događaja|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Prikaz proizvoda|
|2|07-23-2022 10:05:00|abc123|707|Prijavljivanje lojalnosti|
|3|07-23-2022 10:10:00|abc123|707|Završetak kupovine|
|4|07-23-2022 10:20:00|xyz789|--|Prikaz proizvoda|

## <a name="data-ingestion"></a>Unos podataka

Podaci o klijentima mogu da potiču sa Vaše Web lokacije kao podaci o događajima i mogu se uskladištiti u sopstvenim uslugama analitike podataka u kući ili nezavisnih proizvođača. Veb podaci sadrže poznate i nepoznate korisnike ako Web lokacija ima tok potvrde identiteta koji se integriše sa uslugom potvrde identiteta. Na primer, eCommerce sistem koji zahteva od korisnika da obezbede kompletne detalje da bi završili transakciju kupovine. Ili sistem lojalnosti koji zahteva potvrdu identiteta da bi se potvrdio važeći primalac popusta na nagrade.

Podaci o događaju u našem gorenavedenom primeru sadrže različite ID-ove profila poznatih i nepoznatih korisnika. U slučaju 1 i 4, korisnici su nepoznati dok se u slučaju 2 i 3 korisnik sa ID abc123 ujavljuju na program lojalnosti.

:::image type="content" source="media/website-data-source.png" alt-text="Izvori podataka uključujući Contoso veb lokaciju.":::

Više informacija o dostupnim opcijama za unos podataka potražite u pregledu [izvora podataka](data-sources.md).

## <a name="data-unification"></a>Ujednačavanje podataka

Konvergiranje nepoznatih identiteta sa poznatim identitetima pomaže u omogućavanju personalizacije na osnovu ponašanja korisnika, bez obzira na njihovo stanje profila (poznato ili nepoznato). Personalizovani sadržaj za sve korisnike pomaže korisnicima da brzo dođe do najrelevantnijih proizvoda ili usluga za koje su zainteresovani u tom trenutku.

Pošto su neki od korisnika u našim podacima poznati, možemo da koristimo korisničke uvide da bismo kombinovali te podatke sa profilom korisnika. Više informacija o ujedinjenju profila klijenata potražite u članku [Pregled ujedinjenja podataka](data-unification.md).

1. Izaberite izvorna polja iz entiteta Web podataka. Koristite podatke profila koji su uskladišteni u Podacima sa Veba i izaberite polja koja predstavljaju ID-ove sa demografskim podacima.

   :::image type="content" source="media/website-source-fields.png" alt-text="Izvorna polja za Veb izvor podataka.":::

1. Dodajte pravila za objedinjavanje dupliranih zapisa. Za Web podatke odaberite najpunjene podatke.

1. Konfigurišite pravila i uslove podudaranja. Podaci o događaju Web profila u ovom primeru biće upamćeni sa ID-ovima sa profilima iz drugih izvora podataka koji sadrže informacije o klijentima. Podesite tačna pravila podudaranja na ID-ovima kao zasebna pravila sa svakim od ostalih entiteta profila koji imaju odgovarajući primarni ključ ili ID podudaranje. U primeru, podaci profila Web događaja se koriste kao poslednji entitet koji se podudara tako da se prvo kombinuju drugi podaci profila.
   1. Neproveraču **Uključi sve zapise** kreira objedinjene profile za poznate korisnike i uključuje odgovarajuće nepoznate korisničke ID-ove. Korisno je u scenarijima kada ste zainteresovani da pregledate aktivnosti ponašanja poznatih korisnika iz prošlosti kada su još uvek bile nepoznate.
   1. Provera uključivanja **svih zapisa kreira** zasebne zapise profila za nepoznate korisnike. Nepoznati korisnici dobijaju jedinstveni ID klijenta. Ubuduće, kada je poznati profil povezan sa podacima profila Web događaja, putovanje novopoznatih korisnika može se prikazati i koristiti za personalizaciju na osnovu ranije nepoznatih podataka o ponašanju.

:::image type="content" source="media/website-match-rule.png" alt-text="Podudaranje pravila za Veb lokaciju izvor podataka entitet.":::

## <a name="get-insights"></a>Ostvarite uvide

Ako su profili klijenata kreirani za nepoznate i poznate korisnike, podaci o Web događajima visoke vrednosti mogu da se koriste kao [aktivnosti](activities.md). Ove aktivnosti se mogu koristiti za kreiranje više uvida. Na primer, klijenti koji su posetili Veb lokaciju pre šest meseci (kada su još uvek bili nepoznati) ili klijenti koji nemaju ID lojalnosti nikada nisu dovršili odjavu.

:::image type="content" source="media/website-known-unknown.png" alt-text="Snimak ekrana stranice kupca sa poznatim i nepoznatim klijentima.":::

[Obogatite](enrichment-hub.md) podatke, izgradite [mere i](measures.md) kreirajte [segmente za dalju](segments.md) aktivaciju.

Na primer, možete da kreirate segmente poznatih korisnika koji su pogledali neke proizvode, ali nikada nisu dovršili odjavu.

Više informacija potražite u članku [Pregled segmenata](segments.md).

## <a name="activate-insights"></a>Aktivirajte uvide

Postoji nekoliko načina za izvoz podataka i preduzete radnje na osnovu osnovnih uvida.

Više informacija potražite u članku [Pregled izvoza](export-destinations.md).
