---
title: Obogatite profile klijenata brendovima i podacima o interesovanjima korporacije Microsoft (pregled)
description: Koristite vlasničke podatke korporacije Microsoft da biste obogatili podatke o korisnicima afinitetima udeo u izražavanju.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: e1827adca10a3b193c02a20c4abccacf73194a77
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082708"
---
# <a name="enrich-customer-profiles-with-brands-and-interests-data-from-microsoft-preview"></a>Obogatite profile klijenata brendovima i podacima o interesovanjima korporacije Microsoft (pregled)

Koristite Microsoftove vlasničke podatke da biste obogatili podatke o korisnicima afinitetima brenda, afinitetima interesovanja i udeo u izražavanju (SoV). Ovi afiniteti i soV zasnovani su na podacima osoba sa demografijom sličnom vašim kupcima. Ove informacije vam pomažu da bolje razumete i segmentite svoje kupce na osnovu njihovih afiniteta ili soV-a prema određenim brendovima i interesovanjima.

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

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.

   - Da biste konfigurisali afinitete brenda i Obogaćivanje SOV-a, izaberite **stavku Obogati moje** podatke na **pločici** Brendovi.

   - Da biste konfigurisali afinitete interesovanja i Obogaćivanje soV-a, izaberite **stavku Obogati moje** podatke na **pločici** "Interesovanja".

   > [!div class="mx-imgBorder"]
   > ![Pločice Brendovi i Interesovanja.](media/BrandsInterest-tile-Hub.png "Pločice Brendovi i Interesovanja")

1. Pregledajte pregled, a zatim kliknite na dugme **Dalje**.

1. Da biste promenili državu ili region, kliknite na **dugme "** Promeni" pored **stavke "Zemlja/region"**. U oknu **sa postavkama države**/regiona odaberite podržanu [državu/region i izaberite](#supported-countriesregions) stavku **Primeni**.

   > [!NOTE]
   > Kada birate sopstvene brendove, sistem pruža predloge na osnovu izabrane zemlje ili regiona. Kada birate delatnost, dobićete najrelevantnije brendove ili interesovanja na osnovu izabrane zemlje ili regiona.

1. Izaberite do pet brendova ili interesovanja pomoću jedne ili obe ove opcije:

   - **Delatnost**: Izaberite svoju delatnost sa padajuće liste, a zatim odaberite najbolje brendove ili interesovanja za tu delatnost.
   - **Izaberite svoje**: Unesite brend ili interesovanje koji su relevantni za vašu organizaciju, a zatim odaberite među predlozima za podudaranje. Ako ne navedemo brend ili interesovanje koje tražite, pošaljite nam povratne informacije koristeći vezu **Predloži**.

1. Kliknite **na dugme** "Dalje" i pregledajte podrazumevane željene opcije za obogaćivanje i ažurirajte ih po potrebi.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Snimak ekrana prozora za željena podešavanja obogaćivanja.":::

1. Izaberite **Sledeće**.

1. Izaberite opciju **Skup podataka i odaberite** profil ili segment koji želite da obogatite podacima korporacije Microsoft. Entitet *kupca* obogaćuje sve profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

1. Izaberite **Sledeće**.

1. Mapirajte polja iz objedinjenog entiteta klijenta na Microsoft podatke.

   > [!NOTE]
   > Potreban je bar datum rođenja ili atributi pola. Država/region i najmanje grad (i država/pokrajina) ili poštanski broj su obavezni. Preporučujemo da se datum rođenja konvertuje u tip dateTime tokom unošenja podataka. Alternativno, to može biti niska u [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formatu "yyyy-MM-dd" ili "yyyy-MM-ddTHH:mm:ss".

1. Izaberite **Sledeće** da biste dovršili mapiranje polja.

1. Navedite naziv obogaćivanja. Ime **entiteta izlaza** se automatski bira.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stranica za pregled i imenovanje interesa.":::

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

1. Kliknite **na dugme** "Pokreni" da biste započeli proces obogaćivanja ili blizu da biste se vratili na stranicu **"Obogaćivanje** ".

   Kada obogaćujete profile, obogatićemo sve profile klijenata za koje dobijamo podatke za izabrane brendove i interesovanja, uključujući profile koji nisu u izabranoj zemlji ili regionu. Na primer, ako ste izabrali Nemačku, obogatićemo profile koji se nalaze u Sjedinjenim Državama ako imamo podatke o izabranim brendovima i interesovanjima u SAD.

## <a name="view-enrichment-results"></a>Prikaži rezultate obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Pregled rezultata nakon pokretanja procesa obogaćivanja.":::

Rezultati uključuju nivo **afiniteta** ili **udeo u izražavanju** grafikone.

Entiteti kreirani od obogaćivanja navedeni su u grupi "Obogaćenje **"** u **entitetima** > **podataka**. Obogaćeni podaci za brendove idu **na BrandAffinityFromMicrosoft** i **BrandShareOfVoiceFromMicrosoft** entitete. Podaci za interese su u **subjektima InterestAffinityFromMicrosoft** i **InterestShareOfVoiceFromMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Pogledajte podatke o obogaćivanju na kartici klijenta

Brend i interesovanje SoV se takođe mogu videti na pojedinačnim karticama kupaca. Idite na **Klijenti** i izaberite profil klijenta. Na kartici kupca pronaći ćete grafikone za brend ili interes soV na osnovu osoba u demografskom profilu tog kupca.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartica klijenta sa obogaćenim podacima.":::

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
