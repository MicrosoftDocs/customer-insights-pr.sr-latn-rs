---
title: Kreiranje segmenata pomoću alatke za pravljenje segmenata
description: Napravite segmente klijenata da biste ih grupisali na osnovu različitih atributa.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494519"
---
# <a name="create-segments"></a>Kreiranje segmenata

Definišite složene filtere oko jedinstvenog entiteta klijenta i sa njim povezanih entiteta. Svaki segment nakon obrade kreira skup korisničkih zapisa koje možete da izvoziti i za koje možete da preduzimate neke korake. Segmentima se upravlja na stranici **Segmenti**. Možete da [kreirate nove segmente](#create-a-new-segment) pomoću [alatke za pravljenje segmenata](#segment-builder) ili da [kreirate brze segmente](#quick-segments) iz drugih oblasti aplikacije.

## <a name="segment-builder"></a>Alatka za pravljenje segmenata

Sledeća slika ilustruje različite aspekte alatke za pravljenje segmenata. Prikazuje segment koji rezultira grupom klijenata. Klijenti su naručivali robu u određenom vremenskom okviru i prikupili brojne nagradne bodove ili potrošili određenu količinu novca. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementi alatke za kreiranje segmenata." lightbox="media/segment-builder-overview.png":::

1 – Organizujte segment sa pravilima i podpravilima. Svako pravilo ili podpravilo se sastoji od uslova. Kombinujte uslove sa logičkim operatorima

2 – Odaberite [putanju relacije](relationships.md) između entiteta koja se primenjuje na pravilo. Putanja relacije određuje koji se atributi mogu koristiti u uslovu.

3 – Upravljajte pravilima i podpravilima. Promenite položaj pravila ili ga izbrišite.

4 – Dodajte uslove i izgradite odgovarajući nivo ugnežđavanja pomoću podpravila.

5 – Primenite zadate operacije na povezana pravila.

6 – Koristite okno sa atributima da biste dodali dostupne atribute entiteta ili kreirali uslove na osnovu atributa. Okno prikazuje listu entiteta i atributa, na osnovu izabrane putanje relacija, koji su dostupni za izabrano pravilo.

7 – Dodajte uslove na osnovu atributa u postojeća pravila i podpravila ili ih dodajte u novo pravilo.

8 – Opozovite i ponovite promene tokom izgradnje segmenta.

Gornji primer ilustruje mogućnost segmentacije. Definisali smo segment za klijente koji su na mreži kupili robu u vrednosti od najmanje 500 USD *i* imaju interesovanje za razvoj softvera.

## <a name="create-a-new-segment"></a>Kreirajte novi segment

Postoji više načina za kreiranje novog segmenta. Ovaj odeljak opisuje kako da napravite svoj segment od nule. Takođe možete da kreirate *brzi segment* na osnovu postojećih entiteta ili iskoristite modele mašinskog učenja da biste dobili *predložene segmente*. Još informacija: [Pregled segmenata](segments.md).

Dok pravite segment, možete da sačuvate radnu verziju. Biće sačuvana kao neaktivni segment i ne može se aktivirati kao završena sa važećom konfiguracijom.

1. Idite na stranicu **Segmenti**.

1. Izaberite **Novo** > **Napravite svoj**.

1. Na stranici za pravljenje segmenata definišete prvo pravilo. Pravilo se sastoji od jednog ili više uslova i definiše skup klijenata.

1. U odeljku **Rule1**, odaberite atribut entiteta prema kome želite da filtrirate klijente. Postoje dva načina izbora atributa: 
   - Pregledajte listu dostupnih entiteta i atributa u oknu **Dodaj u pravilo** i izaberite ikonu **+** pored atributa za dodavanje. Odaberite da li želite da dodate atribut postojećem pravilu ili da ga koristite za kreiranje novog pravila.
   - Unesite naziv atributa u odeljak pravila da biste videli odgovarajuće predloge.

1. Odaberite operatore kako biste naveli podudarne vrednosti uslova. Atribut može imati jedan od četiri tipa podataka kao vrednost: numerički, niz, datum ili Bulov. U zavisnosti od tipa podataka atributa, različiti operatori su dostupni za određivanje uslova. 

1. Izaberite **Dodaj uslov** za dodavanje više uslova u pravilo. Da biste kreirali pravilo u okviru trenutnog pravila, izaberite **Dodaj potpravilo**.

1. Ako pravilo koristi druge entitete osim entiteta *Klijent*, morate postaviti putanju relacija. Putanja relacija je obavezna kako bi obaveštavala sistem preko kojih relacija želite da pristupite objedinjenom entitetu klijenta. Izaberite **Podešavanje putanje relacija** da biste mapirali izabrani entitet u objedinjeni entitet klijenta. Ako postoji samo jedna moguća putanja relacija, sistem će je automatski izabrati. Različite putanje relacija mogu postići različite rezultate. Svako pravilo može imati svoju putanju relacija.

   :::image type="content" source="media/relationship-path.png" alt-text="Potencijalna putanja relacija pri kreiranju pravila zasnovanog na entitetu mapiranom u jedinstveni entitet klijenta.":::

   Na primer, entitet *eCommerce_eCommercePurchases* na snimku ekrana ima četiri opcije za mapiranje na entitet *Klijent*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Klijent
   - eCommerce_eCommercePurchases > Klijent
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Klijent
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Klijent Kada birate poslednju opciju, možemo da obuhvatimo atribute iz svih navedenih entiteta u uslovima pravila. Verovatno ćemo dobiti manje rezultata jer podudarni zapisi o klijentima moraju biti deo svih entiteta. U ovom primeru, kupili su robu putem e-trgovine (*eCommerce_eCommercePurchases*), na prodajnom mestu (*POS_posPurchases*) i učestvuju u našem programu lojalnosti (*loyaltyScheme_loyCustomers*). Prilikom odabira druge opcije možemo odabrati samo atribute iz entiteta *eCommerce_eCommercePurchases* i *Klijent*. Ovo verovatno dovodi do većeg broja profila klijenata.

1. Ako u pravilu imate više uslova, možete odabrati koji ih logički operator povezuje.

   - **I** operator: svi uslovi moraju biti ispunjeni da bi se zapis uključio u segment. Ova opcija je najkorisnija kada definišete uslove u različitim entitetima.

   - **ILI** operator: jedan od uslova mora biti ispunjen da bi se zapis uključio u segment. Ova opcija je najkorisnija kada definišete više uslova u istom entitetu.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Pravilo sa dva I uslova.":::

   Prilikom korišćenja operatora ILI, svi uslovi moraju biti zasnovani na entitetima uključenim u putanju relacija.

   1. Možete da kreirate više pravila da biste kreirali različite skupove zapisa o klijentima. Možete kombinovati grupe da biste uključili klijente potrebne za vaš poslovni predmet. Da biste kreirali novo pravilo, izaberite **Dodaj pravilo**. Konkretno, ako ne možete da uključite entitet u pravilo zbog navedene putanje relacija, morate da kreirate novo pravilo da biste izabrali atribute koji ga obrazuju.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Dodajte novo pravilo segmentu i izaberite zadati operator.":::

   1. Izaberite jedan od operatora skupova: **Unija**, **Presek** ili **Razlika**.

   - **Unija** objedinjuje dve grupe.

   - **Presek** preklapa dve grupe. Samo podaci koji *su zajednički* za obe grupe zadržavaju se u objedinjenoj grupi.

   - **Osim** kombinuje dve grupe. Samo podaci u grupi A koji *nisu zajednički* sa podacima iz grupe B zadržavaju se.

1. Podrazumevano, segmenti generišu izlazni entitet koji sadrži sve atribute profila klijenata koji odgovaraju definisanim filterima. Ako se segment zasniva na drugim entitetima osim na entitetu *Klijent*, izlaznom entitetu možete dodati više atributa iz tih entiteta. Izaberite **Atributi projekta** da biste odabrali atribute koji će biti dodati izlaznom entitetu.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Primer projektovanih atributa izabranih u bočnom oknu za dodavanje izlaznom entitetu.":::
  
   Primer: segment se zasniva na entitetu koji sadrži podatke o kupovini, koji su povezani sa entitetom *Klijent*. Ovaj segment traži sve klijente iz Španije koji su kupili robu u tekućoj godini. Možete odabrati da dodate atribute poput cene robe ili datuma kupovine svim odgovarajućim zapisima klijenata u izlaznom entitetu. Ove informacije mogu biti korisne za analizu sezonskih korelacija u odnosu na ukupnu potrošnju.

   > [!NOTE]
   > - Projektovani atributi rade samo za entitete koji imaju odnos „jedan prema više“ sa entitetom klijenta. Na primer, jedan klijent može imati više pretplata.
   > - Atribute možete projektovati samo iz entiteta koji se koristi u svakom pravilu upita segmenta koji pravite.
   > - Projektovani atributi uzimaju se u obzir kada se koriste operatori skupova.

1. Pre nego što sačuvate i pokrenete segment, izaberite **Izmeni detalje** pored naziva segmenta. Navedite naziv svog segmenta i ažurirajte predloženi **Naziv izlaznog entiteta** za segment. U segment možete dodati i opis.

1. Izaberite **Pokreni** da biste sačuvali i obradili segment ako su svi zahtevi potvrđeni. U suprotnom, biće sačuvan kao neaktivna radna verzija segmenta.

1. Izaberite **Nazad na segmente** da biste se vratili na stranicu **Segmenti**.

> [!TIP]
> - Alatka za pravljenje segmenata neće predlagati važeće vrednosti entiteta prilikom postavljanja operatora za uslove. Možete da odete na **Podaci** > **Entiteti** i da preuzmite podatke entiteta da biste videli koje su vrednosti dostupne.
> - Uslovi zasnovani na datumima vam omogućavaju prebacivanje između fiksnih datuma i promenljivog vremenskog perioda.
> - Ako imate više pravila za segment, videćete plavu traku oko pravila koje uređujete.
> - Pravila i uslove možete premestiti na druga mesta u definiciji segmenta. Izaberite [...] pored pravila ili uslova i odaberite kako i gde da ga premestite.
> - Kontrole **Poništi** i **Ponovi** na komandnoj traci vam omogućavaju da vratite promene.

## <a name="quick-segments"></a>Brzi segmenti

Brzi segmenti vam omogućavaju brzu izgradnju jednostavnih segmenata pomoću jednog operatora za brže uvide.

1. Na stranici **Segmenti**, izaberite **Novo** > **Kreiraj iz**.

   - Izaberite opciju **Profili** da izgradite segment koji je zasnovan na entitetu *objedinjenog klijenta*.
   - Izaberite opciju **Mere** za izgradnju segmenta oko mera koje ste prethodno kreirali.
   - Izaberite opciju **Obaveštavanje** da izgradite segment oko jednog od izlaznih entiteta koje ste generisali koristeći mogućnosti **Predviđanja** ili **Prilagođeni modeli**.

2. U dijalogu **Novi brzi segment** izaberite atribut iz padajuće liste **Polje**.

3. Sistem će vam pružiti više uvida koji će vam pomoći da kreirate bolje segmente svojih klijenata.
   - Za kategorijska polja prikazaćemo 10 glavnih brojeva klijenta. Odaberite **Vrednost** i izabrali **Pregled**.

   - Za numerički atribut, sistem će pokazati koja vrednost atributa spada ispod svakog procenta klijenta. Odaberite **Operator** i **Vrednost**, a zatim izaberite **Pregled**.

4. Sistem će vam pružiti **Procenjenu veličinu segmenta**. Možete odabrati da li da generišete segment koji ste definisali ili da ga prvo pregledate kako biste dobili drugu veličinu segmenta.

    > [!div class="mx-imgBorder"]
    > ![Naziv i procena za brzi segment.](media/quick-segment-name.png "Naziv i procena za brzi segment")

5. Navedite **Naziv** za segment. Opcionalno, navedite **Ime za prikaz**.

6. Izaberite **Sačuvaj** da biste kreirali segment.

7. Nakon završetka obrade segmenta, možete ga pregledati kao i bilo koji drugi segment koji ste kreirali.

## <a name="next-steps"></a>Sledeći koraci

[Izvezite segment](export-destinations.md) i istražite članak [Integracija korisničke kartice](customer-card-add-in.md) da biste koristili segmente u drugim aplikacijama.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
