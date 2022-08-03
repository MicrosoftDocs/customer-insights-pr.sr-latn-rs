---
title: Kreiranje složenih segmenata pomoću izrade segmenata
description: Koristite izradu segmenata da biste kreirali složene segmente kupaca grupišući ih na osnovu različitih atributa.
ms.date: 03/25/2022
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
ms.openlocfilehash: cde373cd65e296675e1b3c92f3024e1093853842
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170652"
---
# <a name="create-complex-segments-with-segment-builder"></a>Kreiranje složenih segmenata pomoću izrade segmenata

Definišite složene filtere oko jedinstvenog entiteta klijenta i sa njim povezanih entiteta. Svaki segment nakon obrade kreira skup korisničkih zapisa koje možete da izvoziti i za koje možete da preduzimate neke korake.

> [!TIP]
> Segmenti zasnovani na **individualnim klijentima** automatski uključuju dostupne kontakt informacije za članove segmenta. U okruženjima za **poslovne naloge**, segmenti se zasnivaju na nalozima (preduzeća ili podružnice). Da biste uključili kontakt informacije u segment, koristite funkcionalnost **Atributi projekta** u alatki za pravljenje segmenata. Uverite se da su izvori podataka kontakta [semantički mapirani u entitet ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

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

1. Izaberite **uredi detalje** pored segmenta bez naslova. Navedite naziv svog segmenta i ažurirajte predloženi **Naziv izlaznog entiteta** za segment. Opcionalno, dodajte opis [i](work-with-tags-columns.md#manage-tags) oznake segmentu.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dijalog &quot;Uređivanje detalja&quot;.":::

1. U odeljku **Pravilo1** odaberite atribut entiteta po kojem želite da filtrirate kupce. Postoje dva načina izbora atributa:
   - Pregledajte listu dostupnih entiteta i atributa u oknu **Dodaj u pravilo** i izaberite ikonu **+** pored atributa za dodavanje. Odaberite da li želite da dodate atribut postojećem pravilu ili da ga koristite za kreiranje novog pravila.
   - Unesite naziv atributa u odeljak pravila da biste videli odgovarajuće predloge.

1. Odaberite operatore kako biste naveli podudarne vrednosti uslova. Atribut može imati jedan od četiri tipa podataka kao vrednost: numerički, niz, datum ili Bulov. U zavisnosti od tipa podataka atributa, različiti operatori su dostupni za određivanje uslova. Za segmente sa poslovnim nalozima, na raspolaganju su dva posebna operatera za uključivanje potencijalnih hijerarhija između unetih naloga. Koristite operatore *podređeno za* i *nadređeno za* da biste uključili povezane naloge.

1. Izaberite **Dodaj uslov** za dodavanje više uslova u pravilo. Da biste kreirali pravilo u okviru trenutnog pravila, izaberite **Dodaj potpravilo**.

1. Ako pravilo koristi druge entitete od entiteta kupca *,* izaberite **stavku Postavi putanju relacije** da biste mapirali izabrani entitet u objedinjeni entitet kupca. Ako postoji samo jedna moguća putanja relacije, sistem je automatski bira. Različite [putanje relacija mogu](relationships.md#relationship-paths) dati različite rezultate. Svako pravilo može imati svoju putanju relacija.

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

1. Po podrazumevanoj vrednosti, izlazni entitet će automatski sadržati sve atribute profila klijenata koji se podudaraju sa definisanim filterima. Ako je segment zasnovan na drugim entitetima osim na entitetu *kupca*, **izaberite atribute** projekta da biste izlaznom entitetu dodali više atributa iz ovih entiteta.

   > [!IMPORTANT]
   > Za segmente zasnovane na poslovnim nalozima, detalji jednog ili više kontakata *svakog konta iz entiteta ContactProfile* moraju biti uključeni u segment da bi se omogućilo aktiviranje ili izvoz tog segmenta na odredišta koja zahtevaju kontakt informacije. Više informacija o entitetu *ContactProfile* potražite u članku [Semantička mapiranja](semantic-mappings.md).
   > Uzorak izlaza za segment zasnovan na poslovnim kontaktima sa projektovanim atributima kontakata može da izgleda ovako:
   >
   > |ID  |Naziv naloga  |Prihod  |Ime kontakta  | Uloga kontakta|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100K | [Ebi Mos, Rut Soto]  | [generalni direktor, upravljanje nabavkama]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Primer projektovanih atributa izabranih u bočnom oknu za dodavanje izlaznom entitetu.":::
  
   Na primer: Segment se zasniva na entitetu koji sadrži podatke o kupovini, koji su povezani sa entitetom *Klijent*. Ovaj segment traži sve klijente iz Španije koji su kupili robu u tekućoj godini. Možete odabrati da u izlazni entitet upišete atribute kao što su cena robe ili datum nabavke svim odgovarajućim zapisima kupaca. Ove informacije mogu biti korisne za analizu sezonskih korelacija u odnosu na ukupnu potrošnju.

   > [!NOTE]
   > - **Atributi projekta** funkcioniše samo za entitete koji imaju odnos jedan prema više sa entitetom klijenta. Na primer, jedan klijent može imati više pretplata.
   > - Ako je atribut koji želite da projektujete udaljen više od jednog koraka od entiteta *Klijent*, kako je definisano relacijom, taj atribut treba koristiti u svakom pravilu upita segmenta koji pravite.
   > - Ako je atribut koji želite da projektujete udaljen samo jedan korak od entiteta *Klijent*, taj atribut ne treba biti prisutan u svakom pravilu upita segmenta koji pravite.
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
