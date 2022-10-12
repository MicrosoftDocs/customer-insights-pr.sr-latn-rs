---
title: Entiteti u usluzi Customer Insights
description: Pogledajte podatke na stranici Entiteti.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610115"
---
# <a name="entities-in-customer-insights"></a>Entiteti u usluzi Customer Insights

Kada [konfigurišete izvore podataka](data-sources.md), idite na stranicu **Entiteti** da procenite kvalitet unetih podataka. Entiteti se smatraju skupovima podataka. Više mogućnosti usluge Dynamics 365 Customer Insights napravljeno je na osnovu ovih entiteta. Njihov pažljiv pregled može vam pomoći da potvrdite valjanost ishoda tih mogućnosti.

Dok radite u uvidima klijenata obogaćivanje podataka ili kreiranje segmenata, mera i aktivnosti, entiteti koji su kreirani iz tih radnji prikazuju se na **stranici "Entiteti** ".

## <a name="view-a-list-of-entities"></a>Prikazivanje liste entiteta

Idite na **entitete** > **podataka** da biste prikazali listu entiteta. Sledeće informacije se prikazuju za svaki entitet.

- **Ime**: Ime entiteta podataka. Ako vidite simbol upozorenja pored naziva entiteta, to znači da se podaci za taj entitet nisu uspešno učitali.
- **Izvor**: Type of izvor podataka that ingested the entity.
- **Ažurirano**: vreme poslednjeg ažuriranja entiteta.
- **Status**: Detalji o poslednjoj ispravki entiteta.

## <a name="explore-a-specific-entitys-data"></a>Istražite podatke određenog entiteta

1. Idite na **entitete** > **podataka**.
1. Izaberite entitet da biste otvorili stranicu sa detaljima.  
1. Istražite različita polja i zapise koji su uključeni za taj entitet.

- Kartica **"Atributi** " je podrazumevano izabrana i prikazuje detalje za izabrani entitet, kao što su imena polja, tipovi podataka i tipovi. Kolona **Tip** prikazuje tipove povezane sa Common Data Model, koje sistem automatski prepoznaje ili ih korisnici [ručno mapiraju](map-entities.md). Ovi tipovi su semantički tipovi koji se mogu razlikovati od tipova podataka atributa. Na primer, polje E-pošta ispod ima nisku tipa podataka *, ali* njen (semantički) tip uobičajenog modela podataka može *biti e-pošta*, *e-pošta* *ili Identity.Service.Email*.*·*

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tabela polja.":::

   > [!NOTE]
   > Ova stranica prikazuje samo uzorak podataka vašeg entiteta. Da biste prikazali celu skup podataka, idite **na stranicu "Izvori** podataka", izaberite entitet, **izaberite stavku Uredi**, a zatim prikažite podatke ovog entiteta sa uređivačem Power Query [kao što je objašnjeno u izvorima podataka](data-sources.md).

   Da biste saznali više o podacima koji su uneti u entitet, **kolona "** Rezime" obezbeđuje neke važne karakteristike podataka, kao što su "null", vrednosti koje nedostaju, jedinstvene vrednosti, broji i raspodele, šta god da je primenljivo na vaše podatke. Izaberite ikonu grafikona da biste videli rezime podataka.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Tabela rezimea podataka.":::

- Kartica **"** Podaci" prikazuje detalje o pojedinačnim zapisima entiteta. Navedeni detalji zavise od tipa podataka entiteta.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Izaberite entitet.":::

- Kartica **"** Izveštaji" (dostupna za neke entitete) omogućava vizuelizaciju podataka kreiranjem izveštaja koji uključuje sledeće kolone:

  - **Ime izveštaja**: Ime izveštaja.
  - **Kreirao**: Ime osobe koja je kreirala entitet.
  - **Kreirano**: Datum i vreme kreiranja entiteta.
  - **Uredio**: Ime osobe koja je izmenila entitet.
  - **Edited**: Datum i vreme izmene entiteta.

[!INCLUDE [footer-include](includes/footer-banner.md)]
