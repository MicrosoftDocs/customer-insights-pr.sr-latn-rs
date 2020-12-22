---
title: Nove i predstojeće funkcije
description: Informacije o novim funkcijama, poboljšanjima i ispravkama grešaka.
ms.date: 11/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 07b4bee0445f9cd7d53a37cd405af839feb07ae3
ms.sourcegitcommit: 4004eadac7a65e50e0a409cb925958523c2b6348
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/30/2020
ms.locfileid: "4650021"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Šta je novo u mogućnosti uvida u ciljnu grupu usluge Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Drago nam je što možemo da najavimo naše najnovije ispravke. Ovaj članak rezimira funkcije verzija za javni pregled, poboljšanja opšte dostupnosti i ispravke za funkcije. Da biste videli dugoročne planove funkcija, pogledajte [planove izdanja Dynamics 365 i Power Platform](https://docs.microsoft.com/dynamics365/release-plans/).

Takođe možete pogledati sledeći video da biste saznali više o mogućnostima planiranim za poslednjih šest meseci.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Ažuriranja objavljujemo od regiona do regiona. Tako da određeni regioni mogu da vide funkcije pre drugih. Ako nije drugačije navedeno, ne trebate ništa da preduzimate a mi ćemo automatski ažurirati aplikaciju bez prekida rada.

> [!TIP]
> Da biste prosledili i glasali za zahteve za funkcije i predloge za proizvode, idite na [Dynamics 365 portal za ideje u aplikacijama](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="november-2020-updates"></a>Ispravke za novembar 2020

Ispravke u novembru 2020. uključuju nekoliko funkcija, nadogradnje performansi i ispravke grešaka.

### <a name="new-and-updated-features-in-november-2020"></a>Nove i ažurirane funkcije u novembru 2020

#### <a name="data-enrichment"></a>Obogaćivanje podataka

- **Donesite svoje podatke za obogaćivanje putem prilagođenog uvoza pomoću protokola Secure File Transfer Protocol (SFTP)**
  
  SFTP prilagođeni uvoz vam omogućava da uvezete podatke za obogaćivanje koji ne moraju da prolaze kroz proces objedinjavanja podataka. Saznajte više o SFTP prilagođenom uvozu.

  Za više informacija pogledajte [Obogatite profile klijenata prilagođenim podacima (verzija za pregled)](enrichment-SFTP-custom-import.md).
 
- **Obogatite podatke o klijentima pomoću podataka o lokaciji kompanije HERE Technologies**

  Pomoću usluga obogaćivanja podataka kompanije HERE Technologies možete da izgradite preciznije razumevanje lokacije svojih klijenata pomoću normalizacije adresa, izdvajanja geografske širine i dužine i još mnogo toga. Saznajte više o obogaćivanju uz HERE Technologies.

  Za više informacija pogledajte [Obogaćivanje profila klijenata uz HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Ujednačavanje podataka

- **Fleksibilnost za omogućavanje profilisanja podataka na odabranim entitetima i poljima sa vašeg naloga za skladištenje**

  Možete da naznačite za koje entitete podataka i polja iz fascikle Common Data Model na vašem Azure Data Lake nalogu za skladištenje želite da omogućite profilisanje podataka kao deo procesa unosa podataka.

  Za više informacija pogledajte [Povežite se sa Common Data Model fasciklom](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Proširivost

- **Aktivirajte segmente putem Google oglasa**

  Izvezite segmente na liste ciljnih grupa Google oglasa i koristite ih za oglašavanje u Google pretrazi, na Google mreži multimedijalnog oglašavanja, kao i u uslugama YouTube i Gmail. Saznajte više o aktiviranju segmenata putem Google oglasa.

  Za više informacija pogledajte [Konektor za Google oglase](export-google-ads.md).

- **Aktivirajte segmente putem usluge Marketo**

  Izvezite segmente u Marketo ciljne grupe i koristite ih za tržišnu automatizaciju. Saznajte više o aktiviranju segmenata putem usluge Marketo. 

  Za više informacija pogledajte [Konektor za Marketo](export-marketo.md).

- **Aktivirajte segmente putem usluge DotDigital**

  Izvezite segmente u DotDigital i koristite ih u marketinške svrhe. Saznajte više o aktiviranju segmenata putem usluge DotDigital. 

  Za više informacija pogledajte [Konektor za DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Predviđanja

- **Predvidite gubitak transakcija**

  Funkcija predviđanja gubitka transakcija omogućava vam, bez pomoći naučnika za podatke, da predvidite verovatnoću da klijent zaustavi kupovinu proizvoda ili usluga.  Koristeći rezultat predviđanja, možete da kombinujete druge informacije o svojim klijentima, poput vrednosti klijenta, da biste kreirali segmente klijenata sa velikim rizikom od gubitka. Koristite ovaj segment za direktno ciljanje klijenata kroz marketinške aktivnosti, korisničku podršku i druge scenarije kako biste smanjili rizik od gubitka.
 
  Konfigurišite definiciju gubitka kao vremenski period specifičan za vaše preduzeće i definišite kada se klijenti smatraju izgubljenim. Na primer, prehrambena prodavnica možda želi da smatra klijenta izgubljenim ako on ništa nije kupio u poslednjih 30 dana.
 
  Kako nastavljate sa kreiranjem predviđanja, vodićemo vas kroz to koji su podaci potrebni i omogućićemo vam da mapirate podatke o svom preduzeću sa poljima potrebnim za predviđanje gubitka klijenata. Takođe možete postaviti raspored za ponovnu obuku modela na osnovu novih informacija u vašem sistemu kako bi se prilagodio promenljivim poslovnim okolnostima.
 
  Za više informacija pogledajte [Predviđanje gubitka transakcija (verzija za pregled)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Administracija sistema

- **Uspostavljanje početnih vrednosti okruženja**

  Resetujte sve u okruženju odabrane instance da biste započeli iznova.

  Za još informacija, pogledajte članak [Resetovanje postojećeg okruženja](manage-environments.md#reset-an-existing-environment).


- **Povežite se sa svojim Azure Data Lake nalogom za skladištenje koristeći principal usluge**

  Upišite izlazne podatke na nalog za skladištenje i pročitajte podatke sa njega pomoću principala Azure usluge. Postojeće veze naloga za skladištenje mogu i dalje koristiti ključ naloga. Takođe nude opciju nadogradnje za korišćenje principa usluge u budućnosti. Nove veze će se zasnivati na načinu potvrde identiteta principala usluge za vaš nalog za skladištenje.

  Za više informacija pogledajte [Povezivanje sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge za uvide u ciljnu grupu](connect-service-principal.md).

## <a name="october-2020-updates"></a>Ispravke za oktobar 2020

Ispravke u oktobru 2020. uključuju nekoliko funkcija, nadogradnje performansi i ispravke grešaka.

### <a name="new-and-updated-features-in-october-2020"></a>Nove i ažurirane funkcije u oktobru 2020

#### <a name="extensibility"></a>Proširivost

- **Izvoz u Mailchimp**

Izvezite segmente na postojeće liste ciljnih grupa u usluzi Mailchimp kako biste svojim klijentima pružili personalizovano iskustvo e-pošte.

Za više informacija pogledajte [Konektor za Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Obogaćivanje podataka

- **Deduplikacija izvornih zapisa u entitetu podudaranja**

Navedite pravila deduplikacije na entitetima koji se koriste u procesu podudaranja za identifikovanje duplikata zapisa. Spojite ih u jedan zapis i povežite sve izvorne zapise sa ovim spojenim zapisom. Ovaj deduplicirani zapis će se zatim koristiti u procesu podudaranja među entitetima.

Za više informacija pogledajte [Definišite deduplikaciju na entitetu podudaranja](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Administracija sistema

- **Orkestracija: Nova opcija osvežavanja u objedinjavanju**

Do danas, kada pokrenete postupak objedinjavanja, sistem je obavljao sve procese posledičnog premeštanja koji zavise od objedinjavanja i kasnijih procesa. Sada možete da verifikujete izlaz procesa objedinjavanja (objedinjeni entitet klijenta) pre nego što ga upotrebite u posledičnoj obradi, poput segmenata ili mera.
Na stranici objedinjavanja sada možete da izaberete da pokrenete samo korak objedinjavanja i pokrenete samo ovaj proces. Da biste osvežili i sve posledične procese, možete odabrati pokretanje objedinjavanja i posledičnih procesa. 

## <a name="september-2020-updates"></a>Ispravke za septembar 2020.

Ispravke u septembru 2020. uključuju nekoliko funkcija, nadogradnje performansi i ispravke grešaka.

### <a name="new-and-updated-features-in-september-2020"></a>Nove i ažurirane funkcije u septembru 2020.

#### <a name="activities"></a>Aktivnosti

- **Inteligentno predviđanje semantike atributa**

Ova nova funkcija predviđa semantičke tipove ulaznih atributa koji se prenose u proces objedinjavanja podataka. Koristi modele mašinskog učenja koji poboljšavaju tačnost i štede vreme.

#### <a name="enrichments"></a>Obogaćivanja

- **Obogaćivanje demografskih podataka kompanije Experian**

Obogaćivanje demografskih podataka kompanije Experian sada je dostupno u pregledu. Experian je globalni lider u izveštavanju o potrošačkim i poslovnim kreditima i marketinškim uslugama. Pomoću [usluga obogaćivanja podataka kompanije Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), možete da izgradite dublje razumevanje svojih klijenata obogaćivanjem profila klijenata demografskim podacima kao što su veličina domaćinstva, prihod i još mnogo toga.

Da biste koristili ovu funkciju, morate imati aktivnu pretplatu na Experian.

Za više informacija pogledajte [Obogatite profile klijenata demografskim podacima kompanije Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Administracija sistema

- **Okno sa detaljima zadataka**

Okno sa detaljima zadataka omogućava vam da vidite detalje o zadacima koje sistem pokreće. To je zgodan način da identifikujete probleme sa konfiguracijom i pronađete rešenja.
Pregledajte poruke o greškama i pogledajte kako da rešite potencijalne probleme.
 
- **Obrada informacija dodatih na dodatne stranice**

Ovo poboljšanje dodaje informacije o statusu vaših entiteta na stranicama **Entiteti** i **Klijenti**.
 
Pored toga, na obe ove stranice možete pronaći detalje o napretku procesa, zajedno sa detaljima zadataka.

- **Poboljšanja stranice sa statusom sistema**

Poboljšali smo strukturu tabele sa detaljima statusa u odeljku **Sistem** > **Status** prilikom pregleda izvoza podataka.
 
Pored toga, greške u koloni **Detalji** sada su detaljnije i operativne. 
 
- **Otkažite vraćanje posla u prethodno stanje**

Kada otkažete zadatak, na primer, u procesu podudaranja, on će se vratiti u svoje najnovije stanje. Na primer, ako je postupak podudaranja završen juče, a danas ga otkažete, vratiće se u jučerašnje uspešno stanje.


## <a name="august-2020-updates"></a>Ispravke za avgust 2020.

Ispravke u avgustu 2020. uključuju nekoliko funkcija, nadogradnje performansi i ispravke grešaka.

### <a name="new-and-updated-features-in-august-2020"></a>Nove i ažurirane funkcije u avgustu 2020.

#### <a name="data-unification"></a>Ujednačavanje podataka

- **Poboljšano iskustvo za fazu mapiranja tokom objedinjavanja podataka**

  Iskustvo sa fazom mapiranja u procesu objedinjavanja podataka omogućava vam odabir entiteta, atributa i definisanje semantike na lakši način.

  Promene obuhvataju:
  
  - potrebno je manje interakcija za dodavanje entiteta i polja
  - poboljšane mogućnosti pretraživanja na stranici mapiranja
  - vizuelna i laka identifikacija predloženog tipa polja

#### <a name="enrichment"></a>Obogaćivanje

- **Obogaćivanje afiniteta interesovanja dostupno je na dodatnim tržištima**

  Proširujemo dostupnost obogaćivanja afiniteta izvan Sjedinjenih Država na pet dodatnih tržišta: Kanada, Australija, Ujedinjeno Kraljevstvo, Francuska i Nemačka. Ovim proširenjem možete obogatiti podatke o klijentima dodatnim interesovanjima primenljivim na ovim tržištima. Takođe ćemo obogatiti vaše profile klijenata koji se nalaze na tim tržištima koristeći lokalne privatne podatke iz usluge Microsoft Graph.
  Za više informacija, pogledajte [Obogaćivanje profila klijenata afinitetima prema brendovima i interesovanjima](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Ispravke za jul 2020.

Ispravke u julu 2020. uključuju nekoliko funkcija, nadogradnje performansi i ispravke grešaka.

### <a name="new-and-updated-features-in-july-2020"></a>Nove i ažurirane funkcije u julu 2020. godine

#### <a name="extensibility"></a>Proširivost

- **Power Automate okidač za završeni proces objedinjavanja**

  Produžili smo okidače za Power Automate i omogućili vam da kreirate obaveštenje ili radnju kada se završi osvežavanje procesa objedinjavanja (mapiranje, podudaranje, objedinjavanje).    
  Više informacija potražite u članku [Power Automate konektor](export-power-automate.md)

#### <a name="enrichment"></a>Obogaćivanje

- **Obogaćivanje afiniteta brendova je dostupno na dodatnim tržištima**

  Dostupnost obogaćivanja afiniteta brendova proširujemo izvan Sjedinjenih Država na pet dodatnih tržišta: Kanada, Australija, Ujedinjeno Kraljevstvo, Francuska i Nemačka. Ovim proširenjem možete da obogatite podatke o klijentima lokalnim brendovima na tim tržištima. Takođe ćemo obogatiti vaše profile klijenata koji se nalaze na tim tržištima koristeći lokalne privatne podatke iz usluge Microsoft Graph.
  Za više informacija, pogledajte [Obogaćivanje profila klijenata afinitetima prema brendovima i interesovanjima](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Ispravke za jun 2020. godine

Ispravke u junu 2020. uključuju nekoliko funkcija, nadogradnje performansi i ispravke grešaka.

### <a name="new-and-updated-features-in-june-2020"></a>Nove i ažurirane funkcije u junu 2020. godine

#### <a name="enrichment"></a>Obogaćivanje

- **Obogaćivanje podacima kompanije iz usluge Leadspace**
  
  Definišite polja u objedinjenim profilima klijenata koja se koriste za traženje podataka srodnih kompanija iz usluge Leadspace. Nakon pokretanja postupka obogaćivanja, B2B profili su obogaćeni dodatnim atributima, uključujući veličinu kompanije, lokaciju, delatnost i još mnogo toga.    
  Ova saradnja omogućava vam da poboljšate kvalitet svojih podataka unosom usluga trećih strana. Da biste iskoristili ovo obogaćenje, potrebna vam je licenca kompanije Leadspace za pristup B2B podacima kompanije. Sistem će koristiti tu licencu da vaše podatke neprekidno obogaćuje.    
  Za više informacija, pogledajte [Obogaćivanje profila kompanije pomoću usluge Leadspace](enrichment-leadspace.md).

- **Stranica čvorišta za obogaćivanje**

  Sva dostupna obogaćivanja podataka od dobavljača obogaćivanja prvih i trećih strana konfigurišu se na istom mestu. Konfigurisanje obogaćivanja podataka je besprekorno iskustvo kojim se upravlja sa uobičajenog mesta.    
  Za više informacija, pogledajte [Obogaćivanje za profile klijenata](enrichment-hub.md).

- **Zasebno obogaćivanje afiniteta brendova i interesovanja**

  Afiniteti za brendove i interesovanja sada su dostupni kao dva nezavisna obogaćivanja. Zasebna obogaćivanja daju vam fleksibilnost da ih samostalno konfigurišete i upravljate njima, u zavisnosti od vaših poslovnih zahteva ili potreba.    
  Za više informacija, pogledajte [Obogaćivanje profila klijenata afinitetima prema brendovima i interesovanjima](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Proširivost

- **URL-ovi na koje se može kliknuti za objedinjene aktivnosti na Dynamics 365 dodatku za karticu klijenta**

  Objedinjene aktivnosti u programskom dodatku za klijentske kartice sada prikazuju URL-ove na koje je moguće kliknuti ako su takvi URL-ovi definisani tokom konfiguracije aktivnosti.    
  Za više informacija pogledajte [Dodatak kartice klijenta](customer-card-add-in.md).

- **Afiniteti brendova i interesovanja dostupni su u Dynamics 365 dodatku za karticu klijenta**

  Nova kontrola Dynamics 365 dodatka za karticu klijenta omogućava vam da prikažete obogaćivanje brendova i interesovanja na svojim kontaktima u aplikacijama za angažovanje klijenata u sistemu Dynamics 365.    
  Za više informacija pogledajte [Dodatak kartice klijenta](customer-card-add-in.md).

- **Dodatni Power Automate okidači**

  Produžili smo naše okidače za Power Automate i dodali sledeće okidače:
  - Dobijte obaveštenje ili izvršite radnju kada se dovrši automatsko potpuno osvežavanje (izvori podataka, objedinjavanje, segmenti, mere, izvoz)
  - Definišite prag za poslovnu meru. Na primer, možete da kreirate obaveštenje koje se šalje prilikom prelaska definisanog praga. Uz to, okidač donosi informacije koje vam omogućavaju da izgradite složenije tokove posla u usluzi Power Automate.    
  Više informacija potražite u članku [Power Automate konektor](export-power-automate.md)

- **Izvoz u Facebook menadžer oglasa**
  
  Ova mogućnost vam dozvoljava izvoz segmenata u menadžer Facebook oglasa. Segmenti se izvoze kao prilagođena publika da bi se koristili objedinjeni profili klijenata u Facebook marketinškim kampanjama i oglasima. Prilagođena publika je takođe korisna za kreiranje kampanja na mreži Instagram preko Facebook menadžera oglasa.    
  Za više informacija, pogledajte [Konektor za Facebook menadžer oglasa](export-facebook.md).

#### <a name="predictions"></a>Predviđanja

- **Predviđanje odliva pretplate**

  Pratite vođeno iskustvo da biste predviđanje odliva u oblastima pretplate poput usluga u oblaku, članstva klijenata i drugih sektora. 

  Funkcija predviđanja odliva pretplate omogućava vam da predvidite verovatnoću da će klijent zaustaviti upotrebu proizvoda ili usluga zasnovanih na pretplati bez angažovanja istraživača podataka. Koristeći ocenu predviđanja, možete kombinovati druge informacije o svojim klijentima da biste kreirali segmente visokog rizika. Uz pomoć ovog segmenta možete direktno ciljati klijente u marketingu, korisničkoj podršci i drugim scenarijima kako biste smanjili rizik od gubitka određenih klijenata radi poboljšanja prihoda i smanjenja troškova.

  U okviru iskustva, možete da konfigurišete definiciju odliva kao vremenski okvir specifičan za vaše poslovanje. Na primer, preduzeće za strimovanje video sadržaja koji ima mesečnu pretplatu možda treba da smatra da je klijent izgubljen 15 dana nakon isteka pretplate.

  Dok nastavljate kroz predviđanje, uputićemo vas kroz podatke koji su vam potrebni i omogućiti vam da mapirate podatke o svom poslovanju u polja potrebna za predviđanje gubitka klijenata. Pošto se poslovne informacije menjaju, takođe možete podesiti raspored za ponovno obučavanje na osnovu novih informacija u sistemu kako biste se prilagodili promenljivim poslovnim okolnostima.    
  Za više informacija, pogledajte [Predviđanje odliva pretplate (pregled)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmenti

- **Pronađi slične klijente**
  
  Pronađite slične klijente u svojoj korisničkoj bazi koristeći veštačku inteligenciju. Model mašinskog učenja binarne klasifikacije dodeljuje ocenu sličnosti klijentima u proširenom segmentu. Rezultat je zasnovan na sličnosti sa kupcima u izvornom segmentu. U zavisnosti od ocene sličnosti, profili klijenata se dodaju u novokreirani segment.

  U digitalnom marketingu se ponekad nazivajući i modelom sličnosti, on koristi model veštačke inteligencije da bi pomogao da pronađete klijente koji su nalik drugom segmentu vaših klijenata, uzimajući u obzir dodatne atribute. To ne samo da vam omogućava da odaberete atribute, već vam omogućava da odredite maksimalni broj klijenata koji bi trebalo da budu u ovom novom segmentu. Model veštačke inteligencije će zatim izračunati ocene sličnosti za svakog klijenta na osnovu izabranih atributa i pronaći klijente sa višom prosečnom ocenom sličnosti. Rezultujući segment će uključiti klijente koji izgledaju slično klijentima u vašem originalnom segmentu.    
  Za više informacija pogledajte članak [Slični klijenti](find-similar-customer-segments.md).

- **Preklapanje segmenata i diferencijatori**

  Preklapanje segmenata omogućava vam da vidite koliko je klijenata zajedničko za dva ili više segmenata. Na primer, kako se segment velikih potrošača preklapa sa segmentom klijenata sa velikim zadovoljstvom ili kako se segment gubitka klijenata preklapa sa segmentom kupaca sa malim zadovoljstvom. Pored toga, možete analizirati kako se preklapanje menja na osnovu nekog dodatnog atributa po vašem izboru.

  Diferencijatori segmenata otkrivaju šta razlikuje jedan segment od ostatka vaših klijenata ili drugog segmenta. Sve što treba da uradite je da identifikujete segment i sistem će identifikovati atribute profila i mere koje razlikuju segment u obrascu rangirane liste diferencijatora – od najjačeg diferencijatora do najslabijeg.    
  Za više informacija, pogledajte članak [Uvidi u segmente (pregled)](segment-insights.md).

- **Vek trajanja segmenta**
  
  Definišite raspored za aktiviranje ili deaktiviranje segmenta.    
  Još informacija potražite u članku [Upravljanje postojećim segmentima](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Ispravke za maj 2020.

Ispravke maj 2020. obuhvataju nekoliko funkcija, nadogradnje performansi i popravke grešaka.

### <a name="new-and-updated-features-in-may-2020"></a>Nove i ažurirane funkcije u maju 2020. godine

#### <a name="data-ingestion"></a>Unos podataka

- **Unos podataka u realnom vremenu: prikazi istorije**

  Kada koristite naš API za unos ispravki u realnom vremenu, možete videti objedinjenu istoriju tih ispravki do 30 dana. Imate pristup svim objedinjenim uspešnim ili neuspešnim API pozivima, uključujući njihov ishod, izvorni sistem i druge korisne metapodate.    
  Više informacija potražite u članku [Unos podataka u realnom vremenu](real-time-data-ingestion.md).

- **Unos podataka u realnom vremenu: ažuriranja profila**

  Ovo proširenje unosa podataka u realnom vremenu omogućava vam da u roku od nekoliko sekundi vidite promene u određenim poljima korisničkog profila.    
  Pored funkcionalnosti za aktivnosti u realnom vremenu, sistem podržava ažuriranje polja profila sa malim kašnjenjem. Ispravke za polja profila u realnom vremenu imaju vreme isteka i zato nisu zamena za planirano osvežavanje.    
  Više informacija potražite u članku [Unos podataka u realnom vremenu](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Proširivost

- **Ažurirana vremenska linija i straničenje na dodatku kartice klijenta**

  Vremenska osa rešenja programskog dodatka za karticu klijenta podudara se sa vremenskom osom aktivnosti. Poboljšano je straničenje vremenske linije, prikazuje do 50 aktivnosti odjednom. Takođe omogućava učitavanje dodatnih aktivnosti na vremenskoj traci.    
  Za više informacija pogledajte [Dodatak kartice klijenta](customer-card-add-in.md).

- **Power Automate okidač za promene segmenta**

  Okidači za Power Automate definišu od čega možete da gradite tok. Novo dodavani okidač omogućava vam definisanje praga za segment. Na primer, možete da kreirate obaveštenje koje se šalje prilikom prelaska definisanog praga.    
  Više informacija potražite u članku [Power Automate konektor](export-power-automate.md).

- **Podrška višeklijentskog sistema za prilagođene modele**

  Konfigurišite tokove posla za prilagođene modele sa veb-uslugom drugog zakupca Azure mašinskog učenja. Možete se prijaviti na zakupac za Azure mašinsko učenje prilikom kreiranja novog toka posla za prilagođene modele. Ova sposobnost je dodatak postojećoj mogućnosti integracije sa vašom prilagođenom veb-uslugom Azure mašinsko učenje.    
  Za više informacija pogledajte [Prilagođeni modeli mašinskog učenja](custom-models.md).

#### <a name="segments"></a>Segmenti

- **Automatizacija putanje entiteta**

  Kada kreiraju segment, korisnici treba da definišu putanju entiteta. Ova sposobnost čini prvi korak u automatizaciji definicije putanje entiteta tako da možete da se fokusirate na kriterijume segmentacije koje imate na umu.    
  Ako je entitet pomoću kojeg želite da segmentirate svoje kupce direktno povezan sa objedinjenim entitetom kupca, više nećete morati da definišete putanju entiteta. Međutim, ako postoji više mogućih putanja entiteta, to još uvek morate da definišete ručno.

- **Radnje na više segmenata**
  
  Korisnici mogu da izaberu više segmenata i da samo jednim klikom preduzmu radnje na njima, poput osvežavanja segmenata.    

- **Osvežavanje segmenata**

  Korisnici mogu da osveže jedan segment ili da izaberu samo one segmente koje žele da osveže.    

  
- **Poboljšanja složenih segmenata**

  Korisnici mogu da kreiraju, uređuju i brišu segmente koji se zasnivaju na drugim segmentima. Na primer, segment izgrađen na drugom segmentu koji je izgrađen na trećem segmentu.    

- **Stranica sa listom segmenata**

  Novi dizajn stranice segmenata koristi format liste koji vam omogućava da vidite više segmenata odjednom. Za brzo pronalaženje segmenata dodaje se polje za pretragu. Korisnici sada mogu primeniti radnje poput preuzimanja ili brisanja na više segmenata odjednom. Uvodi se novi trend u iskustvu za brzo identifikovanje značajnih promena.    
  Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).

#### <a name="system-administration"></a>Administracija sistema

- **Customer Insights je dostupan u Microsoft Dynamics 365 Online Government**

  Sa sve više i više kanala za interakciju, podaci o građanima su raštrkani po bezbroj sistema, što dovodi do zbirnih podataka i fragmentiranog prikaza informacija o interakcijama građana. Bez kompletnog uvida u interakciju pojedinih građana preko kanala, nemoguće je modernizovati vlade u širokom obimu. Microsoft je posvećen podršci tehnološkim potrebama državne institucije kako bi išao u korak sa očekivanjima građana za doslednim i prilagodljivim iskustvima.    
  Sa izdanjem 1. talasa iz 2020. Dynamics 365 Customer Insights će biti dostupan za Government Community Cloud (GCC), okruženje koje je izgrađeno da zadovolji veće potrebe za usklađenošću vladinih agencija Sjedinjenih Država. Agencije stiču jedinstven uvid u građane i koriste unapred ugrađenu veštačku inteligenciju za sticanje uvida koji poboljšavaju interakcije, osnažuju zaposlene i transformišu zajednice, dok istovremeno smanjuju IT složenost i ispunjavaju standarde za usaglašenost i bezbednost Sjedinjenih Država. Dynamics 365 Government ispunjava obimne zahteve Saveznog programa za upravljanje rizikom i autorizacijom (FedRAMP) Sjedinjenih Država i tako omogućava federalnim ustanovama Sjedinjenih Država da iskoriste uštedu troškova i rigoroznu bezbednost koju ima Microsoft Cloud.

## <a name="april-2020-updates"></a>Ispravke za april 2020. godine

Ispravke za april 2020. obuhvataju nekoliko funkcija, nadogradnje performansi i popravke grešaka.

### <a name="new-and-updated-features-in-april-2020"></a>Nove i ažurirane funkcije u aprilu 2020. godine

#### <a name="activities"></a>Aktivnosti

- **Mapiranje entiteta aktivnosti u standardni tip aktivnosti**
  
  Konfiguracija aktivnosti i skladištenje trenutno se zasnivaju na statičkom dizajnu kako biste ih videli u vremenskoj liniji. Semantičko značenje aktivnosti, koje ima potencijal za više slučajeva primene u modelima veštačke inteligencije, trenutno se ne koristi u potpunosti. Planiramo da dinamika vremena aktivnosti postane dinamičnija, zasnovana na vrsti aktivnosti i boljem semantičkom razumevanju aktivnosti. Ova funkcija ima za cilj identifikovanje vrste aktivnosti kako je definisano u odeljku Common Data Model za svaku započetu aktivnost.
  Za više informacija pogledajte [aktivnosti klijenta](activities.md).

#### <a name="data-ingestion"></a>Unos podataka

- **Unos podataka u realnom vremenu: aktivnosti**
  
  Unos podataka u realnom vremenu pruža podatke koji se odmah mogu koristiti, sve dok naknadno planirano osvežavanje ne povuče ove podatke iz izvora podataka.    
  Više informacija potražite u članku [Unos podataka u realnom vremenu](real-time-data-ingestion.md).

- **Poboljšanja u pripremi podataka**
  
  Saznajte više o podacima koji se unose u entitet. Sa rezimeom podataka možete razumeti karakteristike kvaliteta podataka koje mogu pomoći da se preduzmu odgovarajuće mere.    
  Više informacija potražite u članku [Istraživanje entiteta podataka](entities.md#exploring-a-specific-entitys-data).

- **Unesite analitičke podatke iz programa Dynamics 365 sa Common Data Service**
  
  Common Data Service je dostupan za kreiranje izvora podataka. Postojeći korisnici programa Dynamics 365 mogu uneti analitičke entitete iz Common Data Service u Customer Insights. Jedan izvor podataka može istovremeno da koristi isto jezero kojim upravlja Common Data Service u Customer Insights okruženju.    
  Za više informacija pogledajte članak [Povežite se sa podacima u jezeru podataka kojim upravlja Common Data Service](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Proširivost

- **Izvezi u LiveRamp**

  Aktivirajte svoje podatke u usluzi LiveRamp® da biste se povezali sa preko 500 platformi u digitalnim, društvenim i TV ekosistemima. Upotrebite svoje podatke u LiveRamp za ciljanje, suzbijanje i personalizovanje oglasnih kampanja.    
  Više informacija potražite u [LiveRamp&reg; konektoru](export-liveramp.md).

- **Customer Insights programski dodatak za Teams**
  
  Robot pruža mogućnosti pronalaženja za objedinjene profile klijenata. Pokazaće karticu sa do 15 polja iz rezultirajućeg profila kupca. Više podudaranja vraća listu rezultata na kojima možete odabrati profil.    
  Za više informacija pogledajte [Roboti za Teams za Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Mere

- **Stranica sa spiskom mera**
  
  Poboljšanja stranice sa merama uključuju podršku za radnje u vezi sa jednom merom i više mera odjednom. Uz to ćete pronaći polje za pretragu da biste brzo pronašli i pratili mere.    
  Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).

- **Poboljšanja složenih mera**
  
  Korisnici mogu da kreiraju, uređuju i brišu mere koje se zasnivaju na drugim merama. Na primer, mera izgrađena na drugoj meri koja je izgrađena na trećoj meri.

#### <a name="segments"></a>Segmenti

- **Dodatni činilac**
  
  Činilac u skupu dozvoljava segmentaciju za kupce po nekoliko mogućih vrednosti niski. Pre nego što je dodeljen ovaj činilac, morali ste da konstruišete takve segmente sa višestrukim uslovima ILI. Činilac u skupu vam omogućava da to uradite sa jednim uslovom.    
  Više informacija potražite u odeljku [Kreiranje i upravljanje segmentima](segments.md).

#### <a name="system-administration"></a>Administracija sistema

- **Kopirajte podešavanja konfiguracije u novo okruženje**
  
  Kopirajte svoju konfiguraciju iz jednog okruženja u drugo. Dok kreirate novo okruženje, možete odabrati postojeće okruženje iz kojeg želite da kopirate konfiguraciju. Trenutno podržavamo izvore podataka, objedinjavanje podataka, odnose, mere i segmente za kopiranje. Akreditivi izvora podataka i stvarni podaci se ne kopiraju.    
  Više informacija potražite u članku [Upravljanje okruženjem](manage-environments.md).
