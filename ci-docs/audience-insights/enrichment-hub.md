---
title: Obogatite objedinjene profile klijenata
description: Koristite mogućnosti za obogaćivanje podataka o klijentima.
ms.date: 02/18/2022
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
ms.openlocfilehash: b44f5a4b74c63629811837b853b4e069dea63504
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/02/2022
ms.locfileid: "8372736"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Obogaćivanje za profile korisnika (pregled)

Koristite podatke iz izvora kao što su Microsoft i drugi partneri da biste obogatili podatke o klijentima.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stranica čvorišta za obogaćivanje.":::

U uvidima o korisnicima idite na **Podaci** > **Obogaćivanje** da biste koristili opcije obogaćivanja.  

Da biste kreirali ili menjali obogaćivanja, morate da imate dozvole saradnika ili administratora. Više informacija potražite u [dozvolama](permissions.md).

Na kartici **Otkrivanje**, pronaći ćete sve podržane opcije obogaćivanja.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

- [Brendove](enrichment-microsoft.md) obezbeđuje Microsoft
- [Interesovanja](enrichment-microsoft.md) obezbeđuje Microsoft
- [Poboljšane adrese](enrichment-enhanced-addresses.md) obezbeđuje Microsoft 
- [Demografski podaci](enrichment-experian.md) koje obezbeđuje Experian
- [Prilagođeni podaci](enrichment-SFTP-custom-import.md) pomoću protokola Secure File Transfer Protocol (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) obezbeđuje Microsoft
- [Podatke o lokaciji](enrichment-here.md) pruža HERE Technologies 
- [Identitet](enrichment-liveramp.md) obezbedio LiveRamp AbiliTec

# <a name="business-accounts-b-to-b"></a>[Poslovni nalozi (B-to-B)](#tab/b2b)

- [Podaci o kompaniji](enrichment-leadspace.md) koje pruža Leadspace
- [Poboljšane adrese](enrichment-enhanced-addresses.md) obezbeđuje Microsoft 
- [Poboljšani podaci o](enrichment-enhanced-company-data.md) preduzeću koje obezbeđuje Microsoft
- [Podatke o lokaciji](enrichment-here.md) pruža HERE Technologies 
- [Prilagođeni podaci](enrichment-SFTP-custom-import.md) pomoću protokola Secure File Transfer Protocol (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) obezbeđuje Microsoft
- [Podaci o angažovanju](enrichment-office.md) naloga koje je obezbedio Microsoft

---

Na kartici **Moja obogaćivanja** možete da vidite obogaćivanja koja ste konfigurisali i da menjate njihova svojstva.

## <a name="manage-existing-enrichments"></a>Upravljanje postojećim obogaćivanjima

Idite na karticu **Moja obogaćivanja** da biste videli sva konfigurisana obogaćivanja. Svako obogaćivanje predstavljeno je kao red koji uključuje dodatne informacije o obogaćivanju.

Izaberite obogaćivanje da biste videli dostupne opcije. Takođe možete odabrati tri tačke (...) na stavci liste da biste videli opcije. Ako ste konfigurisali nekoliko obogaćivanja, možete ih brzo pronaći pomoću okvira za pretragu.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcije za upravljanje obogaćivanjima na listi obogaćivanja.":::

- **Prikažite** detalje obogaćivanja sa brojem obogaćenih profila klijenata.
- **Uređujte** konfiguraciju obogaćivanja.
- **Pokrenite** obogaćivanje radi ažuriranja profila klijenata najnovijim podacima.
- **Deaktivirajte** postojeće obogaćivanje kako bi se zaustavili automatsko osvežavanje sa svakim zakazanim osvežavanjem. Podaci iz poslednjeg uspešnog osvežavanja i dalje će biti dostupni. **Aktivirajte** neaktivno obogaćivanje da biste ponovo pokrenuli automatsko osvežavanje sa svakim zakazanim osvežavanjem.
- **Izbrišite** obogaćivanje.

Pokrenite ili deaktivirajte više obogaćivanja odjednom tako što ćete ih izabrati na listi. Opcije prikaza i uređivanja nisu dostupne kao grupne radnje. Rade samo za jedno obogaćivanje istovremeno.

## <a name="enrichments-and-connections"></a>Obogaćivanja i veze

Obogaćenja trećih lica se konfigurišu pomoću [veza](connections.md) koje administrator postavlja sa akreditivima i daje saglasnost za prenos podataka. Veze mogu da koriste administratori i saradnici kako bi konfigurisali obogaćivanja.  

## <a name="multiple-enrichments-of-the-same-type"></a>Višestruka obogaćivanja istog tipa

Entitet koji treba obogatiti navodi se tokom konfiguracije obogaćivanja, što vam omogućava da obogatite samo podskup svojih profila. Na primer, obogatite podatke samo za određeni segment. Možete da konfigurišete nekoliko obogaćivanja istog tipa i da ponovo koristite istu vezu. Neka obogaćivanja će imati ograničenja u broju obogaćivanja istog tipa koja se mogu kreirati. Ograničenja i trenutna upotreba mogu se videti na stranici **Obogaćivanje**.

## <a name="enrich-data-sources-before-unification"></a>Obogati izvore podataka pre ujedinjenja

Podatke o korisnicima možete obogatiti pre ujedinjenja podataka da biste povećali kvalitet podudaranja podataka. Više informacija potražite u članku [izvor podataka bogaćenje](data-sources-enrichment.md).

## <a name="see-the-progress-of-the-enrichment-process"></a>Pogledajte napredak procesa obogaćivanja

Možete pronaći detalje o obradi obogaćivanja, uključujući njegov status i potencijalne probleme dok se osvežava ili nakon završetka osvežavanja. Shvatite koji su procesi uključeni za osvežavanje obogaćivanja i koliko je vremena potrebno za pokretanje procesa. Status obogaćivanja je podržan za Experian, Leadspace, HERE Technologies, SFTP Import i Azure Maps.

Da biste videli status obogaćivanja

1. Idite na **Podaci** > **Obogaćivanje**. 
1. Na kartici **Moja obogaćivanja**, izaberite status obogaćivanja da biste otvorili bočno okno. 
1. U oknu **Detalji o napretku**, proširite odeljak **Obogaćivanja**. 
1. Ispod obogaćivanja za koje želite da vidite napredak, izaberite **Vidi detalje**. 
1. U oknu **Detalji o zadatku**, izaberite **Prikaži detalje** da biste videli procese koji su uključeni u ažuriranje obogaćivanja i njihov status. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
