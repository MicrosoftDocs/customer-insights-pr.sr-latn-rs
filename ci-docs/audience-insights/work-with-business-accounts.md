---
title: Započnite rad sa poslovnim nalozima kao primarnom ciljnom grupom
description: Saznajte o poslovnim nalozima kao primarnom ciljnom grupom Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ac5ae950a44f7f32e3cb9fdc0ffad05b78fddef0
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673704"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Rad sa poslovnim nalozima u uvidima u ciljnu grupu

Mogućnost uvida u ciljnu grupu u usluzi Dynamics 365 Customer Insights omogućava vam da konfigurišete svoje okruženje za različite primarne ciljne grupe: pojedinačne potrošače (B-to-C) i poslovne kontakte (B-to-B). U B-to-C scenarijima, podaci su centrirani oko pojedinaca. Za B-to-B, primarna ciljna grupa su poslovni kontakti – organizacije ili kompanije – i kontakti. Ovaj članak vam pomaže da započnete sa okruženjem za poslovne naloge. On navodi razlike za oblasti karakteristika u uvidima u ciljnu grupu u zavisnosti od fokusa okruženja. Za više informacija o razlikama pregledajte dokumente iz oblasti funkcija. 

## <a name="create-an-environment-for-business-accounts"></a>Kreiranje okruženja za poslovne naloge

Administratori mogu da [kreiraju okruženje u postojećoj organizaciji](create-environment.md). Korak u procesu kreiranja novog okruženja traži od administratora primarnu ciljnu grupu okruženja. U slučaju da se radi o početnom podešavanju uvida u ciljnu grupu nakon kupovine licence, vođeno iskustvo vam pomaže u kreiranju prvog okruženja.

Zatim možete [uneti podatke](data-sources.md) za poslovne naloge i povezane kontakte kao izvore podataka iz svih podržanih izvora.

Nakon objedinjavanja podataka, [navedite hijerarhije naloga](relationships.md#set-up-account-hierarchies) kao deo konfiguracije odnosa. Možete takođe da [konfigurišete semantička mapiranja](semantic-mappings.md) za povezivanje entiteta kontakata i naloga. 

## <a name="switch-between-primary-target-audience"></a>Prebacivanje između primarne ciljne grupe

Ako vaša organizacija održava okruženja za pojedinačne klijente i poslovne naloge, pomoću prekidača u levom oknu možete izabrati primarnu ciljnu grupu.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Prebacivanje za promenu primarne ciljne grupe između pojedinačnih klijenata i poslovnih naloga.":::

## <a name="supported-feature-areas"></a>Oblasti podržani funkcija

- [Aktivnosti](activities.md): Podrška za naloge i povezane kontakte za kreiranje aktivnosti i njihovo prikazivanje na vremenskoj osi.
- [Odnosi](relationships.md): Čarobnjak aktivnosti pomaže pri kreiranju odnosa između entiteta tako da prikaz naloga može prikazati sve aktivnosti kontakata. Kontakti se mogu detaljno pregledati da biste videli prikaz kontakata, a hijerarhije se mogu koristiti za objedinjavanje aktivnosti naloga.
- [Mere](measures.md): Podržava mere kreirane iz proizvođača mera sa jednim izračunavanjem. Opciono podešavanje omogućava objedinjavanje podnaloga pri kreiranju mera.
- [Segmenti](segments.md): Podržava segmente koji su kreirani od nule pomoću alatke za izradu segmenata. Novi operatori dozvoljavaju uključivanje hijerarhije naloga pri izgradnji segmenata.
- [Unos podataka](data-sources.md): Sve funkcije u ovoj oblasti su iste za poslovne naloge i individualne klijente.
- [Objedinjavanje podataka](data-unification.md): Sve funkcije u ovoj oblasti su iste za poslovne naloge i individualne klijente.
- [Obogaćivanje](enrichment-hub.md): Neki tipovi obogaćivanja dostupni su samo za scenarije pojedinačnih klijenata, dok su drugi dostupni samo za poslovne naloge.
- [Predviđanja i gotovi modeli](predictions-overview.md): Predviđanje transakcionog gubitka sadrži dodatne korake za poslovne naloge. Druga predviđanja su dostupna samo za pojedinačne klijente.
- [Aktivacija i izvoz](export-destinations.md): Izvoz je dostupan za poslovne naloge i individualne klijente. Neki izvozi zahtevaju dodatnu konfiguraciju i kontakt informacije projektovane u osnovnim segmentima da bi bili važeći za poslovne naloge.
- [Podešavanja sistema](system.md) i [upravljanje korisnicima](permissions.md): Sve funkcije u ovoj oblasti su iste za poslovne naloge i individualne klijente.
