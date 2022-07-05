---
title: Predloženi segmenti (pregled)
description: Neka vam mašinsko učenje pomogne da pronađete nove i zanimljive segmente zasnovane na atributima klijenata.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: 9229bef1c5df06de973aa671ca70c6c8462d51cf
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082750"
---
# <a name="suggested-segments-preview"></a>Predloženi segmenti (pregled)

Otkrijte zanimljive segmente svojih klijenata uz pomoć modela veštačke inteligencije. Ova funkcija koju pokreće mašinsko učenje predlaže segmente zasnovane na merama ili atributima klijenata. Može vam pomoći da poboljšate KPI-ove ili da bolje razumete uticaj atributa u kontekstu drugih atributa. 

> [!NOTE]
> Predložena funkcija segmenata koristi automatizovana sredstva za procenu podataka i predviđanje na osnovu tih podataka, te stoga ima mogućnost da se koristi kao metoda profilisanja, jer je taj pojam definisan Opštom uredbom o zaštiti podataka („GDPR“). Vaša upotreba ove funkcije za obradu podataka može biti predmet GDPR-a ili drugih zakona ili propisa. Odgovorni ste za to da koristite Dynamics 365 Customer Insights, uključujući ovu funkciju, u skladu sa svim važećim zakonima i propisima, uključujući zakone koji se odnose na privatnost, lične podatke, biometrijske podatke, zaštitu podataka i poverljivost komunikacija.

:::image type="content" source="media/suggested-segments.png" alt-text="Stranica „Predloženi segmenti“ koja prikazuje detalje predloga u bočnom oknu.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Predloženi segmenti za poboljšanje KPI-ova

Kao korisnik uvida klijenata, verovatno imate kreiran niz [mera koje pomažu](measures.md) u praćenju ključnih indikatora performansi (KPI). Važno je razumeti kako određeni atributi utiču na ovaj KPI da bi kreirao segmente i vodio visoko ciljanu kampanju.   
Na primer, pratite meru koja se zove *TotalSpendPerCustomer*. Kao preduzeće, želeli biste da ovaj broj raste. Izborom mere kao primarnog atributa, omogućava vam se da izaberete atribute za koje želite da procenite uticaj. Recimo, *nivo članstva*, *period članstva* i *zanimanje*. Customer Insights tada može da predloži segment koji vam govori koji je najveći uticaj te mere. Na primer, *Računovođe* koji su *zlatni* članovi i koji su sa vašim preduzećem *najmanje pet godina* su najuticajniji klijenti u pokazatelju *TotalSpendPerCustomer*. Za svaki predlog dobićete procenjenu veličinu segmenta. Ove informacije možete da koristite za kreiranje kampanja za ciljanu publiku.

## <a name="understand-what-influences-a-customer-attribute"></a>Shvatite šta utiče na atribut klijenta

Možete da odaberete atribut klijenta umesto mere kao primarni atribut. Na osnovu vašeg izbora uticaja na atribute, model veštačke inteligencije kreira niz predloga koji pokazuju kako izabrani atributi utiču na primarni atribut.   
Na primer, vi birate *Nagrađeni član (Da/Ne)* kao primarni atribut. *Zakup*, *Zanimanje* i *Broj tiketa za podršku* postavljeni su kao drugi atributi od uticaja. Model veštačke inteligencije mogao bi predložiti segmente koji ukazuju da su uglavnom IT profesionalci sa mandatom duže od dve godine nagrađeni članovi. Još jedan predlog mogao bi naglasiti da su računovođe sa mandatom duže od godinu dana i sa manje od tri tiketa za podršku nagrađeni članovi. 

## <a name="artificial-intelligence-usage"></a>Upotreba veštačke inteligencije

Koristeći primarni atribut i uticajne atribute, algoritam stabla odlučivanja predlaže zanimljive segmente. Predlozi se zasnivaju na pravilima ili obrascima koje je prihvatio algoritam veštačke inteligencije. Kao predlozi su prikazani samo segmenti koji se značajno razlikuju od prosečne populacije. Poređenje sa prosečnom populacijom zasniva se na izabranoj meri ili primarnom atributu.

### <a name="responsible-ai"></a>Odgovorni AI

Predloženi segmenti vam omogućavaju da izaberete atribute za kreiranje novih segmenata i obradu podataka koje izaberete. Kada birate atribute, uključujući osetljive atribute kao što su rasa, seksualna orijentacija ili pol, morate biti sigurni da možete i treba da obrađujete te podatke. Odgovorni ste za poštovanje svih zakona koji se primenjuju na vašu organizaciju i pridržavanje principa i politika privatnosti vaše organizacije.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Različiti rezultati za primarne atribute sa kategorijskim i numeričkim vrednostima

Predlozi segmenata se razlikuju ako za primarni atribut odaberete numerički ili kategorički atribut. Vrednosti u kategoričkom atributu sadrže dve ili više kategorija ili tipova. Numerički atribut sadrži kvantitativne podatke i sa njima je povezan osećaj merenja.

