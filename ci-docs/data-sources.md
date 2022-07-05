---
title: Pregled izvora podataka
description: Saznajte kako da uvezete ili unesite podatke iz različitih izvora.
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: fbe44f655bdbc20ef7f0956022395e2dcb570adf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051470"
---
# <a name="data-sources-overview"></a>Pregled izvora podataka

Dynamics 365 Customer Insights obezbeđuje veze za prenos podataka iz širokog skupa izvora. Povezivanje sa izvorom podataka se često naziva procesom *unošenja podataka*. Nakon što unesite podatke, možete da [ujedinite](data-unification.md), generišete uvide i aktivirate podatke za izgradnju personalizovanih iskustava.

## <a name="add-data-sources"></a>Dodavanje izvora podataka

Izvore podataka možete da priložite ili uvezete u uvide kupaca. Dole navedene veze pružaju uputstva za dodavanje izvora podataka.

**Prilaganje izvor podataka**

Ako imate pripremljene podatke u nekoj od Microsoft Azure usluga podataka, korisnički uvidi mogu lako da se povežu sa izvor podataka bez ponovnog unosa podataka. Izaberite neku od sledećih opcija:
- [Azure Data Lake Storage(csv ili datoteke parketa u fascikli "Uobičajeni model podataka")](connect-common-data-model.md)
- [Azure Synapse Analytics(Baze podataka jezera)](connect-synapse.md)
- [Microsoft Dataverse jezero sa podacima](connect-dataverse-managed-lake.md)

**Uvoz i transformacija**

Ako koristite lokalne izvore podataka, podatke korporacije Microsoft ili nezavisnih proizvođača, uvezite i transformišite podatke pomoću linija Power Query spajanja.
- [Power Query Konektori](connect-power-query.md)

## <a name="review-data-sources"></a>Redigovanje izvora podataka

Ako je vaše okruženje konfigurisano da koristi skladište "Uvidi kupaca", a vi koristite lokalne izvore podataka, koristite Power Platform priliv podataka. Pomoću Power Platform toka podataka možete da prikažete deljene izvore podataka i izvore podataka kojima upravljaju drugi. Stranica **"Izvori podataka** " navodi izvore podataka u tri odeljka:
- **Deljeno**: Izvori podataka kojima mogu upravljati svi administratori korisničkog uvida. Power Platform priliv podataka, sopstveni nalog za skladištenje i prilaganje Dataverse uz jezero sa podacima kojim upravljate su primeri deljenih izvora podataka.
- **Kojim upravljam** ja: Power Platform priliv podataka kojima ste kreirali i kojim upravljate samo vi. Drugi administratori korisničkih uvida mogu da pregledaju samo ove podatke, ali ne i da ih uređuju, osvežavaju ili brišu.
- **Njima upravljaju drugi**: Power Platform priliv podataka koji su kreirali drugi administratori. Možete samo da ih videli. On navodi vlasnika priliva podataka da bi se obratiti za svaku pomoć.
> [!NOTE]
> Sve entitete mogu da pregledaju i koriste drugi korisnici. Dok su izvori podataka u vlasništvu korisnika koji ih je kreirao, dobijene entitete iz unošenja podataka može da koristi svaki korisnik uvida klijenta.

Ako vaše okruženje ne koristi tok Power Platform podataka, stranica " **Izvori podataka** " sadrži samo listu svih izvora podataka. Ne prikazuju se sekcije.

Idite **na izvore** > **podataka** podataka da biste prikazali ime svakog izvor podataka, njegov status i poslednji put kada su podaci osveženi za taj izvor. Spisak izvora podataka možete sortirati po svakoj koloni.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Izvor podataka je dodat.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Učitavanje podataka može potrajati. Nakon uspešnog osvežavanja, uneseni podaci mogu se pregledati sa stranice **Entiteti**. Za više informacija, pogledajte članak [Entiteti](entities.md).

## <a name="refresh-data-sources"></a>Osvežavanje izvora podataka

Izvori podataka mogu se osvežavati po automatskom rasporedu ili ručno na zahtev. [Sopstveni izvori podataka osvežavaju](connect-power-query.md#add-data-from-on-premises-data-sources) po sopstvenim rasporedima koji su podešeni tokom unošenja podataka. Za priložene izvore podataka, unos podataka troši najnovije dostupne podatke iz tog izvor podataka.

Idite na **administrativni** > **·** > [**plan sistema**](system.md#schedule-tab) da biste konfigurisali sistemski planirano osvežavanje nanetih izvora podataka.

Da biste osvežili izvor podataka na zahtev, sledite ove korake:

1. Idite na **Podaci** > **Izvori podataka**.

1. Izaberite vertikalnu elipsu () pored&vellip; prozora izvor podataka želite da osvežite i sa **padajuće** liste izaberite stavku Osveži. Izvor podataka je sada aktiviran za ručno osvežavanje. Osvežavanjem izvora podataka ažuriraće se i šema entiteta i podaci za sve entitete navedene u izvoru podataka.

1. Izaberite **Prestanite sa osvežavanjem** ako želite da otkažete postojeće osvežavanje i izvor podataka će se vratiti na svoj poslednji status osvežavanja.

## <a name="delete-a-data-source"></a>Izbriši izvor podataka

Novi izvor podataka se može izbrisati samo ako se podaci ne koriste u bilo kojoj obradi kao što su ujedinjenje, uvidi, aktivacije ili izvoz.

1. Idite na **Podaci** > **Izvori podataka**.

2. Izaberite vertikalnu elipsu () pored prozora&vellip; izvor podataka želite da uklonite i u padajućem meniju **izaberite** stavku "Izbriši".

3. Potvrdite brisanje.


[!INCLUDE [footer-include](includes/footer-banner.md)]
