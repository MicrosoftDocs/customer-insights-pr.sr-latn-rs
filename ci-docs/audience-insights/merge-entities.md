---
title: Objedinjavanje entiteta kod objedinjavanja podataka
description: Objedinite entitete da biste kreirali objedinjene profile klijenata.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305671"
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

1. Izaberite objedinjeno polje.
  
1. Izaberite **Prikaži više** i birajte **Izuzmi**.

1. Potvrdite izuzimanje.

1. Izaberite **Sačuvaj** i **Pokreni** da biste obradili promene. 

Na stranici **Objedinjavanje**, izaberite **Izuzeta polja** da biste videli listu svih izuzetih polja. Ovo okno vam omogućava da ponovo dodate izuzeta polja.

## <a name="manually-combine-fields"></a>Ručno kombinovanje polja

Ručno navedite objedinjeni atribut. 

1. Na stranici **Objedinjavanje**, izaberite **Kombinuj polja**.

1. Navedite **Naziv** i jedan **Naziv izlaznog polja**.

1. Odaberite polje koje želite da dodate. Izaberite **Dodaj polja** da biste kombinovali više polja.

1. Potvrdite izuzimanje.

1. Izaberite **Sačuvaj** i **Pokreni** da biste obradili promene. 

## <a name="change-the-order-of-fields"></a>Promena redosleda polja

Neki entiteti sadrže više detalja od drugih. Ako entitet uključuje najnovije podatke o polju, možete mu dati prioritet nad ostalim entitetima pri objedinjavanju vrednosti.

1. Izaberite objedinjeno polje.
  
1. Izaberite **Prikaži više** i birajte **Uredi**.

1. U oknu **Kombinuj polja**, izaberite **Pomeri nagore/nadole** da biste postavili redosled ili ih prevucite i ispustite u željeni položaj.

1. Potvrdite promenu.

1. Izaberite **Sačuvaj** i **Pokreni** da biste obradili promene.

## <a name="run-your-merge"></a>Pokrenite svoje spajanje

Bez obzira da li ručno spajate atribute ili puštate sistem da ih spaja, uvek možete pokrenuti spajanje. Izaberite **Pokreni** na stranici **Spajanje** da započnete proces.

> [!div class="mx-imgBorder"]
> ![Spajanje podataka Sačuvaj i Pokreni](media/configure-data-merge-save-run.png "Spajanje podataka Sačuvaj i Pokreni")

Odaberite **Pokreni samo objedinjavanje** ako želite da se izlaz odrazi samo u ujednačenom entitetu klijenta. Posledični procesi će se osvežiti kao [definisani u rasporedu osvežavanja](system.md#schedule-tab).

Odaberite **Pokreni objedinjavanje i posledične procese** da osvežite sistem sa vašim promenama. Svi procesi, uključujući obogaćivanje, segmente i mere automatski će se ponovo pokrenuti. Po završetku svih posledičnih procesa, korisnički profili odražavaju sve promene koje ste napravili.

Da biste uneli više promena i ponovo pokrenuli korak, možete da otkažete objedinjavanje u toku. Izaberite tekst **Osvežavanje u toku...** i izaberite **Otkaži posao** u bočnom oknu koje se prikazuje.

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies). Možete izabrati status procesa da biste videli detalje o toku celog posla. Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.

## <a name="next-step"></a>Sledeći korak

Konfigurišite [aktivnosti](activities.md), [obogaćivanje](enrichment-hub.md) ili [relacije](relationships.md) da biste ostvarili bolji uvid u klijente.

Ako ste već konfigurisali aktivnosti, obogaćivanje ili segmente, oni će se automatski obraditi kako bi se koristili najnoviji podaci o klijentima.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
