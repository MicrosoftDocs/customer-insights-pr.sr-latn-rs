---
title: Poboljšanje podataka preduzeća
description: Obogatite i normalizujte podatke kompanije Microsoft modelima.
ms.date: 11/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: d11700c87f31cedc40d32b201251d8a9e2e2c312
ms.sourcegitcommit: dfc4843cc78857f1e3ca49d7b938e3ba77969169
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/15/2021
ms.locfileid: "7818794"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Obogaćivanje profila preduzeća poboljšanim podacima kompanije

Koristite Microsoftove modele i prevedene podatke kompanije da biste ispravili, dopunili i standardizovali profile preduzeća. Koristićemo format [Common Data Model za bolju](/common-data-model/schema/core/applicationcommon/account) tačnost i uvide.

## <a name="how-we-enhance-company-data"></a>Kako poboljšavamo podatke kompanije

Naš model prolazi kroz proces u dva koraka da bi poboljšao profil kompanije. Prvo, normalizuje ime kompanije. Na primer, *Microsoft Corp će biti* ispravljen i standardizovan u *korporaciji Microsoft*. On pokušava da pronađe podudaranje u prevedenim podacima korporacije Microsoft. Ako se podudaranje nađe, obogaćujemo profil kompanije informacijama iz naših sačinjenih podataka kompanije, uključujući i ime kompanije.


### <a name="example"></a>Primer

Informacije o preduzeću možda neće slediti standardizovani format i sadržati pravopisne greške. Model pokušava da reši ove probleme i kreira dosledne informacije.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Ograničenja

Postoji nekoliko ograničenja sa poboljšanim podacima. Model ne podržava stavke sa dole navedenog spiska.

1.  Potvrdite identitet preduzeća. Ne proveravamo da li je unos postojeća organizacija ili da li preduzeće koristi izlaz kao standardno ime.
2.  Sveobuhvatno pokriva kompanije na globalnom nivou. Podaci Majkrosoftove sačinjene kompanije imaju globalnu pokrivenost, ali nude većinu pokrivenosti u Australiji, Kanadi, Velikoj Britaniji i Sjedinjenim Državama.
3.  Standardizujte adrese preduzeća na globalnom nivou. Trenutno podržavamo standardizovanje adresa u tim zemljama ili regionima: Australiji, Kanadi, Francuskoj, Nemačkoj, Italiji, Japanu, Velikoj Britaniji i Sjedinjenim Državama.
4.  Garancija tačnosti ili svežine podataka. Kako se poslovne informacije često menjaju, ne možemo da garantujemo da su poboljšani podaci kompanije uvek tačni ili autirni.

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite na **Podaci** > **Obogaćivanje**.

1. Izaberite **stavku Obogati moje** podatke na **pločici sa podacima** poboljšanog preduzeća.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Pločica za obogaćivanje u čvorištu za obogaćivanje podataka preduzeća.":::

1. Izaberite **Skup podataka klijenta** i odaberite entitet koji sadrži adrese koje želite da obogatite. Možete izabrati entitet *Klijent* da obogatite adrese u svim vašim korisničkim profilima ili izaberite entitet segmenta za obogaćivanje adresa samo u korisničkim profilima sadržanim u tom segmentu.

1. Izaberite koji tip polja iz profila preduzeća treba da se koristi za podudaranje sa podacima microsoftovog prevedenog preduzeća. Ovaj izbor će uticati na polja za mapiranje kojima imate pristup u sledećem koraku.

1.  Mapirajte polja preduzeća iz objedinjenog entiteta kupca. Što više ključnih identifikatora i polja mapirate, veća je verovatnoća veće stope podudaranja.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Korak mapiranja podataka prilikom konfigurisanja obogaćivanja preduzeća.":::

1. Izaberite **Sledeće** da biste dovršili mapiranje polja.

1. Obezbedite naziv za obogaćivanje i izlazni entitet.

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake. Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab). Vreme obrade zavisi od veličine podataka vaših klijenata.

Nakon završetka procesa obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod opcijom **Moja obogaćivanja**. Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
