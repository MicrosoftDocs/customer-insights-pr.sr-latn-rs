---
title: Koristite izvore podataka radi unosa podataka
description: Naučite kako da uvezete podatke iz različitih izvora.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643970"
---
# <a name="overview-about-data-sources"></a>Pregled izvora podataka

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Sposobnost uvida o korisnicima u usluzi Dynamics 365 Customer Insights povezuje se sa podacima iz širokog skupa izvora. Povezivanje sa izvorom podataka se često naziva procesom *unošenja podataka*. Nakon unošenja podataka, možete ih [objediniti](data-unification.md) i preduzeti radnju nad njima.

## <a name="add-a-data-source"></a>Dodavanje izvora podataka

Pogledajte detaljne članke o tome kako da dodate izvor podataka, u zavisnosti od toga koju opciju ste izabrali.

Izvor podataka možete dodati na tri glavna načina:

- [Kroz desetine Power Query konektora](connect-power-query.md)
- [Iz Common Data Model fascikle](connect-common-data-model.md)
- [Iz vašeg sopstvenog Common Data Service jezera](connect-common-data-service-lake.md)

> [!NOTE]
> Još ne možete da dodate podatke iz lokalnih izvora podataka.

## <a name="review-ingested-data"></a>Pregled unetih podataka

Videćete naziv svakog unetog izvora podataka, njegov status i poslednji put kada su podaci osveženi za taj izvor. Spisak izvora podataka možete sortirati po svakoj koloni.

> [!div class="mx-imgBorder"]
> ![Izvor podataka je dodat](media/configure-data-datasource-added.png "Izvor podataka je dodat")

|Status  |Opis  |
|---------|---------|
|Uspešno   |Izvor podataka je uspešno unet ako je vreme navedeno u koloni **Osveženo**.
|Nije započeto   |Izvor podataka još nema unetih podataka ili je još uvek u režimu radne verzije.         |
|Osvežavanje    |Unos podataka je u toku. Ovu operaciju možete otkazati ako izaberete **Zaustavi osvežavanje** u koloni **Radnje**. Zaustavljanje osvežavanja izvora podataka vratiće ga u poslednje stanje osvežavanja.       |
|Neuspela     |Unos podataka je naišao na greške.         |

Izaberite **Osveži status** da biste pregledali više detalja o statusu osvežavanja, uključujući detalje o greškama i nadogradnje procesa.

Učitavanje podataka može da potraje. Nakon uspešnog osvežavanja, uneseni podaci mogu se pregledati sa stranice **Entiteti**. Za više informacija, pogledajte članak [Entiteti](entities.md).

## <a name="refresh-a-data-source"></a>Osvežite izvor podataka

Izvori podataka mogu se osvežavati po automatskom rasporedu ili ručno na zahtev. 

Idite na **Administrator** > **Sistem** > [**Raspored**](system.md#schedule-tab) da biste konfigurisali zakazana osvežavanja svih unetih izvora podataka.

Da biste osvežili izvor podataka na zahtev, sledite ove korake:

1. U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**

2. Izaberite vertikalnu elipsu pored izvora podataka koji želite da osvežite i izaberite **Osveži** sa padajuće liste.

3. Izvor podataka je sada aktiviran za ručno osvežavanje. Osvežavanjem izvora podataka ažuriraće se obe šeme entiteta kao i podaci za sve entitete navedene u izvoru podataka.

4. Izaberite **Prestanite sa osvežavanjem** ako želite da otkažete postojeće osvežavanje i izvor podataka će se vratiti na svoj poslednji status osvežavanja.

## <a name="delete-a-data-source"></a>Izbriši izvor podataka

1. U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.

2. Izaberite uspravne tri tačke pored izvora podataka koji želite da uklonite i izaberite **Izbriši** iz padajućeg menija.

3. Potvrdite brisanje.
