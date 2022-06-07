---
title: Unesti podaci preko linije Power Query spajanja (sadrži video)
description: Linije spajanja za izvore podataka zasnovane na Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4db97ec02eb96662d30a8536ea42372f81f318d2
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800200"
---
# <a name="connect-to-a-power-query-data-source"></a>Povezivanje sa Power Query izvor podataka

Power Query nudi širok skup konektora za unos podataka. Većinu ovih konektora podržava Dynamics 365 Customer Insights. 

Dodavanje izvora podataka zasnovanih na Power Query linijama spajanja obično sledi korake navedene u ovom odeljku. Međutim, u zavisnosti od konektora koji koristite, potrebne su različite informacije. Da biste saznali više, pogledajte dokumentaciju o pojedinačnim linijama spajanja u [Power Query referenci linije spajanja](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Kreiranje novog izvora podataka

1. Idite na **Podaci** > **Izvori podataka**.

1. Izaberite **Dodaj izvor podataka**.

1. Izaberite **Microsoft Power Query**.

1. Navedite **Naziv** za izvor podataka, pa izaberite **Sledeće** kako biste kreirali izvor podataka.

1. Odaberite jedan od [dostupnih konektora](#available-power-query-data-sources). U ovom primeru biramo text **/CSV konektor**.

1. Unesite potrebne detalje u **Podešavanja veze** za izabrani konektor i izaberite **Sledeće** da biste videli pregled podataka.

1. Izaberite **Transformacija podataka**. U ovom koraku ćete dodati entitete svom izvoru podataka. Entiteti su skupovi podataka. Ako imate bazu podataka koja uključuje više skupova podataka, svaki skup podataka je svoj sopstveni entitet.

1. Dijalog **Power Query " - Uređivanje upita vam** omogućava da pregledate i suzite suzite broj podataka. Entiteti koje su sistemi identifikovali u vašem izabranom izvoru podataka prikazuju se u levom oknu.

   > [!div class="mx-imgBorder"]
   > ![Dijalog za uređivanje upita.](media/data-manager-configure-edit-queries.png "Dijalog za uređivanje upita")

1. Takođe možete da transformišete svoje podatke. Izaberite entitet za uređivanje ili transformisanje. Koristite opcije u prozoru Power Query da biste primenili transformacije. Svaka transformacija se navodi u okviru **Primenjenih koraka**. Power Query pruža brojne unapred izgrađene opcije transformacije. Više informacija potražite u članku [Power Query Transformacije](/power-query/power-query-what-is-power-query#transformations).

   Preporučujemo da koristite sledeće transformacije:

   - Ako unosite podatke iz CSV datoteke, prvi red često sadrži zaglavlja. Idite na dugme **"Transformiši** **" i izaberite stavku Koristi prvi red kao zaglavlja**.
   - Uverite se da je tip podataka podešen na odgovarajući način. Na primer, za polja tipa datuma izaberite tip datuma.

1. Da biste dodali dodatne entitete u izvor podataka dijalogu "**Uređivanje upita**", idite na stavku "Početak" i **izaberite** stavku "Uzmi **podatke"**.

1. Kliknite **na** dugme Sačuvaj na dnu prozora Power Query da biste sačuvali transformacije. Nakon čuvanja, pronaći ćete svoj izvor podataka u okviru **Podaci** > **Izvori podataka**.

1. Na stranici **Izvori podataka**, primetićete da je novi izvor podataka u statusu **Osvežavanje**.

## <a name="available-power-query-data-sources"></a>Dostupni Power Query izvori podataka

Pogledajte referencu [Power Query linije spajanja](/power-query/connectors/) za listu linija spajanja koju možete da koristite za uvoz podataka u "Uvid kupca". 

Linije spajanja sa potvrdnim znakom u koloni **"Uvidi kupaca (dataflows)"** dostupne su za kreiranje novih izvora podataka na osnovu Power Query. Pregledajte dokumentaciju određenog konektora da biste saznali više o njegovim preduslovima, ograničenjima i ostalim detaljima.

## <a name="edit-power-query-data-sources"></a>Uređivanje Power Query izvora podataka

> [!NOTE]
> Možda neće biti moguće izvršiti promene izvora podataka koji se trenutno koriste u jednom od procesa aplikacije (npr. *segmentacija*, *podudaranje* ili *spajanje*). 
>
> Na stranici **"** Postavke" možete da pratite tok svakog aktivnog procesa. Kada se proces dovrši, možete se vratiti na stranicu **Izvori podataka** i uneti izmene.

1. Idite na **Podaci** > **Izvori podataka**.

2. Izaberite vertikalnu elipsu () pored prozora&vellip; izvor podataka želite da promenite i u padajućem meniju **izaberite** stavku "Uredi".

   > [!div class="mx-imgBorder"]
   > ![Uređivanje opcije.](media/edit-option-data-sources.png "Uređivanje opcije")

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]
   
3. Primenite promene i transformacije u dijalogu **Power Query - Uređivanje upita** kao što je opisano u [odeljku Kreiranje izvor podataka stranice](#create-a-new-data-source).

4. Kliknite **na dugme** Sačuvaj Power Query nakon dovršavanja uređivanja da biste sačuvali promene.


[!INCLUDE [footer-include](includes/footer-banner.md)]
