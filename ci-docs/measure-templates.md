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
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170790"
---
# <a name="create-measures-from-templates"></a>Kreiranje mera iz predložaka

Koristite unapred definisane predloške uobičajenih mera [za](measures.md) njihovu kreiranje. Predlošci se nadovezuju na mapirane podatke iz entiteta *Objedinjena aktivnost*. Uverite se da ste konfigurisali [aktivnosti klijenata](activities.md) pre nego što kreirate meru iz predloška.

Predlošci mera su podržani samo u okruženjima za pojedinačne **klijente**. Da biste kreirali prilagođene mere ili kreirali mere za B-na-B, pogledajte članak [Korišćenje izrade mera](measure-builder.md).

Dostupni predlošci mera:
- Prosečna vrednost transakcije (ATV)
- Ukupna vrednost transakcije
- Prosečan dnevni prihod
- Prosečan mesečni prihod
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

1. U odeljku **Podešavanje vremenskog perioda** vremenski okvir prikaz podataka. Odaberite da li želite da nova mera pokriva čitav skup podataka izborom **Sve vreme**, ili ako želite da se mera fokusira na **Određeni vremenski period**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Snimak ekrana koji prikazuje odeljak vremenskog perioda prilikom konfigurisanja mere iz predloška.":::

1. U sledećem odeljku, izaberite **Dodaj podatke** da biste izabrali aktivnosti i mapirali odgovarajuće podatke iz svog entiteta *Objedinjena aktivnost*.

    1. Korak 1 od 2: Ispod **Tipa aktivnosti** odaberite tip entiteta koji želite da koristite. Za aktivnosti **izaberite** entitete koje želite da mapirate, a zatim kliknite na dugme **Dalje**.
    1. Korak 2 od 2: Izaberite atribut iz entiteta *Objedinjena aktivnost* za komponentu koja je obavezna za formulu. Na primer, za „Prosečna vrednost transakcije“, to je atribut koji predstavlja vrednost transakcije. Za **vremensku štigu** aktivnosti odaberite atribut iz *entiteta* objedinjene aktivnosti koji predstavlja datum i vreme aktivnosti.
    1. Izaberite **Sačuvaj**.

    Kada mapiranje podataka bude uspešno, status prikazuje " **Dovršeno** ", a prikazano je ime mapiranih aktivnosti i atributa.

1. Kliknite **na** dugme "Pokreni" da biste izračunali rezultate mere. Izaberite **stavku Sačuvaj radnu** verziju ako želite da zadržite trenutnu konfiguraciju i pokrenite je kasnije. Prikazaće **se stranica** "Mere".

## <a name="next-step"></a>Sledeći korak

Koristite postojeće mere da biste kreirali [segment kupca](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