Sa numeričkim atributom poput *godišnji prihod* ili *period članstva* kao primarnim atributom, sistem predlaže segmente koji imaju veću ili manju prosečnu vrednost numeričkog atributa u poređenju sa svim klijentima.

Kategorički atribut poput *zadovoljstvo klijenta* kao primarnim atributom dovodi do predloženih segmenata koji imaju veći ili manji procenat klijenata koji pripadaju određenoj kategoriji u poređenju sa procentom svih klijenata koji pripadaju istoj kategoriji. Na primer, *zadovoljstvo klijenata* se bira kao primarni atribut i sastoji se od tri kategorije (*Nisko*, *Srednje* i *Visoko*). Za svaku kategoriju biće predloženi segmenti koji imaju veći ili manji procenat klijenata koji pripadaju toj kategoriji u poređenju sa proporcijom svih klijenata u istoj kategoriji. Ako 22% svih klijenata ima *visoko* zadovoljstvo, onda će za tu kategoriju biti predloženi samo segmenti koji imaju veću ili manju proporciju klijenata sa *visokim* zadovoljstvom u poređenju sa 22%. Slično tome, segmenti će biti predloženi za svaku od ostalih kategorija (*Nisko* i *Srednje*) ako su statistički značajni.

> [!NOTE]
> Trenutno podržavamo samo primarne kategoričke atribute koji imaju do 10 kategorija. Ako želite da vidite predloge za segmente zasnovane na primarnom atributu sa više od 10 kategorija, preporučujemo da neke od kategorija grupišete da biste smanjili broj kategorija na 10 ili manje. Ovo ograničenje odnosi se samo na primarne atribute. Radi uticaja na kategoričke atribute, trenutno podržavamo najviše 100 kategorija.

## <a name="generate-suggested-segments"></a>Generišite predložene segmente

1. Idite na **Segmenti**.

1. Izaberite karticu **Predlozi (pregled)**.

1. Izaberite **Dobijte nove predloge** da biste započeli vođeno iskustvo.

1. Odaberite meru ili atribut klijenta kao primarni atribut i izaberite **Sledeće**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Izbor primarnog atributa za predloge za predložene segmente.":::

1. Izaberite uticajne atribute i izaberite **Sačuvaj**.
   
   > [!TIP]
   > Odabir više uticajnih atributa poboljšava šanse za procenu kako oni utiču na primarni atribut. Ne uključujte atribute koji nemaju uticaj na primarni atribut. Na primer, ako su svi vaši kupci iz određene zemlje, nemojte uključiti atribut *zemlja*, jer to neće imati uticaja na izlaz.

1. U zavisnosti od broja korisničkih profila i izabranih atributa, obrada izabranih atributa može potrajati nekoliko minuta. 

## <a name="view-details-of-a-suggested-segment"></a>Prikaz detalja predloženog segmenta

Kada model veštačke inteligencije generiše predloge, naći ćete ih na listi **Segmenti** > **Predlozi (pregled)**.
 
Izaberite predloženi segment da biste pregledali detalje tog predloga. Takođe možete pregledati vrednosti atributa ili pravila koja je model veštačke inteligencije naučio da bi predložio izabrani segment.

## <a name="save-a-suggestion-as-a-segment"></a>Čuvanje predloga kao segmenta

1. Idite na **Segmenti** > **Predlozi (pregled)**.

1. Izaberite segment koji želite da sačuvate. 

1. U bočnom oknu izaberite **Sačuvaj kao segment**. 

1. Kada sačuvate segment, prikazaće se na listi segmenata na kartici **Svi segmenti**. On može biti [osvežen, izmenjen ili izbrisan kao i bilo koji drugi segment](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Osvežite ili izmenite skup predloga

1. Idite na **Segmenti** > **Predlozi (pregled)**.

1. Izaberite **Osveži predloge** da biste osvežili predloge uz zadržavanje konfigurisanih atributa. Ili izaberite **Uređivanje atributa** da biste izmenili konfigurisane atribute. Sistem će ponovo pokrenuti model veštačke inteligencije, generisati predloge za segmente na osnovu najnovijih podataka i zameniti trenutne predloge.

## <a name="limitations"></a>Ograničenja

1. Nepodudaranje procenjene veličine segmenta: Ako odaberete primarni atribut koji sadrži prazne vrednosti, to može uticati na procenjenu veličinu segmenta u predlozima segmenata. Prilikom čuvanja takvog segmenta, stvarna veličina segmenta može se razlikovati od prvobitne procene.
 
2. Primarni atributi logičkog tipa ne rade: Trenutno kao primarni atribut podržavamo samo nisku i numeričke tipove podataka.

3. Predloženi segmenti nisu dovoljno različiti: Imajte na umu da izabrani atributi i distribucija vrednosti tih atributa utiču na rezultate. Možete da promenite atribute uticaja ili čak primarni atribut da biste dobili različite rezultate.



[!INCLUDE [footer-include](includes/footer-banner.md)]