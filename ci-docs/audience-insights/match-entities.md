---
title: Podudaranje entiteta za objedinjavanje podataka
description: Podudarite entitete da biste kreirali objedinjene profile klijenata.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267495"
---
# <a name="match-entities"></a>Podudaranje entiteta

Kada završite fazu mapiranja, spremni ste za podudaranje sa entitetima. Faza podudaranja navodi kako da kombinujete svoje skupove podataka u objedinjeni skup podataka profila klijenta. Faza podudaranja zahteva najmanje [dva mapirana entiteta](map-entities.md).

## <a name="specify-the-match-order"></a>Navedite redosled podudaranja

Idi na **Podaci** > **Ujednačavanje** > **Podudaranje** i izaberite **Podesi redosled** da započnete fazu podudaranja.

Svako podudaranje objedinjuje dva ili više entiteta u jedan entitet, istovremeno zadržavajući svaki jedinstveni zapis korisnika. U sledećem primeru odabrali smo tri entiteta: **ContactCSV: TestData** kao **Primarni** entitet, **WebAccountCSV: TestData** kao **Entitet 2** i **CallRecordSmall: TestData** kao **Entitet 3**. Dijagram iznad izbora ilustruje kako će se redosled podudaranja izvršiti.

> [!div class="mx-imgBorder"]
> ![Uredite redosled podudaranja podataka](media/configure-data-match-order-edit-page.png "Uređivanje redosleda podudaranja podataka")
  
**Primarni** entitet je usklađen sa **Entitetom 2**. Skup podataka koji proističe iz prvog podudaranja je usklađen sa **Entitetom 3**.
U ovom primeru smo izabrali samo dva podudaranja, ali sistem može da ih podrži više.

> [!IMPORTANT]
> Entitet koji ste odabrali kao svoj **Primarni** entitet poslužiće kao osnova za objedinjeni matični skup podataka. Dodatni entiteti koji su izabrani tokom faze podudaranja biće dodati ovom entitetu. Istovremeno, to ne znači da će objedinjeni entitet uključivati *sve* podatke uključene u ovaj entitet.
>
> Postoje dva razloga koja vam mogu pomoći da odaberete hijerarhiju svojih entiteta:
>
> - Za koji entitet smatrate da ima najpotpunije i najpouzdanije podatke o vašim klijentima?
> - Da li entitet koji ste upravo identifikovali ima atribute koje dele i drugi subjekti (na primer, ime, broj telefona ili adresa e-pošte)? Ako ne, odaberite svoj drugi najpouzdaniji entitet.

Izaberite **Gotovo** da biste sačuvali redosled podudaranja.

## <a name="define-rules-for-your-first-match-pair"></a>Definišite pravila za prvi par za podudaranje

Kada navedete redosled podudaranja, videćete definisana podudaranja na stranici **Podudaranje**. Pločice na vrhu ekrana biće prazne dok ne pokrenete svoj redosled podudaranja.

> [!div class="mx-imgBorder"]
> ![Definišite pravila](media/configure-data-match-need-rules.png "Definisanje pravila")

Upozorenje **Potrebna su pravila** sugeriše da nije određeno pravilo podudaranja za par za podudaranje. Pravila podudaranja određuju logiku kojom će se određeni par entiteta uskladiti.

1. Da biste definisali prvo pravilo, otvorite okno **Definicija pravila** odabirom odgovarajućeg reda podudaranja u tabeli sa podudaranjima (1), a zatim izaberite **Kreiraj novo pravilo** (2).

   > [!div class="mx-imgBorder"]
   > ![Kreiraj novo pravilo](media/configure-data-match-new-rule2.png "Kreiraj novo pravilo")

