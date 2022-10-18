---
title: Šta je novo u sistemu Dynamics 365 Customer Insights
description: Informacije o novim funkcijama, poboljšanjima i ispravkama grešaka.
ms.date: 08/31/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: dcee60a73e0c32278553253040478c31e45237ae
ms.sourcegitcommit: 618ef15b434de0a68213383b6521ce2a60753afb
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/07/2022
ms.locfileid: "9638368"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Šta je novo u sistemu Dynamics 365 Customer Insights

Drago nam je što možemo da najavimo naše najnovije ispravke. Ovaj članak rezimira funkcije verzija za javni pregled, poboljšanja opšte dostupnosti i ispravke za funkcije. Da biste videli dugoročne planove funkcija, pogledajte [planove izdanja Dynamics 365 i Power Platform](/dynamics365/release-plans/).

Ažuriranja objavljujemo od regiona do regiona. Tako da određeni regioni mogu da vide funkcije pre drugih. Ukoliko nije drugačije navedeno, nije potrebno da preduzmete nikakve radnje, automatski ćemo ažurirati aplikaciju bez daunlouda.

> [!TIP]
> Da biste prosledili i glasali za zahteve za funkcije i predloge za proizvode, idite na [Dynamics 365 portal za ideje u aplikacijama](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="september-2022-updates"></a>Ispravke za septembar 2022.

Ispravke u septembru 2022.

### <a name="export-data-to-hubspot"></a>Izvoz podataka u HubSpot

Izvezite segmente objedinjenih profila kupaca u HubSpot i koristite ih za marketing e-pošte.

Više informacija potražite u članku [Izvoz segmenata u HubSpot](export-hubspot.md).

### <a name="remove-a-unified-field-or-entity-from-data-unification"></a>Uklanjanje objedinjenog polja ili entiteta iz ujedinjenja podataka

Polja i entitete možete da uklonite iz procesa ujedinjenja podataka.

Više informacija potražite u članku [Uklanjanje objedinjenog polja](data-unification-update.md#remove-a-unified-field).

### <a name="manage-unknown-customer-profiles"></a>Upravljanje nepoznatim profilima klijenata

Pamćenje personalizacije zavisi od bogatstva i potpunosti vaših podataka o korisnicima i Uvidi klijenata vam pomažu da ostvarite ove ciljeve. Možete da upravljate korisničkim profilima za korisnike za koje nemate nikakve informacije osim ID-a.

Više informacija potražite u članku Upravljanje [nepoznatim profilima pomoću uvida kupaca](manage-unknown-profiles.md).

## <a name="august-2022-updates"></a>Ispravke za avgust 2022.

Ispravke u avgustu 2022.

### <a name="contact-unification-in-b-to-b-environments"></a>Ujedinjenje kontakata u okruženjima od B do B

B-to-B okruženja u uvidima klijenata sada podržavaju poboljšano iskustvo ujedinjenja podataka.

Sada pored naloga možete da ujedinite kontakte da biste dobili pun prikaz poslovnih kontakata. Objedinjeni kontakti su povezani sa objedinjenim nalozima i sada su navedeni na karticama kupaca. 

Više informacija potražite u članku [Kreiranje objedinjenog profila kontakata](data-unification-contacts.md).

### <a name="create-and-export-of-segments-based-on-unified-contacts"></a>Kreiranje i izvoz segmenata zasnovanih na objedinjenim kontaktima

Zahvaljujući novom ujedinjenju kontakata, segmente kontakata možete kreirati pomoću kriterijuma iz kontakata, naloga ili od oba. Ovi segmenti se mogu izvoziti radi aktivacije u drugim uslugama.

Više informacija potražite u članku [Pregled izvoza](export-destinations.md).

### <a name="deployment-regions-aligned-with-microsoft-dataverse"></a>Oblasti primene usklađene sa Microsoft Dataverse

Prilikom kreiranja novog okruženja "Uvidi kupaca", možete izabrati region u kojem želite da usluga bude raspoređena i hostovana. Ažurirali smo izbor regiona sa kojima ćemo se uskladiti Microsoft Dataverse i Power Platform.

Sada možete lako da izaberete istu oblast kao postojeće Microsoft Dataverse okruženje ili Azure Data Lake nalog za skladištenje (ako odaberete tu opciju), u zavisnosti od raspoloživosti uvida kupaca u tom regionu.

Više informacija potražite u članku [Kreiranje novog okruženja](create-environment.md) i dostupnosti [proizvoda po geografiji](https://dynamics.microsoft.com/availability-reports/).

## <a name="july-2022-updates"></a>Ispravke za jul 2022.

Ispravke u julu 2022.

### <a name="export-to-moengage"></a>Izvoz u MoEngage

Izvezite segmente objedinjenih profila klijenata u MoEngage i koristite ih za marketing e-pošte u MoEngageu.

Više informacija potražite u članku [Izvoz segmenata u MoEngage](export-moengage.md).

### <a name="ssh-support-for-sftp-based-exports"></a>Podrška SSH izvozu sa sedištem u SFTP

Odaberite da li želite da potvrdite verodostojnost putem SSH ili korisničkog imena/lozinke za veze sa SFTP izvoznim odredištima.

Više informacija potražite u članku [Izvoz podataka u SFTP domaćine](export-sftp.md).

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>Personalizovanje iskustava sa podacima o poznatim i nepoznatim korisnicima

Upravljanje podacima o korisnicima nije novi izazov, ali postaje sve teži kako se korisnici kreću kroz različite digitalne kanale koje brendovi nude. Korisnik koji je poznat (potvrđena verodostojnost) u jednom kanalu postaje nepoznat (neautorizovan) u drugom ako nije prijavljen. Problem je često u tome što neautorizovani (nepoznati) korisnici nemaju uobičajeni ID. Može se koristiti za povezivanje smislenih atributa profila i generisanje objedinjenih profila klijenata. Uvidi klijenata pomažu u rešavanju ovog problema tako što unose podatke iz metoda praćenja na izvornim sistemima.

Više informacija potražite u članku [Personalizovanje iskustava sa podacima o poznatim i nepoznatim korisnicima](unknown-to-known.md).

## <a name="june-2022-updates"></a>Ispravke za jun 2022. godine

Ispravke u junu 2022.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Ažurirano korisničko iskustvo za izvore podataka i unošenje podataka

Uvoz podataka iz širokog spektra izvora podataka je osnova za konsolidovanje podataka korisnika u programu Dynamics 365 Customer Insights. Ponovo smo razmotrili korisničko iskustvo za uvoz i povezivanje izvora podataka. Ova ispravka ima za cilj da vam olakša unos podataka u korisničke uvide.

Više informacija potražite u članku [Pregled izvora podataka](data-sources.md).

### <a name="export-to-inmobi"></a>Izvezi u InMobi

InMobi pomaže brendovima da razumeju, identifikuju, angažuju i steknu potrošače. Segmente i druge podatke možete da izvezete u InMobi servis preko Azure Blob Storage naloga.

Više informacija potražite u članku [Izvoz u InMobi (pregled)](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>Podrška za zaključavanje u okviru stavke "Uvidi korisnika"

Customer Lockbox obezbeđuje interfejs za redigovanje i odobravanje (ili odbacivanje) zahteva za pristup podacima. Do ovih zahteva dolazi kada je potreban pristup podacima o podacima korisnika da bi se rešio predmet podrške.

Više informacija potražite u članku [Bezbedan pristup podacima klijenata pomoću okvira za zaključavanje kupca (Pregled)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview).

### <a name="connect-to-your-data-using-azure-private-link"></a>Povezivanje sa podacima pomoću Azure privatne veze

Azure Privatna veza omogućava korisničkim uvidima da se povežu sa vašim Azure Data Lake Storage nalogom preko privatnog krajnja tačka u virtuelnoj mreži. Za podatke u nalogu za skladištenje, koji nije izložen javnom Internetu, privatna veza omogućava povezivanje sa tom ograničenom mrežom.

Više informacija potražite u članku Korišćenje [privatne veze u uvidima klijenata](security-overview.md#set-up-an-azure-private-link).

## <a name="may-2022-updates"></a>Ispravke za maj 2022.

Ispravke u maju 2022.

### <a name="updated-data-unification-experience"></a>Ažurirano iskustvo ujedinjenja podataka

 Ujedinjenje podataka vam omogućava da jednom omalovažite izvore podataka u jedan glavni skup podataka koji obezbeđuje objedinjeni prikaz tih podataka. Podaci se mogu objediniti u jednom entitetu ili više entiteta. Prvo izaberite entitete [i izvorna polja, uklonite](map-entities.md)[duplirane zapise](remove-duplicates.md), navedite pravila za [uslove podudaranja](match-entities.md) i definišite [koja polja treba uključiti u objedinjene profile kupaca](merge-entities.md).

Više informacija potražite u članku [Pregled ujedinjenja podataka](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Osvežena matična stranica u uvidima kupaca

**Kućni** vodiči kroz proces konfiguracije za ključne funkcije i pružaju pregled segmenata, mera i podataka obogaćivanju. Osvežili smo iskustvo da bismo na prvi pogled pružili relevantnije informacije.

Više informacija potražite u članku Istraživanje [uvida klijenata](home.md).

### <a name="track-usage-of-a-segment"></a>Praćenje korišćenja segmenta

Sada možete da [pratite korišćenje segmenta u aplikacijama](segments.md#track-usage-of-a-segment) koje se zasnivaju na organizaciji koja Dataverse je povezana sa uvidom klijenata. Za [segmente uvida kupaca koji se koriste u putovanjima kupaca u Dynamics 365 Marketingu](/dynamics365/marketing/real-time-marketing-ci-profile), sistem vas obaveštava o korišćenju tog segmenta.

### <a name="export-to-criteo"></a>Izvezi u Criteo

Criteo je onlajn platforma koja pomaže korisnicima da upravljaju digitalnim oglašavanjem. Sada možete da izvozite segmente objedinjenih profila klijenata da biste generisali kampanje, obezbedili marketing e-pošte i koristili određene grupe kupaca sa programom Criteo.

Više informacija potražite u članku [Izvoz segmenata u Criteo (pregled)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Prerađena struktura dokumentacije za izradu životne sredine

Ponovo smo razmotrili dokumente za pomoć u vezi sa kreiranjem i upravljanjem okruženjima u uvidima klijenata. Članci su sada grupisani pod klima-okruženjem u sadržaju. Restrukturirani članci pružaju više smernica za različite načine za podešavanje okruženja i jasniju strukturu. Ako imate povratne informacije za deljenje, obavestite nas putem kontrola pred kraj članaka pomoći.

Više informacija potražite u članku [Kako da: kreiranje novog okruženja](create-environment.md).

## <a name="april-2022-updates"></a>Ispravke za april 2022. godine

Ispravke u aprilu 2022.

### <a name="dun--bradstreet-enrichment-preview"></a>Dun & Bradstreet obogaćivanje (Pregled)

Dun & Bradstreet pruža komercijalne podatke, analitiku i uvide za preduzeća. Omogućuje klijentima sa objedinjenim profilima klijenata za kompanije da obogaćuju svoje podatke. Obogaćivanje uključuje atribute kao što su DUNS broj, veličina kompanije, lokacija, industrija i još mnogo toga.

Više informacija potražite u članku [Obogaćivanje profila preduzeća pomoću Dun & Bradstreet (Preview)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Definisanje vrste mere prilikom kreiranja nove mere

Sada možete da napravite razliku između mera za pojedinačne profile i mera u celom svom poslovanju. Dok se poslovne mere prikazuju na matičnoj stranici "Uvidi kupaca", mere kupaca su izložene u detaljnim prikazima kupaca.

Više informacija potražite u članku [Korišćenje izrade mera za kreiranje mera od početka](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Konsolidacija dokumentacije uvida kupaca

Ponovo smo pregledali naše dokumentacione članke i uklonili pominjanje uvida o angažovanju i korisnici uvida. Krećući se napred, dosledno ćemo se odnositi na ime proizvoda "Customer Insights" kada pišemo o osnovnim funkcijama aplikacije. Ova promena takođe dovodi do značajnog restrukturiranja sadržaja, strukture URL adrese i putanja datoteka u osnovnom skladištu dokumentacije. Svi obeleživači ili postojeće veze nastavljaju sa radom i preusmeravaju se na ažurirane URL adrese.

Ako želite da nas obavestite kako doživljavate tu promenu ili uočite da nešto ne funkcioniše na očekivani način, recite nam prosleđivanje [povratnih informacija za ovu stranicu](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Ispravke za mart 2022.

Ispravke u martu 2022.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec obogaćivanje (pregled)

LiveRamp obezbeđuje rešavanje identiteta i konsolidaciju podataka korisnika. Lične identifikatore u podacima korisnika možete da mapirate u AbiliTec grafikon identiteta i primite AbiliTec ID-ove. Zatim možete da koristite ove lične datoteke za bolje ujedinjenje podataka klijenata.

Više informacija potražite u članku [Obogaćivanje profila klijenata podacima o identitetu iz programa LiveRamp (Preview)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organizovanje segmenata i mera pomoću oznaka i filtera

Ako vaša organizacija održava mnogo segmenata ili mera, pronalaženje pravog ponekad može da se oseti izazovnim. Ova nova funkcija vam omogućava da organizujete liste pomoću oznaka i kolona. Pomaže u brzom i lakom pronalaženju podataka i prilagođavanju prikaza.

Više informacija potražite u članku [Rad sa oznakama i kolonama](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Omogućavanje deljenja podataka prilikom Dataverse korišćenja sopstvenog naloga za skladištenje

Ako vaše okruženje koristi za skladištenje Azure Data Lake Storage podataka "Uvid korisnika", za deljenje podataka potrebna je Microsoft Dataverse dodatna konfiguracija.
Ranije ste mogli da omogućite deljenje podataka samo kada su Dataverse vaši podaci uskladišteni u našem upravljajućem jezeru sa podacima.

Više informacija potražite u članku [Omogućavanje deljenja podataka Dataverse iz sopstvenog Azure Data Lake Storage (Preview)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Nove izvozne destinacije: Iterable i Braze

Nastavljamo da širimo naš ekosistem izvoznih destinacija novim vezama. Sada možete da izvozite segmente u Iterable i Braze da biste koristili njihove usluge aktivacije.

Više informacija potražite u članku [Izvoz segmenata u Iterable (pregled)](export-iterable.md) i [Izvoz segmenata u Braze (pregled)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Poboljšanja izvoza Marketo i Google Ads

Promena API-ja u povezanim uslugama dovodi do toga da ispravke za linije spajanja mogu pouzdano i nesmetano da se pokreću. Objavili smo neka ažuriranja za izvoz u Marketo i Google Ads usluge:

- Google Ads: Nova verzija Google Ads export konektora pojednostavljuje iskustvo potvrde identiteta i sada vam omogućava da automatski kreirate novu Google Ads publiku. 
- Marketo: Nova verzija Marketo export konektora pruža podršku za Marketo ID, omogućavajući vam da izbegnete dupliranje podataka, ažurirate postojeće zapise i kreirate nove zapise u marketu. 

## <a name="february-2022-updates"></a>Ispravke za februar 2022.

Ispravke u februaru 2022.

### <a name="general-availability-for-prediction-models"></a>Opšta dostupnost predviđanje modela

Modeli za predviđanje, **uključujući pretplatnički churn**, **transactional churn** i **vrednost doživotnog klijenta (CLV)** postaju opšte dostupni kao deo uvida klijenata. 

Više informacija potražite u članku [Pregled predviđanja](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Novi izvor podataka: integracija sa Azure Synapse Analytics (pregled)

Azure Synapse Analytics je usluga analitike preduzeća koja ubrzava vreme na uvide u skladištima podataka i velikim sistemima podataka.

Organizacije koje već koriste mogu Azure Synapse Analytics da uneste te podatke u uvid kupca. 

Više informacija potražite u članku [Povezivanje Azure Synapse izvor podataka (Pregled)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp obogaćivanje (pregled)

LiveRamp obezbeđuje rešavanje identiteta i konsolidaciju podataka korisnika. Lične identifikatore u podacima korisnika možete da mapirate u AbiliTec grafikon identiteta i primite AbiliTec ID-ove. Zatim možete da koristite ove lične datoteke za bolje ujedinjenje podataka klijenata.

Više informacija potražite u članku [Obogaćivanje profila klijenata podacima o identitetu iz programa LiveRamp (Preview)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Obogaćivanje izvora podataka (pregled)

Koristite podatke iz izvora kao što su Microsoft i drugi partneri da biste obogatili podatke o klijentima pre ujedinjenja podataka. Izvor podataka obogaćivanja pomažu u proizvodnji veće potpunosti podataka i kvaliteta koji mogu da pomognu u postizanju boljih rezultata kada ujedinite svoje podatke.

Više informacija potražite u članku [Obogaćivanje izvora podataka (Preview)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Promena vlasnika okruženja

Dok nekoliko korisnika može da ima administratorske dozvole u programu Customer Insights, samo jedan korisnik je vlasnik okruženja. Poboljšano iskustvo vam omogućava da promenite vlasnika okruženja i preuzmete vlasništvo ako je bivši vlasnik napustio organizaciju. 

Više informacija potražite u članku [Promena vlasnika okruženja](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Proces pripreme podataka navodi razlog oštećenja oštećenih zapisa

Priprema podataka sada pokazuje razlog za oštećenje svih polja sa oštećenim podacima. Informacije su obezbeđene na pojedinačnom nivou zapisa radi lake identifikacije.

Više informacija potražite u članku [Oštećenje izvora podataka](data-sources.md#corrupt-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Kraj pregleda za funkcije izveštavanja u mogućnosti uvida u angažovanje

Pregled Dynamics 365 Customer Insights mogućnosti uvida u angažovanje završen je 15. februara 2022. godine.  
Ova promena znači da probno iskustvo "Uvidi klijenata" više ne uključuje mogućnost kreiranja levaka niti druge funkcionalnosti izveštavanja.

Pozivamo vas da istražite i procenite mnoge druge funkcije korisničkog [uvida](https://dynamics.microsoft.com/ai/customer-insights/), Microsoft platforme za podatke o korisnicima (CDP).    
 
Za prelazni period, postojeći učesnici pregleda i dalje imaju pristup nekim mogućnostima i funkcionalnosti pregleda:

- Preuzimanje koda za upravljanje veb lokacijom ili aplikacijom za mobilne uređaje 
- Pogledajte događaje i svojstva događaja 
- Poboljšajte objedinjene profile sa prenaglašenom i prefinjenom manifestacijom kako biste imali koristi od pune vrednosti podataka korisnika
  
Tokom prelaznog perioda, uhvaćeni događaji se i dalje strimuju do povezanog Data Jezera. Kada se ova funkcionalnost isključi, deljenje podataka će se zaustaviti i neće se novi događaji slati na povezano skladište.
Obratite se direktno timu Microsoft naloga ako imate pitanja o kraju pregleda mogućnosti. Tim naloga će vas obaveštavati o narednim lansiranjima. 

## <a name="january-2022-updates"></a>Ispravke za januar 2022. godine

Ispravke u januaru 2022.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analiza sentimenta povratnih informacija vašeg kupca

Customer Insights pruža novu funkciju sa AI napajanjem koja sintetiše sentiment klijenata i identifikuje određene poslovne aspekte kao mogućnosti za ciljana poboljšanja. Analizom pisanih povratnih informacija vaših kupaca možete dobiti tačne uvide uz nisku cenu. Analiza sentimenta koju napajaju modeli obrade prirodnog jezika (NLP) koji generišu dva izvedena uvida za ID svakog kupca. Ocena sentimenta (od –5 do 5) i lista primenljivih poslovnih aspekata. 

Više informacija potražite u članku [Analiza sentimenta u povratnim informacijama korisnika (Preview)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]