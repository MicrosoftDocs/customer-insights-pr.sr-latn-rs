---
title: Podudaranje entiteta za objedinjavanje podataka
description: Podudarite entitete da biste kreirali objedinjene profile klijenata.
ms.date: 11/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
ms.openlocfilehash: 253c1614725252eb4c794d77669a00b401f0198d
ms.sourcegitcommit: 740e41ec965cee2229592a6d2610c12def116311
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/24/2021
ms.locfileid: "7863828"
---
# <a name="match-entities"></a>Podudaranje entiteta

Faza podudaranja navodi kako da kombinujete svoje skupove podataka u objedinjeni skup podataka profila klijenta. Kada dovršite [korak mapiranja](map-entities.md) u procesu objedinjavanja podataka, spremni ste da podudarate entitete. Faza podudaranja zahteva najmanje dva mapirana entiteta.

Stranica za podudaranje sastoji se od tri odeljka: 
- Ključne metrike koje sumiraju broj podudarnih zapisa
- Redosled podudaranja i pravila za međusobno podudaranje entiteta
- Pravila za deduplikaciju entiteta za podudaranje

## <a name="specify-the-match-order"></a>Navedite redosled podudaranja

Idi na **Podaci** > **Ujednačavanje** > **Podudaranje** i izaberite **Podesi redosled** da započnete fazu podudaranja.

Svako podudaranje objedinjava dva ili više entiteta u jedan, objedinjeni entitet. Istovremeno, objedinjavanje čuva jedinstvene zapise o klijentima. Na primer, izabrali smo dva entiteta: **eCommerce:eCommerceContacts** kao primarni entitet i **LoyaltyScheme:loyCustomers** kao drugi entitet. Redosled entiteta određuje kojim redosledom će sistem pokušati da podudari zapise.

:::image type="content" source="media/match-page.png" alt-text="Snimak ekrana stranice Podudaranje u oblasti Objedinjavanje procesa objedinjavanja podataka.":::
  
Primarni entitet *eCommerce:eCommerceContacts* se podudara sa sledećim entitetom *LoyaltyScheme:loyCustomers*. Skup podataka koji je rezultat prvog koraka podudaranja podudara se sa sledećim entitetom ako imate više od dva entiteta.

> [!IMPORTANT]
> Entitet koji ste odabrali kao svoj primarni entitet poslužiće kao osnova za skup podataka objedinjenih profila. Dodatni entiteti koji su izabrani tokom faze podudaranja biće dodati ovom entitetu. To ne znači da će objedinjeni entitet sadržati *sve* podatke obuhvaćene ovim entitetom.
>
> Postoje dva razloga koja vam mogu pomoći da odaberete hijerarhiju svojih entiteta:
>
> - Odaberite entitet sa najpotpunijim i najpouzdanijim podacima o profilu o svojim klijentima kao primarni entitet.
> - Odaberite entitet koji ima nekoliko atributa zajedničkih sa drugim entitetima (npr. ime, broj telefona ili adresa e-pošte) kao primarni entitet.

Kada odredite redosled podudaranja, videćete definisane parove podudaranja u odeljku **Detalji podudarnih zapisa** u dijalogu **Podaci** > **Objedinjavanje** > **Podudaranje**. Ključne metrike će biti prazne dok se postupak podudaranja ne završi.

## <a name="define-rules-for-match-pairs"></a>Definisanje pravila za podudarne parove

Pravila podudaranja određuju logiku kojom će se određeni par entiteta uskladiti.

Upozorenje **Zahteva pravila** pored naziva entiteta sugeriše da nije određeno pravilo podudaranja za par podudaranja. 

:::image type="content" source="media/match-rule-add.png" alt-text="Snimak ekrana odeljka Detalji podudarnih zapisa sa kontrolom za dodavanje istaknutih pravila.":::

1. Izaberite **Dodaj pravila** pod entitetom u odeljku **Detalji podudarnih zapisa** da biste definisali pravila podudaranja.