2. U oknu **Uredi pravilo**, konfigurišite uslove za to pravilo. Svaki uslov je predstavljen u dva reda koja uključuju obavezne izbore.

   > [!div class="mx-imgBorder"]
   > ![Okno za novo pravilo](media/configure-data-match-new-rule-condition.png "Okno za novo pravilo")

   Entitet/polje (prvo) – Atribut koji će se koristiti za podudaranje iz entiteta prvog para za podudaranje. Primeri mogu da uključuju broj telefona ili adresu e-pošte. Odaberite atribut koji će verovatno biti jedinstven za klijenta.

   > [!TIP]
   > Izbegavajte podudaranje na osnovu atributa tipa aktivnosti. Drugim rečima, ako se čini da je neki atribut aktivnost, onda to može biti loš kriterijum za podudaranje.  

   Entitet/polje (drugo) – Atribut koji će se koristiti za podudaranje iz entiteta drugog para za podudaranje.

   Normalizuj – **Metoda normalizacije**: Za izabrane atribute dostupne su razne opcije normalizacije. Na primer, uklanjanje interpunkcijskih znakova ili uklanjanje razmaka

   Za normalizaciju naziva organizacije (Pregled), takođe možete da izaberete **Vrsta (telefon, ime, organizacija)**

   > [!div class="mx-imgBorder"]
   > ![Normalizacija-B2B](media/match-normalization-b2b.png "Normalizacija-B2B")

   Nivo preciznosti – Nivo preciznosti koji će se koristiti za ovo stanje. Podešavanje nivoa preciznosti za uslov podudaranja može imati dva tipa: **Osnovni** i **Prilagođeni**.  
   - Osnovni: Omogućava vam izbor između četiri opcije: Niski, Srednji, Visoki i Tačni. Izaberite **Tačni** da biste podudarali samo zapise koji se podudaraju 100 posto. Izaberite jedan od ostalih nivoa da biste podudarali zapise koji nisu 100 posto identični.
   - Prilagođeni: Koristite klizač da biste definisali prilagođeni procenat za koji se zapisi moraju podudarati ili uneti vrednost u polje **Prilagođeni**. Sistem će podudarati samo one zapise koji prelaze ovaj prag kao parovi spojenih podudaranja. Vrednosti na klizaču su između 0 i 1. Dakle, 0,64 predstavlja 64 procenta.

3. Izaberite **Gotovo** da biste sačuvali pravilo.

### <a name="add-multiple-conditions"></a>Dodavanje više uslova

Da biste podudarali entitete samo ako je ispunjeno više uslova, dodajte još uslova koji su povezani preko operatora I.

1. U oknu **Uređivanje pravila**, izaberite **Dodajte uslov**. Takođe možete izbrisati uslove tako što ćete izabrati dugme za uklanjanje pored postojećeg uslova.

2. Izaberite **Gotovo** da biste sačuvali pravilo.

## <a name="add-multiple-rules"></a>Dodavanje više pravila

Svaki uslov odnosi se na jedan par atributa, dok pravila predstavljaju skupove uslova. Da bi se vaši entiteti podudarili sa različitim skupovima atributa, možete dodati više pravila.

1. U uvidima o korisnicima idite na **Podaci** > **Objedini** > **Podudari**.

2. Izaberite entitet koji želite da ažurirate i izaberite **Dodaj pravila**.

