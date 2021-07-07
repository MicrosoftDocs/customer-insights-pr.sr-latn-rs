---
title: Koristite izvore podataka radi unosa podataka
description: Naučite kako da uvezete podatke iz različitih izvora.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304713"
---
# <a name="data-sources-overview"></a>Pregled izvora podataka

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Sposobnost uvida o korisnicima u usluzi Dynamics 365 Customer Insights povezuje se sa podacima iz širokog skupa izvora. Povezivanje sa izvorom podataka se često naziva procesom *unošenja podataka*. Nakon unošenja podataka, možete ih [objediniti](data-unification.md) i preduzeti radnju nad njima.

## <a name="add-a-data-source"></a>Dodavanje izvora podataka

Pogledajte detaljne članke o tome kako da dodate izvor podataka, u zavisnosti od toga koju opciju ste izabrali.

Izvor podataka možete dodati na tri glavna načina:

- [Kroz desetine Power Query konektora](connect-power-query.md)
- [Iz Common Data Model fascikle](connect-common-data-model.md)
- [Iz vašeg sopstvenog Microsoft Dataverse jezera](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Dodavanje podataka iz lokalnih izvora podataka

Unošenje podataka iz lokalnih izvora podataka u uslugu Uvidi u korisnike podržano je na osnovu Microsoft Power Platform tokova podataka. Tokovi podataka se mogu omogućiti u usluzi Customer Insights [navođenjem URL adrese Microsoft Dataverse okruženja](manage-environments.md#create-an-environment-in-an-existing-organization) prilikom podešavanja okruženja.

Izvori podataka koji se kreiraju nakon povezivanja Dataverse okruženja sa uslugom Customer Insights će podrazumevano koristiti [Power Platform tokove podataka](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Tokovi podataka podržavaju lokalnu povezanost pomoću mrežnog prolaza za podatke. Uklonite i ponovo kreirajte izvore podataka koji su postojali pre nego što je Dataverse okruženje bilo povezano za [upotrebu lokalnih mrežnih prolaza za podatke](/data-integration/gateway/service-gateway-app.md).

Mrežni prolazi za podatke iz postojećeg Power BI ili Power Apps okruženja će biti vidljivi i možete ponovo da ih koristite u usluzi Customer Insights. Stranica sa izvorima podataka prikazuje veze do Microsoft Power Platform okruženja u kojem možete da pregledate i lokalne mrežne prolaze za podatke.

## <a name="review-ingested-data"></a>Pregled unetih podataka

Videćete naziv svakog unetog izvora podataka, njegov status i poslednji put kada su podaci osveženi za taj izvor. Spisak izvora podataka možete sortirati po svakoj koloni.

> [!div class="mx-imgBorder"]
> ![Izvor podataka je dodat](media/configure-data-datasource-added.png "Izvor podataka je dodat")

|Status  |Opis  |
|---------|---------|
|Uspešno   |Izvor podataka je uspešno unet ako je vreme navedeno u koloni **Osveženo**.
|Nije započeto   |Izvor podataka još nema unetih podataka ili je još uvek u režimu radne verzije.         |
|Osvežavanje    |Unos podataka je u toku. Ovu operaciju možete otkazati ako izaberete **Zaustavi osvežavanje** u koloni **Radnje**. Zaustavljanje osvežavanja izvora podataka vratiće ga u poslednje stanje osvežavanja.       |
|Neuspeh     |Unos podataka je naišao na greške.         |

Izaberite vrednost u koloni **Status** bilo kog izvora podataka da biste pregledali više detalja. U oknu **Detalji napretka**, proširite stavku **Izvori podataka**. Izaberite **Pogledaj detalje** da biste dobili više informacija o statusu osvežavanja, uključujući detalje o greškama i nadogradnje procesa.

Učitavanje podataka može potrajati. Nakon uspešnog osvežavanja, uneseni podaci mogu se pregledati sa stranice **Entiteti**. Za više informacija, pogledajte članak [Entiteti](entities.md).

## <a name="refresh-a-data-source"></a>Osvežite izvor podataka

Izvori podataka mogu se osvežavati po automatskom rasporedu ili ručno na zahtev. 

Idite na **Administrator** > **Sistem** > [**Raspored**](system.md#schedule-tab) da biste konfigurisali zakazana osvežavanja svih unetih izvora podataka.

Da biste osvežili izvor podataka na zahtev, sledite ove korake:

1. U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.

2. Izaberite vertikalne tri tačke pored izvora podataka koje želite da osvežite i izaberite **Osveži** iz padajuće liste.

3. Izvor podataka je sada aktiviran za ručno osvežavanje. Osvežavanjem izvora podataka ažuriraće se i šema entiteta i podaci za sve entitete navedene u izvoru podataka.

4. Izaberite **Prestanite sa osvežavanjem** ako želite da otkažete postojeće osvežavanje i izvor podataka će se vratiti na svoj poslednji status osvežavanja.

## <a name="delete-a-data-source"></a>Izbriši izvor podataka

1. U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.

2. Izaberite vertikalne tri tačke pored izvora podataka koje želite da uklonite i izaberite **Izbriši** iz padajućeg menija.

3. Potvrdite brisanje.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
