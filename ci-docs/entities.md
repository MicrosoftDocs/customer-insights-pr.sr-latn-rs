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
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183602"
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

## <a name="entity-specific-information"></a>Informacije određene za entitet

Sledeći odeljak pruža informacije o nekim entitetima koje je kreirao sistem.

### <a name="corrupted-data-sources"></a>Oštećeni izvori podataka

Polja iz unetog izvora podataka mogu sadržati oštećene podatke. Zapisi sa oštećenim poljima izloženi su u sistemski kreiranim entitetima. Poznavanje oštećenih zapisa pomaže vam da identifikujete koje podatke pregledati i ažurirati na izvornom sistemu. Nakon sledećeg osvežavanja izvora podataka, korigovani zapisi se unose u rešenje Customer Insights i prosleđuju posledičnim procesima. 

Na primer, kolona „rođendan“ ima tip podataka postavljen kao „datum“. U zapis klijenta ima datum rođenja unet kao „01/01/19777“. Sistem će označiti ovaj zapis kao oštećen. Neko sada može da promeni rođendan u izvornom sistemu na „1977“. Nakon automatskog osvežavanja izvora podataka, polje sada ima važeći format i zapis će biti uklonjen iz oštećenog entiteta.

Idite na **Podaci** > **Entiteti** i potražite oštećene entitete u odeljku **Sistem**. Šema imenovanja oštećenih entiteta: 'NazivIzvoraPodataka_NazivEntiteta_corrupt'. Izaberite oštećeni entitet da biste identifikovali oštećena polja i razlog na pojedinačnom nivou zapisa.

   :::image type="content" source="media/corruption-reason.png" alt-text="Razlog korupcije.":::

Customer Insights i dalje obrađuje oštećene zapise. Međutim, oni mogu dovesti do problema pri radu sa objedinjenim podacima.

Sledeće provere se vrše na unetim podacima kako bi se otkrili oštećeni zapisi:

- Vrednost polja se ne podudara sa tipom podataka njegove kolone.
- Polja sadrže znakove zbog kojih se kolone ne podudaraju sa očekivanom šemom. Na primer: nepravilno oblikovani navodnici, neupareni navodnici ili znakovi novog reda.
- Ako postoje kolone datuma/datuma/datuma/datuma, njihov format mora biti naveden u modelu ako ne sledi standardni ISO format.

[!INCLUDE [footer-include](includes/footer-banner.md)]
