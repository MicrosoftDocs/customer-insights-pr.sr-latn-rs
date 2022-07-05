---
title: Obogatite profile klijenata poboljšanim adresama (sadrži video)
description: Obogatite i normalizujte informacije o adresama korisničkih profila pomoću Microsoft modela.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082078"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Obogatite profile klijenata poboljšanim adresama

Adrese u vašim podacima mogu biti nestrukturirane, nepotpune ili netačne. Koristite Microsoft modele za normalizaciju i obogaćivanje adresa u [formatu Common Data Model](/common-data-model/schema/core/applicationcommon/address) radi veće tačnosti i uvida.

Takođe možete da [obogatite adrese na izvorima podataka da](data-sources-enrichment.md) biste poboljšali tačnost podudaranja u procesu ujedinjenja podataka. 

## <a name="how-we-enhance-addresses"></a>Kako poboljšavamo adrese

Naš model prolazi kroz postupak u dva koraka za poboljšanje adrese. Prvo raščlanjuje adresu da bi identifikovao njene komponente i stavlja ih u strukturirani format. Zatim koristimo AI za ispravljanje, popunjavanje i standardizaciju vrednosti u adresi.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Primer

Informacije o adresi mogu biti u nestandardnom formatu i sadržati pravopisne greške. Model može rešiti ove probleme i kreirati dosledne adrese u objedinjenim korisničkim profilima.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Ograničenja

Poboljšane adrese funkcionišu samo sa vrednostima koje već postoje u podacima o unetim adresama. Model ne radi sledeće:

1. Ne proverava da li je adresa važeća.
2. Ne proverava da li je neka od vrednosti, poput poštanskih brojeva ili naziva ulica, važeća.
3. Ne menja vrednosti koje ne prepoznaje.

Model za poboljšanje adresa koristi tehnike zasnovane na mašinskom učenju. Kao i kod svakog modela zasnovanog na mašinskom učenju, 100% tačnost nije zagarantovana.

## <a name="supported-countries-or-regions"></a>Podržane zemlje ili regioni

Trenutno podržavamo obogaćivanje adresa u ovim zemljama ili regionima:

- Australija
- Kanada
- Francuska
- Nemačka
- Italija
- Japan
- Ujedinjeno Kraljevstvo
- Sjedinjene Države

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.

1. Izaberite **Obogati moje podatke** na pločici **Poboljšane adrese**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Snimak ekrana pločice Poboljšane adrese.":::

1. Pregledajte pregled, a zatim kliknite na dugme **Dalje**.

1. Izaberite opciju **skup podataka i** odaberite profil ili segment koji želite da obogatite. Entitet *kupca* obogaćuje sve profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

1. Izaberite način oblikovanja adresa u skupu podataka. Odaberite **Adresa sa jednim atributom** ako adrese u vašim podacima koriste jedno polje. Odaberite **Adresa sa više atributa** ako adrese u vašim podacima koriste više od jednog polja podataka.

1. Kliknite **na dugme** "Dalje" i mapirajte polja adrese iz objedinjenog entiteta kupca.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Poboljšana stranica za mapiranje polja adrese.":::

   > [!NOTE]
   > Zemlja/region je obavezan podatak za adrese i sa jednim i sa više atributa. Adrese koje ne sadrže važeće ili podržane vrednosti zemlje/regiona neće biti obogaćene.

1. Izaberite **Sledeće** da biste dovršili mapiranje polja.

1. Navedite **ime** za bogaćenje i izlazni **entitet**.

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

## <a name="view-enrichment-results"></a>Prikaži rezultate obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Broj **kupaca obogaćenih poljem obezbeđuje** dubinsku analizu pokrivenosti svakog obogaćenog polja.

### <a name="overview-card"></a>Kartica za pregled

Kartica **"Kupci menjaju pregled** " prikazuje detalje o pokrivenosti bogaćenjem:

- **Adrese obrađene i promenjene**: broj profila klijenata sa adresama koje su uspešno obogaćene.
- **Adrese obrađene i nisu promenjene**: broj profila klijenata sa adresama koje su prepoznate, ali nisu promenjene. To se obično dešava kada su ulazni podaci važeći i ne mogu se poboljšati bogaćenjem.
- **Adrese nisu obrađene i nisu** promenjene: broj profila sa adresama koje nisu prepoznate. Obično za ulazne podatke koji su nevažeći ili ih obogaćuje ne podržava.

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
