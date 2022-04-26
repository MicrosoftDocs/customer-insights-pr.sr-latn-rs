---
title: Nove i predstojeće funkcije
description: Informacije o novim funkcijama, poboljšanjima i ispravkama grešaka.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 2f081306271a170cf3e250fc1a193cedb70aeec6
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547689"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Šta je novo u mogućnosti uvida u ciljnu grupu usluge Dynamics 365 Customer Insights

Drago nam je što možemo da najavimo naše najnovije ispravke. Ovaj članak rezimira funkcije verzija za javni pregled, poboljšanja opšte dostupnosti i ispravke za funkcije. Da biste videli dugoročne planove funkcija, pogledajte [planove izdanja Dynamics 365 i Power Platform](/dynamics365/release-plans/).

Ažuriranja objavljujemo od regiona do regiona. Tako da određeni regioni mogu da vide funkcije pre drugih. Ako nije drugačije navedeno, ne trebate ništa da preduzimate a mi ćemo automatski ažurirati aplikaciju bez prekida rada.

> [!TIP]
> Da biste prosledili i glasali za zahteve za funkcije i predloge za proizvode, idite na [Dynamics 365 portal za ideje u aplikacijama](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


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

Više informacija potražite u članku [Omogućavanje deljenja podataka Dataverse iz sopstvenog Azure Data Lake Storage (Preview)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

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

Više informacija potražite u članku [Povezivanje Azure Synapse izvor podataka (pregled)](connect-synapse.md).

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

Više informacija potražite u članku [Oštećeni izvori podataka](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Kraj pregleda za funkcije izveštavanja u mogućnosti uvida u angažovanje

Pregled Dynamics 365 Customer Insights mogućnosti uvida u angažovanje završen je 15. februara 2022. godine.  
Ova promena znači da probno iskustvo "Uvidi klijenata" više ne uključuje mogućnost kreiranja levaka niti druge funkcionalnosti izveštavanja.

Pozivamo vas da istražite i procenite mnoge druge funkcije korisničkog [uvida](https://dynamics.microsoft.com/ai/customer-insights/), Microsoft platforme za podatke o korisnicima (CDP).    
 
Za prelazni period, postojeći učesnici pregleda i dalje imaju pristup nekim mogućnostima i funkcionalnosti pregleda:

- Preuzimanje koda za upravljanje veb lokacijom ili aplikacijom za mobilne uređaje 
- Pogledajte događaje i svojstva događaja 
- Poboljšajte objedinjene profile sa prenaglašenom i prefinjenom manifestacijom kako biste imali koristi od pune vrednosti podataka korisnika
  
Tokom prelaznog perioda, uhvaćeni događaji se i dalje strimuju do povezanog Data Jezera. Kada se ova funkcionalnost isključi, deljenje podataka između uvida u angažovanje i korisnici uvidi će prestati i neće se novi događaji slati u povezano skladište.
Obratite se direktno timu Microsoft naloga ako imate pitanja o kraju pregleda mogućnosti. Tim naloga će vas obaveštavati o narednim lansiranjima. 

## <a name="january-2022-updates"></a>Ispravke za januar 2022. godine

Ispravke u januaru 2022.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analiza sentimenta povratnih informacija vašeg kupca

Customer Insights pruža novu funkciju sa AI napajanjem koja sintetiše sentiment klijenata i identifikuje određene poslovne aspekte kao mogućnosti za ciljana poboljšanja. Analizom pisanih povratnih informacija vaših kupaca možete dobiti tačne uvide uz nisku cenu. Analiza sentimenta koju napajaju modeli obrade prirodnog jezika (NLP) koji generišu dva izvedena uvida za ID svakog kupca. Ocena sentimenta (od –5 do 5) i lista primenljivih poslovnih aspekata. 

Više informacija potražite u članku [Analiza sentimenta u povratnim informacijama korisnika (Preview)](sentiment-analysis.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]