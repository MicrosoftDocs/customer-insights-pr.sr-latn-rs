---
title: Entiteti i skupovi podataka
description: Pogledajte podatke na stranici Entiteti.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: ac8b0671b20123091bef64e672fc53398fe8955a
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/13/2021
ms.locfileid: "6553992"
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

## <a name="explore-a-specific-entitys-data"></a>Istražite podatke određenog entiteta

Izaberite entitet da biste istražili različita polja i zapise koji su uključeni u taj entitet.

> [!div class="mx-imgBorder"]
> ![Izaberite entitet.](media/data-manager-entities-data.png "Izbor entiteta")

- Kartica **Podaci** prikazuje detalje listinga tabela o pojedinačnim zapisima entiteta.

> [!div class="mx-imgBorder"]
> ![Tabela polja.](media/data-manager-entities-fields.PNG "Tabela polja")

- Kartica **Atributi** je podrazumevano izabrana i prikazuje tabelu za pregled detalja za izabrani entitet, kao što su imena polja, tipovi podataka i tipovi. Kolona **Tip** prikazuje tipove povezane sa Common Data Model, koje sistem automatski prepoznaje ili ih korisnici [ručno mapiraju](map-entities.md). Ovi tipovi su semantički tipovi koji se mogu razlikovati od tipova podataka atributa. Na primer, polje *e-pošta* ispod ima tip podataka *Tekst*, ali njegov (semantički) Common Data Model tip može biti *E-pošta* ili *Adresa e-pošte*.

> [!NOTE]
> Obe tabele prikazuju samo uzorak podataka vašeg entiteta. Da biste videli ceo skup podataka, idite na stranicu **Izvori podataka**, izaberite entitet, izaberite **Uredi**, a zatim pregledajte podatke ovog entiteta pomoću Power Query uređivača, kao što je objašnjeno u članku [Izvori podataka](data-sources.md).

Da biste saznali više o podacima koji se unose u entitet, kolona **Rezime** vam pruža neke važne karakteristike podataka, kao što su polja bez vrednosti, nedostajuće vrednosti, jedinstvene vrednosti, brojevi i distribucije, kako je već primenjivo na podatke.

Izaberite ikonu grafikona da biste videli rezime podataka.

> [!div class="mx-imgBorder"]
> ![Simbol rezimea.](media/data-manager-entities-summary.png "Tabela sa rezimeom podataka")

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
- Ako postoje kolone datum i vreme/datum/pomak datuma i vremena, njihov format mora biti naveden u modelu ako ne sledi standardni ISO format.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
