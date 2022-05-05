---
title: Kreiranje mera iz predložaka
description: Definišite mere korišćenja obrazaca za uobičajene slučajeve korišćenja.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: eeabd889f7b694f8d809894169a3cdc068acc340
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643137"
---
# <a name="use-a-template-to-build-a-measure"></a>Korišćenje predloška za izgradnju mere

Za njihovu kreiranje možete da koristite unapred definisane predloške [uobičajenih](measures.md) mera. Detaljni opisi predložaka i vođeno iskustvo pomažu vam u efikasnom kreiranju mera. Predlošci se nadovezuju na mapirane podatke iz entiteta *Objedinjena aktivnost*. Uverite se da ste konfigurisali [aktivnosti klijenata](activities.md) pre nego što kreirate meru iz predloška.

Da biste kreirali prilagođene mere, pogledajte [članak Korišćenje izrade mera za kreiranje mera od početka](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

Dostupni predlošci mera: 
- Prosečna vrednost transakcije (ATV)
- Ukupna vrednost transakcije
- Prosečan dnevni prihod
- Prosečan godišnji prihod
- Broj transakcija
- Osvojeni poeni lojalnosti
- Iskorišćeni poeni lojalnosti
- Bilans poena iz programa lojalnosti
- Vremenski opseg aktivnosti klijenta
- Trajanje članstva u programu lojalnosti
- Vreme od poslednje kupovine

## <a name="build-a-new-measure-using-a-template"></a>Izrada nove mere pomoću predloška

1. Idite **na mere**.

1. Izaberite **Nova** i birajte **Odaberi predložak**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Snimak ekrana padajućeg menija prilikom kreiranja nove mere sa isticanjem na predlošku.":::

1. Pronađite predložak koji odgovara vašim potrebama i izaberite **Odaberi predložak**.

1. Pregledajte potrebne podatke i izaberite **Započnite** ako su svi podaci na svom mestu.

1. Izaberite **uredi detalje** pored imena mere. Navedite ime za meru. Opcionalno, [dodajte](work-with-tags-columns.md#manage-tags) oznake u meru.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dijalog &quot;Uređivanje detalja&quot;.":::

1. Izaberite **Gotovo**.

1. U odeljku **Podešavanje vremenskog perioda** definišite vremenski okvir podataka koji će se koristiti. Odaberite da li želite da nova mera pokriva čitav skup podataka izborom **Sve vreme**, ili ako želite da se mera fokusira na **Određeni vremenski period**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Snimak ekrana koji prikazuje odeljak vremenskog perioda prilikom konfigurisanja mere iz predloška.":::

1. U sledećem odeljku, izaberite **Dodaj podatke** da biste izabrali aktivnosti i mapirali odgovarajuće podatke iz svog entiteta *Objedinjena aktivnost*.

    1. Korak 1 od 2: Ispod **Tipa aktivnosti** odaberite tip entiteta koji želite da koristite. Za **Aktivnosti**, izaberite entitete koje želite da mapirate.
    1. Korak 2 od 2: Izaberite atribut iz entiteta *Objedinjena aktivnost* za komponentu koja je obavezna za formulu. Na primer, za „Prosečna vrednost transakcije“, to je atribut koji predstavlja vrednost transakcije. Za **Vremensku oznaku aktivnosti**, odaberite atribut iz entiteta objedinjene aktivnosti koji predstavlja datum i vreme aktivnosti.
   
1. Kada mapiranje podataka bude uspešno, možete videti da status ima vrednost **Kompletno** i naziv mapiranih aktivnosti i atributa.

1. Sada možete odabrati **Pokreni** da biste izračunali rezultate mere. Da biste je kasnije precizirali, izaberite **Sačuvaj radnu verziju**.

# <a name="business-accounts-b-to-b"></a>[Poslovni nalozi (B-to-B)](#tab/b2b)

Ova funkcija je dostupna samo za mere kreirane u okruženjima čiji su pojedinačni klijenti primarna ciljna grupa.

---
