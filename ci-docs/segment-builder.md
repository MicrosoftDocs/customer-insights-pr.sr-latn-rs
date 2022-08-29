---
title: Kreiranje složenih segmenata pomoću izrade segmenata
description: Koristite izradu segmenata da biste kreirali složene segmente kupaca grupišući ih na osnovu različitih atributa.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304766"
---
# <a name="create-complex-segments-with-segment-builder"></a>Kreiranje složenih segmenata pomoću izrade segmenata

Definišite složene filtere oko objedinjenog kupca ili objedinjenog kontakta i to su povezani entiteti. Svaki segment, nakon obrade, kreira skup zapisa kupaca ili kontakata na koje možete da izvezete i preduzmete radnje.

> [!TIP]
> Segmenti zasnovani na **individualnim klijentima** automatski uključuju dostupne kontakt informacije za članove segmenta. U **poslovnim nalozima**, ako ste [objedinili](data-unification.md) i konta i kontakte, odaberite da li je segment zasnovan na poslovnim kontaktima. Da biste izvezli na odredište koje očekuje kontakt informacije, koristite segment kontakata. Da biste izvezli na odredište koje očekuje informacije o kontima, koristite segment konta.

## <a name="segment-builder"></a>Alatka za pravljenje segmenata

Sledeća slika ilustruje različite aspekte alatke za pravljenje segmenata. Prikazuje segment koji rezultira grupom klijenata. Klijenti su naručivali robu u određenom vremenskom okviru i prikupljali nagradne bodove ili trošili određenu sumu novca.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementi alatke za kreiranje segmenata." lightbox="media/segment-builder-overview.png":::

1. Organizujte segment sa pravilima i podpravilima. Svako pravilo ili podpravilo se sastoji od uslova. Kombinujte uslove sa logičkim operatorima.

1. Odaberite [putanju relacije](relationships.md) između entiteta koja se primenjuje na pravilo. Putanja relacije određuje koji se atributi mogu koristiti u uslovu.

1. Upravljajte pravilima i podpravilima. Promenite položaj pravila ili ga izbrišite.

1. Dodajte uslove i izgradite odgovarajući nivo ugnežđavanja pomoću podpravila.

1. Primenite zadate operacije na povezana pravila.

1. Koristite okno sa atributima da biste dodali dostupne atribute entiteta ili kreirali uslove na osnovu atributa. Okno prikazuje listu entiteta i atributa, na osnovu izabrane putanje relacija, koji su dostupni za izabrano pravilo.

1. Dodajte uslove na osnovu atributa u postojeća pravila i podpravila ili ih dodajte u novo pravilo.

1. Opozovite i ponovite promene tokom izgradnje segmenta.

Gornji primer ilustruje mogućnost segmentacije. Definisali smo segment za klijente koji su na mreži kupili robu u vrednosti od najmanje 500 USD *i* imaju interesovanje za razvoj softvera.

## <a name="create-a-new-segment-with-segment-builder"></a>Kreiranje novog segmenta pomoću izrade segmenta

1. Idite na **Segmenti**.