3. Sledite proceduru kao što je opisano u [Definišite pravila za prvi par za podudaranje](#define-rules-for-your-first-match-pair).

> [!NOTE]
> Redosled pravila je važan. Algoritam podudaranja pokušava da podudari sadržaj na osnovu prvog pravila i nastavlja na drugo pravilo samo ako pod prvim pravilom nije identifikovano nijedno podudaranje.

## <a name="define-deduplication-on-a-match-entity"></a>Definišite deduplikaciju na entitetu podudaranja

Pored navođenja pravila za unakrsno podudaranje kako je navedeno u gornjim odeljcima, takođe možete da odredite pravila za deduplikaciju. *Deduplikacija* je proces. Identifikuje duplikate zapisa, spaja ih u jedan zapis i povezuje sve izvorne zapise sa ovim objedinjenim zapisom sa alternativnim ID-ovima za objedinjeni zapis.

Kada se deduplicirani zapis identifikuje, on će se zatim koristiti u procesu unakrsnog podudaranja. Deduplikacija se primenjuje na nivou entiteta i može se primeniti na svaki entitet koji se koristi u procesu podudaranja.

### <a name="add-deduplication-rules"></a>Dodavanje pravila za deduplikaciju

1. U uvidima o korisnicima idite na **Podaci** > **Objedini** > **Podudari**.

1. U odeljku **Objedinjeni duplikati** izaberite **Podesite entitete**.

1. U odeljku **Objedinjavanje željenih podešavanja** izaberite entitete na koje želite da primenite deduplikaciju.

1. Navedite kako treba objediniti duplikate zapisa i odaberite jednu od tri opcije objedinjavanja:
   - *Najpopunjeniji*: Identifikuje zapis sa najviše popunjenih atributa kao dobitni. To je podrazumevana opcija objedinjavanja.
   - *Najnoviji*: Identifikuje dobitni zapis na osnovu najskorijeg vremena. Zahteva datum ili numeričko polje za definisanje skorašnjosti.
   - *Najkasniji*: Identifikuje dobitni zapis na osnovu najkasnijeg vremena. Zahteva datum ili numeričko polje za definisanje skorašnjosti.
 
   > [!div class="mx-imgBorder"]
   > ![Korak 1 za pravila za deduplikaciju](media/match-selfconflation.png "Korak 1 za pravila za deduplikaciju")
 
1. Kada su entiteti izabrani i kada su postavljene željene opcije za objedinjavanje, izaberite **Napravite novo pravilo** da bi se definisala pravila deduplikacije na nivou entiteta.
   - **Izaberite polje** navodi sva dostupna polja iz tog entiteta na kojem želite da deduplicirate izvorne podatke.
   - Navedite postavke normalizacije i preciznosti na sličan način kao što je navedeno u unakrsnom podudaranju entiteta.
   - Možete da definišete dodatne uslove izborom opcije **Dodajte uslov**.
 
   > [!div class="mx-imgBorder"]
   > ![Korak 2 za pravila za deduplikaciju](media/match-selfconflation-rules.png "Korak 2 za pravila za deduplikaciju")

  Možete da kreirate više pravila za deduplikaciju za entitet. 

1. Pokretanje procesa podudaranja sada grupiše zapise na osnovu uslova definisanih u pravilima deduplikacije. Nakon grupisanja zapisa, primenjuju se smernice objedinjavanja za identifikovanje dobitnog zapisa.

1. Dobitni zapis se zatim prosleđuje na podudaranje sa entitetima, zajedno sa zapisima koji nisu dobitni (na primer, alternativni ID-ovi) radi poboljšanja kvaliteta podudaranja.

1. Prilagođena pravila podudaranja definisana „podudaraj uvek“ i „ne podudaraj nikada“ zamenjuju pravila deduplikacije. Ako pravilo deduplikacije identifikuje podudarne zapise, a prilagođeno pravilo podudaranja je podešeno da se nikada ne podudara sa tim zapisima, onda se ova dva zapisa neće podudarati.

1. Nakon pokretanja procesa podudaranja, videćete statistiku deduplikacije.
   
> [!NOTE]
> Navođenje pravila deduplikacije nije obavezno. Ako takva pravila nisu konfigurisana, primenjuju se sistemski definisana pravila. Ona sažimaju sve zapise koji dele istu kombinaciju vrednosti (tačno podudaranje) iz primarnog ključa i polja u podudarnim pravilima u jedan zapis pre nego što proslede podatke entiteta u međusobno podudaranje entiteta radi poboljšanih performansi i ispravnosti sistema.

## <a name="run-your-match-order"></a>Pokretanje redosleda podudaranja

Nakon definisanja pravila podudaranja, uključujući pravila za podudaranje i deduplikaciju među entitetima, možete pokrenuti redosled podudaranja. Na stranici **Podudaranje**, izaberite **Pokreni** da započnete proces. Može da prođe neko vreme dok se algoritam podudaranja ne dovrši. Ne možete promeniti svojstva na stranici **Podudaranje** dok se ne dovrši proces podudaranja. Pronaći ćete objedinjeni entitet korisničkog profila koji je kreiran na stranici **Entiteti**. Vaš objedinjeni entitet klijenta se zove **ConflationMatchPairs : CustomerInsights**.

Da biste uneli dodatne izmene i ponovo pokrenuli korak, možete otkazati podudaranje u toku. Izaberite tekst **Osvežavanje u toku...** i izaberite **Otkaži posao** pri dnu bočnog okna koje se prikazuje.

Kada se proces podudaranja završi, tekst **Osvežavanje u toku...** će se promeniti u **Uspešno** i ponovo možete da koristite svu funkcionalnost stranice.

Proces prvog podudaranja dovodi do kreiranja jedinstvenog master entiteta. Sva naredna pokretanja podudaranja dovode do širenja tog entiteta.

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies). Možete izabrati status procesa da biste videli detalje o toku celog posla. Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.

## <a name="deduplication-output-as-an-entity"></a>Izlaz postupka uklanjanja duplikata kao entitet
Pored objedinjenog glavnog entiteta kreiranog kao deo podudaranja sa entitetima, postupak uklanjanja duplikata takođe generiše novi entitet za svaki entitet iz redosleda podudaranja kako bi se identifikovali zapisi iz kojih su uklonjeni duplikati. Ovi entiteti se mogu naći zajedno sa **ConflationMatchPairs:CustomerInsights** u odeljku **Sistem** na stranici **Entiteti**, sa imenom **Deduplication_Datasource_Entity**.

