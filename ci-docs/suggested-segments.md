---
title: Predloženi segmenti na osnovu mera (pregled)
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
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170974"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Predloženi segmenti na osnovu mera (pregled)

Otkrijte zanimljive segmente svojih klijenata uz pomoć modela veštačke inteligencije. Ova funkcija koju pokreće mašinsko učenje predlaže segmente zasnovane na merama ili atributima klijenata. To može pomoći da poboljšate ključne indikatore performansi (KPI) ili da bolje razumete uticaj atributa u kontekstu drugih atributa.

> [!NOTE]
> Funkcija predloženih segmenata koristi automatizovana sredstva za procenu podataka i pravljenje predviđanja na osnovu podataka. Stoga ima mogućnost da se koristi kao metod profilisanja, jer je taj termin definisan Opštom uredbom o zaštiti podataka ("GDPR"). Vaša upotreba ove funkcije za obradu podataka može biti predmet GDPR-a ili drugih zakona ili propisa. Odgovorni ste za to da koristite Dynamics 365 Customer Insights, uključujući ovu funkciju, u skladu sa svim važećim zakonima i propisima, uključujući zakone koji se odnose na privatnost, lične podatke, biometrijske podatke, zaštitu podataka i poverljivost komunikacija.

:::image type="content" source="media/suggested-segments.png" alt-text="Stranica „Predloženi segmenti“ koja prikazuje detalje predloga u bočnom oknu.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Predloženi segmenti za poboljšanje KPI-ova

Ako koristite [mere kreirane za](measures.md) praćenje KPI indikatora, kreirajte segmente da biste videli uticaje na KPI indikator. Ove informacije možete da koristite za pokretanje visoko ciljane kampanje.

Na primer, pratite meru koja se zove *TotalSpendPerCustomer*. Kao preduzeće, želeli biste da ovaj broj raste. Izaberite meru kao primarni atribut, izaberite atribute koje želite da procenite za uticaj. Recimo, *nivo članstva*, *period članstva* i *zanimanje*. Customer Insights tada može da predloži segment koji vam govori koji je najveći uticaj te mere. Na primer, *Računovođe* koji su *zlatni* članovi i koji su sa vašim preduzećem *najmanje pet godina* su najuticajniji klijenti u pokazatelju *TotalSpendPerCustomer*. Za svaki predlog dobićete procenjenu veličinu segmenta. Ove informacije možete da koristite za kreiranje kampanja za ciljanu publiku.

## <a name="understand-what-influences-a-customer-attribute"></a>Shvatite šta utiče na atribut klijenta

Možete da odaberete atribut klijenta umesto mere kao primarni atribut. Na osnovu vašeg izbora uticaja na atribute, model veštačke inteligencije kreira niz predloga koji pokazuju kako izabrani atributi utiču na primarni atribut.

Na primer, vi birate *Nagrađeni član (Da/Ne)* kao primarni atribut. *Zakup*, *Zanimanje* i *Broj tiketa za podršku* postavljeni su kao drugi atributi od uticaja. Model veštačke inteligencije mogao bi predložiti segmente koji ukazuju da su uglavnom IT profesionalci sa mandatom duže od dve godine nagrađeni članovi. Još jedan predlog mogao bi naglasiti da su računovođe sa mandatom duže od godinu dana i sa manje od tri tiketa za podršku nagrađeni članovi.

## <a name="artificial-intelligence-usage"></a>Upotreba veštačke inteligencije

Koristeći primarni atribut i uticajne atribute, algoritam stabla odlučivanja predlaže zanimljive segmente. Predlozi se zasnivaju na pravilima ili obrascima koje je prihvatio algoritam veštačke inteligencije. Kao predlozi su prikazani samo segmenti koji se značajno razlikuju od prosečne populacije. Poređenje sa prosečnom populacijom zasniva se na izabranoj meri ili primarnom atributu.

### <a name="responsible-ai"></a>Odgovorni AI

Pomoću predloženih segmenata birate atribute da biste kreirali nove segmente i obradili podatke koje izaberete. Kada birate atribute, uključujući osetljive atribute kao što su rasa, seksualna orijentacija ili pol, morate biti sigurni da možete i treba da obrađujete te podatke. Odgovorni ste za poštovanje svih zakona koji se primenjuju na vašu organizaciju i pridržavanje principa i politika privatnosti vaše organizacije.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Različiti rezultati za primarne atribute sa kategorijskim i numeričkim vrednostima

