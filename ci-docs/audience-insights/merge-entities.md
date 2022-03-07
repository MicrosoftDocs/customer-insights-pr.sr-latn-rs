---
title: Objedinjavanje entiteta kod objedinjavanja podataka
description: Objedinite entitete da biste kreirali objedinjene profile klijenata.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597850"
---
# <a name="merge-entities"></a>Objedinjavanje entiteta

Faza spajanja je poslednja faza u procesu objedinjavanja podataka. Njegova svrha je usklađivanje neusaglašenih podataka. Primeri neusaglašenih podataka mogu uključivati korisničko ime koje se nalazi u dva skupa podataka, ali to se prikazuje malo drugačije u svakom („Jovan Dučić“ u odnosu na „Jovo Dučić“) ili telefonski broj koji se razlikuje u formatu (npr. 617-803-091 u odnosu na 617803091). Spajanje tih neusaglašenih tačaka podataka obavlja se na osnovu poređenja atributa.

Kada se dovrši [faza podudaranja](match-entities.md), fazu spajanja započinjete odabirom pločice **Objedini** na stranici **Ujednačavanje**.

## <a name="review-system-recommendations"></a>Pregled sistemskih preporuka

Na stranici **Spajanje** možete izabrati i isključiti atribute koji će se spajati unutar objedinjenog entiteta profila klijenta (rezultat postupka konfiguracije). Sistem automatski spaja neke atribute.

### <a name="view-merged-attributes"></a>Prikaz spojenih atributa

Da biste videli atribute koji su uključeni u jedan od vaših automatski spojenih atributa, izaberite taj spojeni atribut. Dva atributa koja čine taj spojeni atribut prikazuju se u dva nova reda ispod spojenog atributa.

> [!div class="mx-imgBorder"]
> ![Izbor spojenog atributa](media/configure-data-merge-profile-attributes.png "Izbor spojenog atributa")

### <a name="separate-merged-attributes"></a>Odvajanje spojenih atributa

Da biste odvojili ili raskinuli bilo koji od automatski spojenih atributa, pronađite atribut u tabeli **Atributi profila**.

1. Izaberite dugme sa tri tačke (...).
  
2. U padajućoj listi izaberite **Odvoji polja**.

### <a name="remove-merged-attributes"></a>Uklanjanje spojenih atributa

Da biste izuzeli atribut iz entiteta krajnjeg profila klijenta, pronađite ga u tabeli **Atributi profila**.

1. Izaberite dugme sa tri tačke (...).
  
2. U padajućoj listi izaberite **Ne objedinjuj**.

   Atribut je premešten u odeljak **Uklonjeno iz evidencije korisnika**.

## <a name="manually-add-a-merged-attribute"></a>Ručno dodajte spojeni atribut

Da biste dodali spojeni atribut, idite na stranicu **Spajanje**.

1. Izaberite **Dodavanje spojenog atributa**.

2. Navedite **Ime** da ga kasnije identifikujete na stranici **Spajanje**.

3. Opcionalno, navedite **Ime za prikaz** koje će se prikazati u objedinjenom entitetu Profil klijenta.

4. Konfigurišite **Izaberite atribute duplikata** da biste izabrali atribute koje želite da spojite iz podudarnih entiteta. Takođe možete da pretražujete atribute.

5. Podesite **Poredak po važnosti** da jedan atribut postavite iznad ostalih. Na primer, ako entitet *WebAccountCSV* uključuje najtačnije podatke o atributu *Puna imena*, možete dati prednost tom entitetu u odnosu na *ContactCSV* tako što ćete izabrati *WebAccountCSV*. Kao rezultat, *WebAccountCSV* prelazi na prvi prioritet, dok *ContactCSV* prelazi na drugi prioritet pri povlačenju vrednosti za atribut *Puno ime*.

## <a name="run-your-merge"></a>Pokrenite svoje spajanje

Bez obzira da li ručno spajate atribute ili puštate sistem da ih spaja, uvek možete pokrenuti spajanje. Izaberite **Pokreni** na stranici **Spajanje** da započnete proces.

> [!div class="mx-imgBorder"]
> ![Spajanje podataka Sačuvaj i Pokreni](media/configure-data-merge-save-run.png "Spajanje podataka Sačuvaj i Pokreni")

Da biste uneli dodatne izmene i ponovo pokrenuli korak, možete otkazati objedinjavanje koje je u toku. Izaberite tekst **Osvežavanje u toku...** i izaberite **Otkaži posao** u bočnom oknu koje se prikazuje.

Kada se tekst **Osvežavanje u toku...** promeni u **Uspešno**, objedinjavanje je dovršeno i rešilo kontradikcije u vašim podacima u skladu sa smernicama koje ste definisali. Objedinjeni i neobjedinjeni atributi su uključeni u objedinjeni entitet profila. Izuzeti atributi nisu uključeni u objedinjeni entitet profila.

Ako to nije prvi put da ste uspešno izveli objedinjavanje, svi procesi na nižem toku, uključujući obogaćivanje, segmentaciju i mere, automatski će se ponovo pokrenuti. Nakon što su svi procesi na nižem toku ponovo pokrenuti, profili klijenata odražavaju sve vaše izmene.

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies). Možete izabrati status procesa da biste videli detalje o toku celog posla. Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.

## <a name="next-step"></a>Sledeći korak

Konfigurišite [aktivnosti](activities.md), [obogaćivanje](enrichment-microsoft-graph.md) ili [relacije](relationships.md) da biste ostvarili bolji uvid u klijente.

Ako ste već konfigurisali aktivnosti, obogaćivanje ili relacije ili ako ste definisali segmente, oni će se automatski obraditi kako bi se koristili najnoviji podaci o klijentima.




[!INCLUDE[footer-include](../includes/footer-banner.md)]