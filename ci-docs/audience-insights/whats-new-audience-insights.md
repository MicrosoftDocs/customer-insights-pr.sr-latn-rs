---
title: Nove i predstojeće funkcije
description: Informacije o novim funkcijama, poboljšanjima i ispravkama grešaka.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 355dc22ac381145b231848830cefc47eda7968f4
ms.sourcegitcommit: 6944c1592877eb92ec789df5f2e0dbecef638837
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/15/2021
ms.locfileid: "6263268"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Šta je novo u mogućnosti uvida u ciljnu grupu usluge Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Drago nam je što možemo da najavimo naše najnovije ispravke. Ovaj članak rezimira funkcije verzija za javni pregled, poboljšanja opšte dostupnosti i ispravke za funkcije. Da biste videli dugoročne planove funkcija, pogledajte [planove izdanja Dynamics 365 i Power Platform](/dynamics365/release-plans/).

Ažuriranja objavljujemo od regiona do regiona. Tako da određeni regioni mogu da vide funkcije pre drugih. Ako nije drugačije navedeno, ne trebate ništa da preduzimate a mi ćemo automatski ažurirati aplikaciju bez prekida rada.

> [!TIP]
> Da biste prosledili i glasali za zahteve za funkcije i predloge za proizvode, idite na [Dynamics 365 portal za ideje u aplikacijama](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="may-2021-updates"></a>Ispravke za maj 2021.

Ispravke u maju 2021. uključuju nekoliko funkcija, nadogradnje performansi i ispravke grešaka.

### <a name="data-ingestion"></a>Unos podataka

- **Pregledajte ili izmenite metapodatke ili definiciju entiteta kada prilažete podatke iz skladišta Azure Data Lake Storage** Sada možete da pregledate i uredite metapodatke ili definiciju entiteta u uvidima u ciljne grupe kada prilažete podatke iz fascikle Common Data Model u vašem skladištu Azure Data Lake Storage. Ova mogućnost pruža povratne informacije u realnom vremenu, validaciju modela i proveru grešaka. Omogućava vam da bez problema uređujete i model.json i manifest.json.

### <a name="extensibility"></a>Proširivost

- **Poboljšan izvoz segmenata, prilagođeni raspored i dupliranje** Sada možete da [pogledate sve izvoze za određeni segment](export-destinations.md#view-exports-and-export-details) u listi. Ovaj novi prikaz pomaže u upravljanju načinom na koji se koristi određeni segment i prilagođavanju postojećeg ili kreiranju novih izvoza.    
  Možete da [definišete prilagođene rasporede osvežavanja](export-destinations.md#schedule-and-run-exports) za pojedinačne izvoze ili nekoliko izvoza odjednom. Do sada se sav izvoz vodio sa svakim osvežavanjem sistema.    
  Umesto da kreirate novi izvoz od nule, možete da započnete na osnovu postojećeg da biste uštedeli vreme.

- **Izvoz segmenata u Microsoft Advertising** Proširili smo svoja odredišta za izvoz tako da uključuju i Microsoft Advertising. Kreirajte ciljne grupe za podudaranje klijenata u usluzi Microsoft Advertising pomoću objedinjenih podataka profila klijenata i koristite ciljne grupe za kampanje oglašavanja. Za više informacija, pogledajte [Izvoz segmenata u Microsoft Advertising](export-microsoft-advertising.md).

- **Izvoz segmenata u LinkedIn Ads** Proširili smo svoja odredišta za izvoz tako da uključuju LinkedIn Ads i omogućavamo vam da otključate ciljanje kontakata, kao i ciljanje kompanija putem platforme LinkedIn, izvozom objedinjenih podataka o profilu klijenta. Za više informacija, pogledajte [Izvoz segmenata u LinkedIn Ads](export-linkedin-ads.md).


- **Izvoz segmenata u Omnisend** Proširili smo svoja odredišta za izvoz tako da uključuju Omnisend. Koristite segmente kreirane u uvidima u ciljnu grupu da biste generisali kampanje, obezbedili marketing e-poštom i koristili određene grupe klijenata sa uslugom Omnisend. Za više informacija, pogledajte [Izvoz segmenata u Omnisend](export-omnisend.md)

### <a name="predictions"></a>Predviđanja

- **Izveštaj o upotrebljivosti ulaznih podataka** Izveštaj o upotrebljivosti ulaznih podataka pruža konsolidovani prikaz grešaka i upozorenja koja mogu proizvesti vaša gotova predviđanja. Takođe daje preporuke kako da poboljšate performanse modela.    
  Izveštaj je dostupan nakon što model završi svoj proces obuke. Kreira se za svaki model posebno, bez obzira na to da li je uspešno završen ili ne.
  Trenutno, ova funkcija je dostupna samo za model gubitka transakcija. Za više informacija, pogledajte [Izveštaj o upotrebljivosti ulaznih podataka](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Relacije

- **Vizuelizator relacija** Prikaz vizuelizatora relacija omogućava vam da vidite sve postojeće relacije između entiteta i njihove kardinalnosti. Relacije se sada organizuju u grupe: korisnički kreirane, sistemske i nasleđene relacije. Takođe možete da izvezete prikaz kao sliku. Za više informacija, pogledajte [Prikaz relacija](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Ispravke za april 2021. godine

Ispravke u aprilu 2021. uključuju nekoliko funkcija, nadogradnje performansi i ispravke grešaka.

### <a name="data-unification"></a>Ujednačavanje podataka
 
- **Poboljšano iskustvo objedinjavanja za ujednačavanje podataka**    
  
   Sada imamo poboljšano korisničko iskustvo u konfiguraciji objedinjavanja procesa ujednačavanja podataka. Promene uključuju intuitivno uređivanje objedinjenih polja i detaljne statistike o kombinovanim i pojedinačnim poljima.

- **Preuređivanje entiteta i konfigurisanje svih izvornih zapisa u entitet klijenta**  
      
   Sada u procesu ujednačavanja podataka možete preurediti i ukloniti entitete iz postojećeg plana povezivanja. To daje fleksibilnost za preuređivanje entiteta u procesu podudaranja u skladu sa poslovnim potrebama. Pored toga, omogućavamo uključivanje svih nepodudarnih zapisa u konačni entitet *Klijent*, koji im omogućava da definišu definiciju skupa podataka o svom korisničkom profilu.

### <a name="enrichments"></a>Obogaćivanja

 - **Novo obogaćivanje: Poboljšane adrese**    
  
   Uzbuđeni smo što smo predstavili novo obogaćivanje za poboljšanje adresa u vašim podacima o klijentima. Adrese u vašim podacima mogu biti nestrukturirane, nepotpune ili netačne. Ova funkcija koristi Microsoft modele za normalizaciju i obogaćivanje adresa u formatu Common Data Model radi veće tačnosti i uvida.
 
   Za više informacija pogledajte [Obogaćivanje korisničkih profila sa poboljšanim adresama](enrichment-enhanced-addresses.md).

- **Vođeno iskustvo konfiguracije za obogaćivanje**    
  
   Ponovo smo posetili iskustvo konfiguracije radi obogaćivanja jednostavnim, vođenim iskustvom. Sada imate jasan detaljan postupak kreiranja i uređivanja obogaćivanja.
 
   Pored toga, odvojili smo konfiguraciju veza za obogaćivanja nezavisnih proizvođača kako bismo omogućili da se ista veza koristi u više obogaćivanja. Samo administratori mogu da konfigurišu nove veze, ali kreirane veze su dostupne i administratorima i saradnicima.    

   Za još informacija, pogledajte [Pregled veza](connections.md).

- **Višestruka obogaćivanja istog tipa**    
  
   Sada omogućavamo korisnicima da kreiraju i upravljaju višestrukim obogaćivanjima istog tipa obogaćivanja. Na primer, sada možete da napravite dva odvojena obogaćivanja adresa da biste obogatili dva različita segmenta klijenata. Ograničenja se primenjuju na to koliko obogaćivanja istog tipa je moguće kreirati i varirati u zavisnosti od tipa obogaćivanja.
  
   Za više informacija, pogledajte [Obogaćivanje za profile klijenata](enrichment-hub.md).

## <a name="march-2021-updates"></a>Ispravke za mart 2021.

Ispravke u martu 2021. uključuju nekoliko funkcija, nadogradnje performansi i ispravke grešaka.

### <a name="activities"></a>Aktivnosti

- **Čarobnjak za aktivnosti i semantički tipovi**

   Poboljšali smo i ažurirali iskustvo mapiranja aktivnosti kako bismo vodili i pojednostavili kreiranje mapiranja aktivnosti. U ovom novom iskustvu, korisnici dobijaju vođeno iskustvo koje pomaže u dovršavanju svakog koraka procesa. U koraku mapiranja aktivnosti, pored izbora između mnogih vrsta aktivnosti, korisnik može odabrati i semantičko mapiranje podataka za *Pretplatu* i / ili *Detalj ulazne porudžbine* prema šemama industrijskog standarda, koje se mogu koristiti u naknadnoj potrošnji.   

   Za više informacija pogledajte [aktivnosti klijenta](activities.md).

### <a name="data-ingestion"></a>Unos podataka

- **Povežite se na lokalne izvore podataka koristeći Power Platform tokove podataka i mrežne prolaze** Zadovoljstvo nam je da najavimo verziju za pregled Power Platform tokova podataka i lokalnog povezivanja pomoću mrežnih prolaza u usluzi Customer Insights sa pridruženom uslugom Power Platform ili Dataverse okruženjem. Svi novi izvor podataka kreiran u Customer Insights okruženju sa povezanim Dataverse okruženjem će podrazumevano biti Power Platform tokovi podataka koji donose lokalnu povezanost podataka i bogat skup konektora i mogućnosti transformacije.

### <a name="extensibility"></a>Proširivost

- **Izvozi organizovani u vezama i izvozima** Promenili smo naziv stranice **Odredišta za izvoz** u **Veze** i dodali smo posebnu stranicu za **Izvoze**. Kao deo ove ispravke, prebacićemo postojeći izvoz u parove veze i izvoz koji koristi tu vezu. Administratori sada imaju više jasnoće u odnosu na odlazne podatke na stranici **Veze**. Sve korisničke uloge imaju pristup stranici **Izvoz**, ali samo administratori mogu da odluče da dozvole saradnicima da uređuju određene izvore pomoću deljenih veza.     
  Za više informacija, pogledajte [Pregled veza](connections.md) i [Pregled izvoza](export-destinations.md).

- **Izvoz segmenata u Campaign Monitor** Proširili smo svoja odredišta za izvoz tako da uključuju i Campaign Monitor. Sada možete izvesti segmente iz usluge Customer Insights u Campaign Monitor liste i koristiti ih kao osnovu za vaše marketinške kampanje.    
   Za više informacija, pogledajte [Izvoz u Campaign Monitor](export-campaign-monitor.md).

- **Izvoz segmenata u Constant Contact** Proširili smo svoja odredišta za izvoz tako da uključuju i Constant Contact. Sada možete izvesti segmente iz usluge Customer Insights u Constant Contact liste i koristiti ih kao osnovu za vaše marketinške kampanje.   
   Za više informacija, pogledajte [Izvoz u Constant Contact](export-constant-contact.md).

- **Izvoz segmenata u RollWorks** Proširili smo svoja odredišta za izvoz tako da uključuju i RollWorks. Sada možete izvesti segmente iz usluge Customer Insights u RollWorks ciljne grupe i koristiti ih kao osnovu za vaše B2B oglašavanje.    
   Za više informacija, pogledajte [Izvoz podataka u RollWorks ](export-rollworks.md).

- **Izvoz segmenata u Snapchat** Proširili smo svoja odredišta za izvoz tako da uključuju i Snapchat. Sada možete izvesti segmente iz usluge Customer Insights u Snapchat ciljne grupe i koristiti ih kao osnovu za vaše marketinške kampanje.     
   Za više informacija, pogledajte [Izvoz podataka u Snapchat](export-snapchat.md).

### <a name="predictions"></a>Predviđanja

- **Koristite filtere za proizvode u prediktivnim preporukama za proizvode** U model preporuka za proizvode smo dodali mogućnost upotrebe filtera za proizvode. Sada možete da kreirate predviđanje koje koristi samo podskup vaših proizvoda.    
   Za više informacija, pogledajte odeljak [Konfigurisanje filtera proizvoda](predict-product-recommendation.md#configure-product-filters).

- **Kreiranje segmenata na osnovu predviđanja modela** Dodali smo brz način za kreiranje segmenata pomoću rezultata modela predviđanja. Na stranici rezultata modela, možete lako kreirati novi segment izborom nove opcije **Kreiraj segment**.    
  Za više informacija, pogledajte članak [Kreiranje segmenta na osnovu modelu predviđanja](prediction-based-segment.md).

- **Objašnjenja za preporuke proizvoda** Dodali smo informacije koje objašnjavaju ključne faktore koje je model veštačke inteligencije naučio da bi generisao preporuke za proizvode i stepen u kojem ti faktori doprinose preporukama za proizvode. Ove informacije se dodaju na ekran rezultata modela.    
   Za više informacija pogledajte [Pregledajte status i rezultate predviđanja](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Ispravke za februar 2021.

Ispravke u februaru 2021. uključuju nekoliko funkcija, nadogradnje performansi i ispravke grešaka.

#### <a name="extensibility"></a>Proširivost

- **Izvoz segmenata u AdRoll**

  Proširili smo svoja izvozna odredišta tako da uključuju i AdRoll. Sada možete izvesti segmente iz usluge Customer Insights u AdRoll ciljnu grupu i koristiti ih kao osnovu za oglašavanje. Za više informacija, pogledajte [Konektor za AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmenti
 
- **Dupliranje segmenta**
  
  Da biste kreirali novi segment na osnovu postojećeg, sada možete da duplirate segment i uredite duplirani segment da biste ga dalje precizirali. 

- **Dodajte dodatne atribute u segment**

  Sada možete da uključite atribute u izlaz segmenta, čak i ako ti atributi nisu deo korisničkog profila. Na primer, uključite ID-ove pretplate u segment iako je deo entiteta pretplate koji ima relaciju M:1 sa entitetom klijenta. Sve dok atribut pripada entitetu povezanom sa entitetom klijenta, sada možete uključiti te atribute.  

#### <a name="predictions"></a>Predviđanja

- **Kreiranje prediktivnih preporuka proizvoda**

  Razumevanje za šta su klijenti zainteresovani u toku kupovine jedan je od prvih koraka potrebnih za poboljšanje poslovnog prihoda i izgradnju lojalnosti klijenata kroz personalizaciju i angažovanje. Davanje preporuka za proizvode koji nisu usklađeni sa interesima vašeg klijenta može kreirati osećaj prekida veze između klijenta i preduzeća, a na kraju i ograničiti klijentu ukupan potencijalni prihod i iskustvo. 

  Koristeći sopstvene podatke, sada možete da kreirate predviđanja za proizvode koje će vaši klijenti verovatno kupiti u budućnosti. Za više informacija, pogledajte [Predviđanje preporuka proizvoda](predict-product-recommendation.md).

#### <a name="system-administration"></a>Administracija sistema

- **Okruženje za kopiranje podržava više vrsta izvora podataka**

  Administratori mogu da kopiraju konfiguracije okruženja u novo okruženje u istoj organizaciji. Ova funkcija proširuje funkcionalnost okruženja za kopiranje za slučajeve u kojima se koriste izvori podataka zasnovani na Common Data Service jezeru podataka ili fascikli Common Data Model.

## <a name="january-2021-updates"></a>Ispravke za januar 2021. godine

Ispravke u januaru 2021. uključuju nekoliko funkcija, nadogradnje performansi i ispravke grešaka.

#### <a name="extensibility"></a>Proširivost

- **Proširena funkcionalnost i poboljšane performanse za SFTP izvoz** Sada možete da izvezete sve izlazne entitete iz usluge Customer Insights na SFTP host. Ranije je izvoz bio ograničen na entitete segmenta. Pored toga, performanse SFTP izvoza omogućavaju veći obim podataka za manje vremena, u zavisnosti od performansi vašeg SFTP hosta.    
  Za više informacija pogledajte [Konektor za SFTP (pregled)](export-sftp.md).  

#### <a name="segments"></a>Segmenti

- **Predloženi segmenti koje omogućava mašinsko učenje za poboljšanje metrike** Postoji nov način otkrivanja i kreiranja segmenata. Sistem koristi model veštačke inteligencije da predloži segmente koji mogu pomoći u poboljšanju KPI (mere) koji već pratite. Prikazujemo stepen uticaja atributa koje ste odabrali na meru ili neki drugi primarni atribut. Ove informacije pomažu u pronalaženju potencijalnih segmenata koji predstavljaju mogućnosti za poslovanje.    
  Za više informacija, pogledajte [Predloženi segmenti (pregled)](suggested-segments.md).

#### <a name="data-unification"></a>Ujednačavanje podataka

- **Poboljšano iskustvo podudaranja** U oblasti objedinjavanja podataka, ažurirano je iskustvo podudaranja. Ono vam omogućava da konfigurišete i pregledate pravila podudaranja, uključujući detaljne statistike kako biste dalje objasnili kako podudaranje funkcioniše. Postoje opcije za onemogućavanje pravila podudaranja, tako da ono više nije aktivno, ali zadržava konfiguraciju, pravila podudaranja za prevlačenje i ispuštanje i još mnogo toga.
  Za više informacija, pogledajte članak [Podudaranje entiteta](match-entities.md).

- **Izlaz postupka uklanjanja duplikata iz procesa podudaranja dostupan je kao entitet** Izlaz postupka uklanjanja duplikata iz procesa podudaranja sada je zapisan u zasebni entitet za dalju analizu. Ovaj entitet se sastoji od polja koja se koriste u procesu uklanjanja duplikata i dobitnih zapisa i odgovarajućih alternativnih zapisa koji se objedinjavaju sa dobitnim zapisom.
  Za više informacija pogledajte [Izlaz postupka uklanjanja duplikata kao entitet](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Administracija sistema

- **Jednostavno delite podatke sa platformom Microsoft Dataverse** Sada možete da delite izlaz iz usluge Customer Insights sa Microsoft Dataverse aplikacijama koje koriste Microsoft Dataverse Managed Data Lake. Kada povežete Dataverse okruženje sa uslugom Customer Insights, dobijate opciju da omogućite deljenje podataka.
  Više informacija potražite u članku [Upravljanje okruženjem](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]