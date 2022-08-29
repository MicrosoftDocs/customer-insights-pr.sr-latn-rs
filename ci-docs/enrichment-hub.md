---
title: Pregled obogaćivanja podataka (pregled)
description: Koristite mogućnosti korporacije Microsoft i drugih usluga nezavisnih proizvođača da biste obogatili podatke o klijentima.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: fb747f7adc7d87f30f66c5d0ed20bbe238558fde
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304536"
---
# <a name="data-enrichment-preview-overview"></a>Pregled obogaćivanja podataka (pregled)

Koristite podatke iz izvora kao što su Microsoft i drugi partneri da biste obogatili podatke o klijentima. Obogaćenja trećih lica se konfigurišu pomoću [veza](connections.md) koje administrator postavlja sa akreditivima i daje saglasnost za prenos podataka. Veze mogu da koriste administratori i saradnici kako bi konfigurisali obogaćivanja.  

## <a name="multiple-enrichments-of-the-same-type"></a>Višestruka obogaćivanja istog tipa

Entitet koji treba obogatiti navodi se tokom konfiguracije obogaćivanja, što vam omogućava da obogatite samo podskup svojih profila. Na primer, obogatite podatke samo za određeni segment. Možete da konfigurišete nekoliko obogaćivanja istog tipa i da ponovo koristite istu vezu. Neka obogaćivanja će imati ograničenja u broju obogaćivanja istog tipa koja se mogu kreirati. Ograničenja i trenutna upotreba mogu se videti na svakoj pločici na kartici "Otkrivanje **"** na stranici "Obogaćivanje **·**".

## <a name="enrich-data-sources-before-unification"></a>Obogati izvore podataka pre ujedinjenja

