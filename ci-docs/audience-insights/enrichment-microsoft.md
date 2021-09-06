---
title: Obogaćivanje profila klijenata podacima kompanije Microsoft
description: Koristite zaštićene podatke kompanije Microsoft da biste obogatili podatke o klijentima afinitetima prema brendu i interesovanjima.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 726edb19a9fd97d80ae357103dc7d48ed38b005131ad44137b47d629a1c60b12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033878"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Obogatite profile klijenata afinitetima brenda i interesovanja (pregled)

Koristite zaštićene podatke kompanije Microsoft da biste obogatili podatke o klijentima afinitetima prema brendu i interesovanjima. Ovi afiniteti su zasnovani na podacima od osoba sa sličnim demografskim kategorijama kao vaši klijenti. Ove informacije vam pomažu da bolje razumete i segmentirate svoje klijente na osnovu njihovih afiniteta prema određenim brendovima i interesovanjima.

U uvidima o korisnicima, idite na **Podaci** > **Obogaćivanje** da biste [konfigurisali i pregledali obogaćivanja](enrichment-hub.md).

Da biste konfigurisali obogaćivanje afiniteta za brendove, idite na karticu **Otkrijte** i izaberite **Obogati moje podatke** na pločici **Brendovi**.

Da biste konfigurisali obogaćivanje afiniteta interesovanja, idite na karticu **Otkrijte** i izaberite **Obogati moje podatke** na pločici **Interesovanja**.

   > [!div class="mx-imgBorder"]
   > ![Pločice Brendovi i Interesovanja.](media/BrandsInterest-tile-Hub.png "Pločice Brendovi i Interesovanja")

## <a name="how-we-determine-affinities"></a>Kako utvrđujemo afinitete

Koristimo podatke za pretragu na mreži kompanije Microsoft za pronalaženje afiniteta prema brendovima i interesovanjima u različitim demografskim segmentima (definisani uzrastom, polom ili lokacijom). Obim pretraživanja brendova ili interesovanja na mreži određuje koliki afinitet demografski segment ima prema tom brendu ili interesovanju, u poređenju s drugim segmentima.

## <a name="affinity-level-and-score"></a>Nivo afiniteta i rezultat

Na svakom obogaćenom korisničkom profilu pružamo dve povezane vrednosti: nivo afiniteta i ocenu afiniteta. Ove vrednosti vam pomažu da utvrdite koliko je jak afinitet prema demografskom segmentu tog profila, prema brendu ili interesovanju u poređenju sa drugim demografskim segmentima.

*Nivo afiniteta* sastoji se od četiri nivoa, a *ocena afiniteta* se izračunava na skali od 100 poena koja se preslikava na nivo afiniteta.


|Nivo afiniteta |Ocena afiniteta  |
|---------|---------|
|Veoma visoko     | 85-100       |
|Visok     | 70-84        |
|Srednje     | 35-69        |
|Nizak     | 1-34        |

U zavisnosti od granularnosti kojom želite da merite afinitet, možete da koristite nivo afiniteta ili rezultat. Ocena afiniteta vam daje precizniju kontrolu.

## <a name="supported-countriesregions"></a>Podržane zemlje/regioni

Trenutno podržavamo sledeće opcije zemlje/regiona: Australija, Kanada (engleski), Francuska, Nemačka, Ujedinjeno Kraljevstvo ili Sjedinjene Države (engleski).

Da biste izabrali zemlju ili region, otvorite **Obogaćivanje brendova** ili **Obogaćivanje interesovanja** i izaberite opciju **Promeni** pored **Država / region**. U oknu **Podešavanja zemlje/regiona** odaberite opciju i izaberite **Primeni**.

### <a name="implications-related-to-country-selection"></a>Posledice koje se odnose na izbor zemlje

