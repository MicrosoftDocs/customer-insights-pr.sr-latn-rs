---
title: Kreiranje segmenata pomoću alatke za pravljenje segmenata
description: Napravite segmente klijenata da biste ih grupisali na osnovu različitih atributa.
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
ms.openlocfilehash: 1a28289ecb740ab6cdfa603b2cd66376e7e8b576
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529602"
---
# <a name="create-segments"></a>Kreiranje segmenata

Definišite složene filtere oko jedinstvenog entiteta klijenta i sa njim povezanih entiteta. Svaki segment nakon obrade kreira skup korisničkih zapisa koje možete da izvoziti i za koje možete da preduzimate neke korake. Segmentima se upravlja na stranici **Segmenti**. Možete da [kreirate nove segmente](#create-a-new-segment) pomoću alatke za pravljenje segmenata ili da [kreirate brze segmente](#quick-segments) iz drugih oblasti aplikacije.

> [!TIP]
> - Brzi segmenti su podržani samo u okruženjima za **individualne klijente**.
> - Segmenti zasnovani na **individualnim klijentima** automatski uključuju dostupne kontakt informacije za članove segmenta. U okruženjima za **poslovne naloge**, segmenti se zasnivaju na nalozima (preduzeća ili podružnice). Da biste uključili kontakt informacije u segment, koristite funkcionalnost **Atributi projekta** u alatki za pravljenje segmenata. Uverite se da su izvori podataka kontakta [semantički mapirani u entitet ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Alatka za pravljenje segmenata

Sledeća slika ilustruje različite aspekte alatke za pravljenje segmenata. Prikazuje segment koji rezultira grupom klijenata. Klijenti su naručivali robu u određenom vremenskom okviru i prikupljali nagradne bodove ili trošili određenu sumu novca.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementi alatke za kreiranje segmenata." lightbox="media/segment-builder-overview.png":::

1. Organizujte segment sa pravilima i podpravilima. Svako pravilo ili podpravilo se sastoji od uslova. Kombinujte uslove sa logičkim operatorima

1. Odaberite [putanju relacije](relationships.md) između entiteta koja se primenjuje na pravilo. Putanja relacije određuje koji se atributi mogu koristiti u uslovu.

1. Upravljajte pravilima i podpravilima. Promenite položaj pravila ili ga izbrišite.

1. Dodajte uslove i izgradite odgovarajući nivo ugnežđavanja pomoću podpravila.

1. Primenite zadate operacije na povezana pravila.

1. Koristite okno sa atributima da biste dodali dostupne atribute entiteta ili kreirali uslove na osnovu atributa. Okno prikazuje listu entiteta i atributa, na osnovu izabrane putanje relacija, koji su dostupni za izabrano pravilo.

1. Dodajte uslove na osnovu atributa u postojeća pravila i podpravila ili ih dodajte u novo pravilo.

1. Opozovite i ponovite promene tokom izgradnje segmenta.

Gornji primer ilustruje mogućnost segmentacije. Definisali smo segment za klijente koji su na mreži kupili robu u vrednosti od najmanje 500 USD *i* imaju interesovanje za razvoj softvera.

## <a name="create-a-new-segment"></a>Kreirajte novi segment

Postoji više načina za kreiranje novog segmenta. Ovaj odeljak opisuje kako da napravite svoj segment od nule. Takođe možete da kreirate *brzi segment* na osnovu postojećih entiteta ili iskoristite modele mašinskog učenja da biste dobili *predložene segmente*. Više informacija potražite u [pregledu segmenata](segments.md).

Dok pravite segment, možete da sačuvate radnu verziju. U fazi radne verzije, segment se čuva kao neaktivan segment. Kada završite konfiguraciju segmenta, pokrenite je da biste aktivirali segment. Možete i da **Aktivirate** segment sa stranice **Svi segmenti**.

1. Idite na stranicu **Segmenti**.

1. Izaberite **Novo** > **Napravite svoj**.

1. Na stranici za pravljenje segmenata definišete ili sastavljate pravila. Pravilo se sastoji od jednog ili više uslova koji definišu skup klijenata.

1. U odeljku **Pravilo1** odaberite atribut entiteta po kojem želite da filtrirate kupce. Postoje dva načina izbora atributa:
   - Pregledajte listu dostupnih entiteta i atributa u oknu **Dodaj u pravilo** i izaberite ikonu **+** pored atributa za dodavanje. Odaberite da li želite da dodate atribut postojećem pravilu ili da ga koristite za kreiranje novog pravila.
   - Unesite naziv atributa u odeljak pravila da biste videli odgovarajuće predloge.

1. Odaberite operatore kako biste naveli podudarne vrednosti uslova. Atribut može imati jedan od četiri tipa podataka kao vrednost: numerički, niz, datum ili Bulov. U zavisnosti od tipa podataka atributa, različiti operatori su dostupni za određivanje uslova. Za segmente sa poslovnim nalozima, na raspolaganju su dva posebna operatera za uključivanje potencijalnih hijerarhija između unetih naloga. Koristite operatore *podređeno za* i *nadređeno za* da biste uključili povezane naloge.

1. Izaberite **Dodaj uslov** za dodavanje više uslova u pravilo. Da biste kreirali pravilo u okviru trenutnog pravila, izaberite **Dodaj potpravilo**.

1. Ako pravilo koristi druge entitete osim entiteta *Klijent*, morate postaviti putanju relacija. Putanja relacija je obavezna kako bi obaveštavala sistem preko kojih relacija želite da pristupite objedinjenom entitetu klijenta. Izaberite **Podešavanje putanje relacija** da biste mapirali izabrani entitet u objedinjeni entitet klijenta. Ako postoji samo jedna moguća putanja relacija, sistem će je automatski izabrati. Različite putanje relacija mogu postići različite rezultate. Svako pravilo može imati svoju putanju relacija.

   :::image type="content" source="media/relationship-path.png" alt-text="Potencijalna putanja relacija pri kreiranju pravila zasnovanog na entitetu mapiranom u jedinstveni entitet klijenta.":::

   Na primer, entitet *eCommerce_eCommercePurchases* na snimku ekrana ima četiri opcije za mapiranje na entitet *Klijent*:
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Klijent
   - eCommerce_eCommercePurchases > Klijent
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Klijent
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Klijent Kada birate poslednju opciju, možemo da obuhvatimo atribute iz svih navedenih entiteta u uslovima pravila. Verovatno ćemo dobiti manje rezultata jer odgovarajući zapisi o klijentima moraju biti deo svih entiteta. U ovom primeru, kupili su robu putem e-trgovine (*eCommerce_eCommercePurchases*), na prodajnom mestu (*POS_posPurchases*) i učestvuju u našem programu lojalnosti (*loyaltyScheme_loyCustomers*). Prilikom odabira druge opcije možemo odabrati samo atribute iz entiteta *eCommerce_eCommercePurchases* i *Klijent*. Ovo verovatno dovodi do većeg broja profila klijenata.

1. Ako u pravilu imate više uslova, možete odabrati koji ih logički operator povezuje.  
   - **I** operator: svi uslovi moraju biti ispunjeni da bi se zapis uključio u segment. Ova opcija je najkorisnija kada definišete uslove u različitim entitetima.
   - **ILI** operator: jedan od uslova mora biti ispunjen da bi se zapis uključio u segment. Ova opcija je najkorisnija kada definišete više uslova u istom entitetu.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Pravilo sa dva I uslova.":::

   Prilikom korišćenja operatora ILI, svi uslovi moraju biti zasnovani na entitetima uključenim u putanju relacija.

   - Možete da kreirate više pravila da biste kreirali različite skupove zapisa o klijentima. Možete kombinovati grupe da biste uključili klijente potrebne za vaš poslovni predmet. Da biste kreirali novo pravilo, izaberite **Dodaj pravilo**. Konkretno, ako ne možete da uključite entitet u pravilo zbog navedene putanje relacije, morate da kreirate novo pravilo da biste odabrali atribute koji ga formiraju.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Dodajte novo pravilo segmentu i izaberite zadati operator.":::

   - Izaberite jedan od operatora skupova: **Unija**, **Presek** ili **Razlika**.

      - **Unija** objedinjuje dve grupe.
      - **Presek** preklapa dve grupe. Samo podaci koji *jesu zajednički* obema grupama ostaju u objedinjenoj grupi.
      - **Osim** kombinuje dve grupe. Čuvaju se samo podaci u grupi A koji *nisu zajednički* sa podacima u grupi B.

1. Podrazumevano, segmenti generišu izlazni entitet koji sadrži sve atribute profila klijenata koji odgovaraju definisanim filterima. Ako se segment zasniva na drugim entitetima osim na entitetu *Klijent*, izlaznom entitetu možete dodati više atributa iz tih entiteta. Izaberite **Atributi projekta** da biste odabrali atribute koji će biti dodati izlaznom entitetu.

   > [!IMPORTANT]
   > Za segmente zasnovane na poslovnim nalozima, detalji o jednom ili više kontakata svakog naloga iz entiteta *ContactProfile* moraju biti uključeni u segment da bi se omogućili aktiviranje tog segmenta ili izvoz na odredišta za koja su potrebne kontakt informacije. Više informacija o entitetu *ContactProfile* potražite u članku [Semantička mapiranja](semantic-mappings.md).
   > Uzorak izlaza za segment zasnovan na poslovnim kontaktima sa projektovanim atributima kontakata može da izgleda ovako:
   >
   > |ID  |Naziv naloga  |Prihod  |Ime kontakta  | Uloga kontakta|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100K | [Ebi Mos, Rut Soto]  | [generalni direktor, upravljanje nabavkama]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Primer projektovanih atributa izabranih u bočnom oknu za dodavanje izlaznom entitetu.":::
  
   Na primer: Segment se zasniva na entitetu koji sadrži podatke o kupovini, koji su povezani sa entitetom *Klijent*. Ovaj segment traži sve klijente iz Španije koji su kupili robu u tekućoj godini. Možete odabrati da dodate atribute poput cene robe ili datuma kupovine svim odgovarajućim zapisima klijenata u izlaznom entitetu. Ove informacije mogu biti korisne za analizu sezonskih korelacija u odnosu na ukupnu potrošnju.

   > [!NOTE]
   > - **Atributi projekta** funkcioniše samo za entitete koji imaju odnos jedan prema više sa entitetom klijenta. Na primer, jedan klijent može imati više pretplata.
   > - Ako je atribut koji želite da projektujete udaljen više od jednog koraka od entiteta *Klijent*, kako je definisano relacijom, taj atribut treba koristiti u svakom pravilu upita segmenta koji pravite.
   > - Ako je atribut koji želite da projektujete udaljen samo jedan korak od entiteta *Klijent*, taj atribut ne treba biti prisutan u svakom pravilu upita segmenta koji pravite.
   > - **Projektovani atributi** uzimaju se u obzir kada se koriste operatori skupova.

1. Izaberite **uredi detalje** pored segmenta bez naslova. Navedite naziv svog segmenta i ažurirajte predloženi **Naziv izlaznog entiteta** za segment. Opcionalno, dodajte opis [i](work-with-tags-columns.md#manage-tags) oznake segmentu.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dijalog &quot;Uređivanje detalja&quot;.":::

1. Izaberite **Pokreni** da biste sačuvali segment, aktivirajte ga i počnite sa obradom segmenta na osnovu svih pravila i uslova. U suprotnom, biće sačuvan kao neaktivan segment.

1. Izaberite **Nazad na segmente** da biste se vratili na stranicu **Segmenti**.

1. Segment se podrazumevano kreira kao dinamički segment. To znači da se segment osvežava tokom osvežavanja sistema. Da biste [zaustavili automatsko osvežavanje](segments.md#manage-existing-segments), izaberite segment, pa odaberite opciju **Neka bude statički**. Statički segmenti se mogu [osvežiti ručno](segments.md#refresh-segments) u bilo kom trenutku.

> [!TIP]
> - Alatka za pravljenje segmenata neće predlagati važeće vrednosti entiteta prilikom postavljanja operatora za uslove. Možete da odete na **Podaci** > **Entiteti** i da preuzmite podatke entiteta da biste videli koje su vrednosti dostupne.
> - Uslovi zasnovani na datumima vam omogućavaju prebacivanje između fiksnih datuma i promenljivog vremenskog perioda.
> - Ako imate više pravila za segment, pravilo koje uređujete ima vertikalnu plavu liniju pored sebe.
> - Pravila i uslove možete premestiti na druga mesta u definiciji segmenta. Izaberite [...] pored pravila ili uslova i odaberite kako i gde da ga premestite.
> - Kontrole **Opozovi** i **Ponovi** na komandnoj traci vam omogućavaju da vratite promene.

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

   :::image type="content" source="media/quick-segment-name.png" alt-text="Naziv i procena za brzi segment.":::

5. Navedite **ime** i **ime izlaznog entiteta** za segment. Opcionalno, dodajte [oznake](work-with-tags-columns.md#manage-tags).

6. Izaberite **Sačuvaj** da biste kreirali segment.

7. Nakon završetka obrade segmenta, možete ga pregledati kao i bilo koji drugi segment koji ste kreirali.

## <a name="next-steps"></a>Sledeći koraci

[Izvezite segment](export-destinations.md) i istražite članak [Integracija korisničke kartice](customer-card-add-in.md) da biste koristili segmente u drugim aplikacijama.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
