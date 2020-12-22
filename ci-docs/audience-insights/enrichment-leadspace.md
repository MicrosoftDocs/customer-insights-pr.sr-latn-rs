---
title: Obogaćivanje profila preduzeća nezavisnim Leadspace-om za obogaćivanje
description: Opšte informacije o Leadspace obogaćivanju treće strane.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668740"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Obogaćivanje profila preduzeća uz Leadspace (pregled)

Leadspace je kompanija za nauku o podacima koja obezbeđuje B2B platformu za podatke o klijentima. Omogućuje klijentima sa objedinjenim profilima klijenata za kompanije da obogaćuju svoje podatke. Obogaćivanja obuhvataju dodatne atribute uključujući veličinu kompanije, lokaciju, delatnost i još mnogo toga.

## <a name="prerequisites"></a>Preduslovi

Da biste konfigurisali Leadspace, morate da ispunite sledeće preduslove:

- Imate aktivnu Leadspace licencu i „trajni ključ“ (nazvan **Leadspace token**). Kontaktirajte direktno [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) za detalje o njihovom proizvodu.
- Imate [administratorske](permissions.md#administrator) dozvole.
- Imate [objedinjene profile klijenata](customer-profiles.md) za kompanije.

## <a name="configuration"></a>Konfigurisanje

1. U uvidima o korisnicima idite na **Podaci** > **Obogaćivanje**.

1. Izaberite **Obogati moje podatke** na pločici Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Snimak ekrana Leadspace pločice.":::

1. Izaberite **Započnite**, a zatim unesite aktivan **Leadspace token** (trajni ključ). Pregledajte i dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**. Potvrdite oba ulaza izborom opcije **Povežite se na Leadspace**.

1. Izaberite **Podaci mape** i definišite koja polja iz vaših objedinjenih profila treba koristiti za traženje odgovarajućih podataka o kompaniji iz Leadspace-a. Polje **Ime kompanije** je obavezno. Za veću preciznost podudaranja, do dva druga polja, **Veb-lokacija kompanije** i **Lokacija kompanije**, mogu se dodati.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Okno za mapiranje polja Leadspace.":::
   
1. Izaberite **Primeni** da dovršite mapiranje polja.

1. Izaberite **Pokreni** kako biste obogatili profile preduzeća. Koliko dugo traje obogaćivanje, zavisi od broja objedinjenih profila klijenata.

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Nakon osvežavanja obogaćivanja, možete pregledati novo obogaćene podatke kompanije u delu [Moja obogaćenja](enrichment-hub.md). Možete pronaći vreme poslednjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.

Više informacija potražite u članku [Leadspace API-ji](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Sledeći koraci

Nadogradite na obogaćenim podacima o klijentima. Kreirajte [segmente](segments.md), [mere](measures.md), pa čak i [izvezite podatke](export-destinations.md) da biste pružili personalizovana iskustva svojim klijentima.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Leadspace, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Leadspace ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.