Podatke o korisnicima možete obogatiti pre ujedinjenja podataka da biste povećali kvalitet podudaranja podataka. Više informacija potražite u članku [izvor podataka bogaćenje](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Kreiraj obogaćivanje

Potrebno je da imate dozvole saradnik administratora [za kreiranje](permissions.md) ili uređivanje obogaćivanja.

Idite na **Podaci** > **Obogaćivanje**. Kartica " **Otkrij** " prikazuje sve podržane opcije obogaćivanja.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stranica čvorišta za obogaćivanje.":::

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

- [AbiliTec identitet](enrichment-liveramp.md) obezbedio LiveRamp AbiliTec
- [Brendove](enrichment-microsoft.md) obezbeđuje Microsoft
- [Demografski podaci](enrichment-experian.md) koje obezbeđuje Experian
- [Poboljšane adrese](enrichment-enhanced-addresses.md) obezbeđuje Microsoft
- [Interesovanja](enrichment-microsoft.md) obezbeđuje Microsoft
- [podaci](enrichment-azure-maps.md) o lokaciji obezbeđuju mape Microsoft Azure
- [Podatke o lokaciji](enrichment-here.md) pruža HERE Technologies
- [SFTP prilagođeni podaci](enrichment-SFTP-custom-import.md) kroz Secure File Transfer Protocol (SFTP)

# <a name="business-accounts-b-to-b"></a>[Poslovni nalozi (B-to-B)](#tab/b2b)

- [Podaci o angažovanju](enrichment-office.md) naloga koje je obezbedio Microsoft
- [Podatke](enrichment-dnb.md) kompanije dostavio Dun & Bradstreet
- [Podaci o kompaniji](enrichment-leadspace.md) koje pruža Leadspace
- [Poboljšane adrese](enrichment-enhanced-addresses.md) obezbeđuje Microsoft
- [Poboljšani podaci o](enrichment-enhanced-company-data.md) preduzeću koje obezbeđuje Microsoft
- [podaci](enrichment-azure-maps.md) o lokaciji obezbeđuju mape Microsoft Azure
- [Podatke o lokaciji](enrichment-here.md) pruža HERE Technologies
- [SFTP prilagođeni podaci](enrichment-SFTP-custom-import.md) kroz Secure File Transfer Protocol (SFTP)

---

## <a name="manage-existing-enrichments"></a>Upravljanje postojećim obogaćivanjima

Idite na **Podaci** > **Obogaćivanje**. Na kartici **Moja bogaćenja** pogledajte konfigurisana bogaćenja, njihov status, broj obogaćenih klijenata i poslednji put kada su podaci osveženi. Listu obogaćivanja možete da sortirate po bilo kojoj koloni ili da koristite polje za pretragu da biste pronašli bogaćenje kojim želite da upravljate.

Izaberite bogaćenje da biste prikazali dostupne radnje.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcije za upravljanje obogaćivanjima na listi obogaćivanja.":::

- **Prikažite** detalje obogaćivanja sa brojem obogaćenih profila klijenata.
- **Uređujte** konfiguraciju obogaćivanja.
- [**Pokrenite**](#run-or-refresh-enrichments) bogaćenje da biste ažurirali profile klijenata najnovijim podacima. Pokrenite više obogaćivanja odjednom tako što ćete ih izabrati na listi.
- **Aktivirajte** **ili deaktivirajte** bogaćenje. Neaktivna obogaćivanja se neće osvežiti tokom planiranog [osvežavanja](schedule-refresh.md).
- **Izbrišite** obogaćivanje.

Segmente ili mere možete [kreirati](segments.md) i [od obogaćivanja](measures.md).

## <a name="run-or-refresh-enrichments"></a>Pokretanje ili osvežavanje obogaćivanja

Kada se pokrenete, obogaćivanje se može osvežiti automatskim rasporedom ili osvežiti ručno na zahtev.

1. Da biste ručno osvežili jedno ili više obogaćivanja, izaberite ih i odaberite stavku **Pokreni**. Da biste [zakazali automatsko osvežavanje](schedule-refresh.md), idite **na administrativni** > **plan** > **sistema**. Vreme obrade zavisi od veličine podataka vaših klijenata.

1. Opcionalno, [pogledajte napredak procesa obogaćivanja](#see-the-progress-of-the-enrichment-process).

1. Kada se proces obogaćivanja završi, idite na **Moja bogaćenja** da pregledate novoobogaćene podatke profila klijenata, vreme poslednjeg ažuriranja i broj obogaćenih profila.

1. Izaberite bogaćenje da biste videli rezultate [obogaćivanja](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Pogledajte napredak procesa obogaćivanja

Detalje o obradi obogaćenja možete pronaći, uključujući njegov status i potencijalne probleme dok je osvežavanje ili nakon dovršenja osvežavanja. Shvatite koji su procesi uključeni za osvežavanje obogaćivanja i koliko je vremena potrebno za pokretanje procesa. Status obogaćivanja je podržan za Experian, Leadspace, HERE Technologies, SFTP Import i Azure Maps.

1. Idite na **Podaci** > **Obogaćivanje**.
1. Na kartici **Moja obogaćivanja** izaberite status bogaćenja da biste otvorili bočno okno.
1. U oknu **Detalji o napretku**, proširite odeljak **Obogaćivanja**.
1. Ispod obogaćivanja za koje želite da vidite napredak, izaberite **Vidi detalje**.
1. U oknu **Detalji o zadatku**, izaberite **Prikaži detalje** da biste videli procese koji su uključeni u ažuriranje obogaćivanja i njihov status.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Prikaži rezultate obogaćivanja

Nakon završenog trčanja za bogaćenje, pregledajte rezultate obogaćivanja.

1. Idite na **Podaci** > **Obogaćivanje**.
1. Na kartici **Moja obogaćivanja** izaberite bogaćenje koje želite da prikažete.

Sva bogaćenja prikazuju osnovne informacije kao što su broj obogaćenih profila i broj obogaćenih profila tokom vremena. Pločica **za pregled obogaćenih** klijenata prikazuje uzorak generisanog entiteta obogaćivanja. Da biste videli detaljan prikaz, izaberite stavku Pogledajte **više i** izaberite karticu **Podaci**.

:::image type="content" source="media/enrichments-results.png" alt-text="Stranica sa rezultatima obogaćivanja.":::

Ako je dostupan **, broj kupaca obogaćenih poljem** obezbeđuje dubinsku analizu pokrivenosti svakog obogaćenog polja.

Neka obogaćivanja takođe pokazuju informacije specifične za vrstu bogaćenja. Više informacija potražite u srodnoj dokumentaciji.

[!INCLUDE [footer-include](includes/footer-banner.md)]
