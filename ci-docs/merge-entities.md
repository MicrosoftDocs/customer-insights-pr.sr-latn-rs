---
title: Objedinjavanje polja klijenata radi ujedinjenja podataka
description: Objedinite entitete da biste kreirali objedinjene profile klijenata.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 4a19b753e7a5979fe72d7e96bc4452d7795c2d48
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139674"
---
# <a name="unify-customer-fields-for-data-unification"></a>Objedinjavanje polja klijenata radi ujedinjenja podataka

U ovom koraku procesa ujedinjenja odaberite i isključite atribute za objedinjavanje unutar objedinjenog entiteta profila. Na primer, ako su tri entiteta imala podatke e-pošte, možda ćete želeti da zadržite sva tri odvojena polja e-pošte ili da ih objedinite u jedno polje e-pošte za objedinjeni profil. Sistem automatski kombinuje neke atribute. Možete kreirati stabilne i jedinstvene ID-ove klijenata i grupišeti srodne profile u klaster.

:::image type="content" source="media/m3_unify.png" alt-text="Stranica objedinjavanja u procesu ujednačavanja podataka koja prikazuje tabelu sa objedinjenim poljima koja definišu ujednačeni korisnički profil.":::

## <a name="review-and-update-the-customer-fields"></a>Redigovanje i ažuriranje polja kupaca

