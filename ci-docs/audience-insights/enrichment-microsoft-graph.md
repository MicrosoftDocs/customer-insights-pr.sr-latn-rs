---
title: Obogatite profile klijenata pomoću usluge Microsoft Graph
description: Koristite vlasničke podatke iz programa Microsoft Graph da biste obogatili podatke o klijentima s afinitetima brenda i interesovanja.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406788"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Obogatite profile klijenata afinitetima brenda i interesovanja (pregled)

Koristite vlasničke podatke iz programa Microsoft Graph da biste obogatili podatke o klijentima s afinitetima brenda i interesovanja. Ovi afiniteti se određuju na osnovu podataka ljudi sa sličnom demografijom kao i vaši klijenti. Ove informacije vam pomažu da bolje razumete i segmentirate svoje klijente na osnovu njihovih afiniteta prema određenim brendovima i interesovanjima.

U uvidima o korisnicima, idite na **Podaci** > **Obogaćivanje** da biste [konfigurisali i pregledali obogaćivanja](enrichment-hub.md).

Da biste konfigurisali obogaćivanje afiniteta za brendove, idite na karticu **Otkrijte** i izaberite **Obogati moje podatke** na pločici **Brendovi**.

Da biste konfigurisali obogaćivanje afiniteta interesovanja, idite na karticu **Otkrijte** i izaberite **Obogati moje podatke** na pločici **Interesovanja**.

   > [!div class="mx-imgBorder"]
   > ![Pločice Brendovi i interesovanja](media/BrandsInterest-tile-Hub.png "Pločice Brendovi i interesovanja")

## <a name="about-microsoft-graph"></a>O usluzi Microsoft Graph

Mi koristimo podatke o pretraživanju na mreži iz programa Microsoft Graph da bismo pronašli afinitete prema brendovima i interesovanjima iz različitih demografskih segmenata (definisanih prema starosti, polu ili lokaciji). Obim pretraživanja brendova ili interesovanja na mreži određuje koliki afinitet demografski segment ima prema tom brendu ili interesovanju, u poređenju s drugim segmentima.

