---
title: Obogaćivanje profila klijenata podacima kompanije Microsoft
description: Koristite vlasničke podatke korporacije Microsoft da biste obogatili podatke o klijentima afinitetima i udeo u izražavanju.
ms.date: 11/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 346c79d0a4d5cd5c47e91c195a48d3a153db0dc0
ms.sourcegitcommit: 9d3c9e4eb2ce20996a4f4fb44c42e3fe020c5b48
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/11/2021
ms.locfileid: "7818790"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Obogatite profile klijenata afinitetima i udeo u izražavanju (pregled)

Koristite Microsoftove vlasničke podatke da biste obogatili podatke o korisnicima afinitetima brenda, afinitetima interesovanja i udeo u izražavanju (SoV). Ovi afiniteti i soV zasnovani su na podacima osoba sa demografijom sličnom vašim kupcima. Ove informacije vam pomažu da bolje razumete i segmentite svoje kupce na osnovu njihovih afiniteta ili soV-a prema određenim brendovima i interesovanjima.

U uvidima o korisnicima, idite na **Podaci** > **Obogaćivanje** da biste [konfigurisali i pregledali obogaćivanja](enrichment-hub.md).

Da biste konfigurisali afinitete brenda i soV obogaćivanje, idite na **karticu** "Otkrij" i **izaberite stavku Obogati moje** podatke na **pločici** "Brendovi".

Da biste konfigurisali afinitete interesovanja i Obogaćivanje funkcije SOV, idite na **karticu "Otkrij"** i **izaberite stavku Obogati moje** podatke na **pločici** "Interesovanja".

   > [!div class="mx-imgBorder"]
   > ![Pločice Brendovi i Interesovanja.](media/BrandsInterest-tile-Hub.png "Pločice Brendovi i Interesovanja")

## <a name="how-we-determine-affinities-and-sov"></a>Kako određujemo afinitete i SOV

Koristimo podatke Microsoft pretrage na mreži da bismo pronašli afinitete i SOV za brendove i interesovanja u različitim demografskim segmentima (definisanim po uzrastu, polu ili lokaciji). Volumen pretrage na mreži za brend ili kamatu čini osnovu za utvrđivanje afiniteta ili SOV-a. Međutim, svaki od njih pruža različitu perspektivu razumevanja vaših klijenata.

- Afinitet je uporedni u različitim demografskim segmentima. Ove informacije možete koristiti za identifikaciju demografskih segmenata koji imaju najveće afinitete prema datom brendu ili interesovanju, u poređenju sa drugim segmentima.

- Udeo u izražavanju je uporedivo u odnosu na odabrane brendove ili interesovanja. Ove informacije možete da koristite da biste identifikovali koji brend ili interesovanje ima najveći deljeni glas za dati demografski segment, u poređenju sa drugim brendovima ili interesovanjima koja ste izabrali.

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

## <a name="share-of-voice-sov"></a>Udeo u izražavanju (SoV)

Izračunavamo SOV na skali od 100 poena. Ukupan SOV u svim brendovima ili interesovanjima za svaki obogaćeni profil kupaca sabira i do 100. Za razliku od afiniteta, SOV je u odnosu na brendove i interesovanja koja izaberete. Na primer, SoV vrednosti za 'Microsoft' mogu da se razlikuju ako su izabrani brendovi ('Microsoft', 'GitHub') naspram ('Microsoft', 'LinkedIn').

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

Izaberite **obogaćeni entitet i** odaberite skup podataka želite da obogatite podacima korporacije Microsoft. Možete izabrati entitet Klijent da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.

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

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Nakon pokretanja postupka obogaćivanja, idite na **Moja obogaćivanja** da biste pregledali ukupan broj obogaćenih klijenata i raspodelu brendova ili interesovanja u obogaćenim profilima klijenata.

:::image type="content" source="media/my-enrichments.png" alt-text="Pregled rezultata nakon pokretanja procesa obogaćivanja.":::

Videćete grafikon sa brojem obogaćenih profila klijenata tokom vremena i pregledima obogaćenih entiteta. Pregledajte obogaćene podatke tako što ćete **izabrati stavku** Pogledajte više **na nivou** afiniteta **ili udeo u izražavanju** grafikona. Obogaćeni podaci za brendove idu **na BrandAffinityFromMicrosoft** i **BrandShareOfVoiceFromMicrosoft** entitete. Podaci za interese su **u subjektima InterestAffinityFromMicrosoft** i **InterestShareOfVoiceFromMicrosoft.** Naći ćete i ove entitete navedene u grupi **Obogaćivanje** u odeljku **Podaci** > **Entiteti**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Pogledajte podatke o obogaćivanju na kartici klijenta

Brend i interesovanje SoV se takođe mogu videti na pojedinačnim karticama kupaca. Idite na **Klijenti** i izaberite profil klijenta. Na kartici kupca pronaći ćete grafikone za brend ili interes soV na osnovu osoba u demografskom profilu tog kupca.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica klijenta sa obogaćenim podacima.":::

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
