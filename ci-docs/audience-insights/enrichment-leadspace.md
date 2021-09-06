---
title: Obogaćivanje profila preduzeća nezavisnim Leadspace-om za obogaćivanje
description: Opšte informacije o Leadspace obogaćivanju treće strane.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 34b73b37670ed45e2c31ea164c0788b793bee433829ce21317c83903f3fca1fe
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031720"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Obogaćivanje profila preduzeća uz Leadspace (pregled)

Leadspace je kompanija za nauku o podacima koja obezbeđuje B2B platformu za podatke o klijentima. Omogućuje klijentima sa objedinjenim profilima klijenata za kompanije da obogaćuju svoje podatke. Obogaćivanja obuhvataju više atributa kao što su veličina preduzeća, lokacija, delatnost i još mnogo toga.

## <a name="prerequisites"></a>Preduslovi

Da biste konfigurisali Leadspace, morate da ispunite sledeće preduslove:

- Imate aktivnu Leadspace licencu.
- Imate [objedinjene profile klijenata](customer-profiles.md) za kompanije.
- Administrator je već konfigurisao Leadspace vezu ili imate dozvole [administratora](permissions.md#administrator) i „večiti ključ“ (koji se zove **Leadspace token**). Kontaktirajte [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) direktno da biste saznali detalje o njihovom proizvodu.

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. U uvidima o korisnicima idite na **Podaci** > **Obogaćivanje**.

1. Izaberite **Obogati moje podatke** na pločici Leadspace i izaberite **Započni**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Snimak ekrana Leadspace pločice.":::

1. Izaberite [vezu](connections.md) sa padajuće liste. Ako veza nije dostupna, obratite se administratoru. Ako ste administrator, vezu možete kreirati izborom **Dodaj vezu** i biranjem opcije **Leadspace**. 

1. Izaberite **Povežite se sa uslugom Leadspace** da biste potvrdili izbor veze.

1. Izaberite **Sledeće** i birajte **Skup podataka klijenta** koji želite da obogatite podacima preduzeća iz usluge Leadspace. Možete izabrati entitet **Klijent** da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Snimak ekrana prilikom odabira skupa podataka o klijentima.":::

1. Izaberite **Sledeće** i definišite koja polja iz vaših objedinjenih profila se koriste za podudaranje podataka o preduzeću iz usluge Leadspace. Polje **Ime kompanije** je obavezno. Za veću preciznost podudaranja, do dva druga polja, **Veb-lokacija kompanije** i **Lokacija kompanije**, mogu se dodati.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Okno za mapiranje polja Leadspace.":::

1. Izaberite **Sledeće** da biste dovršili mapiranje polja.

1. Navedite ime za obogaćivanje i izaberite **Sačuvaj obogaćivanje** nakon pregleda vašeg izbora.


## <a name="configure-the-connection-for-leadspace"></a>Konfigurišite vezu za Leadspace 

Morate biti administrator da biste konfigurisali veze. Izaberite **Dodaj vezu** prilikom konfigurisanja obogaćivanja *ili* idite na **Administrator** > **Veze** i izaberite **Podešavanje** na pločici Leadspace.

1. Izaberite **Prvi koraci**. 

1. Unesite naziv veze u polje **Ime za prikaz**.

1. Navedite važeći token za Leadspace.

1. Pregledajte i dajte saglasnost za **Privatnost podataka i usklađenost** izborom opcije **Slažem se**.

1. Izaberite **Verifikuj** da biste proverili valjanost konfiguracije.

1. Po završetku verifikacije, izaberite **Sačuvaj**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Stranica za konfiguraciju veze za Leadspace.":::

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Nakon osvežavanja obogaćivanja, možete pregledati novo obogaćene podatke kompanije u delu [Moja obogaćenja](enrichment-hub.md). Možete pronaći vreme poslednjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.

Više informacija potražite u članku [Leadspace API-ji](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Sledeći koraci

Nadogradite na obogaćenim podacima o klijentima. Kreirajte [segmente](segments.md) i [mere](measures.md), pa čak i [izvoz podataka](export-destinations.md) da pružite personalizovana iskustva svojim klijentima.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Leadspace, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Leadspace ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