1. Izaberite **Novo** > **Napravite svoj**. Na stranici za pravljenje segmenata definišete ili sastavljate pravila. Pravilo se sastoji od jednog ili više uslova koji definišu skup klijenata.

   > [!NOTE]
   > Za okruženja zasnovana na poslovnim nalozima **izaberite** > **novi segment naloga** ili **segment kontakata (pregled)** na osnovu tipa segmenta koji želite da kreirate. Ako je hijerarhija [naloga definisana](relationships.md#set-up-account-hierarchies) i želite da kreirate pravila za filtriranje podataka zasnovanih na podređenoj i nadređenoj relaciji, izaberite stavku **Koristi hijerarhiju? (pregled)**, izaberite hijerarhiju, a zatim **primenite**.
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="Segment izaberite okno za hijerarhiju naloga.":::

1. Izaberite **uredi detalje** pored segmenta bez naslova. Navedite naziv svog segmenta i ažurirajte predloženi **Naziv izlaznog entiteta** za segment. Opcionalno, dodajte opis [i](work-with-tags-columns.md#manage-tags) oznake segmentu.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dijalog &quot;Uređivanje detalja&quot;.":::

1. U odeljku **Pravilo1** odaberite atribut entiteta po kojem želite da filtrirate kupce. Postoje dva načina izbora atributa:
   - Pregledajte listu dostupnih entiteta i atributa u oknu **Dodaj u pravilo** i izaberite ikonu **+** pored atributa za dodavanje. Odaberite da li želite da dodate atribut postojećem pravilu ili da ga koristite za kreiranje novog pravila.
   - Unesite naziv atributa u odeljak pravila da biste videli odgovarajuće predloge.

1. Odaberite operatore kako biste naveli podudarne vrednosti uslova. Atribut može imati jedan od četiri tipa podataka kao vrednost: numerički, niz, datum ili Bulov. U zavisnosti od tipa podataka atributa, različiti operatori su dostupni za određivanje uslova.

1. Izaberite **Dodaj uslov** za dodavanje više uslova u pravilo. Da biste kreirali pravilo u okviru trenutnog pravila, izaberite **Dodaj potpravilo**.

1. Ako pravilo koristi druge entitete od entiteta *kupca* (ili *entiteta KontaktProfile za B-na-B), izaberite* stavku Postavi **putanju relacije** da biste mapirali izabrani entitet u objedinjeni entitet kupca. Ako postoji samo jedna moguća putanja relacije, sistem je automatski bira. Različite [putanje relacija mogu](relationships.md#relationship-paths) dati različite rezultate. Svako pravilo može imati svoju putanju relacija.

   :::image type="content" source="media/relationship-path.png" alt-text="Potencijalna putanja relacija pri kreiranju pravila zasnovanog na entitetu mapiranom u jedinstveni entitet klijenta.":::

1. Ako u pravilu imate više uslova, odaberite koji logički operator će ih povezati.  
   - **I** operator: svi uslovi moraju biti ispunjeni da bi se zapis uključio u segment. Koristite ovu opciju kada definišete uslove u različitim entitetima.
   - **ILI** operator: jedan od uslova mora biti ispunjen da bi se zapis uključio u segment. Koristite ovu opciju kada definišete više uslova za isti entitet.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Pravilo sa dva I uslova.":::

   Prilikom korišćenja operatora ILI, svi uslovi moraju biti zasnovani na entitetima uključenim u putanju relacija.

1. Kreirajte više pravila da biste kreirali različite skupove zapisa kupaca. Kombinujte grupe da biste uključili kupce potrebne za poslovni predmet. Preciznije, ako ne možete da uključite entitet u pravilo zbog navedene putanje relacije, kreirajte novo pravilo da biste odabrali atribute iz njega.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Dodajte novo pravilo segmentu i izaberite zadati operator.":::

   1. Izaberite **dodaj pravilo**.
   1. Izaberite jedan od operatora skupova: **Unija**, **Presek** ili **Razlika**.

      - **Unija** objedinjuje dve grupe.
      - **Presek** preklapa dve grupe. Samo podaci koji *jesu zajednički* obema grupama ostaju u objedinjenoj grupi.
      - **Osim** kombinuje dve grupe. Čuvaju se samo podaci u grupi A koji *nisu zajednički* sa podacima u grupi B.

1. Po podrazumevanoj vrednosti, izlazni entitet će automatski sadržati sve atribute profila klijenata koji se podudaraju sa definisanim filterima. U fascikli B-na-B kada koristite *entitet KontaktProfile*, ID naloga se automatski uključuje. Ako je segment zasnovan na drugim entitetima osim na entitetu *kupca* ili na uključivanju više atributa iz datoteke *"KontaktProfile",* izaberite atribute **projekta** da biste izlaznom entitetu dodali više atributa iz ovih entiteta.
 
   Na primer: Segment se zasniva na entitetu koji sadrži podatke o kupovini, koji su povezani sa entitetom *Klijent*. Ovaj segment traži sve klijente iz Španije koji su kupili robu u tekućoj godini. Možete odabrati da u izlazni entitet upišete atribute kao što su cena robe ili datum nabavke svim odgovarajućim zapisima kupaca. Ove informacije mogu biti korisne za analizu sezonskih korelacija u odnosu na ukupnu potrošnju.

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Primer projektovanih atributa izabranih u bočnom oknu za dodavanje izlaznom entitetu.":::
 
   Uzorak izlaza za segment zasnovan na poslovnim kontaktima sa projektovanim atributima kontakata može da izgleda ovako:

   |ID  |Naziv naloga  |Prihod  |Ime kontakta  | Uloga kontakta|
   |---------|---------|---------|---------|---|
   |10021     | Contoso | 100K | [Ebi Mos, Rut Soto]  | [generalni direktor, upravljanje nabavkama]

   > [!NOTE]
   > - **Atributi projekta funkcionišu** samo za entitete koji imaju relaciju "jedan-prema-više" sa *entitetom "Kupac* " ili " *KontaktProfile* ". Na primer, jedan klijent može imati više pretplata.
   > - Ako je atribut koji želite da projektujete *udaljen više od jednog skoka od entiteta "* *Kupac" ili "KontaktProfile*", kao što je definisano relacijom, taj atribut bi trebalo da se koristi u svakom pravilu upita segmenta koji gradite.
   > - Ako je atribut koji želite da projektujete samo jedan *skok od entiteta "* *Kupac" ili "KontaktProfile*", taj atribut ne mora da bude prisutan u svakom pravilu upita segmenta koji gradite.
   > - **Projektovani atributi** uzimaju se u obzir kada se koriste operatori skupova.

1. Kliknite **na dugme** "Pokreni" da biste kreirali segment. Kliknite **na** dugme Sačuvaj ako želite da zadržite trenutnu konfiguraciju i pokrenite segment kasnije. Prikazaće **se stranica "** Segmenti".

### <a name="segment-builder-tips"></a>Saveti za izradu segmenata

Kada kreirate segment pomoću izrade segmenata, imajte na umu sledeće savete:

- Alatka za pravljenje segmenata neće predlagati važeće vrednosti entiteta prilikom postavljanja operatora za uslove. Možete da odete na **Podaci** > **Entiteti** i da preuzmite podatke entiteta da biste videli koje su vrednosti dostupne.
- Uslovi zasnovani na datumima vam omogućava da se prebacujete između fiksnih datuma i plutajućeg opsega datuma.
- Ako imate više pravila za segment, pravilo koje uređujete ima vertikalnu plavu liniju pored sebe.
- Pravila i uslove možete premestiti na druga mesta u definiciji segmenta. Izaberite vertikalnu elipsu (&vellip;) pored pravila ili uslova i odaberite kako i gde ćete je premestiti.
- Kontrole **Opozovi** i **Ponovi** na komandnoj traci vam omogućavaju da vratite promene.
- Nakon kreiranja segmenta, neki segmenti vam omogućavaju [da pratite korišćenje segmenta](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Sledeći koraci

[Izvezite segment](export-destinations.md) i istražite članak [Integracija korisničke kartice](customer-card-add-in.md) da biste koristili segmente u drugim aplikacijama.

[!INCLUDE [footer-include](includes/footer-banner.md)]
