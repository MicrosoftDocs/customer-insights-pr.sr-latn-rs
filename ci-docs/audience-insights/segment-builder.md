---
title: Kreiranje segmenata i upravljanje njima
description: Napravite segmente klijenata da biste ih grupisali na osnovu različitih atributa.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a19661abea42618ef1848110c05d635a925c68f
ms.sourcegitcommit: c45b094072cbe3fbf61d1e9e7d220e1f29ffebd0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/29/2021
ms.locfileid: "6685479"
---
# <a name="create-and-manage-segments"></a>Kreiranje segmenata i upravljanje njima

> [!IMPORTANT]
> U iskustvo kreiranja segmenata u septembru 2021. uvedeno je nekoliko promena: 
> - Alatka za pravljenje segmenata će izgledati malo drugačije sa restilizovanim elementima i poboljšanim tokom korisnika.
> - U alatki za kreiranje segmenata omogućeni su novi operatori datuma i poboljšani birač datuma.
> - Moći ćete da dodajete ili uklanjate uslove i pravila iz segmenata. 
> - Ugnežđena pravila koja počinju sa uslovom ILI postaće dostupna. Više vam nije potreban uslov I na najudaljenijem sloju.
> - Bočno okno za izbor atributa biće stalno dostupno.
> - Opcija za izbor putanja odnosa između entiteta.
> Da biste isprobali novu alatku za kreiranje segmenata, pošaljite poruku e-pošte sa naslovom „Zahtev za omogućavanje alatke za pravljenje novih segmenata“ na cihelp [at] microsoft.com. Uključite naziv vaše organizacije i ID Sandbox okruženja.

Definišite složene filtere oko jedinstvenog entiteta klijenta i sa njim povezanih entiteta. Svaki segment nakon obrade kreira skup korisničkih zapisa koje možete da izvoziti i za koje možete da preduzimate neke korake. Segmentima se upravlja na stranici **Segmenti**. 

Sledeći primer ilustruje korišćenje mogućnosti segmentacije. Definisali smo segment za klijente koji su naručili robu za najmanje 500 USD u poslednjih 90 dana *i* koji su bili uključeni u poziv korisničke službe koji je prosleđen.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Snimak ekrana korisničkog interfejsa kreatora segmenata sa dve grupe koje određuju segment klijenata.":::

## <a name="create-a-new-segment"></a>Kreirajte novi segment

Postoji više načina za kreiranje novog segmenta. Ovaj odeljak opisuje kako se kreira *prazan segment* ispočetka. Takođe možete da kreirate *brzi segment* na osnovu postojećih entiteta ili iskoristite modele mašinskog učenja da biste dobili *predložene segmente*. Još informacija: [Pregled segmenata](segments.md).

Dok pravite segment, možete da sačuvate radnu verziju. Biće sačuvana kao neaktivni segment i ne može se aktivirati kao završena sa važećom konfiguracijom.

1. Idite na stranicu **Segmenti**.

1. Izaberite **Novo** > **Prazan segment**.

