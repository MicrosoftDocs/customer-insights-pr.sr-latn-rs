---
title: Podudaranje uslova za ujedinjenje podataka
description: Podudarite entitete da biste kreirali objedinjene profile klijenata.
recommendations: false
ms.date: 05/05/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: e3e4e37d5b4c9caf2520a789d5f78ef33b491793
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139720"
---
# <a name="match-conditions-for-data-unification"></a>Podudaranje uslova za ujedinjenje podataka

Ovaj korak u ujedinjenju definiše redosled podudaranja i pravila za podudaranje sa više entiteta. Ovaj korak zahteva najmanje dva entiteta.

> [!NOTE]
> Kada kreirate uslove podudaranja i izaberete **opciju** "Dalje", ne možete ukloniti izabrani entitet ili atribut. Ako je potrebno, kliknite **na dugme** "Nazad" da biste pregledali izabrane entitete i atribute pre nego što nastavite.

## <a name="include-enriched-entities-preview"></a>Uključi obogaćene entitete (pregled)

Ako ste obogatili entitete na nivou izvor podataka biste poboljšali rezultate ujedinjenja, izaberite ih. Više informacija potražite u članku [Obogaćivanje izvora podataka](data-sources-enrichment.md). Ako ste izabrali obogaćene entitete na stranici " **Duplirani** zapisi", nije potrebno da ih ponovo izaberete.

1. Na stranici **Podudarni** uslovi **izaberite stavku Korišćenje obogaćenih** entiteta na vrhu stranice.

1. Iz okna **"Korišćenje obogaćenih entiteta** " odaberite jedan ili više obogaćenih entiteta.

1. Izaberite **Gotovo**.

## <a name="specify-the-match-order"></a>Navedite redosled podudaranja

Svako podudaranje objedinjava dva ili više entiteta u jedan, objedinjeni entitet. Istovremeno, objedinjavanje čuva jedinstvene zapise o klijentima. Redosled podudaranja označava redosled kojim sistem pokušava da se podudara sa zapisima.

> [!IMPORTANT]
> Prvi entitet na listi naziva se primarni entitet. Primarni entitet služi kao osnova za skup podataka objedinjenih profila. Dodatni izabrani entiteti biće dodati ovom entitetu.
>
> Važna razmatranja:
>
> - Odaberite entitet sa najposebnijim i najpouzdanijim podacima profila o klijentima kao primarnom entitetu.
> - Odaberite entitet koji ima nekoliko zajedničkih atributa sa drugim entitetima (na primer, ime, broj telefona ili e-adresu) kao primarni entitet.

1. Na stranici **Podudarni** uslovi koristite strelice za premeštanje nagore i nadole da biste premestili entitete redosledom kojim želite ili ih prevucite i otpustite. Na primer, izaberite **Contacts:eCommerce** kao primarni entitet **i CustomerLoyalty:Loyalty** kao drugi entitet.

1. Da biste imali svaki zapis u entitetu kao jedinstvenog kupca, bez obzira na to da li je pronađeno podudaranje, izaberite uključi **sve zapise**. Svi zapisi u ovom entitetu koji se ne podudaraju sa zapisima u bilo kom drugom entitetu biće uključeni u objedinjeni profil. Zapisi koji nemaju podudaranje nazivaju se singltoni.
  
Primarni entitet Contacts *:eCommerce* se podudara sa sledećim entitetom *CustomerLoyalty:Loyalty*. Skup podataka koji je rezultat prvog koraka podudaranja podudara se sa sledećim entitetom ako imate više entiteta.

:::image type="content" source="media/m3_match.png" alt-text="Snimak ekrana izabranog redosleda podudaranja za entitete." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Definisanje pravila za podudarne parove

Pravila podudaranja određuju logiku kojom će se određeni par entiteta uskladiti. Pravilo se sastoji od jednog ili više uslova.

Upozorenje pored imena entiteta znači da nije definisano pravilo podudaranja za par podudaranja.

1. Izaberite **opciju Dodaj** pravilo za par entiteta da biste definisali pravila podudaranja.

