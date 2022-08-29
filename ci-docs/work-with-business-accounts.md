---
title: Rad sa poslovnim nalozima
description: Saznajte više o poslovnim nalozima kao primarnom ciljnom korisnici u Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: abb77a720ab737520a905b0c93b65573e669109f
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303933"
---
# <a name="work-with-business-accounts"></a>Rad sa poslovnim nalozima

Omogućava Dynamics 365 Customer Insights vam da konfigurišete okruženje za različite primarne ciljne korisnike: pojedinačne potrošače (B-to-C) i poslovne naloge (od B do B). U B-to-C scenarijima, podaci su centrirani oko pojedinaca. Za B-to-B, primarna ciljna grupa su poslovni kontakti – organizacije ili kompanije – i kontakti. Ovaj članak vam pomaže da započnete sa okruženjem za poslovne naloge. On navodi razlike za oblasti funkcija u uvidima klijenata, u zavisnosti od fokusa okruženja. Za više informacija o razlikama pregledajte dokumente iz oblasti funkcija. 

## <a name="create-an-environment-for-business-accounts"></a>Kreiranje okruženja za poslovne naloge

Administratori mogu da [kreiraju okruženje u postojećoj organizaciji](create-environment.md). Korak u procesu kreiranja novog okruženja traži od administratora primarnu ciljnu grupu okruženja. U slučaju da se radi o početnom podešavanju nakon kupovine licence, vođeno iskustvo pomaže u kreiranju prvog okruženja.

Zatim možete [uneti podatke](data-sources.md) za poslovne naloge i povezane kontakte kao izvore podataka iz svih podržanih izvora.

 [Ujedinite podatke](data-unification.md) naloga praćene kontakt podacima da biste povezali entitete kontakata i naloga.

## <a name="switch-between-primary-target-audience"></a>Prebacivanje između primarne ciljne grupe

Ako vaša organizacija održava okruženja za pojedinačne klijente i poslovne naloge, pomoću prekidača u levom oknu možete izabrati primarnu ciljnu grupu.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Prebacivanje za promenu primarne ciljne grupe između pojedinačnih klijenata i poslovnih naloga.":::

## <a name="supported-feature-areas"></a>Oblasti podržani funkcija

- [Aktivnosti](activities.md): Podrška za naloge i povezane kontakte za kreiranje aktivnosti i njihovo prikazivanje na vremenskoj osi.
- [Odnosi](relationships.md): Čarobnjak aktivnosti pomaže pri kreiranju odnosa između entiteta tako da prikaz naloga može prikazati sve aktivnosti kontakata. Kontakti se mogu detaljno pregledati da biste videli prikaz kontakata, a hijerarhije se mogu koristiti za objedinjavanje aktivnosti naloga.
- [Mere](measures.md): Podržava mere kreirane iz proizvođača mera sa jednim izračunavanjem. Opciono podešavanje omogućava objedinjavanje podnaloga pri kreiranju mera.
- [Segmenti](segments.md): Podržava segmente koji su kreirani od nule pomoću alatke za izradu segmenata. Segmenti mogu biti zasnovani na poslovnim kontaktima ili kontaktima.
- [Unos podataka](data-sources.md): Sve funkcije u ovoj oblasti su iste za poslovne naloge i individualne klijente.
- B-to-B ujedinjenje podataka je veoma slično ujedinjenju podataka B-to-C, ali ima dodatni korak za ujedinjenje kontakata nakon ujedinjenja naloga. Pogledajte [poslovne naloge (od B do B)](data-unification.md).
- [Obogaćivanje](enrichment-hub.md): Neki tipovi obogaćivanja dostupni su samo za scenarije pojedinačnih klijenata, dok su drugi dostupni samo za poslovne naloge.
- [Predviđanja i gotovi modeli](predictions-overview.md): Predviđanje transakcionog gubitka sadrži dodatne korake za poslovne naloge. Druga predviđanja su dostupna samo za pojedinačne klijente.
- [Aktivacija i izvoz](export-destinations.md): Izvoz je dostupan za poslovne naloge i individualne klijente. Neki izvozi zahtevaju dodatnu konfiguraciju i kontakt informacije projektovane u osnovnim segmentima da bi bili važeći za poslovne naloge.
- [Podešavanja sistema](system.md) i [upravljanje korisnicima](permissions.md): Sve funkcije u ovoj oblasti su iste za poslovne naloge i individualne klijente.

[!INCLUDE [footer-include](includes/footer-banner.md)]