1. U oknu **Kreiranje pravila** konfigurišite uslove za pravilo.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Snimak ekrana otvorenog pravila podudaranja sa dodatim uslovima.":::

   - **Entitet/polje (prvi red)**: Izaberite povezani entitet i atribut da biste odredili svojstvo zapisa koje je verovatno jedinstveno za klijenta. Na primer, broj telefona ili adresa e-pošte. Izbegavajte podudaranje po atributima tipa aktivnosti. Na primer, ID kupovine verovatno neće naći podudaranje u drugim vrstama zapisa.

   - **Entitet/polje (drugi red)**: Izaberite atribut koji se odnosi na atribut entiteta navedenog u prvom redu.

   - **Normalizacija**: Izaberite neku od sledećih opcija normalizacije za izabrane atribute. 
     - Razmak: Uklanja sve razmake. *Zdravo svima* postaje *ZdravoSvima*.
     - Simboli: Uklanja sve simbole i posebne znakove. *Glava & Ramena* postaje *GlavaRamena*.
     - Tekst malim slovima: Pretvara sve znakove u mala slova. *VELIKA SLOVA i Slova Za Naslov* postaje *velika slova i slova za naslov*.
     - Iz Unikoda u ASCII: Pretvara Unikod notaciju u ASCII znakove. */u00B2* postaje *2*.
     - Brojevi: Konvertuje druge brojevne sisteme, kao što su rimski brojevi, u arapske brojeve. *VIII* postaje *8*.
     - Semantički tipovi: Standardizuje imena, naslove, brojeve telefona, adrese itd. 

   - **Preciznost**: Podesite nivo preciznosti da se primenjuje za ovaj uslov. 
     - **Osnovno**: Birajte između *Nisko*, *Srednje*, *Visoko* i *Tačno*. Izaberite **Tačni** da biste podudarali samo zapise koji se podudaraju 100 posto. Izaberite jedan od ostalih nivoa da biste podudarali zapise koji nisu 100 posto identični.
     - **Prilagođeno**: Podesite procenat sa kojim zapisi moraju da se podudaraju. Sistem će se podudarati samo sa zapisima koji prelaze ovu graničnu vrednost.

1. Navedite **Naziv** pravila.