Predlozi segmenata se razlikuju ako za primarni atribut odaberete numerički ili kategorički atribut. Vrednosti u kategoričkom atributu sadrže dve ili više kategorija ili tipova. Numerički atribut sadrži kvantitativne podatke i sa njima je povezan osećaj merenja.

Sa numeričkim atributom poput *godišnji prihod* ili *period članstva* kao primarnim atributom, sistem predlaže segmente koji imaju veću ili manju prosečnu vrednost numeričkog atributa u poređenju sa svim klijentima.

Kategorički atribut poput *zadovoljstvo klijenta* kao primarnim atributom dovodi do predloženih segmenata koji imaju veći ili manji procenat klijenata koji pripadaju određenoj kategoriji u poređenju sa procentom svih klijenata koji pripadaju istoj kategoriji. Na primer, *zadovoljstvo klijenata* se bira kao primarni atribut i sastoji se od tri kategorije (*Nisko*, *Srednje* i *Visoko*). Za svaku kategoriju biće predloženi segmenti koji imaju veći ili manji procenat kupaca koji pripadaju toj kategoriji u poređenju sa proporcijom svih kupaca u istoj kategoriji. Ako 22% svih klijenata ima *visoko* zadovoljstvo, onda će za tu kategoriju biti predloženi samo segmenti koji imaju veću ili manju proporciju klijenata sa *visokim* zadovoljstvom u poređenju sa 22%. Slično tome, segmenti će biti predloženi za svaku od ostalih kategorija (*Nisko* i *Srednje*) ako su statistički značajni.

> [!NOTE]
> Trenutno podržavamo samo primarne kategoričke atribute koji imaju do 10 kategorija. Ako želite da vidite predloge segmenata na osnovu primarnog atributa sa više od 10 kategorija, preporučujemo grupisanje nekih kategorija da biste smanjili broj kategorija na 10 ili manje. Ovo ograničenje odnosi se samo na primarne atribute. Radi uticaja na kategoričke atribute, trenutno podržavamo najviše 100 kategorija.

## <a name="generate-suggested-segments"></a>Generišite predložene segmente

1. Idite na **karticu Segmenti** i izaberite **karticu Predlozi (pregled**).

1. Izaberite **stavku Pronađi nove predloge** i odaberite **Stavku Poboljšaj meru/metriku**. Izaberite **početni ekran**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Izbor poboljšane mere na predloženim segmentima.":::

1. Odaberite atribut kupca ili meru kao primarni atribut i kliknite na dugme **Dalje**.

1. Izaberite atribute koji utiču na njih i izaberite **pokreni**.

   > [!TIP]
   > Odabir više uticajnih atributa poboljšava šanse za procenu kako oni utiču na primarni atribut. Nemojte uključivati atribute koji nemaju uticaja na primarni atribut. Na primer, ako su svi vaši kupci iz određene zemlje, nemojte uključiti atribut *zemlja*, jer to neće imati uticaja na izlaz.

U zavisnosti od broja korisničkih profila i izabranih atributa, obrada izabranih atributa može potrajati nekoliko minuta.

## <a name="manage-suggested-segments"></a>Upravljanje predloženim segmentima

Idite na **karticu Segmenti** i izaberite **karticu Predlozi (pregled**). U odeljku **Predlozi segmenata zasnovani na atributu** izaberite predloženi segment da biste prikazali dostupne radnje.

- **Prikažite** predložene detalje segmenta i vrednosti atributa ili pravila koja je AI model naučio.
- **Sačuvajte kao segment** predlog kao segment. Prikazuje se na kartici **"Svi segmenti** " i može se [osvežiti, urediti ili izbrisati](segments.md).
- **Uredite atribute** i izmenite konfigurisane atribute koji će zameniti trenutne predloge.
- **Osvežite predloge** da biste osvežili predloge zadržavajući konfigurisane atribute.

## <a name="limitations"></a>Ograničenja

1. Nepodudaranje procenjene veličine segmenta: Ako odaberete primarni atribut koji sadrži prazne vrednosti, to može uticati na procenjenu veličinu segmenta u predlozima segmenata. Prilikom čuvanja takvog segmenta, stvarna veličina segmenta može se razlikovati od prvobitne procene.

2. Primarni atributi logičkog tipa ne rade: Trenutno kao primarni atribut podržavamo samo nisku i numeričke tipove podataka.

3. Predloženi segmenti nisu dovoljno različiti: Imajte na umu da izabrani atributi i distribucija vrednosti tih atributa utiču na rezultate. Možete da promenite atribute uticaja ili čak primarni atribut da biste dobili različite rezultate.

[!INCLUDE [footer-include](includes/footer-banner.md)]