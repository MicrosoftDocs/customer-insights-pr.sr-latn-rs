---
title: Pregled izvoza (verzija za pregled)
description: Upravljajte izvozima da biste delili podatke.
ms.date: 07/25/2022
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
ms.openlocfilehash: a70aadda4fc0eff3ddb4c89665506762613c291a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9194985"
---
# <a name="exports-preview-overview"></a>Pregled izvoza (verzija za pregled)

 Izvoz vam omogućava da delite određene podatke sa različitim aplikacijama. Oni mogu uključivati profile klijenata, entitete, šeme i detalje mapiranja. Svaki izvoz zahteva [vezu koju je postavio administrator radi upravljanja potvrdom identiteta i pristupom](connections.md). Stranica **Izvoz** prikazuje sve konfigurisane izvoze.

## <a name="export-types"></a>Tipovi izvoza

Postoje dva glavna tipa izvoza:  

- **Izvoz podataka: izvezite** bilo koji tip entiteta koji je dostupan u uvidima kupaca. Entiteti koje izaberete za izvoz izvoze se sa svim poljima podataka, metapodacima, šemama i detaljima mapiranja.
- **Izvoz segmenta**: izvoz entiteta segmenta iz uvida kupaca. Segmenti predstavljaju listu profila klijenata. Prilikom konfigurisanja izvoza birate uključena polja podataka, u zavisnosti od ciljnog sistema u koji izvozite podatke.

### <a name="export-segments"></a>Izvoz segmenata

**Izvoz segmenata u okruženja za poslovne naloge (B-to-B) ili pojedinačne potrošače (B-to-C)**  
Većina opcija izvoza podržava oba tipa okruženja. Izvoz segmenata u različite ciljne sisteme ima specifične zahteve. 

**Segmentirajte izvoze u okruženjima za individualne potrošače (B-to-C)**  
- Segmenti u kontekstu okruženja za pojedinačne klijente izgrađeni su na entitetu *objedinjenog profila klijenta*. Svaki segment koji ispunjava zahteve ciljnih sistema (na primer, adresa e -pošte) može biti izvezena.

**Okruženja izvoza segmenata za poslovne kontakte (B-to-B)**  
- Segmenti u kontekstu okruženja za poslovne naloge izgrađeni su na entitetu *poslovni kontakt*. Da biste izvezli segmente poslovnih kontakata takvi kakvi jesu, ciljni sistem mora da podržava segmente čistih poslovnih kontakata. Ovo je slučaj za [LinkedIn](export-linkedin-ads.md) kada izaberete opciju **kompanija** prilikom definisanja izvoza.
- Svi drugi ciljni sistemi zahtevaju polja iz entiteta kontakta. Da biste osigurali da segmenti poslovnog kontakta mogu pribaviti podatke iz povezanih kontakata, definicija segmenta mora projektovati atribute entiteta kontakta. Saznajte više o tome kako da [konfigurišete segmente i atribute projekta](segment-builder.md).

**Ograničenja izvoza segmenata**  
- Ciljni sistemi nezavisnih proizvođača mogu ograničiti broj profila klijenata koje možete izvesti. 
- Za pojedinačne klijente, videćete stvarni broj članova segmenta kada izaberete segment za izvoz. Dobićete upozorenje ako je segment prevelik. 
- Za poslovne kontakte videćete broj poslovnih naloga u segmentu; međutim, broj kontakata koji može biti projektovan se ne prikazuje. U nekim slučajevima to može dovesti do toga da izvezeni segment zapravo sadrži više profila klijenata nego što ciljni sistem prihvata. Ako su ograničenja ciljnog sistema prekoračena, izvoz se preskače.

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

Svaki izvoz koji konfigurišete ima raspored osvežavanja. Tokom osvežavanja, sistem traži nove ili ažurirane podatke koje će uključiti u izvoz. Podrazumevano se izvozi kao deo svakog [zakazanog osvežavanja sistema](system.md#schedule-tab). Možete prilagoditi raspored osvežavanja ili ga isključiti za ručno pokretanje izvoza.

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

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