[Saznajte više o usluzi Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Ocena i pouzdanost afiniteta

**Ocena afiniteta** se izračunava se na skali od 100 poena, gde 100 predstavlja segment koji ima najveći afinitet prema brendu ili interesovanju.

Parametar **pouzdanosti afiniteta** takođe se izračunava na skali od 100 poena. To ukazuje na nivo pouzdanosti sistema da segment ima afinitet prema brendu ili interesovanju. Nivo pouzdanosti se zasniva na veličini segmenta i granularnosti segmenta. Veličina segmenta određuje se količinom podataka koju imamo za određeni segment. Granularnost segmenta se određuje po broju atributa (starost, pol, lokacija) koji postoje na profilu.

Ne normalizujemo rezultate za vaš skup podataka. Zbog toga možda nećete videti sve moguće vrednosti ocene afiniteta za svoj skup podataka. Na primer, u vašim podacima možda neće biti obogaćenog profila klijenta sa ocenom afiniteta 100. To je moguće ako u demografskom segmentu nema klijenata koji su postigli 100 za određeni brend ili interesovanje.

> [!TIP]
> Kada [kreirate segmente](segments.md) pomoću ocena afiniteta, pregledajte raspodelu ocena afiniteta za svoj skup podataka pre nego što odlučite o odgovarajućim graničnim vrednostima ocena. Na primer, ocena afiniteta od 10 može se smatrati značajnom u skupu podataka koji ima najviši rezultat afiniteta od samo 25 za dati brend ili interesovanje.

## <a name="supported-countriesregions"></a>Podržane zemlje/regioni

Trenutno podržavamo sledeće opcije zemlje/regiona: Australija, Kanada (engleski), Francuska, Nemačka, Ujedinjeno Kraljevstvo ili Sjedinjene Države (engleski).

Da biste izabrali zemlju, otvorite **Obogaćivanje brendova** ili **Obogaćivanje kamata** i izaberite **Promeni** pored stavke **Država/region**. U oknu **Podešavanja zemlje/regiona** odaberite opciju i izaberite **Primeni**.

### <a name="implications-related-to-country-selection"></a>Posledice koje se odnose na izbor zemlje

- Kada [odaberete sopstvene brendove](#define-your-brands-or-interests), obezbedićemo predloge na osnovu odabrane zemlje/regiona.

- Kada [birate delatnost](#define-your-brands-or-interests), identifikovaćemo najrelevantnije brendove ili interesovanja na osnovu izabrane zemlje/regiona.

- Kada [mapirate polja](#map-your-fields), ako polje Zemlja/Region nije mapirano, koristićemo Microsoft Graph podatke iz izabrane zemlje/regiona da bismo obogatili vaše profile klijenta. Taj izbor ćemo iskoristiti i za obogaćivanje profila klijenata koji nemaju dostupne podatke o zemlji/regionu.

- Kada [obogaćujete profile](#refresh-enrichment), obogatićemo sve profile klijenata za koje imamo dostupne Microsoft Graph podatke za izabrane brendove i interesovanja, uključujući profile koji nisu u izabranoj zemlji/regionu. Na primer, ako ste izabrali Nemačku, obogatićemo profile smeštene u Sjedinjenim Državama ako imamo Microsoft Graph podatke za izabrane brendove i interesovanja u SAD.

## <a name="configure-enrichment"></a>Konfigurisanje obogaćivanja

Konfigurisanje obogaćivanja za brendove ili interesovanja se sastoji od dva koraka:

### <a name="define-your-brands-or-interests"></a>Definisanje brendova ili interesovanja

Izaberite neku od sledećih opcija:

- **Delatnost**: Sistem identifikuje najbolje brendove ili interesovanja koja su relevantna za vašu delatnost i obogaćuje vaše podatke o klijentima.
- **Odaberite sopstveno**: Izaberite do pet stavki sa liste brendova ili interesovanja koja su najrelevantnija za vašu organizaciju.

Da biste dodali brend ili interesovanje, unesite ga u polje za unos da biste dobili predloge na osnovu termina koji se podudaraju. Ako ne navedemo brend ili interesovanje koje tražite, pošaljite nam povratne informacije koristeći vezu **Predloži**.

### <a name="map-your-fields"></a>Mapiranje polja

Mapirajte polja vašeg objedinjenog entiteta klijenta u najmanje dva atributa da biste definisali demografski segment koji želite da upotrebimo za obogaćivanje podataka o klijentima. Izaberite **Uredi** da biste definisali mapiranje polja i izaberite **Primeni** kada završite. Izaberite **Sačuvaj** da biste dovršili mapiranje polja.

Sledeći formati i vrednosti su podržani, vrednosti ne razlikuju velika i mala slova:

- **Datum rođenja**: Preporučujemo da se datum rođenja konvertuje u tip DateTime tokom unosa podataka. Alternativno, to može biti niz u [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formatu „yyyy-MM-dd“ ili „yyyy-MM-ddTHH:mm:ssZ“.
- **Pol**: Muško, Žensko, Nepoznato
- **Poštanski broj**: Petocifreni poštanski brojevi za SAD, standardni poštanski broj na svim drugim mestima
- **Grad**: Naziv grada na engleskom jeziku
- **Država/pokrajina**: Skraćenica sa dva slova za SAD i Kanadu. Skraćenica od dva ili tri slova za Australiju. Nije primenjivo za Francusku, Nemačku ili Ujedinjeno Kraljevstvo.
- **Zemlja/region**:

  - SAD: Sjedinjene Američke Države, Sjedinjene Države, SAD, USA, Amerika
  - CA: Kanada, CA
  - GB: Ujedinjeno Kraljevstvo, UK, Velika Britanija, GB, Ujedinjeno Kraljevstvo Velike Britanije i Severne Irske, Ujedinjeno Kraljevstvo Velike Britanije
  - AU: Australija, AU, Komonvelt Australije
  - FR: Francuska, FR, Francuska Republika
  - DE: Nemačka, Germany, Deutschland, Allemagne, DE, Savezna Republika Nemačka, Republika Nemačka

## <a name="refresh-enrichment"></a>Osvežite obogaćivanje

Pokrenite obogaćivanje nakon konfigurisanja brendova, interesovanja i mapiranja polja za demografske kategorije. Da biste pokrenuli postupak, izaberite **Pokreni** na stranici za konfigurisanje brendova ili interesovanja. Pored toga, možete pustiti sistem da automatski pokrene obogaćivanje kao deo zakazanog osvežavanja.
U zavisnosti od veličine podataka o klijentima, može proći nekoliko minuta da se oplemenjivanje završi.

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies). Možete izabrati status procesa da biste videli detalje o toku celog posla. Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Nakon pokretanja postupka obogaćivanja, idite na **Moja obogaćivanja** da biste pregledali ukupan broj obogaćenih klijenata i raspodelu brendova ili interesovanja u obogaćenim profilima klijenata.

:::image type="content" source="media/my-enrichments.png" alt-text="Pregled rezultata nakon pokretanja procesa obogaćivanja":::

Pregledajte obogaćene podatke izborom opcije **Prikaz obogaćenih podataka** u grafikonu. Obogaćeni podaci o brendovima idu u entitet **BrandAffinityFromMicrosoft**. Podaci za interesovanja su u entitetu **InterestAffinityFromMicrosoft**. Naći ćete i ove entitete navedene u grupi **Obogaćivanje** u odeljku **Podaci** > **Entiteti**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Pogledajte podatke o obogaćivanju na kartici klijenta

Afiniteti prema brendu i interesovanju mogu se takođe videti na karticama pojedinačnih klijenata. Idite na **Klijenti** i izaberite profil klijenta. Na kartici klijenta ćete pronaći grafikone za brendove ili interesovanja za koje ljudi u demografskom profilu tog klijenta imaju afinitet.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica klijenta sa obogaćenim podacima":::

## <a name="next-steps"></a>Sledeći koraci

Nadogradite na obogaćenim podacima o klijentima. Kreirajte [segmente](segments.md), [mere](measures.md), pa čak i [izvoz podataka](export-destinations.md) da biste pružili personalizovana iskustva svojim klijentima.
