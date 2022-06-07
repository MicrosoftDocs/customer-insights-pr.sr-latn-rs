---
title: Korišćenje objedinjenih profila u Dynamics 365 marketingu
description: Saznajte kako da integrišete objedinjene profile i segmente sa Dynamics 365 marketingom.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4cc3cbde97d0f9da198652e86c0843476393b646
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833325"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Rad sa objedinjenim profilima klijenata u Dynamics 365 marketingu

[Dynamics 365 Marketing](/dynamics365/marketing/overview) uzdiže korisnička iskustva, omogućavajući vam da orkestrirate personalizovana putovanja na svim dodirnim tačkama kako biste ojačali odnosi i zaradili lojalnost. Dynamics 365 marketing aplikacija neprimetno funkcioniše sa Dynamics 365 Sales, Dynamics 365 Customer Insights, i Microsoft Teams drugim proizvodima i omogućava vam da donosite brže i bolje odluke koristeći moć podataka i AI.

Povezivanjem podataka "Uvid u korisnike" sa marketingom možete da:

- Ciljaj objedinjene profile klijenata i segmente. Ovo vam omogućava da angažujete svakog kupca, bez obzira na lokaciju podataka kupca.
- Osnovni dinamički sadržaj (kao što su personalizovani tokeni) u e-porukama, SMS-u i guranje obaveštenja o merama kao što su status lojalnosti, datum obnavljanja pretplate, nadređeni nalog ili bilo koja druga mera koju ste uhvatili u objedinjenom profilu uvida klijenata.
- Učitajte podatke iz marketinga u uvide klijenata i kombinujte ih sa podacima klijenata iz drugih izvora.
- Primenite alatke za čišćenje, obogaćivanje i nejasno podudaranje podataka korisničkog uvida.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Korišćenje bogatih profila klijenata u marketingu u realnom vremenu

Marketing u realnom vremenu vam omogućava da kreirate prilagođene [okidače koji pokreću](/dynamics365/marketing/real-time-marketing-custom-triggers) putovanja klijenata na osnovu bilo koje radnje klijenta. Što su vaši podaci personalizovaniji, vaša putovanja će biti relevantnija i personalizovanija. To je ono što kombinovanje marketinga i uvida klijenata čini tako moćnim. Možete da [ujedinite podatke iz](data-unification.md) bilo kog izvora, a zatim da ih koristite za podsticanje hiper-personalizovanih putovanja kupaca.

Saznajte više: Koristite [profile i segmente korisničkog uvida u marketing u realnom vremenu](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Korišćenje objedinjenih segmenata sa putovanjima odlaznih kupaca

Uvidi klijenata vam omogućavaju da pročistite podatke iz mnogih izvora i kombinujete ih u segmente agregatnih klijenata. Povezivanjem [uvida klijenata sa izlaznim marketingom](export-dynamics365-marketing.md), ovi segmenti će se automatski pojaviti *i* osvežiti u put koji pređe korisnik dizajnera.

Saznajte više: [Korišćenje segmenata iz Dynamics 365 Customer Insights dynamics 365 marketinga](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Povucite podatke iz svojih Azure Data Lake Storage

Niste ograničeni na skladište u oblaku ako želite da koristite podatke "Uvidi klijenata" sa marketingom. Ako već imate sopstveno podešavanje Azure Data Lake Storage, možete da se povežete sa programom Customer Insights, a zatim da delite podatke sa marketinškom aplikacijom kao što biste to uradili sa podešavanjem zasnovanim na oblaku.

Saznajte više: [Omogućite deljenje podataka Dataverse pomoću sopstvenih Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