Izlazni entitet uklanjanja duplikata sadrži sledeće informacije:
- ID-ovi/Ključevi
  - Polje primarnog ključa i njegovo polje alternativnih ID-ova. Polje alternativnih ID-ova sastoji se od svih alternativnih ID-ova identifikovanih za zapis.
  - Polje Deduplication_GroupId prikazuje grupu ili klaster identifikovane u okviru entiteta koji grupiše sve slične zapise na osnovu navedenih polja uklanjanja duplikata. Ovo se koristi u svrhe obrade sistema. Ako nisu navedena ručna pravila za uklanjanje duplikata i ako se primenjuju sistemski definisana pravila za uklanjanje duplikata, ovo polje možda nećete pronaći u izlaznom entitetu uklanjanja duplikata.
  - Deduplication_WinnerId: Ovo polje sadrži ID pobednika iz identifikovanih grupa ili klastera. Ako je Deduplication_WinnerId ista kao vrednost primarnog ključa za zapis, to znači da je taj zapis dobitni.
- Polja koja se koriste za definisanje pravila za uklanjanje duplikata.
- Odredite pravila i ocenite polja da označite koja su od pravila za uklanjanje duplikata primenjena i koji rezultat vraća algoritam za podudaranje.

## <a name="review-and-validate-your-matches"></a>Pregledajte i potvrdite svoja podudaranja

Ocenite kvalitet parova za podudaranje i precizirajte ga:

- Na stranici **Podudaranje** ćete pronaći dve pločice koje prikazuju početne uvide o vašim podacima.

  - **Jedinstveni klijenti**: prikazuje broj jedinstvenih profila koje je sistem identifikovao.
  - **Podudarni zapisi**: prikazuje broj podudaranja u svim parovima za podudaranje.

- U tabeli **Redosled podudaranja** možete oceniti rezultate svakog para upoređujući broj zapisa koji su došli iz ovog entiteta parova za podudaranje u odnosu na procenat uspešno podudarenih zapisa.

- U odeljku **Pravila** entiteta u tabeli **Redosled podudaranja** ćete pronaći procenat uspešno podudarenih zapisa na nivou pravila. Odabirom simbola tabele pored pravila možete pregledati sve te zapise na nivou pravila. Preporučujemo vam da pregledate podskup zapisa da biste utvrdili da su pravilno podudareni.

- Eksperimentišite sa različitim pragovima preciznosti oko uslova za identifikovanje optimalne vrednosti.

  1. Izaberite tri tačke (...) za pravilo para za podudaranje sa kojim želite da eksperimentišete i izaberite **Uredi**.

  2. Izaberite uslov sa kojim želite da eksperimentišete. Svaki kriterijum predstavljen je jednim redom u oknu **Pravilo podudaranja**.

  3. Ono što ćete videti na stranici **Pregled kriterijuma** zavisi od nivoa preciznosti koji ste izabrali za uslov. Pronađite broj podudarnih i nepodudarnih zapisa za izabrani uslov.

     Steknite veliko razumevanje efekata različitih graničnih nivoa. Možete da uporedite koliko će se zapisa podudarati ispod svakog od graničnih nivoa i da pregledate zapise za svaku opciju. Izaberite svaku pločicu i pregledajte podatke u odeljku tabele.

## <a name="optimize-your-matches"></a>Optimizovanje podudaranja

Povećajte kvalitet tako što ćete ponovo konfigurisati neke parametre podudaranja:

- **Promenite raspored podudaranja** tako što ćete izabrati **Uredi** i promeniti polja rasporeda podudaranja.

  > [!div class="mx-imgBorder"]
  > ![Uređivanje redosleda podudaranja podataka](media/configure-data-match-order-edit.png "Uređivanje redosleda podudaranja podataka")

- **Promenite redosled svojih pravila** ako ste definisali više pravila. Redosled pravila podudaranja možete promeniti tako što ćete birati opcije **Premesti nagore** i **Premesti nadole** u mreži pravila podudaranja.

  > [!div class="mx-imgBorder"]
  > ![Promena redosleda pravila](media/configure-data-change-rule-order.png "Promena redosleda pravila")

- **Napravite duplikate pravila** ako ste definisali pravilo podudaranja i želite da kreirate slično pravilo sa izmenama. Učinite to izborom opcije **Dupliraj**.

  > [!div class="mx-imgBorder"]
  > ![Duplirajte pravilo](media/configure-data-duplicate-rule.png "Dupliranje pravila")