1. U oknu **"Dodavanje** pravila" konfigurišite uslove za pravilo.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Snimak ekrana okna za dodavanje pravila.":::

   - **Izaberite entitet/polje (prvi red)**: Odaberite povezani entitet i atribut da biste naveli svojstvo zapisa koje je verovatno jedinstveno za kupca. Na primer, broj telefona ili adresa e-pošte. Izbegavajte podudaranje po atributima tipa aktivnosti. Na primer, ID kupovine verovatno neće naći podudaranje u drugim vrstama zapisa.

   - **Izaberite entitet/polje (drugi red)**: Odaberite atribut koji se odnosi na atribut entiteta navedenog u prvom redu.

   - **Normalizacija**: Izaberite neku od sledećih opcija normalizacije za izabrane atribute.
     - **Brojevi: Konvertuje** druge numeričke sisteme, kao što su rimski brojevi, u arapske brojeve. *VIII* postaje *8*.
     - **Simboli**: Uklanja sve simbole i specijalne znakove. *Glava & Ramena* postaje *GlavaRamena*.
     - **Tekst u manju sloћenja**: Konvertuje sve znakove u niћa. *VELIKA SLOVA i Slova Za Naslov* postaje *velika slova i slova za naslov*.
     - **Tip (telefon, ime, adresa, organizacija)**: Standardizuje imena, naslove, brojeve telefona, adrese i organizacije.
     - **Unikod u ASCII**: Konvertuje unikod notaciju u ASCII znakove. */u00B2* postaje *2*.
     - **Razmak:** Uklanja sve razmake. *Zdravo svima* postaje *ZdravoSvima*.

   - **Preciznost**: Podesite nivo preciznosti da se primenjuje za ovaj uslov.
     - **Osnovno: odaberite** sa niskih (30%)*,* Srednje (60%)*,* High (80%)*i* Exact (100%)*.* Izaberite **opciju Tačno** da bi se podudarali samo sa zapisima koji se podudaraju sa 100 procenata.
     - **Prilagođeno**: Podesite procenat sa kojim zapisi moraju da se podudaraju. Sistem će se podudarati samo sa zapisima koji prelaze ovu graničnu vrednost.

   - **Ime**: Ime za pravilo.

1. Da biste podudarali entitete samo ako atributi ispunjavaju više uslova, izaberite opciju **Dodaj** > **uslov da** biste dodali još uslova pravilu podudaranja. Uslovi su povezani sa logičkim operatorom I, pa se stoga izvršavaju samo ako su ispunjeni svi uslovi.

