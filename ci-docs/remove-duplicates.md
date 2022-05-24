---
title: Uklanjanje duplikata pre ujedinjenja podataka
description: Drugi korak u procesu ujedinjenja je izbor zapisa koji će se voditi prilikom traženja duplikata.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 27dff3551ab411a12c273536d7431d651c48573e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/11/2022
ms.locfileid: "8742978"
---
# <a name="remove-duplicates-before-unifying-data"></a>Uklanjanje duplikata pre ujedinjenja podataka

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Ovaj korak u ujedinjenju opcionalno vam omogućava da podesite pravila za rukovanje dupliranim zapisima unutar entiteta. *Deduplication* identifikuje duplirane zapise i objedinjuje ih u jedan zapis. Izvorni zapisi se povezuju sa objedinjenim zapisom sa alternativnim ID-ovima. Ako pravila nisu konfigurisana, primenjuju se pravila definisana sistemom.

## <a name="include-enriched-entities-preview"></a>Uključi obogaćene entitete (pregled)

Ako ste obogatili entitete na nivou izvor podataka biste poboljšali rezultate ujedinjenja, izaberite ih. Više informacija potražite u članku [Obogaćivanje izvora podataka](data-sources-enrichment.md).

1. Na stranici **"Duplirani** zapisi" izaberite **stavku Korišćenje obogaćenih** entiteta na vrhu stranice.

1. Iz okna **"Korišćenje obogaćenih entiteta** " odaberite jedan ili više obogaćenih entiteta.

1. Izaberite **Gotovo**.

## <a name="define-deduplication-rules"></a>Definisanje pravila deduplikacije