- **Deaktivirajte pravilo** da zadržite pravilo podudaranja dok ga isključujete iz procesa podudaranja.

  > [!div class="mx-imgBorder"]
  > ![Deaktiviranje pravila](media/configure-data-deactivate-rule.png "Deaktiviranje pravila")

- **Uređujte pravila** izborom simbola **Uredi**. Možete primeniti sledeće promene:

  - Promenite atribute za uslov: Izaberite nove atribute u određenom redu uslova.
  - Promenite graničnu vrednost uslova: Prilagodite klizač preciznosti.
  - Promenite metod normalizacije za uslov: Ažurirajte metodu normalizacije.

## <a name="specify-your-custom-match-records"></a>Navedite prilagođene zapise podudaranja

Možete da navedete uslove za koje bi određena pravila trebalo uvek da se podudaraju ili nikada da se ne podudaraju. Ova pravila se mogu grupno otpremiti u proces podudaranja.

1. Izaberite opciju **Prilagođeno podudaranje** na ekranu **Redosled podudaranja**.

   > [!div class="mx-imgBorder"]
   > ![Kreiranje prilagođenog podudaranja](media/custom-match-create.png "Kreiranje prilagođenog podudaranja")

2. Ako nemate otpremljene entitete, videćete novi dijalog **Prilagođeno podudaranje** koji treba da popunite nekim detaljima. Ako ste ranije naveli ove detalje, pređite na korak 8.

   > [!div class="mx-imgBorder"]
   > ![Novi dijalog prilagođenog podudaranja](media/custom-match-new-dialog-box.png "Novi dijalog prilagođenog podudaranja")

3. Izaberite **Popunite predložak** da biste dobili datoteku predloška koja može da odredi koji će se zapisi iz kojih entiteta uvek podudarati ili se neće nikad podudariti. Morate zasebno da popunite zapise „uvek se podudara“ i „nikad se ne podudara“ u dve različite datoteke.

4. Predložak sadrži polja za specifikaciju entiteta i vrednosti primarnog ključa entiteta koje će se koristiti u prilagođenom podudaranju. Na primer, ako želite da se primarni ključ 12345 entiteta Prodaja uvek podudara sa primarnim ključem 34567 entiteta Kontakt, moraćete to da navedete na sledeći način:
    - Entity1: Prodaja
    - Entity1Key: 12345
    - Entity2: Kontakt
    - Entity2Key: 34567

   Ista datoteka predloška može odrediti zapise prilagođenih podudaranja iz više entiteta.
   
   Ako želite da navedete prilagođeno podudaranje za uklanjanje duplikata na entitetu, navedite isti entitet kao i Entity1 i Entity2 i postavite različite vrednosti primarnog ključa.

5. Kada dodate sva zamenjivanja koja želite da primenite, sačuvajte datoteku šablona.

6. Idite na **Podaci** > **Izvori podataka** i unesite datoteke predložaka kao nove entitete. Kada ih unesete, možete ih koristiti za određivanje konfiguracije podudaranja.

7. Kada otpremite datoteke i entitete koji su dostupni, ponovo izaberite opciju **Prilagođeno podudaranje**. Videćete opcije za određivanje entiteta koje želite da uključite. Izaberite potrebne entitete iz padajućeg menija.

   > [!div class="mx-imgBorder"]
   > ![Zamenjivanja prilagođenih podudaranja](media/custom-match-overrides.png "Zamenjivanja prilagođenih podudaranja")

8. Izaberite entitete koje želite da koristite za **Uvek se podudara** i **Nikad se ne podudara**, izaberite **Gotovo**.

9. Izaberite **Sačuvaj** na stranici **Podudaranje** za prilagođenu konfiguraciju podudaranja koju ste upravo postavili.

10. Izaberite **Pokreni** na stranici **Podudaranje** da biste započeli postupak podudaranja, a prilagođena konfiguracija podudaranja će stupiti na snagu. Sva pravila podudarna u sistemu se zamenjuju skupom konfiguracije.

11. Kada se podudaranje završi, možete proveriti entitet **ConflationMatchPair** da biste potvrdili da su izmene primenjene u podudaranjima pri sastavljanju.

## <a name="next-step"></a>Sledeći korak

Kada dovršite postupak podudaranja za najmanje jedan par podudaranja, možete rešiti moguće protivrečnosti u podacima tako što ćete proći kroz temu [**Objedinjavanje**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]