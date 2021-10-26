---
title: Objedinjavanje entiteta kod objedinjavanja podataka
description: Objedinite entitete da biste kreirali objedinjene profile klijenata.
ms.date: 10/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-merge
ms.openlocfilehash: 6b3002b21ea043315e50724ec103aef8a3ced98e
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648271"
---
# <a name="merge-entities"></a>Objedinjavanje entiteta

Faza spajanja je poslednja faza u procesu objedinjavanja podataka. Njegova svrha je usklađivanje neusaglašenih podataka. Primeri neusaglašenih podataka mogu uključivati korisničko ime koje se nalazi u dva skupa podataka, ali to se prikazuje malo drugačije u svakom („Jovan Dučić“ u odnosu na „Jovo Dučić“) ili telefonski broj koji se razlikuje u formatu (npr. 617-803-091 u odnosu na 617803091). Spajanje tih neusaglašenih tačaka podataka obavlja se na osnovu poređenja atributa.

:::image type="content" source="media/merge-fields-page.png" alt-text="Stranica objedinjavanja u procesu ujednačavanja podataka koja prikazuje tabelu sa objedinjenim poljima koja definišu ujednačeni korisnički profil.":::

Kada se dovrši [faza podudaranja](match-entities.md), fazu spajanja započinjete odabirom pločice **Objedini** na stranici **Ujednačavanje**.

## <a name="review-system-recommendations"></a>Pregled sistemskih preporuka

U meniju **Podaci** > **Ujednačavanje** > **Objedinjavanje**, birate i izuzimate atribute za objedinjavanje u okviru vašeg ujednačenog entiteta korisničkog profila. Ujednačeni korisnički profil je rezultat procesa ujednačavanja podataka. Sistem automatski spaja neke atribute.

Da biste videli atribute koji su uključeni u jedan od vaših automatski objedinjenih atributa, odaberite taj objedinjeni atribut na kartici **Polja za klijente** tabele. Atributi koji čine taj objedinjeni atribut prikazaće se u dva nova reda ispod objedinjenog atributa.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Odvojite, preimenujte, izuzmite i uredite objedinjena polja

Možete da promenite način na koji sistem obrađuje objedinjene atribute da generiše ujednačeni korisnički profil. Izaberite **Prikaži više** i izaberite šta želite da promenite.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opcije u padajućem meniju „Prikaži još“ za upravljanje objedinjenim atributima.":::

Pogledajte sledeće odeljke za više informacija.

## <a name="separate-merged-fields"></a>Razdvajanje objedinjenih polja

Da biste razdvojili objedinjena polja, pronađite atribut u tabeli. Razdvojena polja se prikazuju kao pojedinačne tačke podataka na objedinjenom korisničkom profilu. 

1. Izaberite objedinjeno polje.
  
1. Izaberite **Prikaži više** i birajte **Razdvoji polja**.
 
1. Potvrdite razdvajanje.

1. Izaberite **Sačuvaj** i **Pokreni** da biste obradili promene.

## <a name="rename-merged-fields"></a>Preimenovanje objedinjenih polja

Promenite ime za prikaz objedinjenih atributa. Ne možete da promenite naziv izlaznog entiteta.

1. Izaberite objedinjeno polje.
  
1. Izaberite **Prikaži više** i birajte **Preimenuj**.

1. Potvrdite promenjeno ime za prikaz. 

1. Izaberite **Sačuvaj** i **Pokreni** da biste obradili promene.

## <a name="exclude-merged-fields"></a>Izuzimanje objedinjenih polja

Izuzmite atribut iz ujednačenog korisničkog profila. Ako se polje koristi u drugim procesima, na primer u segmentu, uklonite ga iz tih procesa pre nego što ga izuzmete iz korisničkog profila. 

1. Izaberite spojeno polje.
  
1. Izaberite **Prikaži više** i birajte **Izuzmi**.

1. Potvrdite izuzimanje.

1. Izaberite **Sačuvaj** i **Pokreni** da biste obradili promene. 

Na stranici **Objedinjavanje**, izaberite **Izuzeta polja** da biste videli listu svih izuzetih polja. Ovo okno vam omogućava da ponovo dodate izuzeta polja.