1. Opcionalno, razmotrite napredne opcije kao što su [izuzeci ili](#add-exceptions-to-a-rule) prilagođeni [uslovi podudaranja](#specify-custom-match-conditions).

1. Kliknite **na dugme** "Gotovo" da biste završili pravilo.

1. Opcionalno, [dodajte još pravila](#add-rules-to-a-match-pair).

1. Izaberite stavku **Dalje**.

> [!div class="nextstepaction"]
> [Sledeći korak: Objedinjavanje polja](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Dodavanje pravila paru za podudaranje

Pravila za podudaranje predstavljaju skupove uslova. Dodajte još pravila da biste entitete podudarali sa uslovima zasnovanim na više atributa.

1. Izaberite **opciju** Dodaj pravilo za entitet kojem želite da dodate pravila.

1. Sledite korake u odeljku [Definisanje pravila za parove za podudaranje](#define-rules-for-match-pairs).

> [!NOTE]
> Redosled pravila je važan. Algoritam podudaranja pokušava da se podudara sa datim zapisom kupca na osnovu prvog pravila i nastavlja ka drugom pravilu samo ako nijedno podudaranje nije identifikovano sa prvim pravilom.

## <a name="advanced-options"></a>Napredne opcije

### <a name="add-exceptions-to-a-rule"></a>Dodavanje izuzetaka pravilu

U većini slučajeva podudaranje entiteta vodi do jedinstvenih profila klijenata sa konsolidovanim podacima. Da biste se dinamički pozabavili retkim slučajevima lažnih pozitivnih i lažnih negativnosti, možete definisati izuzetke za pravilo podudaranja. Izuzeci se primenjuju nakon obrade pravila podudaranja i izbegavaju podudaranje svih zapisa koji ispunjavaju kriterijume za izuzetak.

Na primer, ako pravilo podudaranja kombinuje prezime, grad i datum rođenja, sistem će identifikovati blizance sa istim prezime koji žive u istom gradu kao i isti profil. Možete da navedete izuzetak koji se ne podudara sa profilima ako ime u entitetima koje kombinujete nisu isti.

1. U oknu **za uređivanje** izaberite **dodaj** > **izuzetak**.

1. Navedite kriterijume izuzetka.

1. Izaberite **Gotovo** da biste sačuvali pravilo.

### <a name="specify-custom-match-conditions"></a>Navedite uslove za prilagođeno podudaranje

Možete da precizirate uslove koji zamene podrazumevanu logiku podudaranja. Dostupne su četiri opcije:

|Opcija  |Opis |Primer  |
|---------|---------|---------|
|Uvek se podudara     | Definiše vrednosti koje se uvek podudaraju.         |  Uvek se poklapaju *sa* Majkom *i MikeR-om*.       |
|Nikad se ne podudara     | Definiše vrednosti koje se nikada ne podudaraju.        | Nikad se ne poklapaj *sa* Džonom i *Džonatanom*.        |
|Prilagođeno zaobilaženje     | Definiše vrednosti koje sistem uvek treba da ignoriše u fazi podudaranja. |  Zanemari vrednosti *11111 i Nepoznato* *tokom* podudaranja.        |
|Mapiranje pseudonima    | Definisanje vrednosti koje sistem treba da uzme u obzir kao istu vrednost.         | Smatraj *da je Džo jednak sa Džozefom* *.*        |

1. Izaberite **Prilagođeno**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Prilagođeno dugme":::

1. Odaberite prilagođeni **tip i** izaberite stavku **Preuzmi predložak**. Potreban vam je poseban predložak za svaku opciju podudaranja.

1. Otvorite preuzetu datoteku predloška i popunite detalje. Predložak sadrži polja za specifikaciju entiteta i vrednosti primarnog ključa entiteta koje će se koristiti u prilagođenom podudaranju. Na primer, ako želite da se primarni ključ *12345* iz entiteta *Prodaja* uvek podudara sa primarnim ključem *34567* iz entiteta *Kontakt*, popunite predložak:
    - Entity1: Prodaja
    - Entity1Key: 12345
    - Entity2: Kontakt
    - Entity2Key: 34567

   Ista datoteka predloška može odrediti zapise prilagođenih podudaranja iz više entiteta.

   Ako želite da navedete prilagođeno podudaranje za uklanjanje duplikata na entitetu, navedite isti entitet kao i Entity1 i Entity2 i postavite različite vrednosti primarnog ključa.

1. Nakon dodavanja svih premošćivanja, sačuvajte datoteku predloška.

1. Idite na **Podaci** > **Izvori podataka** i unesite datoteke predložaka kao nove entitete.

1. Nakon otpremanja datoteka, ponovo izaberite **opciju** "Prilagođeno". Izaberite potrebne entitete iz padajućeg menija i izaberite **gotovo**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Snimak ekrana dijaloga za odabir zamene za scenario prilagođenog podudaranja.":::

1. Primena prilagođenog podudaranja zavisi od opcije podudaranja koju želite da koristite.

   - Za " **Uvek podudaranje** " **ili "Nikad se** ne podudaraj", pređite na sledeći korak.
   - Za **bajpas** **ili mapiranje pseudonima izaberite** uredi **postojeće** pravilo podudaranja ili kreirajte novo pravilo. U padajućem meniju Normalizacije odaberite opciju mapiranja **prilagođenog bajpasa** **ili pseudonima i** izaberite **gotovo**.

1. U prilagođenom **oknu** izaberite stavku **Gotovo** da biste primenili prilagođenu konfiguraciju podudaranja.

> [!div class="nextstepaction"]
> [Sledeći korak: Objedinjavanje polja](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
