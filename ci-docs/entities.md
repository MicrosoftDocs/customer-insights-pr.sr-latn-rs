---
title: Entiteti u usluzi Customer Insights
description: Pogledajte podatke na stranici Entiteti.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 4abb7704710ac269a4f3c9463fe905fa6eec3234
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082729"
---
# <a name="entities-in-customer-insights"></a>Entiteti u usluzi Customer Insights

Kada [konfigurišete izvore podataka](data-sources.md), idite na stranicu **Entiteti** da procenite kvalitet unetih podataka. Entiteti se smatraju skupovima podataka. Više mogućnosti usluge Dynamics 365 Customer Insights napravljeno je na osnovu ovih entiteta. Njihov pažljiv pregled može vam pomoći da potvrdite valjanost ishoda tih mogućnosti.

Stranica **"Entiteti** " navodi entitete i uključuje sledeće kolone:

- **Ime**: Ime entiteta podataka. Ako vidite simbol upozorenja pored naziva entiteta, to znači da se podaci za taj entitet nisu uspešno učitali.
- **Izvor**: Type of izvor podataka that ingested the entity.
- **Ažurirano**: vreme poslednjeg ažuriranja entiteta.
- **Status**: Detalji o poslednjoj ispravki entiteta.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Istražite podatke određenog entiteta

1. Idite na **entitete** > **podataka**.
1. Sa stranice **Entiteti** izaberite entitet da biste otvorili stranicu sa detaljima.  
1. Istražite različita polja i zapise koji su uključeni za taj entitet.

- Kartica **Atributi** je podrazumevano izabrana i prikazuje tabelu za pregled detalja za izabrani entitet, kao što su imena polja, tipovi podataka i tipovi. Kolona **Tip** prikazuje tipove povezane sa Common Data Model, koje sistem automatski prepoznaje ili ih korisnici [ručno mapiraju](map-entities.md). Ovi tipovi su semantički tipovi koji se mogu razlikovati od tipova podataka atributa. Na primer, polje *e-pošta* ispod ima tip podataka *Tekst*, ali njegov (semantički) Common Data Model tip može biti *E-pošta* ili *Adresa e-pošte*.

> [!div class="mx-imgBorder"]
> ![Tabela polja.](media/data-manager-entities-fields.PNG "Tabela polja")

> [!NOTE]
> Ova stranica prikazuje samo uzorak podataka vašeg entiteta. Da biste prikazali celu skup podataka, idite **na stranicu "Izvori** podataka", izaberite entitet, **izaberite stavku Uredi**, a zatim prikažite podatke ovog entiteta sa uređivačem Power Query [kao što je objašnjeno u izvorima podataka](data-sources.md).

Da biste saznali više o podacima koji se unose u entitet, kolona **Rezime** vam pruža neke važne karakteristike podataka, kao što su polja bez vrednosti, nedostajuće vrednosti, jedinstvene vrednosti, brojevi i distribucije, kako je već primenjivo na podatke. Izaberite ikonu grafikona da biste videli rezime podataka.

> [!div class="mx-imgBorder"]
> ![Simbol rezimea.](media/data-manager-entities-summary.png "Tabela sa rezimeom podataka")

- Kartica **Podaci** prikazuje detalje listinga tabela o pojedinačnim zapisima entiteta. Navedeni detalji zavise od tipa podataka entiteta.

> [!div class="mx-imgBorder"]
> ![Izaberite entitet.](media/data-manager-entities-data.png "Izbor entiteta")

- Kartica **"** Izveštaji" (dostupna za neke entitete) omogućava vizuelizaciju podataka kreiranjem izveštaja i uključuje sledeće kolone:

  - **Ime izveštaja**: Ime izveštaja.
  - **Kreirao**: Ime osobe koja je kreirala entitet.
  - **Kreirano**: Datum i vreme kreiranja entiteta.
  - **Uredio**: Ime osobe koja je izmenila entitet.
  - **Edited**: Datum i vreme izmene entiteta. 

## <a name="entity-specific-information"></a>Informacije određene za entitet

Sledeći odeljak pruža informacije o nekim entitetima koje je kreirao sistem.

### <a name="corrupted-data-sources"></a>Oštećeni izvori podataka

Polja iz unetog izvora podataka mogu sadržati oštećene podatke. Zapisi sa oštećenim poljima izloženi su u sistemski kreiranim entitetima. Poznavanje oštećenih zapisa pomaže vam da identifikujete koje podatke pregledati i ažurirati na izvornom sistemu. Nakon sledećeg osvežavanja izvora podataka, korigovani zapisi se unose u rešenje Customer Insights i prosleđuju posledičnim procesima. 

Na primer, kolona „rođendan“ ima tip podataka postavljen kao „datum“. U zapis klijenta ima datum rođenja unet kao „01/01/19777“. Sistem će označiti ovaj zapis kao oštećen. Neko sada može da promeni rođendan u izvornom sistemu na „1977“. Nakon automatskog osvežavanja izvora podataka, polje sada ima važeći format i zapis će biti uklonjen iz oštećenog entiteta. 

Idite na **Podaci** > **Entiteti** i potražite oštećene entitete u odeljku **Sistem**. Šema imenovanja oštećenih entiteta: 'NazivIzvoraPodataka_NazivEntiteta_corrupt'. Izaberite oštećeni entitet da biste identifikovali sva oštećena polja i razlog na pojedinačnom nivou zapisa.
> [!div class="mx-imgBorder"]
> ![Razlog korupcije.](media/corruption-reason.png "Razlog korupcije")

Customer Insights i dalje obrađuje oštećene zapise. Međutim, oni mogu dovesti do problema pri radu sa objedinjenim podacima.

Sledeće provere se vrše na unetim podacima kako bi se otkrili oštećeni zapisi: 

- Vrednost polja se ne podudara sa tipom podataka njegove kolone.
- Polja sadrže znakove zbog kojih se kolone ne podudaraju sa očekivanom šemom. Na primer: nepravilno oblikovani navodnici, neupareni navodnici ili znakovi novog reda.
- Ako postoje kolone datuma/datuma/datuma/datuma, njihov format mora biti naveden u modelu ako ne sledi standardni ISO format.


[!INCLUDE [footer-include](includes/footer-banner.md)]