## <a name="edit-a-merged-field"></a>Uredite spojeno polje

1.  Izaberite spojeno polje.

1.  Izaberite **Prikaži više** i birajte **Uredi**.

1.  Navedite kako da kombinujete ili spojite polja iz jedne od tri opcije:
    - **Značaj**: identifikuje pobedničku vrednost na osnovu ranga važnosti navedenog za polja koja učestvuju. To je podrazumevana opcija objedinjavanja. Izaberite **Pomeri nagore/nadole** da biste podesili rang važnosti.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Opcija važnosti u dijalogu polja za spajanje."::: 
    - **Najnoviji**: identifikuje dobitnu vrednost na osnovu najnovijeg datuma. Zahteva datum ili numeričko polje za svaki entitet koji učestvuje u opsegu polja za spajanje da bi definisao nedavnu aktivnost.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Opcija nedavne aktivnosti u dijalogu polja za spajanje.":::
    - **Poslednji**: identifikuje dobitnu vrednost na osnovu najdavnije aktivnosti. Zahteva datum ili numeričko polje za svaki entitet koji učestvuje u opsegu polja za spajanje da bi definisao nedavnu aktivnost.

1.  Možete dodati još polja za učešće u procesu spajanja.

1.  Spojeno polje možete preimenovati.

1. Izaberite **Gotovo** da primenite promene.

1. Izaberite **Sačuvaj** i **Pokreni** da biste obradili promene. 

## <a name="manually-combine-fields"></a>Ručno kombinovanje polja

Ručno navedite objedinjeni atribut. 

1. Na stranici **Objedinjavanje**, izaberite **Kombinuj polja**.

1. Navedite politiku pobednika spajanja u padajućoj listi **Kombinuj polja prema**.

1. Odaberite polje koje želite da dodate. Izaberite **Dodaj polja** da biste kombinovali više polja.

1. Navedite **Naziv** i jedan **Naziv izlaznog polja**.

1. Izaberite **Gotovo** da primenite promene.

1. Izaberite **Sačuvaj** i **Pokreni** da biste obradili promene. 

## <a name="change-the-order-of-fields"></a>Promena redosleda polja

Neki entiteti sadrže više detalja od drugih. Ako entitet uključuje najnovije podatke o polju, možete mu dati prioritet nad ostalim entitetima pri objedinjavanju vrednosti.

1. Izaberite objedinjeno polje.
  
1. Izaberite **Prikaži više** i birajte **Uredi**.

1. U oknu **Kombinuj polja**, izaberite **Pomeri nagore/nadole** da biste postavili redosled ili ih prevucite i ispustite u željeni položaj.

1. Potvrdite promenu.

1. Izaberite **Sačuvaj** i **Pokreni** da biste obradili promene.

## <a name="configure-customer-id-generation"></a>Konfigurisanje generisanja ID-a klijenta 

Nakon konfigurisanja spajanja polja možete definisati kako da generišete CustomerId vrednosti, jedinstvene identifikatore profila klijenta. Korak spajanja u procesu spajanja podataka generiše jedinstveni identifikator profila klijenata. Identifikator je CustomerId u entitetu *Klijent* koji je rezultat procesa objedinjavanja podataka. 

CustomerId u entitetu Klijent zasnovan je na hešu prve vrednosti primarnih ključeva koji nemaju vrednost „null“. Ovi ključevi potiču od entiteta koji se koriste u fazi podudaranja i spajanja i na njih utiče redosled podudaranja. Tako se generisani CustomerID može promeniti kada se promeni vrednost primarnog ključa u primarnom entitetu redosleda podudaranja. Dakle, vrednost primarnog ključa možda ne predstavlja uvek istog klijenta.

Konfigurisanje stabilnog ID-a klijenta vam omogućava da izbegnete takvo ponašanje.

**Konfigurisanje jedinstvenog ID-a klijenta**

1. Idite na **Objedini** > **Spoji**.

1. Izaberite karticu **Ključevi**. 

1. Zadržite pokazivač na redu **CustomerId** i izaberite opciju **Konfiguriši**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontrola za prilagođavanje generisanja ID-a.":::

