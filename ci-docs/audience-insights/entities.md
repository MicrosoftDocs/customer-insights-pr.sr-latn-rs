---
title: Entiteti i skupovi podataka
description: Pogledajte podatke na stranici Entiteti.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406787"
---
# <a name="entities-in-audience-insights"></a>Entiteti u uvidima o korisnicima

Kada [konfigurišete izvore podataka](data-sources.md), idite na stranicu **Entiteti** da procenite kvalitet unetih podataka. Entiteti se smatraju skupovima podataka. Više mogućnosti usluge Dynamics 365 Customer Insights napravljeno je na osnovu ovih entiteta. Njihov pažljiv pregled može vam pomoći da potvrdite valjanost ishoda tih mogućnosti.

Stranica **Entiteti** navodi entitete i sadrži nekoliko kolona:

- **Naziv**: Naziv vašeg entiteta podataka. Ako vidite simbol upozorenja pored naziva entiteta, to znači da se podaci za taj entitet nisu uspešno učitali.
- **Izvor**: Vrsta izvora podataka koji su uneti u entitet
- **Autor**: Ime osobe koja je kreirala entitet
- **Kreirano**: Datum i vreme stvaranja entiteta
- **Autor izmene**: Ime osobe koja je ažurirala entitet
- **Vreme poslednje izmene**: Datum i vreme poslednjeg ažuriranja entiteta
- **Poslednje osvežavanje**: Datum i vreme poslednjeg osvežavanja podataka

## <a name="exploring-a-specific-entitys-data"></a>Istraživanje podataka određenog entiteta

Izaberite entitet da biste istražili različita polja i zapise koji su uključeni u taj entitet.

> [!div class="mx-imgBorder"]
> ![Izaberite entitet](media/data-manager-entities-data.png "Izaberite entitet")

- Kartica **Podaci** je podrazumevano izabrana i prikazuje tabelu u kojoj su navedeni detalji o pojedinačnim zapisima entiteta.

> [!div class="mx-imgBorder"]
> ![Tabela polja](media/data-manager-entities-fields.PNG "Tabela polja")

- Kartica **Polja** prikazuje tabelu za pregled detalja za odabrani entitet, kao što su imena polja, tipovi podataka i tipovi. Kolona **Tip** prikazuje tipove povezane sa Common Data Model, koje sistem automatski prepoznaje ili ih korisnici [ručno mapiraju](map-entities.md). Ovo su semantički tipovi koji se mogu razlikovati od tipova podataka atributa – na primer, polje *E-pošta* u nastavku je tipa podataka *Tekst*, ali njegov (semantički) Common Data Model tip može biti *E-pošta* ili *Adresa e-pošte*.

> [!NOTE]
> Obe tabele prikazuju samo uzorak podataka vašeg entiteta. Da biste videli ceo skup podataka, idite na stranicu **Izvori podataka**, izaberite entitet, izaberite **Uredi**, a zatim pregledajte podatke ovog entiteta pomoću Power Query uređivača, kao što je objašnjeno u članku [Izvori podataka](data-sources.md).

Da biste saznali više o podacima koji se unose u entitet, kolona **Rezime** vam pruža neke važne karakteristike podataka, kao što su polja bez vrednosti, nedostajuće vrednosti, jedinstvene vrednosti, brojevi i distribucije, kako je već primenjivo na podatke.

Izaberite ikonu grafikona da biste videli rezime podataka.

> [!div class="mx-imgBorder"]
> ![Simbol rezimea](media/data-manager-entities-summary.png "Tabela sa rezimeom podataka")

### <a name="next-step"></a>Sledeći korak

Pogledajte temu [Ujednačavanje](data-unification.md) da biste saznali kako da *mapirate*, *podudarate* i *spajate* unete podatke.
