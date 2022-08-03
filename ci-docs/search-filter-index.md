---
title: Upravljanje indeksom pretrage & filtera za profile kupaca
description: Brzo pronađite informacije o objedinjenim profilima klijenata i filtrirajte prema određenim atributima.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187926"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Upravljanje indeksom pretrage & filtera za profile kupaca

Rezultat ujedinjenja podataka o klijentima je entitet kupca *koji* obezbeđuje objedinjeni prikaz u ukupnoj bazi kupaca. Da bi korisnici brzo pronašli [informacije o određenom klijentu ili grupi klijenata](customer-profiles.md), administrator mora da konfiguriše **mogućnosti pretraživanja** **i filtriranja** za stranicu "**Kupci**".

   :::image type="content" source="media/search-filter.png" alt-text="Filter pretrage":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Definisanje atributa koji se mogu pretraživati i indeksiranih polja

Ako prvi put definišete atribute koji se mogu pretraživati kao administrator, prvo definišite indeksirana polja. Predlažemo vam da odaberete sve atribute po kojima korisnici mogu da pretražuju i filtriraju klijente na stranici **Klijenti**. Mogu se navesti samo atributi koji postoje *u* entitetu kupca kreiranom tokom procesa ujedinjenja podataka.

1. Idite na **opciju** "Kupci" i izaberite **stavku "Pretraži & filtriraj indeks"**.

1. Izaberite **+ Dodaj**.

1. Izaberite atribute sa liste koje želite da dodate kao indeksirana polja i kliknite na dugme **Primeni**.

1. Kliknite na dugme "Dodaj" da biste dodali još **atributa**. Da biste uklonili izabrani atribut, izaberite atribut, a zatim ga **izbrišite**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Stranica indeksa Search & filter.":::

1. Izaberite **opciju** Pokreni kada budete spremni da primenite postavke pretrage i filtera. Nakon obrade promena, prikažite ih na karticama kupaca [na stranici "Kupac"](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Definisanje opcija filtriranja za dati atribut

Podešavanje polja koja se mogu koristiti za filtriranje kupaca na stranici " **Kupci** ".

1. Idite na **opciju** "Kupci" i izaberite **stavku "Pretraži & filtriraj indeks"**.

1. Izaberite atribut i dodajte **filter**. Definišite broj rezultata i redosled kojim će biti organizovani. U zavisnosti od tipa podataka atributa, pojavljuje se jedno od sledećih okna.

   - Atributi tipa niske: Navedite broj željenih rezultata u oknu **filtera niske** i smernice porudžbine po kojima će biti organizovani.

   - Atributi numeričkog tipa: Navedite intervale uključene u **okno filtera "Broj** " i smernice porudžbine po kojima će biti organizovani.

   - Atributi tipa datuma: Navedite intervale uključene u **okno filtera "Datum** " i smernice porudžbine po kojima će biti organizovani.

1. Izaberite **U redu**. Ponovite ovo za sve atribute po kojima želite da filtrirate.

1. Izaberite **opciju** Pokreni kada budete spremni da primenite postavke pretrage i filtera. Nakon obrade promena, prikažite ih na karticama kupaca [na stranici "Kupac"](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Prikaz indeksiranih polja kupaca

Stranica **indeksa Search** & filter prikazuje sledeće informacije:

- **Ime**: Predstavlja ime atributa onako kako se pojavljuje u entitetu *kupca*.
- **Tip podataka**: Određuje da li je tip podataka niska, broj ili datum.
- **Uključeno u pretragu**: Određuje da li se ovaj atribut može koristiti za pretraživanje klijenata na stranici **Klijenti** pomoću polja **Pretraga**.
- **Dodaj filter**: Kontrola za definisanje kako se ovaj atribut može koristiti za filtriranje na stranici **Klijenti**.

## <a name="next-steps"></a>Sledeći koraci

Pregledajte [stranicu objedinjenih profila](customer-profiles.md) da potražite profile ili koristite indeksirana polja da vidite podskup svih objedinjenih profila.

[!INCLUDE [footer-include](includes/footer-banner.md)]
