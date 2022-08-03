---
title: Povezivanje sa izvor podataka Power Query (sadrži video)
description: Unesti podaci preko linije Power Query spajanja (sadrži video zapis).
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 7af51ed04fbd28149ea501c58e6fe71b5fa6d4b6
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207062"
---
# <a name="connect-to-a-power-query-data-source"></a>Povezivanje sa Power Query izvor podataka

Power Query nudi širok skup konektora za unos podataka. Većinu ovih konektora podržava Dynamics 365 Customer Insights.

Dodavanje izvora podataka zasnovanih na Power Query linijama spajanja obično sledi korake navedene u ovom odeljku. Međutim, u zavisnosti od konektora koji koristite, potrebne su različite informacije. Da biste saznali više, pogledajte dokumentaciju o pojedinačnim linijama spajanja u [Power Query referenci linije spajanja](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Kreiranje novog izvora podataka

1. Idite na **Podaci** > **Izvori podataka**.

1. Izaberite **Dodaj izvor podataka**.

1. Izaberite **Microsoft Power Query**.

1. Navedite ime **i** opcionalni opis **za** izvor podataka kliknite na dugme **Dalje**.

1. Odaberite jedan od [dostupnih konektora](#available-power-query-data-sources). U ovom primeru biramo text **/CSV konektor**.

1. Unesite potrebne detalje u **Podešavanja veze** za izabrani konektor i izaberite **Sledeće** da biste videli pregled podataka.

1. Izaberite **Transformacija podataka**.

1. Dijalog **Power Query " - Uređivanje upita vam** omogućava da pregledate i suzite suzite broj podataka. Entiteti koje su sistemi identifikovali u vašem izabranom izvoru podataka prikazuju se u levom oknu.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Dijalog za uređivanje upita":::

1. Takođe možete da transformišete svoje podatke. Izaberite entitet za uređivanje ili transformisanje. Koristite opcije u prozoru Power Query da biste primenili transformacije. Svaka transformacija je navedena u okviru Primenjenih **koraka**. Power Query pruža brojne [unapred izgrađene opcije](/power-query/power-query-what-is-power-query#transformations) transformacije.

   Preporučujemo da koristite sledeće transformacije:

   - Ako unosite podatke iz CSV datoteke, prvi red često sadrži zaglavlja. Idite na dugme **"Transformiši** **" i izaberite stavku Koristi prvi red kao zaglavlja**.
   - Uverite se da je tip podataka podešen na odgovarajući način. Na primer, za polja tipa datuma izaberite tip datuma.

1. Da biste dodali dodatne entitete u izvor podataka dijalogu "**Uređivanje upita**", idite na stavku "Početak" i **izaberite** stavku "Uzmi **podatke"**. Ponavljajte korake od 5 do 10 dok ne dodate sve entitete za ovu izvor podataka. Ako imate bazu podataka koja uključuje više skupova podataka, svaki skup podataka je svoj sopstveni entitet.

1. Izaberite **Sačuvaj**. Otvoriće **se stranica "Izvori podataka" koja prikazuje novu izvor podataka statusu "Osvežavanje** **·**".

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Učitavanje podataka može potrajati. Nakon uspešnog osvežavanja, uneti podaci se mogu redigovanje sa stranice [**"Entiteti**](entities.md) ".

> [!CAUTION]
> Nova izvor podataka zasnovana na Power Query kreiranju priliva [podataka u Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Nemojte menjati ime priliva podataka u administrativnom centru koji Power Platform se koristi u uvidima klijenata. Preisagavanje priliva podataka dovodi do problema sa referencama između izvor podataka i priliva Dataverse podataka.

### <a name="available-power-query-data-sources"></a>Dostupni Power Query izvori podataka

Pogledajte referencu [Power Query linije spajanja](/power-query/connectors/) za listu linija spajanja koju možete da koristite za uvoz podataka u "Uvid kupca".

Linije spajanja sa potvrdnim znakom u koloni **"Uvidi kupaca (dataflows)"** dostupne su za kreiranje novih izvora podataka na osnovu Power Query. Pregledajte dokumentaciju određenog konektora da biste saznali više o njegovim preduslovima, [ograničenjima upita](/power-query/power-query-online-limits) i drugim detaljima.

## <a name="add-data-from-on-premises-data-sources"></a>Dodavanje podataka iz lokalnih izvora podataka

Unosni podaci iz lokalni podataka su podržani na osnovu Microsoft Power Platform priliva podataka (PPDF). Priliv podataka možete da omogućite u uvidima klijenata tako što ćete [prilikom podešavanja Microsoft Dataverse okruženja obezbediti URL](create-environment.md) adresu okruženja.

Izvori podataka koji su kreirani nakon povezivanje okruženja sa Dataverse uvidom klijenata podrazumevano [Power Platform koriste priliv podataka](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Tokovi podataka podržavaju lokalnu povezanost pomoću mrežnog prolaza za podatke. Možete da uklonite i ponovo kreirate izvore podataka koji su postojali pre Dataverse nego što je okruženje [bilo povezano lokalni mrežnim prolazima podataka](/data-integration/gateway/service-gateway-app).

Mrežni prolazi podataka iz postojećeg okruženja Power BI Power Apps će biti vidljivi i možete ih ponovo koristiti u uvidima klijenata. Stranica sa izvorima podataka prikazuje veze do Microsoft Power Platform okruženja u kojem možete da pregledate i lokalne mrežne prolaze za podatke.

> [!IMPORTANT]
> Uverite se da su mrežni prolazi ažurirani u najnoviju verziju. Možete direktno da instalirate ispravku i ponovo konfigurišete mrežni prolaz sa upita prikazanog na ekranu mrežnog prolaza ili da preuzmete [najnoviju verziju](https://powerapps.microsoft.com/downloads/). Ako ne koristite najnoviju verziju mrežnog prolaza, osvežavanje priliva podataka neće uspeti **sa porukama o greškama kao što je Ključna reč nije podržano: svojstva konfiguracije. Naziv parametra: ključna reč**.
>
> Greške sa lokalni mrežnim prolazima podataka u programu "Uvidi kupaca" često su uzrokovane problemima sa konfiguracijom. Više informacija o rešavanju problema sa mrežnim prolazima podataka potražite u članku [Rešavanje problema lokalni mrežnog prolaza podataka](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Uređivanje Power Query izvora podataka

> [!NOTE]
> Možda neće biti moguće izvršiti promene u izvorima podataka koji se trenutno koriste u jednom od procesa aplikacije (na primer, segmentacija ili ujedinjenje podataka).
>
> Na stranici **"** Postavke" možete da pratite tok svakog aktivnog procesa. Kada se proces dovrši, možete se vratiti na stranicu **Izvori podataka** i uneti izmene.

1. Idite na **Podaci** > **Izvori podataka**.

1. Pored izvor podataka želite da ažurirate, izaberite stavku **Uredi**.

1. Primenite promene i transformacije u dijalogu **Power Query - Uređivanje upita** kao što je opisano u [odeljku Kreiranje izvor podataka stranice](#create-a-new-data-source).

1. Kliknite **na dugme** "Sačuvaj" da biste primenili promene i vratili se na **stranicu "Izvori podataka** ".

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
