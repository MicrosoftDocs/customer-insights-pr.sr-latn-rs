---
title: Obogaćivanje profila preduzeća poboljšanim podacima kompanije
description: Obogatite i normalizujte podatke kompanije Microsoft modelima.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 131ef3d1e123628779609ddec368cfef8f4d607e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054265"
---
# <a name="enrich-company-profiles-with-enhanced-company-data"></a>Obogaćivanje profila preduzeća poboljšanim podacima kompanije

Koristite Microsoftove modele i prevedene podatke kompanije da biste ispravili, dopunili i standardizovali profile preduzeća. Koristićemo format Common [Data Model za](/common-data-model/schema/core/applicationcommon/account) bolju tačnost i uvide.

Takođe možete da [poboljšate podatke kompanije na izvorima podataka](data-sources-enrichment.md) da biste poboljšali tačnost podudaranja u procesu ujedinjenja podataka.

Za javne kompanije u Sjedinjenim Državama dostupne su informacije kao što su prihodi, tiker akcija, industrija i još mnogo toga.  

## <a name="how-we-enhance-company-data"></a>Kako poboljšavamo podatke kompanije

Naš model prolazi kroz proces u dva koraka da bi poboljšao profil kompanije. Prvo, normalizuje ime kompanije. Na primer, *Microsoft Corp će* biti ispravljen i standardizovan u korporaciji *Microsoft*. On pokušava da pronađe podudaranje u prevedenim podacima korporacije Microsoft. Ako se podudaranje nađe, obogaćujemo profil kompanije informacijama iz naših sačinjenih podataka kompanije, uključujući i ime kompanije.

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

Model ne radi sledeće:

- Potvrdite identitet preduzeća. Ne proveravamo da li je unos postojeća organizacija ili da li preduzeće koristi izlaz kao standardno ime.
- Sveobuhvatno pokriva kompanije na globalnom nivou. Podaci Majkrosoftove sačinjene kompanije imaju globalnu pokrivenost, ali nude većinu pokrivenosti u Australiji, Kanadi, Velikoj Britaniji i Sjedinjenim Državama.
- Standardizujte adrese preduzeća na globalnom nivou. Trenutno podržavamo standardizovanje adresa u tim zemljama ili regionima: Australiji, Kanadi, Francuskoj, Nemačkoj, Italiji, Japanu, Velikoj Britaniji i Sjedinjenim Državama.
- Garancija tačnosti ili svežine podataka. Kako se poslovne informacije često menjaju, ne možemo da garantujemo da su poboljšani podaci kompanije uvek tačni ili autirni.

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.

1. Izaberite **stavku Obogati moje podatke** na pločici sa **podacima poboljšanog** preduzeća.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Pločica za obogaćivanje u čvorištu za obogaćivanje podataka preduzeća.":::

1. Pregledajte pregled, a zatim kliknite na dugme **Dalje**.

1. Izaberite opciju **skup podataka i** odaberite profil ili segment koji želite da obogatite. Entitet *kupca* obogaćuje sve profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

1. Izaberite tip polja iz profila preduzeća koja ćete koristiti za podudaranje sa prevedenim podacima korporacije Microsoft. Ovaj izbor će uticati na polja za mapiranje kojima imate pristup u sledećem koraku.

1. Izaberite **Sledeće**.

1. Mapirajte polja preduzeća na podatke preduzeća korporacije Microsoft. Za veću tačnost podudaranja dodajte još polja.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Korak mapiranja podataka prilikom konfigurisanja obogaćivanja preduzeća.":::

1. Izaberite **Sledeće** da biste dovršili mapiranje polja.

1. Navedite **ime** za bogaćenje i izlazni **entitet**.

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

1. Kliknite **na dugme** "Pokreni" da biste započeli proces obogaćivanja ili blizu da biste se vratili na stranicu **"Obogaćivanje** ".

## <a name="view-enrichment-results"></a>Prikaži rezultate obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Kartica za pregled

Pločica **"Kupci menjaju pregled** " prikazuje detalje o pokrivenosti bogaćenja

- **Preduzeća su obrađivanja** i menjala: broj profila preduzeća kupaca koji su uspešno obogaćeni.
- **Preduzeća su obrađivanja i** nisu promenjena: broj profila preduzeća kupaca koji su prepoznati, ali nisu promenjeni. Ovo se obično dešava kada su ulazni podaci važeći i ne mogu se poboljšati bogaćenjem.
- **Preduzeća koja nisu obrađena i** nisu promenjena: broj profila preduzeća kupaca koji nisu prepoznati. Ovo se obično dešava za ulazne podatke koji su nevažeći ili ih obogaćivanje ne podržava.

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