1. U oknu **Novi segment**, odaberite vrstu segmenta:

   - **Dinamički segmenti** se [osvežavaju](segments.md#refresh-segments) po redovnom rasporedu.
   - **Statički segmenti** se pokreću jednom kada ih kreirate.

1. Navedite **Izlazni naziv entiteta** za segment. Opcionalno, unesite ime za prikaz i opis koji pomaže u prepoznavanju segmenta.

1. Izaberite **Sledeće** da dođete na stranicu **Graditelj segmenata** na kojoj definišete grupu. Grupa je skup klijenata.

1. Odaberite entitet koji obuhvata atribute po kojima želite da segmentirate.

1. Odaberite atribut po segmentu. Ovaj atribut može imati jedan od četiri tipa vrednosti: numerički, niska, datum ili logički.

1. Odaberite operator i vrednost za izabrani atribut.

   > [!div class="mx-imgBorder"]
   > ![Prilagođeni filter grupe.](media/customer-group-numbers.png "Filter grupe klijenata")

   |Broj |Definicija  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribut          |
   |3    |Operator         |
   |4    |Vrednost         |

   1. Da biste grupi dodali više uslova, možete da koristite dva logička operatora:

      - Operator **I**: Oba uslova moraju da budu ispunjena kao deo procesa segmentacije. Ova opcija je najkorisnija kada definišete uslove u različitim entitetima.

      - Operator **ILI**: Bilo koji od uslova mora biti ispunjen kao deo procesa segmentacije. Ova opcija je najkorisnija kada definišete više uslova u istom entitetu.

      > [!div class="mx-imgBorder"]
      > ![Operator ILI gde je potrebno ispuniti bilo koji uslov.](media/segmentation-either-condition.png "Operator ILI gde je potrebno ispuniti bilo koji uslov")

      Trenutno je moguće ugnezditi operator **ILI** unutar operatora **I**, ali ne i obrnuto.

   1. Svaka grupa se podudara sa skupom klijenata. Možete kombinovati grupe da biste uključili klijente potrebne za vaš poslovni predmet.    
   Izaberite **Dodaj grupu**.

      > [!div class="mx-imgBorder"]
      > ![Grupa klijenata dodaj grupu.](media/customer-group-add-group.png "Grupa klijenata dodaj grupu")

   1. Izaberite jedan od operatora skupova: **Unija**, **Presek** ili **Razlika**.

   > [!div class="mx-imgBorder"]
   > ![Grupa klijenata dodaj sjedinjenje.](media/customer-group-union.png "Grupa klijenata dodaj uniju")

   - **Unija** objedinjuje dve grupe.

   - **Presek** preklapa dve grupe. Samo podaci koji *su zajednički* za obe grupe zadržavaju se u objedinjenoj grupi.

   - **Osim** kombinuje dve grupe. Samo podaci u grupi A koji *nisu zajednički* sa podacima iz grupe B zadržavaju se.

1. Ako je entitet povezan putem objedinjenog entiteta klijenta putem [odnosa](relationships.md), morate definisati putanju odnosa da biste kreirali važeći segment. Dodajte entitete iz putanje odnosa dok ne budete mogli da izaberete entitet **Klijent: CustomerInsights** iz padajuće liste. Zatim odaberite **Svi zapisi** za svaki korak.

   > [!div class="mx-imgBorder"]
   > ![Putanja odnosa tokom kreiranja segmenta.](media/segments-multiple-relationships.png "Putanja odnosa tokom kreiranja segmenta")

1. Podrazumevano, segmenti generišu izlazni entitet koji sadrži sve atribute korisničkih profila koji se podudaraju sa definisanim filterima. Ako se segment zasniva na drugim entitetima osim na entitetu *Klijent*, izlaznom entitetu možete dodati više atributa iz tih entiteta. Izaberite **Atributi projekta** da biste odabrali atribute koji će biti dodati izlaznom entitetu.  
  
   Primer: Segment se zasniva na entitetu koji sadrži podatke o aktivnostima klijenata koji su povezani sa entitetom *Klijent*. Segment traži sve klijente koji su pozvali tehničku podršku u poslednjih 60 dana. Možete odabrati da dodate trajanje poziva i broj poziva svim podudarnim zapisima klijenata u izlaznom entitetu. Ove informacije mogu biti korisne za slanje e-pošte sa korisnim vezama do članaka pomoći na mreži i često postavljanih pitanja klijentima koji su često zvali.

   > [!NOTE]
   > - Projektovani atributi rade samo za entitete koji imaju odnos „jedan prema više“ sa entitetom klijenta. Na primer, jedan klijent može imati više pretplata.
   > - Atribute možete projektovati samo iz entiteta koji se koristi u svakoj grupi upita za segmente koji gradite.
   > - Projektovani atributi uzimaju se u obzir kada se koriste operatori skupova.

1. Izaberite **Sačuvaj** da biste sačuvali segment. Vaš segment će biti sačuvan i obrađen ukoliko su svi zahtevi potvrđeni. U suprotnom, biće sačuvan kao radna verzija.

1. Izaberite **Nazad na segmente** da biste se vratili na stranicu **Segmenti**.



## <a name="quick-segments"></a>Brzi segmenti

Brzi segmenti vam omogućavaju brzu izgradnju jednostavnih segmenata pomoću jednog operatora za brže uvide.

1. Na stranici **Segmenti**, izaberite **Novo** > **Kreiraj iz**.

   - Izaberite opciju **Profili** da izgradite segment koji je zasnovan na entitetu *objedinjenog klijenta*.
   - Izaberite opciju **Mere** za izgradnju segmenta oko mera koje ste prethodno kreirali.
   - Izaberite opciju **Obaveštavanje** da izgradite segment oko jednog od izlaznih entiteta koje ste generisali koristeći mogućnosti **Predviđanja** ili **Prilagođeni modeli**.

2. U dijalogu **Novi brzi segment** izaberite atribut iz padajuće liste **Polje**.

3. Sistem će vam pružiti neke dodatne uvide koji će vam pomoći da stvorite bolje segmente svojih klijenata.
   - Za kategorijska polja prikazaćemo 10 glavnih brojeva klijenta. Odaberite **Vrednost** i izabrali **Pregled**.

   - Za numerički atribut, sistem će pokazati koja vrednost atributa spada ispod svakog procenta klijenta. Odaberite **Operator** i **Vrednost**, a zatim izaberite **Pregled**.

4. Sistem će vam pružiti **Procenjenu veličinu segmenta**. Možete odabrati da li da generišete segment koji ste definisali ili da ga prvo pregledate kako biste dobili drugu veličinu segmenta.

    > [!div class="mx-imgBorder"]
    > ![Naziv i procena za brzi segment.](media/quick-segment-name.png "Naziv i procena za brzi segment")

5. Navedite **Naziv** za segment. Opcionalno, navedite **Ime za prikaz**.

6. Izaberite **Sačuvaj** da biste kreirali segment.

7. Nakon završetka obrade segmenta, možete ga pregledati kao i bilo koji drugi segment koji ste kreirali.

## <a name="next-steps"></a>Sledeći koraci

[Izvezite segment](export-destinations.md) i istražite [karticu klijenta](customer-card-add-in.md) i [konektore](export-power-bi.md) da biste dobili uvid na nivou klijenta.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
