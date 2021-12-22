---
title: Entiteti i skupovi podataka
description: Pogledajte podatke na stranici Entiteti.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 00c5ee50fb9f0906622c91699852ffba0acb5c15
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900444"
---
# <a name="entities-in-audience-insights"></a>Entiteti u uvidima o korisnicima

Kada [konfigurišete izvore podataka](data-sources.md), idite na stranicu **Entiteti** da procenite kvalitet unetih podataka. Entiteti se smatraju skupovima podataka. Više mogućnosti usluge Dynamics 365 Customer Insights napravljeno je na osnovu ovih entiteta. Njihov pažljiv pregled može vam pomoći da potvrdite valjanost ishoda tih mogućnosti.

Stranica **·** "Entiteti" navodi entitete i uključuje sledeće kolone:

- **Ime** : Ime entiteta podataka. Ako vidite simbol upozorenja pored naziva entiteta, to znači da se podaci za taj entitet nisu uspešno učitali.
- **Izvor** : Vrsta izvor podataka koja je unela entitet.
- **Ažurirano** : vreme poslednjeg ažuriranja entiteta.
- **Status** : Detalji o poslednjem ažuriranju entiteta.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Istražite podatke određenog entiteta

1. U uvidima o korisnicima idite na **Podaci** > **Entiteti**.
1. Sa **stranice** Entiteti izaberite entitet da biste otvorili stranicu sa detaljima.  
1. Istražite različita polja i zapise koji su uključeni za taj entitet.

- Kartica **Atributi** je podrazumevano izabrana i prikazuje tabelu za pregled detalja za izabrani entitet, kao što su imena polja, tipovi podataka i tipovi. Kolona **Tip** prikazuje tipove povezane sa Common Data Model, koje sistem automatski prepoznaje ili ih korisnici [ručno mapiraju](map-entities.md). Ovi tipovi su semantički tipovi koji se mogu razlikovati od tipova podataka atributa. Na primer, polje *e-pošta* ispod ima tip podataka *Tekst*, ali njegov (semantički) Common Data Model tip može biti *E-pošta* ili *Adresa e-pošte*.

> [!div class="mx-imgBorder"]
> ![Tabela polja.](media/data-manager-entities-fields.PNG "Tabela polja")

> [!NOTE]
> Ova stranica prikazuje samo uzorak podataka vašeg entiteta. Da biste videli ceo skup podataka, idite na stranicu **Izvori podataka**, izaberite entitet, izaberite **Uredi**, a zatim pregledajte podatke ovog entiteta pomoću Power Query uređivača, kao što je objašnjeno u članku [Izvori podataka](data-sources.md).

Da biste saznali više o podacima koji se unose u entitet, kolona **Rezime** vam pruža neke važne karakteristike podataka, kao što su polja bez vrednosti, nedostajuće vrednosti, jedinstvene vrednosti, brojevi i distribucije, kako je već primenjivo na podatke. Izaberite ikonu grafikona da biste videli rezime podataka.

> [!div class="mx-imgBorder"]
> ![Simbol rezimea.](media/data-manager-entities-summary.png "Tabela sa rezimeom podataka")

- Kartica **Podaci** prikazuje detalje listinga tabela o pojedinačnim zapisima entiteta. Navedeni detalji zavise od tipa podataka entiteta.

> [!div class="mx-imgBorder"]
> ![Izaberite entitet.](media/data-manager-entities-data.png "Izbor entiteta")

- Kartica **·** "Izveštaji" (dostupna za neke entitete) omogućava vizuelizaciju podataka kreiranjem izveštaja i uključuje sledeće kolone:

  - **Ime** izveštaja : Ime izveštaja.
  - **Kreirao**: Ime osobe koja je kreirala entitet.
  - **Kreirano** : datum i vreme kreiranja entiteta.
  - **Edited by** : Ime osobe koja je izmenila entitet.
  - **Uređeno** : Datum i vreme izmene entiteta. 

## <a name="entity-specific-information"></a>Informacije određene za entitet

Sledeći odeljak pruža informacije o nekim entitetima koje je kreirao sistem.

### <a name="corrupted-data-sources"></a>Oštećeni izvori podataka

Polja iz unetog izvora podataka mogu sadržati oštećene podatke. Zapisi sa oštećenim poljima izloženi su u sistemski kreiranim entitetima. Poznavanje oštećenih zapisa pomaže vam da identifikujete koje podatke pregledati i ažurirati na izvornom sistemu. Nakon sledećeg osvežavanja izvora podataka, korigovani zapisi se unose u rešenje Customer Insights i prosleđuju posledičnim procesima. 

Na primer, kolona „rođendan“ ima tip podataka postavljen kao „datum“. U zapis klijenta ima datum rođenja unet kao „01/01/19777“. Sistem će označiti ovaj zapis kao oštećen. Neko sada može da promeni rođendan u izvornom sistemu na „1977“. Nakon automatskog osvežavanja izvora podataka, polje sada ima važeći format i zapis će biti uklonjen iz oštećenog entiteta. 

Idite na **Podaci** > **Entiteti** i potražite oštećene entitete u odeljku **Sistem**. Šema imenovanja oštećenih entiteta: 'NazivIzvoraPodataka_NazivEntiteta_corrupt'.

Customer Insights i dalje obrađuje oštećene zapise. Međutim, oni mogu dovesti do problema pri radu sa objedinjenim podacima.

Sledeće provere se vrše na unetim podacima kako bi se otkrili oštećeni zapisi: 

- Vrednost polja se ne podudara sa tipom podataka njegove kolone.
- Polja sadrže znakove zbog kojih se kolone ne podudaraju sa očekivanom šemom. Na primer: nepravilno oblikovani navodnici, neupareni navodnici ili znakovi novog reda.
- Ako postoje kolone datuma/datuma/datuma/datuma, njihov format mora biti naveden u modelu ako ne sledi standardni ISO format.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
