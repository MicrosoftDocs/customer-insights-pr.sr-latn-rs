---
title: Izvor podataka obogaćivanje
description: Obogatite izvore podataka pre nego što prođete kroz proces ujedinjenja podataka.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 1225482c4bf432ed747537b2c9bec9ab0e692a51
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800298"
---
# <a name="enrichment-for-data-sources-preview"></a>Obogaćivanje izvora podataka (pregled)

Koristite podatke iz izvora kao što su Microsoft i drugi partneri da biste obogatili podatke o klijentima pre ujedinjenja podataka. Izvor podataka obogaćivanja pomažu u proizvodnji veće potpunosti podataka i kvaliteta koji mogu da pomognu u postizanju boljih rezultata kada ujedinite svoje podatke. Na primer, korišćenje normalizovanog i standardizovanog formata za adrese povećava kvalitet rezultata utakmice. Listu podržanih obogaćivanja pogledajte podržane [opcije izvor podataka za obogaćivanje](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Obogatite izvor podataka

Morate imati dozvole saradnik administratora za kreiranje ili uređivanje obogaćivanja. Više informacija potražite u [dozvolama](permissions.md).  

1. Idite na " **Ujedinjenje** > **podataka"**. Izaberite entitet koji želite da obogatite i izaberite jedan atribut kao primarni ključ za entitet. Više informacija potražite u članku [Izbor primarnog ključa](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Idite na **Podaci** > **Izvori podataka**.

1. Izaberite vertikalnu elipsu () pored prozora izvor podataka&vellip; želite da obogatite i izaberite Opciju **Obogati**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Stranica za obogaćivanje izvora podataka.":::

   Kartica **"** Otkrij" prikazuje podržane [izvor podataka za obogaćivanje.](#supported-data-source-enrichments)

1. Izaberite **stavku Obogati moje podatke** da biste konfigurisali izvor podataka obogaćivanje. Ime izlaznog entiteta se automatski popunjava.

## <a name="supported-data-source-enrichments"></a>Podržana izvor podataka obogaćivanja

Sledeća obogaćivanja su trenutno dostupna za izvore podataka. Pregledajte detaljne korake za bogaćenje da biste saznali kako da ga konfigurišete.

- [Poboljšane adrese](enrichment-enhanced-addresses.md)
- [Poboljšani podaci o preduzeću](enrichment-enhanced-company-data.md)
- [Podaci o identitetu iz liveRamp-a](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Upravljanje postojećim izvor podataka obogaćivanjem

Idite na karticu **Moja obogaćivanja** da biste videli sva konfigurisana obogaćivanja.

Izaberite obogaćivanje da biste videli dostupne opcije. Takođe možete da izaberete vertikalnu elipsu (&vellip;) na stavci liste da biste videli opcije. Ako ste konfigurisali nekoliko obogaćivanja, možete ih brzo pronaći pomoću okvira za pretragu.

Možete da prikažete, uredite, pokrenete ili izbrišete izvor podataka bogaćenje. Više informacija potražite u članku Upravljanje [postojećim obogaćivanjem](enrichment-hub.md).