1. Izaberite do pet polja koja će sadržati jedinstveni ID klijenta i koja su stabilnija. Zapisi koji ne odgovaraju vašoj konfiguraciji umesto toga koriste sistemski konfigurisan ID.  

1. Izaberite **Gotovo** i pokrenite proces spajanja da biste primenili promene.

## <a name="group-profiles-into-households-or-clusters"></a>Grupišite profile u domaćinstva ili klastere

Kao deo procesa konfiguracije generisanja profila klijenta, možete definisati pravila za grupisanje povezanih profila u klaster. Trenutno postoje dve vrste klastera – domaćinstva i prilagođeni klasteri. Sistem automatski bira domaćinstvo sa unapred definisanim pravilima ako entitet *Klijent* sadrži semantička polja *Person.LastName* i *Location.Address*. Takođe možete kreirati klaster sa sopstvenim pravilima i uslovima, slično [pravilima podudaranja](match-entities.md#define-rules-for-match-pairs).

**Definisanje domaćinstva ili klastera**

1. Idite na **Objedini** > **Spoji**.

1. Na kartici **Objedini**, izaberite **Napredno** > **Kreiraj klaster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Kontrola za kreiranje novog klastera.":::

1. Birajte između klastera **Domaćinstvo** ili **Prilagođeni**. Ako semantička polja *Person.LastName* i *Location.Address* postoje u entitetu *Klijent*, domaćinstvo se automatski bira.

1. Unesite naziv klastera i izaberite **Gotovo**.

1. Izaberite karticu **Klasteri** da biste pronašli klaster koji ste kreirali.

1. Navedite pravila i uslove za definisanje klastera.

1. Izaberite **Pokreni** da biste pokrenuli proces objedinjavanja i kreirali klaster.

Nakon pokretanja procesa objedinjavanja, identifikatori klastera se dodaju kao nova polja u entitetu *Klijent*.

## <a name="run-your-merge"></a>Pokrenite svoje spajanje

Bez obzira da li ručno spajate atribute ili puštate sistem da ih spaja, uvek možete pokrenuti spajanje. Izaberite **Pokreni** na stranici **Spajanje** da započnete proces.

> [!div class="mx-imgBorder"]
> ![Čuvanje i pokretanje spajanja podataka.](media/configure-data-merge-save-run.png "Spajanje podataka Sačuvaj i Pokreni")

Odaberite **Pokreni samo objedinjavanje** ako želite da se izlaz odrazi samo u ujednačenom entitetu klijenta. Posledični procesi će se osvežiti kao [definisani u rasporedu osvežavanja](system.md#schedule-tab).

Odaberite **Pokreni objedinjavanje i posledične procese** da osvežite sistem sa vašim promenama. Svi procesi, uključujući obogaćivanje, segmente i mere automatski će se ponovo pokrenuti. Po završetku svih posledičnih procesa, korisnički profili odražavaju sve promene koje ste napravili.

Da biste uneli više promena i ponovo pokrenuli korak, možete da otkažete objedinjavanje u toku. Izaberite tekst **Osvežavanje u toku...** i izaberite **Otkaži posao** u bočnom oknu koje se prikazuje.

> [!TIP]
> Nakon pokretanja procesa spajanja, izaberite status procesa da biste otvorili okno **Detalji o zadatku**. On daje pregled vremena obrade, poslednjeg datuma obrade i svih grešaka i upozorenja povezanih sa zadatkom. Izaberite **Vidi detalje** da biste videli koji su entiteti učestvovali u procesu podudaranja, da li je rešavanje sukoba uspelo i da li su ažuriranja uspešno objavljena.  
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Detaljno analizirajte putanju kako biste pristupili detaljima o obradi sa veze statusa zadatka.":::

## <a name="next-step"></a>Sledeći korak

Konfigurišite [aktivnosti](activities.md), [obogaćivanje](enrichment-hub.md) ili [relacije](relationships.md) da biste ostvarili bolji uvid u klijente.

Ako ste već konfigurisali aktivnosti, obogaćivanje ili segmente, oni će se automatski obraditi kako bi se koristili najnoviji podaci o klijentima.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