1. Pregledajte listu polja koja će biti objedinjena u okviru **kartice polja** Kupac u tabeli. Izvršite bilo kakve promene ako je primenljivo.

   1. Za sva kombinovana polja možete da:
      - [Uređivanje](#edit-a-merged-field)
      - [Preimenuj](#rename-fields)
      - [Odvojeno](#separate-merged-fields)
      - [Izuzmi](#exclude-fields)
      - [Pomeranje na gore ili nadole](#change-the-order-of-fields)

   1. Za sva pojedinačna polja možete da:
      - [Kombinovanje polja](#combine-fields-manually)
      - [Kombinovanje grupe polja](#combine-a-group-of-fields)
      - [Preimenuj](#rename-fields)
      - [Izuzmi](#exclude-fields)
      - [Pomeranje na gore ili nadole](#change-the-order-of-fields)

1. Opcionalno, [generiši konfiguraciju ID-a kupca](#configure-customer-id-generation).

1. Opcionalno, [grupisanje profila u domaćinstva ili klastere](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Sledeći korak: Preispitivanje ujedinjenja](review-unification.md)

### <a name="edit-a-merged-field"></a>Uredite spojeno polje

1. Izaberite objedinjeno polje i odaberite stavku **Uredi**. Prikazaće se okno "Kombinovanje polja".

1. Navedite kako da kombinujete ili spojite polja iz jedne od tri opcije:
    - **Značaj**: identifikuje pobedničku vrednost na osnovu ranga važnosti navedenog za polja koja učestvuju. To je podrazumevana opcija objedinjavanja. Izaberite **Pomeri nagore/nadole** da biste podesili rang važnosti.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Opcija važnosti u dijalogu polja za spajanje.":::

    - **Najnoviji**: identifikuje dobitnu vrednost na osnovu najnovijeg datuma. Zahteva datum ili numeričko polje za svaki entitet koji učestvuje u opsegu polja za spajanje da bi definisao nedavnu aktivnost.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Opcija nedavne aktivnosti u dijalogu polja za spajanje.":::

    - **Poslednji**: identifikuje dobitnu vrednost na osnovu najdavnije aktivnosti. Zahteva datum ili numeričko polje za svaki entitet koji učestvuje u opsegu polja za spajanje da bi definisao nedavnu aktivnost.

1. Možete dodati još polja za učešće u procesu spajanja.

1. Spojeno polje možete preimenovati.

1. Izaberite **Gotovo** da primenite promene.

### <a name="rename-fields"></a>Preimenovanje polja

Promenite ime za prikaz objedinjenih ili odvojenih polja. Ne možete da promenite naziv izlaznog entiteta.

1. Izaberite polje i izaberite stavku **Preimenuj**.

1. Unesite novu ime za prikaz.

1. Izaberite **Gotovo**.

### <a name="separate-merged-fields"></a>Razdvajanje objedinjenih polja

Da biste razdvojili objedinjena polja, pronađite atribut u tabeli. Razdvojena polja se prikazuju kao pojedinačne tačke podataka na objedinjenom korisničkom profilu.

1. Izaberite objedinjeno polje i izaberite stavku **Razdvoj polja**.

1. Potvrdite razdvajanje.

### <a name="exclude-fields"></a>Izuzmi polja

Izuzmite objedinjeno ili odvojeno polje iz objedinjenog profila kupca. Ako se polje koristi u drugim procesima, na primer u segmentu, uklonite ga iz tih procesa pre nego što ga izuzmete iz korisničkog profila.

1. Izaberite polje i izaberite stavku **Izuzmi**.

1. Potvrdite izuzimanje.

Izaberite opciju "Isključena polja" da biste videli listu **svih isključenih polja**. Ako je potrebno, možete pročitati isključeno polje.

### <a name="change-the-order-of-fields"></a>Promena redosleda polja

Neki entiteti sadrže više detalja od drugih. Ako entitet uključuje najnovije podatke o polju, možete mu dati prioritet nad ostalim entitetima pri objedinjavanju vrednosti.

1. Izaberite polje.
  
1. Kliknite **na dugme "Premesti nagore** /nadole" da biste podesili redosled ili ih prevukli i otpustili na željeni položaj.

### <a name="combine-fields-manually"></a>Ručno kombinovanje polja

Kombinujte razdvojena polja da biste kreirali objedinjeni atribut.

1. Izaberite **stavku Kombinuj** > **polja**. Prikazaće se okno "Kombinovanje polja".

1. Navedite politiku pobednika spajanja u padajućoj listi **Kombinuj polja prema**.

1. Kliknite **na dugme "Dodaj** " da biste kombinovali više polja.

1. Navedite **Naziv** i jedan **Naziv izlaznog polja**.

1. Izaberite **Gotovo** da primenite promene.

### <a name="combine-a-group-of-fields"></a>Kombinovanje grupe polja

Tretirajte grupu polja kao jednu jedinicu. Na primer, ako naši zapisi sadrže polja Address1, Address2, City, State i Zip, ne želimo da se objedinjujemo u adresi drugog zapisa, misleći da će to učiniti naše podatke potpunijim.

1. Izaberite **stavku** > **Kombinovanje grupe polja**.

1. Navedite smernice pobednika objedinjavanja u **grupama redova po padajućem** meniju.

1. Izaberite **opciju** Dodaj i odaberi ako želite da u polja dodate još polja ili grupa.

1. Navedite **ime** i ime izlaza **za** svako kombinovano polje.

1. Navedite **ime** za grupu polja.

1. Izaberite **Gotovo** da primenite promene.

## <a name="configure-customer-id-generation"></a>Konfigurisanje generacije ID-a klijenta

Definišite kako da generišete ID vrednosti kupca, jedinstvene identifikatore profila kupca. Korak objedinjavanja polja u procesu ujedinjenja podataka generiše jedinstveni identifikator profila klijenta. Identifikator je ID klijenta *u entitetu* kupca *koji* je rezultat procesa ujedinjenja podataka.

ID *kupca se* zasniva na hashu prve vrednosti primarnih ključeva pobednika koji nisu bez vrednosti. Ovi ključevi potiиu od entiteta koji se koriste u ujedinjenju podataka i pod uticajem su redosleda podudaranja.Tako da se generisani ID kupca može promeniti kada se vrednost primarnog ključa promeni u primarnom entitetu redosleda podudaranja. Vrednost primarnog ključa možda neće uvek predstavljati istog kupca.

Konfigurisanje stabilnog ID-a klijenta vam omogućava da izbegnete takvo ponašanje.

1. Izaberite karticu **Ključevi**.

1. Zadržite pokazivač u redu " **ID kupca" i** izaberite stavku "Konfiguriši **"**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontrola za prilagođavanje generisanja ID-a.":::

1. Izaberite do pet polja koja će sadržati jedinstveni ID klijenta i koja su stabilnija. Zapisi koji ne odgovaraju vašoj konfiguraciji umesto toga koriste sistemski konfigurisan ID.  

1. Izaberite **Gotovo**.

## <a name="group-profiles-into-households-or-clusters"></a>Grupišite profile u domaćinstva ili klastere

Pravila za grupisanje srodnih profila možete definisati u klaster. Trenutno postoje dve vrste klastera – domaćinstva i prilagođeni klasteri. Sistem automatski bira domaćinstvo sa unapred definisanim pravilima ako entitet *Klijent* sadrži semantička polja *Person.LastName* i *Location.Address*. Takođe možete kreirati klaster sa sopstvenim pravilima i uslovima, slično [pravilima podudaranja](match-entities.md#define-rules-for-match-pairs).

1. Izaberite klaster **naprednog** > **kreiranja**.

   :::image type="content" source="media/create-cluster.png" alt-text="Kontrola za kreiranje novog klastera.":::

1. Birajte između klastera **Domaćinstvo** ili **Prilagođeni**. Ako semantička polja *Person.LastName* i *Location.Address* postoje u entitetu *Klijent*, domaćinstvo se automatski bira.

1. Unesite naziv klastera i izaberite **Gotovo**.

1. Izaberite karticu **Klasteri** da biste pronašli klaster koji ste kreirali.

1. Navedite pravila i uslove za definisanje klastera.

1. Izaberite **Gotovo**. Klaster se kreira kada se proces ujedinjenja dovrši. Identifikatori klastera se dodaju kao nova polja entitetu *kupca*.

> [!div class="nextstepaction"]
> [Sledeći korak: Preispitivanje ujedinjenja](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