- Kada [birate sopstvene brendove](#define-your-brands-or-interests), sistem pruža predloge na osnovu izabrane zemlje ili regiona.

- Kada [birate delatnost](#define-your-brands-or-interests), dobićete najrelevantnije brendove ili interesovanja na osnovu izabrane zemlje ili regiona.

- Kada [obogaćujete profile](#refresh-enrichment), obogatićemo sve profile klijenata za koje dobijamo podatke za izabrane brendove i interesovanja, uključujući profile koji nisu u izabranoj zemlji ili regionu. Na primer, ako ste izabrali Nemačku, obogatićemo profile koji se nalaze u Sjedinjenim Državama ako imamo podatke o izabranim brendovima i interesovanjima u SAD.

## <a name="configure-enrichment"></a>Konfigurisanje obogaćivanja

Vođeno iskustvo vam pomaže u konfiguraciji obogaćivanja. 

### <a name="define-your-brands-or-interests"></a>Definisanje brendova ili interesovanja

Izaberite do pet brendova ili interesovanja pomoću jedne ili obe ove opcije:

- **Delatnost**: Izaberite svoju delatnost sa padajuće liste, a zatim odaberite najbolje brendove ili interesovanja za tu delatnost.
- **Izaberite svoje**: Unesite brend ili interesovanje koji su relevantni za vašu organizaciju, a zatim odaberite među predlozima za podudaranje. Ako ne navedemo brend ili interesovanje koje tražite, pošaljite nam povratne informacije koristeći vezu **Predloži**.

### <a name="review-enrichment-preferences"></a>Pregled željenih podešavanja za obogaćivanje

Pregledajte podrazumevane postavke obogaćivanja i ažurirajte ih po potrebi.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Snimak ekrana prozora za željena podešavanja obogaćivanja.":::

### <a name="select-entity-to-enrich"></a>Izaberite entitet koji želite da obogatite

Izaberite **Obogaćeni entitet** i odaberite skup podataka koji želite da obogatite podacima preduzeća iz kompanije Microsoft. Možete izabrati entitet Klijent da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.

### <a name="map-your-fields"></a>Mapiranje polja

Mapirajte polja iz vašeg objedinjenog entiteta klijenta da biste definisali demografski segment koji želite da sistem koristi za obogaćivanje podataka o klijentima. Mapirajte zemlju/region i barem atribute „Datum rođenja“ ili „Pol“. Pored toga, morate da mapirate najmanje jedan grad (i državu/pokrajinu) ili poštanski broj. Izaberite **Uredi** da biste definisali mapiranje polja i izaberite **Primeni** kada završite. Izaberite **Sačuvaj** da biste dovršili mapiranje polja.

Sledeći formati i vrednosti su podržani (vrednosti ne razlikuju velika i mala slova):

- **Datum rođenja**: Preporučujemo da se datum rođenja konvertuje u tip DateTime tokom unosa podataka. Alternativno, to može biti niska u [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formatu "yyyy-MM-dd" ili "yyyy-MM-ddTHH:mm:ss".
- **Pol**: Muški, Ženski, Nepoznat.
- **Poštanski broj**: Petocifreni poštanski brojevi za Sjedinjene Države, standardni poštanski broj svuda drugde.
- **Grad**: Naziv grada na engleskom jeziku.
- **Država/pokrajina**: Skraćenica sa dva slova za SAD i Kanadu. Skraćenica od dva ili tri slova za Australiju. Nije primenjivo za Francusku, Nemačku ili Ujedinjeno Kraljevstvo.
- **Zemlja/region**:

  - SAD: Sjedinjene Američke Države, Sjedinjene Države, SAD, USA, Amerika
  - CA: Kanada, CA
  - GB: Ujedinjeno Kraljevstvo, UK, Velika Britanija, GB, Ujedinjeno Kraljevstvo Velike Britanije i Severne Irske, Ujedinjeno Kraljevstvo Velike Britanije
  - AU: Australija, AU, Komonvelt Australije
  - FR: Francuska, FR, Francuska Republika
  - DE: Nemačka, Germany, Deutschland, Allemagne, DE, Savezna Republika Nemačka, Republika Nemačka

## <a name="review-and-name-the-enrichment"></a>Pregled i davanje naziva obogaćenju

Na kraju, treba da pregledate informacije i navedete ime za obogaćivanje.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stranica za pregled i imenovanje interesa.":::

## <a name="refresh-enrichment"></a>Osvežite obogaćivanje

Pokrenite obogaćivanje nakon konfigurisanja brendova, interesovanja i mapiranja polja za demografske kategorije. Da biste pokrenuli postupak, izaberite **Pokreni** na stranici za konfigurisanje brendova ili interesovanja. Pored toga, možete pustiti sistem da automatski pokrene obogaćivanje kao deo zakazanog osvežavanja.

U zavisnosti od veličine podataka o klijentima, može proći nekoliko minuta da se oplemenjivanje završi.

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies). Možete izabrati status procesa da biste videli detalje o toku celog posla. Nakon izbora **Vidi detalje** za jedan od zadataka posla, pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Nakon pokretanja postupka obogaćivanja, idite na **Moja obogaćivanja** da biste pregledali ukupan broj obogaćenih klijenata i raspodelu brendova ili interesovanja u obogaćenim profilima klijenata.

:::image type="content" source="media/my-enrichments.png" alt-text="Pregled rezultata nakon pokretanja procesa obogaćivanja.":::

Pregledajte obogaćene podatke izborom opcije **Prikaz obogaćenih podataka** u grafikonu. Obogaćeni podaci o brendovima idu u entitet **BrandAffinityFromMicrosoft**. Podaci za interesovanja su u entitetu **InterestAffinityFromMicrosoft**. Naći ćete i ove entitete navedene u grupi **Obogaćivanje** u odeljku **Podaci** > **Entiteti**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Pogledajte podatke o obogaćivanju na kartici klijenta

Afiniteti prema brendu i interesovanju mogu se takođe videti na karticama pojedinačnih klijenata. Idite na **Klijenti** i izaberite profil klijenta. Na kartici klijenta ćete pronaći grafikone za brendove ili interesovanja za koje ljudi u demografskom profilu tog klijenta imaju afinitet.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica klijenta sa obogaćenim podacima.":::

## <a name="next-steps"></a>Sledeći koraci

Nadogradite na obogaćenim podacima o klijentima. Kreirajte [segmente](segments.md) i [mere](measures.md), pa čak i [izvoz podataka](export-destinations.md) da pružite personalizovana iskustva svojim klijentima.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
