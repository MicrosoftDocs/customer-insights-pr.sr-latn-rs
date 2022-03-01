---
title: Prikaz izveštaja o podacima
description: Koristite dostupne izveštaje da biste videli aktivnosti u realnom vremenu na vašoj veb-lokaciji.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 06/18/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: cb6d9ab75b95a5f677d2267f5412a55327930987b2fc3a1a21958633a8116bd2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036665"
---
# <a name="view-reports"></a>Prikaži izveštaje

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Izveštaj je zbirka vizuelizacija podataka koja koristi podatke prikupljene putem SDK-a i koji vam pomažu u merenju i razumevanju ponašanja korisnika. Dynamics 365 Customer Insights uvidi o angažovanju uključuju gotove (OOB) izveštaje za veb i mobilne projekte.  

## <a name="web-reports"></a>Veb-izveštaji

Možete da pristupite veb-izveštajima U delu **Otkrivanje** u levom oknu za navigaciju.

:::image type="content" source="media/report-menu.png" alt-text="Navigacija koja prikazuje listu dostupnih izveštaja.":::

### <a name="real-time-usage-report"></a>Izveštaj o korišćenju u realnom vremenu

Izveštaj **Korišćenje u realnom vremenu** pruža pregled trenutnih aktivnosti na vašoj lokaciji koja se automatski osvežava svakog minuta. Pomoću korišćenja u realnom vremenu nadgledajte uticaj marketinških kampanja, događaja za novinare i drugih scenarija na saobraćaj vaše lokacije.

### <a name="key-metrics-reports"></a>Izveštaji o ključnoj metrici

- **Prikazi stranice** navode prikaze za pojedinačne stranice zajedno sa brojem ukupnih prikaza stranica tokom izabranog vremenskog okvira.

- **Posete** prikazuju informacije o broju poseta i trajanju posete.

- **Posetioci** vas informišu o novim i povratnim jedinstvenim posetiocima na vašoj veb-lokaciji.

### <a name="content-reports"></a>Izveštaji o sadržaju

- **Veze** prikazuju informacije o broju i vrsti klikova.

- **Izlazne stranice** navode veze na koje su posetioci kliknuli da bi izašli sa vaše lokacije.

### <a name="traffic-sources-reports"></a>Izveštaji o izvorima saobraćaja

- **Upućivači** navode domene i URL adrese koje su upućivale posetioce na vašu lokaciju.

- **Kodovi za praćenje** pružaju detalje o kodovima za praćenje u vezama koje su dovele posetioce na vašu lokaciju.

### <a name="visitor-profiles-reports"></a>Izveštaji o profilima posetilaca

- **Uređaji** navode fizičke uređaje koji su korišćeni za pristup vašoj lokaciji.

- **Operativni sistemi i pregledači** pružaju uvide u operativne sisteme i pregledače koji su bili pokrenuti prilikom pristupanja lokaciji.

- **Lokacije** prikazuju informacije o posetiocima po zemlji, regionu i gradu.

- **Jezici** navode prikaze stranica po izabranim jezicima posetioca.

## <a name="mobile-reports"></a>Izveštaji za mobilne uređaje

Izveštaji za mobilne uređaje su grupisani u kategorije korišćenja u realnom vremenu, aplikacija i korisnika. Izveštajima za mobilne uređaje možete pristupiti u delu **Otkrivanje** u levom oknu za navigaciju.   

:::image type="content" source="media/mobile-reports.png" alt-text="Korisnički interfejs uvida u angažovanje koji prikazuje izveštaj o korišćenju u realnom vremenu koji prikazuje podatke na grafikonima i listama.":::   

### <a name="real-time-usage"></a>Korišćenje u realnom vremenu

**Korišćenje u realnom vremenu** pruža pregled trenutnih aktivnosti u vašoj aplikaciji za mobilne uređaje koja se automatski osvežava svakog minuta. Koristite upotrebu u realnom vremenu za nadgledanje broja korisnika i sesija trenutno aktivnih u vašoj aplikaciji, kao i najviše prikaza ekrana.

### <a name="app-reports"></a>Izveštaji o aplikaciji

- **Prikazi ekrana** navode prikaze ekrana za pojedinačne ekrane u aplikaciji i ukupan broj prikaza ekrana tokom izabranog vremenskog okvira. Prikaze ekrana možete pregledati prema imenu ili naslovu ekrana.

- **Sesije** prikazuju informacije o broju sesija i trajanju sesije.

- **Učestalost povratka** grupiše brojeve sesija po broju dana od poslednje sesije.

- **Korisnici** prikazuju nove korisnike i povratnike u mobilnoj aplikaciji,

- **Događaji** navode sve događaje prikupljene iz vaše aplikacije, plus ukupan broj za svaki događaj.

### <a name="user-reports"></a>Izveštaji o korisnicima

- **Verzije aplikacije** navode verzije vaše aplikacije za mobilne uređaje koje koristi vaša baza korisnika.

- **Uređaji i verzije operativnog sistema** pružaju uvid na kojim uređajima i operativnim sistemima je pokrenuta vaša mobilna aplikacija.

- **Lokacije** prikazuju informacije o korisnicima aplikacije po zemlji, regionu i gradu.

## <a name="filter-by-time-or-value"></a>Filtriranje prema vremenu ili vrednosti

Možete da izaberete vremenski okvir ili vrednost u veb-izveštaju ili izveštaju na mobilnom uređaju da biste se usredsredili na vrednost ili vremenski period. 

- Da biste izabrali vremenski okvir, izaberite **Još [...]** sa padajuće liste izveštaja. Izbor vremenskog opsega je onemogućen za izveštaj o korišćenju u realnom vremenu; vremenski raspon za izveštaj o korišćenju u realnom vremenu je „sada“.

- U većini izveštaja izaberite vrednost na grafikonu ili listi da biste filtrirali izveštaj za izabranu vrednost.

[!INCLUDE[footer-include](../includes/footer-banner.md)]