1. Na stranici **"Duplirani** zapisi" izaberite entitet i izaberite opciju **Dodaj pravilo** da biste definisali pravila deduplikacije.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Snimak ekrana stranica sa dupliranim zapisima sa prikaži istaknutije":::

   1. U okno **"Dodavanje** pravila" unesite sledeće informacije:
      - **Polje izaberite**: Odaberite sa liste dostupnih polja iz entiteta koje želite da proverite da li postoje duplikati. Odaberite polja koja su verovatno jedinstvena za svakog klijenta. Na primer, adresa e-pošte ili kombinacija imena, grada i broja telefona.
      - **Normalizacija**: Izaberite neku od sledećih opcija normalizacije za izabrane atribute.
        - **Brojevi: Konvertuje** druge numeričke sisteme, kao što su rimski brojevi, u arapske brojeve. *VIII* postaje *8*.
        - **Simboli**: Uklanja sve simbole i specijalne znakove. *Glava & Ramena* postaje *GlavaRamena*.
        - **Tekst u manju sloћenja: Konvertuje sve znakove u niћa.** *VELIKA SLOVA i Slova Za Naslov* postaje *velika slova i slova za naslov*.
        - **Tip (Telefon, Ime, Adresa, Organizacija)**: Standardizuje imena, naslove, brojeve telefona, adrese itd.
        - **Unikod u ASCII**: Konvertuje unikod notaciju u ASCII znakove. */u00B2* postaje *2*.
        - **Razmak:** Uklanja sve razmake. *Zdravo svima* postaje *ZdravoSvima*.
      - **Preciznost**: Podesite nivo preciznosti da se primenjuje za ovaj uslov.
        - **Osnovno: odaberite** sa niskih (30%)*,* Srednje (60%)*,* High (80%)*i* Exact (100%)*.* Izaberite **opciju Tačno** da bi se podudarali samo sa zapisima koji se podudaraju sa 100 procenata.
        - **Prilagođeno**: Podesite procenat sa kojim zapisi moraju da se podudaraju. Sistem će se podudarati samo sa zapisima koji prelaze ovu graničnu vrednost.
      - **Ime**: Ime za pravilo.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Snimak ekrana okna za dodavanje pravila za uklanjanje duplikata.":::

   1. Opcionalno, izaberite **opciju** > **Dodaj uslov** da biste u pravilo dodali još uslova. Uslovi su povezani sa logičkim operatorom I, pa se stoga izvršavaju samo ako su ispunjeni svi uslovi.

   1. Opcionalno, **dodajte** > **izuzetak** [da biste u pravilo dodali izuzetke](match-entities.md#add-exceptions-to-a-rule). Izuzeci se koriste za rešavanje retkih slučajeva lažnih pozitivnih i lažnih negativnosti.

   1. Kliknite **na dugme** "Gotovo" da biste kreirali pravilo.

1. Opcionalno, [dodajte još pravila](#define-deduplication-rules).

1. Izaberite entitet, a zatim uredite **željene opcije objedinjavanja**.

1. U oknu " **Objedini željene** postavke":
   1. Odaberite jednu od tri opcije da biste odredili koji zapis ćete voditi ako je pronađen duplikat:
      - **Najpopunjeniji**: Identifikuje zapis sa najviše popunjenih atributa kao dobitni zapis. To je podrazumevana opcija objedinjavanja.
      - **Najnoviji**: Identifikuje dobitni zapis na osnovu najskorijeg vremena. Zahteva datum ili numeričko polje za definisanje skorašnjosti.
      - **Najkasniji**: Identifikuje dobitni zapis na osnovu najkasnijeg vremena. Zahteva datum ili numeričko polje za definisanje skorašnjosti.
      
      U slučaju nerešenog rezultata, zapis pobednika je onaj sa MAKS(PK) ili većom vrednošću primarnog ključa.
      
   1. Opcionalno, da biste definisali željene postavke objedinjavanja za pojedinačne atribute entiteta, kliknite **na dugme** "Više opcija" na dnu okna. Na primer, možete odabrati da zadržite najnoviju e-poštu i najspunjenu adresu iz različitih zapisa. Razvijte entitet da biste videli sve njegove atribute i definisali koju opciju da koristite za pojedinačne atribute. Ako odaberete opciju zasnovanu na recenciji, potrebno je da navedete i polje datuma/vremena koje definiše recencij.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Okno sa više opcija za objedinjavanje koje prikazuje nedavnu e-poštu i kompletnu adresu":::

   1. Kliknite na **dugme "** Gotovo" da biste primenili željene postavke objedinjavanja.

1. Nakon definisanja pravila deduplikacije i željenih opcija objedinjavanja, kliknite na dugme **Dalje**.
  
> [!div class="nextstepaction"]
> [Sledeći korak za jedan entitet: Objedinjavanje polja](merge-entities.md)

> [!div class="nextstepaction"]
> [Sledeći korak za više entiteta: podudarni uslovi](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Izlaz postupka uklanjanja duplikata kao entitet

Proces deduplikacije kreira novi deduplicirani entitet za svaki od izvornih entiteta. Ovi entiteti se mogu naći zajedno sa **ConflationMatchPairs:CustomerInsights** u odeljku **Sistem** na stranici **Entiteti**, pod nazivom **Deduplication_DataSource_Entity**.

Izlazni entitet uklanjanja duplikata sadrži sledeće informacije:

- ID-ovi/Ključevi
  - Primarni ključ i polja alternativnog ID-a. Polje alternativnog ID-a se sastoji od svih alternativnih ID-ova identifikovanih za zapis.
  - Polje Deduplication_GroupId prikazuje grupu ili klaster identifikovane u okviru entiteta koji grupiše sve slične zapise na osnovu navedenih polja uklanjanja duplikata. Ovo se koristi u svrhe obrade sistema. Ako nisu navedena ručna pravila za uklanjanje duplikata i ako se primenjuju sistemski definisana pravila za uklanjanje duplikata, ovo polje možda nećete pronaći u izlaznom entitetu uklanjanja duplikata.
  - Deduplication_WinnerId: Ovo polje sadrži ID pobednika iz identifikovanih grupa ili klastera. Ako je Deduplication_WinnerId ista kao vrednost primarnog ključa za zapis, to znači da je taj zapis dobitni.
- Polja koja se koriste za definisanje pravila za uklanjanje duplikata.
- Odredite pravila i ocenite polja da označite koja su od pravila za uklanjanje duplikata primenjena i koji rezultat vraća algoritam za podudaranje.

[!INCLUDE[footer-include](includes/footer-banner.md)]
