---
title: Pregled izvoza (verzija za pregled)
description: Upravljajte izvozima da biste delili podatke.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: c580b6c01e1b4ac6b095733193d86ebd0b4005f2
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304076"
---
# <a name="exports-preview-overview"></a>Pregled izvoza (verzija za pregled)

 Izvoz vam omogućava da delite određene podatke sa različitim aplikacijama. Oni mogu uključivati profile klijenata, entitete, šeme i detalje mapiranja. Svaki izvoz zahteva [vezu koju je postavio administrator radi upravljanja potvrdom identiteta i pristupom](connections.md). Stranica **Izvoz** prikazuje sve konfigurisane izvoze.

## <a name="export-types"></a>Tipovi izvoza

Postoje dva glavna tipa izvoza:  

- **Izvoz podataka vam omogućava da izvezete** bilo koji tip entiteta koji je dostupan u "Uvidi kupaca". Entiteti koje izaberete za izvoz izvoze se sa svim poljima podataka, metapodacima, šemama i detaljima mapiranja.
- **Izvoz segmenta vam omogućava** da izvezete entitete segmenata iz uvida kupaca. Za pojedinačne potrošače (B-to-C), segmenti predstavljaju listu profila kupaca. Segmenti za preduzeća (od B do B) [mogu predstavljati listu poslovnih kontakata ili kontakata](segment-builder.md#create-a-new-segment-with-segment-builder). Prilikom konfigurisanja izvoza birate uključena polja podataka, u zavisnosti od ciljnog sistema u koji izvozite podatke.

### <a name="export-segments"></a>Izvoz segmenata

**Izvoz segmenata u okruženja za poslovne naloge (B-to-B) ili pojedinačne potrošače (B-to-C)**  
Većina opcija izvoza podržava oba tipa okruženja. Izvoz segmenata u različite ciljne sisteme ima specifične zahteve. 

**Segmentirajte izvoze u okruženjima za individualne potrošače (B-to-C)**  
- Segmenti u kontekstu okruženja za pojedinačne klijente izgrađeni su na entitetu *objedinjenog profila klijenta*. Svaki segment koji ispunjava zahteve ciljnih sistema (na primer, adresa e -pošte) može biti izvezena.

**Izvoz segmenta u okruženjima za poslovne račune (od B do B)**  
- Segmenti u kontekstu okruženja za poslovne naloge su izgrađeni na *entitetu* naloga ili entitetu *kontakta*. Da biste izvezli segmente poslovnih kontakata takvi kakvi jesu, ciljni sistem mora da podržava segmente čistih poslovnih kontakata. Ovo je slučaj za [LinkedIn](export-linkedin-ads.md) kada izaberete opciju **kompanija** prilikom definisanja izvoza.
- Svi drugi ciljni sistemi zahtevaju polja iz entiteta kontakta.
- Sa dve vrste segmenata (kontakti i konta), uvidi kupaca automatski identifikuju vrstu segmenata koji ispunjavaju uslove za izvoz na osnovu ciljnog sistema. Na primer, za ciljni sistem fokusiran na kontakt, kao što je Mailchimp, "Uvidi kupaca" vam dozvoljavaju samo da odaberete segmente kontakata za izvoz.

**Ograničenja izvoza segmenata**  
- Ciljni sistemi nezavisnih proizvođača mogu ograničiti broj profila klijenata koje možete izvesti. 
- Za pojedinačne klijente, videćete stvarni broj članova segmenta kada izaberete segment za izvoz. Dobićete upozorenje ako je segment prevelik. 
- Za poslovne naloge ćete videti broj konta ili kontakata u zavisnosti od segmenta. Dobićete upozorenje ako je segment prevelik. Prekoračenje ograničenja ciljnih sistema dovodi do preskakanja izvoza.

## <a name="set-up-a-new-export"></a>Podešavanje novog izvoza

Da biste podesili ili uredili izvoz, potrebne su vam prave veze koje su vam dostupne. Veze zavise od vaše [korisničke uloge](permissions.md):
- **Administratori** imaju pristup svim vezama. Oni takođe mogu da kreiraju nove veze prilikom podešavanja izvoza.
- **Saradnici** mogu imati pristup određenim vezama. Oni zavise od administratora da konfigurišu i dele veze. Lista izvoza u koloni **Vaše dozvole** pokazuje saradnicima da li mogu da uređuju ili samo prikazuju izvoz. Za više informacija idite na [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Gledaoci** mogu samo da pregledaju postojeći izvoz, a ne da ga kreiraju.

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz** da biste kreirali novi izvoz.

1. U oknu **za podešavanje izvoza** izaberite vezu koju [ćete](connections.md) koristiti.

1. Navedite potrebne detalje i izaberite **Sačuvati** da biste kreirali izvoz. Za potrebne detalje pregledajte dokumentaciju "Uvid kupca" za određeni izvoz.

## <a name="manage-existing-exports"></a>Upravljanje postojećim izvozom

Idite **na** > **izvoz podataka** da biste videli izvoz, ime veze, tip veze i status. Sve korisničke uloge mogu pregledati konfigurisane izvoze. Listu izvoza možete da sortirate po bilo kojoj koloni ili da koristite polje za pretragu da biste pronašli izvoz kojim želite da upravljate.

Izaberite izvoz da biste prikazali dostupne radnje.

:::image type="content" source="media/exports_showmore.png" alt-text="Izvozi stranicu.":::

- **Prikažite** ili **uredite** izvoz. Korisnici bez dozvole za uređivanje biraju **Prikaz** umesto **Uređivanje** da videli detalje o izvozu.
- **Pokrenite** izvoz da biste izvezli najnovije podatke.
- **Kreirajte** duplikat izvoza.
- **[Zakažite](#schedule-and-run-exports)** izvoz.
- **Odvojite vezu da** biste uklonili vezu za ovaj izvoz. Odvajanje ne uklanja vezu, ali deaktivira izvoz. Korišćena **kolona "** Veza" prikazuje "Bez veze".
- **Uklonite** izvoz.

## <a name="schedule-and-run-exports"></a>Planiranje i pokretanje izvoza

Svaki izvoz koji konfigurišete ima raspored osvežavanja. Tokom osvežavanja, sistem traži nove ili ažurirane podatke koje će uključiti u izvoz. Podrazumevano se izvozi kao deo svakog [zakazanog osvežavanja sistema](schedule-refresh.md). Možete prilagoditi raspored osvežavanja ili ga isključiti za ručno pokretanje izvoza.

Rasporedi izvoza zavise od statusa vašeg okruženja. Ako su u toku ažuriranja [zavisnih elemenata](system.md#refresh-processes) kada treba da započne planirani izvoz, sistem će prvo dovršiti ažuriranja, a zatim pokrenuti izvoz. Kolona **"Osveženje** " prikazuje kada je izvoz poslednji put osvežen.

### <a name="schedule-exports"></a>Raspored izvoza

Definišite prilagođene rasporede osvežavanja za pojedinačni izvoz ili nekoliko izvoza odjednom. Trenutno definisani raspored naveden je u koloni **Raspored** liste izvoza. Dozvola za promenu rasporeda je ista kao uređivanje [i definisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite izvoz koji želite da zakažete.

1. Izaberite **Raspored**.

1. U oknu **Zakazivanje izvoza**, podesite **Izvršavanje rasporeda** na **Uključeno** da biste automatski pokretali izvoz. Podesite na **Isključeno** da biste ga ručno osvežavali.

1. Da biste automatski osvežavali izvoze, odaberite vrednost **Ponavljanje** i navedite detalje za nju. Definisano vreme se odnosi na sve slučajeve ponavljanja. To je vreme kada bi izvoz trebalo da počne da se osvežava.

1. Izaberite **Sačuvaj**.

Prilikom uređivanja rasporeda za nekoliko izvoza, napravite selekciju u okviru **"Zadrži" ili zamenite rasporede**:

- **Zadržite pojedinačne rasporede**: Zadržite prethodno definisani raspored za izabrani izvoz i onemogućite ih ili onemogućite.
- **Definišite novi raspored za sve izabrane izvoze**: Izmenite postojeće rasporede izabranih izvoza.

### <a name="run-exports-on-demand"></a>Pokretanje izvoza na zahtev

Da biste izvezli podatke bez čekanja na zakazano osvežavanje, idite na stranicu **Podaci** > **Izvoz**.

- Da biste pokrenuli sve izvoze, izaberite **Pokreni sve** u komandnoj traci. Pokreću se samo izvozi koji imaju aktivan raspored. Pokrenite jedan izvoz da biste pokrenuli izvoz koji nije aktivan.
- Da biste pokrenuli jedan izvoz, izaberite ga na listi i izaberite **Pokreni** u komandnoj traci.

## <a name="troubleshooting"></a>Rešavanje problema

### <a name="segment-not-eligible-for-export"></a>Segment ne ispunjava uslove za izvoz

**Problem** u okruženju poslovnih naloga vaš izvoz ne uspeva sa porukom o grešci: "Sledeći segment ne ispunjava uslove za ovo odredište izvoza: '{ime segmenta}'. Odaberite samo segmente tipa KontaktProfile i pokušajte ponovo."

**Okruženja** korisničkih uvida u rešenja za poslovne naloge ažurirana su tako da podržavaju segmente kontakata pored segmenata naloga. Zbog te promene, izvozu su potrebni kontakt detalji samo sa segmentima zasnovanim na kontaktima.

1. [Kreirajte segment zasnovan na kontaktima koji se](segment-builder.md) podudaraju sa prethodno korišćenim segmentom.

1. Kada se taj segment kontakta pokrene, uredite odgovarajući izvoz i izaberite novi segment.

1. Kliknite **na dugme "** Sačuvaj" da biste sačuvali konfiguraciju **ili sačuvajte i** odmah pokrenite da biste odmah testirali ovaj izvoz.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
