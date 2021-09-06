---
title: Obogaćivanje poboljšavanja adrese
description: Obogatite i normalizujte informacije o adresama korisničkih profila pomoću Microsoft modela.
ms.date: 07/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fb3fee72b3420c636d549b600c468c574ee33a662bfafd096247dfddf40150bd
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032683"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Obogaćivanje korisničkih profila sa poboljšanim adresama

Adrese u vašim podacima mogu biti nestrukturirane, nepotpune ili netačne. Koristite Microsoft modele za normalizaciju i obogaćivanje adresa u [formatu Common Data Model](/common-data-model/schema/core/applicationcommon/address) radi veće tačnosti i uvida.

## <a name="how-we-enhance-addresses"></a>Kako poboljšavamo adrese

Naš model prolazi kroz postupak u dva koraka za poboljšanje adrese. Prvo raščlanjuje adresu da bi identifikovao njene komponente i stavlja ih u strukturirani format. Zatim koristimo AI za ispravljanje, popunjavanje i standardizaciju vrednosti u adresi.

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

Poboljšane adrese funkcionišu samo sa vrednostima koje već postoje u podacima unetih adresa. Model ne radi sledeće: 

1. Ne proverava da li je adresa važeća.
2. Ne proverava da li je neka od vrednosti, poput poštanskih brojeva ili naziva ulica, važeća.
3. Ne menja vrednosti koje ne prepoznaje.

Model za poboljšanje adresa koristi tehnike zasnovane na mašinskom učenju. Iako primenjujemo visok prag pouzdanosti kada model menja ulaznu vrednost, kao i kod bilo kog modela zasnovanog na mašinskom učenju, stopostotna tačnost nije zagarantovana.

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

Adrese moraju da sadrže vrednost zemlje/regiona. Ne obrađujemo adrese za zemlje ili regione koji nisu podržani i adrese za koje nije navedena zemlja ili region.

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite na **Podaci** > **Obogaćivanje**.

1. Izaberite **Obogati moje podatke** na pločici **Poboljšane adrese**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Snimak ekrana pločice Poboljšane adrese.":::

1. Izaberite **Skup podataka klijenta** i odaberite entitet koji sadrži adrese koje želite da obogatite. Možete izabrati entitet *Klijent* da obogatite adrese u svim vašim korisničkim profilima ili izaberite entitet segmenta za obogaćivanje adresa samo u korisničkim profilima sadržanim u tom segmentu.

1. Izaberite način oblikovanja adresa u skupu podataka. Odaberite **Adresa sa jednim atributom** ako adrese u vašim podacima koriste jedno polje. Odaberite **Adresa sa više atributa** ako adrese u vašim podacima koriste više od jednog polja podataka.

   > [!NOTE]
   > Zemlja/region je obavezan podatak za adrese i sa jednim i sa više atributa. Adrese koje ne sadrže važeće ili podržane vrednosti zemlje/regiona neće biti obogaćene.

1.  Mapirajte polja adrese iz vašeg objedinjenog entiteta klijenta.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Poboljšana stranica za mapiranje polja adrese.":::

1. Izaberite **Sledeće** da biste dovršili mapiranje polja.

1. Obezbedite naziv za obogaćivanje i izlazni entitet.

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake. Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab). Vreme obrade zavisi od veličine podataka vaših klijenata.

Nakon završetka procesa obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod opcijom **Moja obogaćivanja**. Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.

## <a name="next-steps"></a>Sledeći koraci

Nadogradite na obogaćenim podacima o klijentima. Kreirajte [segmente](segments.md) i [mere](measures.md), pa čak i [izvoz podataka](export-destinations.md) da pružite personalizovana iskustva svojim klijentima.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