1. [Dodajte još uslova](#add-conditions-to-a-rule) ili izaberite **Gotovo** da biste dovršili pravilo.

1. Opcionalno, [dodajte još pravila](#add-rules-to-a-match-pair).

1. Izaberite **Sačuvaj** da primenite promene.

### <a name="add-conditions-to-a-rule"></a>Dodavanje uslova u pravilo

Da biste podudarali entitete samo ako atributi ispunjavaju više uslova, dodajte još uslova u pravilo podudaranja. Uslovi su povezani sa logičkim operatorom I, pa se stoga izvršavaju samo ako su ispunjeni svi uslovi.

1. Idite na **Podaci** > **Objedinjavanje** > **Podudaranje** i izaberite **Uredi** na pravilu kojem želite da dodate uslove.

1. U oknu **Uređivanje pravila**, izaberite **Dodajte uslov**.

1. Izaberite **Gotovo** da biste sačuvali pravilo.

### <a name="add-rules-to-a-match-pair"></a>Dodavanje pravila paru za podudaranje

Pravila za podudaranje predstavljaju skupove uslova. Da biste podudarili entitete prema uslovima zasnovanim na više atributa, dodajte još pravila

1.  Idite na **Podaci** > **Objedinjavanje** > **Podudaranje** i izaberite **Dodaj pravilo** entitetu kojem želite da dodate pravila.

2. Sledite korake u odeljku [Definisanje pravila za parove za podudaranje](#define-rules-for-match-pairs).

> [!NOTE]
> Redosled pravila je važan. Algoritam podudaranja pokušava da podudari sadržaj na osnovu vašeg prvog pravila i nastavlja na drugo pravilo samo ako sa prvim pravilom nije identifikovano nijedno podudaranje.

### <a name="change-the-entity-order-in-match-rules"></a>Promena redosleda entiteta u pravilima podudaranja

Možete promeniti redosled entiteta za pravila podudaranja da biste promenili redosled obrade. Pravila koja su u suprotnosti zbog promenjenog redosleda biće uklonjena. Uklonjena pravila morate ponovo kreirati pomoću ažurirane konfiguracije.

1. Idi na **Podaci** > **Ujednačavanje** > **Podudaranje** i izaberite **Uredi**.

1. U oknu **Uređivanje pravila**, izaberite kontrolu **Pomeri nagore/nadole** ili prevucite i ispustite entitete da biste im promenili redosled.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Opcije za promenu redosleda obrade entiteta u fazi podudaranja.":::

1. Izaberite **Gotovo** da biste sačuvali pravilo.

## <a name="define-deduplication-on-a-match-entity"></a>Definišite deduplikaciju na entitetu podudaranja

Pored [pravila za međusobno podudaranje](#define-rules-for-match-pairs), takođe možete da odredite pravila za uklanjanje duplikata. *Deduplikacija* je još jedan postupak pri uparivanju zapisa. Identifikuje duplikate zapisa i spaja ih u jedan zapis. Izvorni zapisi se povezuju sa objedinjenim zapisom sa alternativnim ID-ovima.

Deduplicirani zapisi će se zatim koristiti u procesu podudaranja među entitetima. Deduplikacija se dešava na pojedinačnim entitetima i može se konfigurisati za svaki entitet koji se koristi u parovima za podudaranje.

Navođenje pravila deduplikacije nije obavezno. Ako takva pravila nisu konfigurisana, primenjuju se sistemski definisana pravila. Oni kombinuju sve zapise u jedan zapis pre nego što prenesu podatke entiteta u međusobno udruživanje radi poboljšanih performansi.

### <a name="add-deduplication-rules"></a>Dodavanje pravila za deduplikaciju

1. Idite na **Podaci** > **Objedinjavanje** > **Podudaranje**.

1. U odeljku **Objedinjeni duplikati** izaberite **Podesite entitete**. U slučaju da su pravila za deduplikaciju već kreirana, izaberite **Uredi**.

1. U oknu **Željena podešavanja objedinjavanja** odaberite entitete nad kojima želite da pokrenete deduplikaciju.

1. Navedite kako treba kombinovati duplikate zapisa i odaberite jednu od tri opcije:
   - **Najpopunjeniji**: Identifikuje zapis sa najviše popunjenih atributa kao dobitni zapis. To je podrazumevana opcija objedinjavanja.
   - **Najnoviji**: Identifikuje dobitni zapis na osnovu najskorijeg vremena. Zahteva datum ili numeričko polje za definisanje skorašnjosti.
   - **Najkasniji**: Identifikuje dobitni zapis na osnovu najkasnijeg vremena. Zahteva datum ili numeričko polje za definisanje skorašnjosti.
 
   > [!div class="mx-imgBorder"]
   > ![Korak 1 za pravila za deduplikaciju.](media/match-selfconflation.png "Korak 1 za pravila za deduplikaciju")
 
1. Kada se entiteti izaberu i kada se postave željene opcije za objedinjavanje, izaberite **Dodaj pravilo** da biste definisali pravila deduplikacije na nivou entiteta.
   - **Izaberi polje** navodi sva raspoloživa polja iz tog entiteta. Odaberite polje na kojem želite da proverite da li postoje duplikati. Odaberite polja koja su verovatno jedinstvena za svakog klijenta. Na primer, adresa e-pošte ili kombinacija imena, grada i broja telefona.
   - Navedite podešavanja normalizacije i preciznosti.
   - Definišite još dodatnih uslova izborom opcije **Dodaj uslov**.
 
   > [!div class="mx-imgBorder"]
   > ![Korak 2 za pravila za deduplikaciju.](media/match-selfconflation-rules.png "Korak 2 za pravila za deduplikaciju")

  Možete da kreirate više pravila za deduplikaciju za entitet. 

1. Pokretanje procesa podudaranja sada grupiše zapise na osnovu uslova definisanih u pravilima deduplikacije. Nakon grupisanja zapisa, primenjuju se smernice objedinjavanja za identifikovanje dobitnog zapisa.

1. Dobitni zapis se zatim prosleđuje na podudaranje sa entitetima, zajedno sa zapisima koji nisu dobitni (na primer, alternativni ID-ovi) radi poboljšanja kvaliteta podudaranja.

1. Svako definisano pravilo za prilagođeno podudaranje zamenjuje pravila za dupliciranje. Ako pravilo deduplikacije identifikuje podudarne zapise, a prilagođeno pravilo podudaranja je podešeno da se nikada ne podudara sa tim zapisima, onda se ova dva zapisa neće podudarati.

1. Nakon [pokretanja procesa podudaranja](#run-the-match-process), videćete statistiku deduplikacije na pločicama ključne metrike.

### <a name="deduplication-output-as-an-entity"></a>Izlaz postupka uklanjanja duplikata kao entitet

Proces deduplikacije kreira novi entitet za svaki entitet iz parova za podudaranje kako bi se identifikovali deduplicirani zapisi. Ovi entiteti se mogu naći zajedno sa **ConflationMatchPairs:CustomerInsights** u odeljku **Sistem** na stranici **Entiteti**, pod nazivom **Deduplication_DataSource_Entity**.

Izlazni entitet uklanjanja duplikata sadrži sledeće informacije:
- ID-ovi/Ključevi
  - Polje primarnog ključa i njegovo polje alternativnih ID-ova. Polje alternativnih ID-ova sastoji se od svih alternativnih ID-ova identifikovanih za zapis.
  - Polje Deduplication_GroupId prikazuje grupu ili klaster identifikovane u okviru entiteta koji grupiše sve slične zapise na osnovu navedenih polja uklanjanja duplikata. Ovo se koristi u svrhe obrade sistema. Ako nisu navedena ručna pravila za uklanjanje duplikata i ako se primenjuju sistemski definisana pravila za uklanjanje duplikata, ovo polje možda nećete pronaći u izlaznom entitetu uklanjanja duplikata.
  - Deduplication_WinnerId: Ovo polje sadrži ID pobednika iz identifikovanih grupa ili klastera. Ako je Deduplication_WinnerId ista kao vrednost primarnog ključa za zapis, to znači da je taj zapis dobitni.
- Polja koja se koriste za definisanje pravila za uklanjanje duplikata.
- Odredite pravila i ocenite polja da označite koja su od pravila za uklanjanje duplikata primenjena i koji rezultat vraća algoritam za podudaranje.
   
## <a name="run-the-match-process"></a>Pokretanje postupka podudaranja

Sa konfigurisanim pravilima podudaranja, uključujući pravila za podudaranje i deduplikaciju među entitetima, možete pokrenuti postupak podudaranja. 

Idite na **Podaci** > **Objedinjavanje** > **Podudaranje** i izaberite **Pokreni** da biste započeli postupak. Algoritmu podudaranja treba neko vreme da se završi i ne možete da promenite konfiguraciju dok se ne završi. Da biste uneli promene, možete otkazati pokrenuti postupak. Izaberite status posla i izaberite **Otkaži posao** u oknu **Detalji napredovanja**.

Rezultat uspešnog pokretanja, objedinjeni entitet profila klijenta, pronaći ćete na stranici **Entiteti**. Vaš objedinjeni entitet klijenta se zove **Klijenti** u odeljku **Profili**. Prvo uspešno pokretanje podudaranja kreira objedinjeni entitet *Klijent*. Sva naredna pokretanja podudaranja proširuju taj entitet.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Pregledajte i potvrdite svoja podudaranja

Idite na **Podaci** > **Objedinjavanje** > **Podudaranje** da biste procenili kvalitet vaših parova i po potrebi ih precizirali.

Pločice na vrhu stranice prikazuju ključne metrike, rezimirajući broj podudarnih zapisa i duplikata.

:::image type="content" source="media/match-KPIs.png" alt-text="Izrezani snimak ekrana ključnih metrika na stranici Podudaranje sa brojevima i detaljima.":::

- **Jedinstveni izvorni zapisi** pokazuje broj pojedinačnih izvornih zapisa koji su obrađeni u poslednjem pokretanju podudaranja.
- **Podudarni i nepodudarni zapisi** ističe koliko jedinstvenih zapisa ostaje nakon obrade pravila podudaranja.
- **Samo odgovarajući zapisi** pokazuje broj podudaranja u svim vašim parovima podudaranja.

Rezultate svakog podudaranja i svakog para za podudaranje možete proceniti u tabeli **Detalji o podudarnim zapisima**. Uporedite broj zapisa koji su proizašli iz para za podudaranje sa procentom uspešno podudarnih zapisa.

Pregledajte pravila parova za podudaranje da biste videli procenat uspešno podudarnih zapisa na nivou pravila. Izaberite tri tačke (...), a zatim izaberite **Pregled podudaranja** da biste pregledali sve ove zapise na nivou pravila. Preporučujemo vam da pogledate neke zapise kako biste potvrdili da su se pravilno podudarali.

Isprobajte različite granične vrednosti za preciznost u uslovima kako biste pronašli optimalnu vrednost.

  1. Izaberite tri tačke (...) za pravilo sa kojim želite da eksperimentišete i izaberite **Uredi**.

  2. Promenite vrednosti preciznosti u uslovima koje želite da revidirate.

  3. Izaberite **Pregled**, pa pogledajte broj podudarnih i nepodudarnih zapisa za izabrani uslov.

## <a name="manage-match-rules"></a>Upravljanje pravilima za podudaranje

Možete da konfigurišete i fino podesite većinu parametara podudaranja.

:::image type="content" source="media/match-rules-management.png" alt-text="Snimak ekrana padajućeg menija sa opcijama pravila podudaranja.":::

- **Promenite redosled svojih pravila** ako ste definisali više pravila. Pravila podudaranja možete preurediti tako što ćete izabrati opcije **Pomeri nagore** i **Pomeri nadole** ili prevlačeći ih.

- **Promenite uslove pravila** izborom opcije **Uredi** i odaberite različita polja.

- **Deaktivirajte pravilo** da zadržite pravilo podudaranja dok ga isključujete iz procesa podudaranja.

- **Duplirajte pravila** ako ste definisali pravilo za podudaranje i želite da napravite slično pravilo sa izmenama, izaberite **Dupliraj**.

- **Izbrišite pravilo** izborom simbola **Izbriši**.

## <a name="specify-custom-match-conditions"></a>Navedite uslove za prilagođeno podudaranje

Možete da precizirate uslove koji zamene podrazumevanu logiku podudaranja. Dostupne su četiri opcije: 

|Opcija  |Opis |Primer  |
|---------|---------|---------|
|Uvek se podudara     | Definiše vrednosti koje se uvek podudaraju.         |  Uvek se *poklapaju* sa Majkom *i MikeR-om*.       |
|Nikad se ne podudara     | Definiše vrednosti koje se nikada ne podudaraju.        | Nikad se ne *poklapaj sa* Džonom i *Džonatanom*.        |
|Prilagođeno zaobilaženje     | Definiše vrednosti koje sistem uvek treba da ignoriše u fazi podudaranja. |  Zanemari vrednosti *11111 i* Nepoznato *tokom* podudaranja.        |
|Mapiranje pseudonima    | Definisanje vrednosti koje sistem treba da uzme u obzir kao istu vrednost.         | Smatraj *da* je Dћo jednak sa *Dћozefom.*        |

1. Idite na **Podaci** > **Objedinjavanje** > **Podudaranje** i izaberite **Prilagođeno podudaranje** u odeljku **Detalji podudarnih zapisa**.

   :::image type="content" source="media/custom-match-create.png" alt-text="Snimak ekrana odeljka pravila podudaranja sa istaknutom kontrolom za prilagođeno podudaranje.":::

1. U **oknu** "Prilagođeno" idite na **karticu** "Zapisi".

1. Odaberite prilagođenu opciju podudaranja iz **padajuće liste** prilagođenog tipa i izaberite **stavku Preuzmi predložak**. Potreban vam je poseban predložak za svaku opciju podudaranja.

1. Datoteka predloška se preuzima. Otvorite ga i popunite detalje. Predložak sadrži polja za specifikaciju entiteta i vrednosti primarnog ključa entiteta koje će se koristiti u prilagođenom podudaranju. Na primer, ako želite da se primarni ključ *12345* iz entiteta *Prodaja* uvek podudara sa primarnim ključem *34567* iz entiteta *Kontakt*, popunite predložak:
    - Entity1: Prodaja
    - Entity1Key: 12345
    - Entity2: Kontakt
    - Entity2Key: 34567

   Ista datoteka predloška može odrediti zapise prilagođenih podudaranja iz više entiteta.
   
   Ako želite da navedete prilagođeno podudaranje za uklanjanje duplikata na entitetu, navedite isti entitet kao i Entity1 i Entity2 i postavite različite vrednosti primarnog ključa.

1. Nakon dodavanja svih premošćivanja, sačuvajte datoteku predloška.

1. Idite na **Podaci** > **Izvori podataka** i unesite datoteke predložaka kao nove entitete.

1. Kada otpremite datoteke i entitete koji su dostupni, ponovo izaberite opciju **Prilagođeno podudaranje**. Videćete opcije za određivanje entiteta koje želite da uključite. U padajućem meniju izaberite potrebne entitete i izaberite stavku **Gotovo**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Snimak ekrana dijaloga za odabir zamene za scenario prilagođenog podudaranja.":::

1. Primena prilagođenog podudaranja zavisi od opcije podudaranja koju želite da koristite. 

   - Za **"Uvek** **podudaranje" ili "Nikad se ne** podudaraj" pređite na sledeći korak.
   - Za **prilagođeno** **premošćavanje ili mapiranje** pseudonima izaberite **opciju** Uredi po postojećem pravilu podudaranja ili kreirajte novo pravilo. U padajućem meniju Normalizacije odaberite opciju **Mapiranje** prilagođenog **bajpasa ili pseudonima** i izaberite **gotovo**.

1. Izaberite **Sačuvaj** na stranici **Podudaranje** da biste primenili konfiguracije za prilagođeno podudaranje.

1. Izaberite **Pokreni** na stranici **Podudaranje** da biste započeli postupak podudaranja. Ostala navedena pravila podudaranja se zamenjuju konfiguracijom za prilagođeno podudaranje.

### <a name="known-issues"></a>Poznati problemi

- Samokonflacija ne pokazuje normalizovane podatke u entitetima deduplikacije. Međutim, ona interno primenjuje normalizaciju tokom deduplikacije. To je po dizajnu za sve normalizacije. 
- Ako je postavka semantičkog tipa uklonjena u fazi mape kada pravilo **podudaranja** koristi mapiranje pseudonima ili prilagođeni bajpas, normalizacija neće biti primenjena. To se dešava samo ako obrišete semantički tip nakon konfigurisanja normalizacije u pravilu utakmice jer će semantički tip biti nepoznat.


## <a name="next-step"></a>Sledeći korak

Kada dovršite proces podudaranja za najmanje jedan par podudaranja, pređite na korak [**·**](merge-entities.md) objedinjavanja.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
