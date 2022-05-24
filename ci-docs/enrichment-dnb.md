---
title: Enrichment of company profile with Dun & Bradstreet
description: Opšte informacije o obogaćivanju treće strane Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c738c2657d4cda213342629156ddc8104366bd8a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755417"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Enrichment of company profile with Dun & Bradstreet (Preview)

Dun & Bradstreet pruža komercijalne podatke, analitiku i uvide za preduzeća. Omogućuje klijentima sa objedinjenim profilima klijenata za kompanije da obogaćuju svoje podatke. Obogaćivanje uključuje atribute kao što su DUNS broj, veličina kompanije, lokacija, industrija i još mnogo toga.

## <a name="prerequisites"></a>Preduslovi

Da biste konfigurisali Dun & Bradstreet bogaćenje, moraju se ispuniti sledeći preduslovi:

- Imate aktivnu Dun [& Bradstreet licencu](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- Imate [objedinjene profile klijenata](customer-profiles.md) za kompanije.
- Dun & Bradstreet [vezu](connections.md) je konfigurisao administrator. Možete ga kreirati ako imate [administratorske](permissions.md#admin) dozvole i akreditive kompanije Dun & Bradstreet Connect.

## <a name="setting-up-your-dun--bradstreet-project"></a>Postavljanje vašeg projekta Dun & Bradstreet

Kao licencirani korisnik Dun & Bradstreet, projekat možete podesiti u [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).


1. Prijavite se na [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Vratite lozinku u prethodno stanje da [biste preuzeli akreditive](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Preuzmite [naš csv template fajl](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) koji će se koristiti za mapiranje polja Customer Insights u odgovarajuća polja Dun & Bradstreet.

1. Upload the file in the **Upload data** step of the Dun & Bradstreet project creation experience.

1. Izaberite horizontalne tačke ispod relevantnog izvora **u** novokreiranom projektu Dun & Bradstreet da biste videli dostupne opcije.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Screenshot of dots in a Dun & Bradstreet project.":::

1. Odaberite **stavku Nabavi S3 detalje**. Uskladištite ove informacije na bezbedno mesto. Biće vam potreban da biste podesili [vezu za bogaćenje u uvidima](#configure-a-connection-for-dun--bradstreet) kupaca.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Screenshot izbora s3 informacija u Dun & Bradstreet projektu.":::

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite na **Podaci** > **Obogaćivanje**.

1. Izaberite **Obogati moje podatke** na Dun & Bradstreet pločici i izaberite Get **Started**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Screenshot of the Dun & Bradstreet pločica.":::

1. Izaberite [vezu](connections.md) sa padajuće liste. Ako veza nije dostupna, obratite se administratoru. Ako ste administrator, možete da kreirate vezu. Izaberite **Dodaj vezu** i odaberite **Dun & Bradstreet**.

1. Izaberite **Poveži se sa Dun & Bradstreet** da biste potvrdili vezu.

1. Kliknite **na** dugme Dalje i odaberite **skup podataka želite** da obogatite podacima kompanije iz Dun & Bradstreet. Možete izabrati entitet kupca **da** biste obogatili sve profile kupaca ili izabrati entitet segmenta da biste obogatili samo objedinjene profile kupaca koji se nalaze u tom segmentu.

1. Kliknite **na dugme** Dalje i definišite koja polja iz vaših objedinjenih profila se koriste za pronalaženje odgovarajućih podataka kompanije iz dun & bradstreet. Broj **DUNS-a** ili **polja "Ime preduzeća** **" i** "Zemlja" su obavezni. Polje zemlje podržava dva ili [tri koda zemlje sa dva ili tri slova, ime](https://www.iso.org/iso-3166-country-codes.html) zemlje na engleskom jeziku, ime zemlje na maternjem jeziku i telefonski prefiks. Neke uobičajene varijante zemlje uključuju:

- SAD: Sjedinjene Američke Države, Sjedinjene Države, SAD, Amerika.
- CA: Kanada.
- GB: Velika Britanija, Velika Britanija, Velika Britanija, GB, Velika Britanija i Severna Irska, Velika Britanija.
- Australija, Komonvelt Australije.
- FR: Francuska, Francuska Republika.
- Nemačka, Nemačka, Dojčland, Alemagne, Savezna Republika Nemačka, Republika Nemačka.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet okno za mapiranje polja.":::

1. Izaberite **Sledeće** da biste dovršili mapiranje polja.

1. Navedite ime za obogaćivanje i izaberite **Sačuvaj obogaćivanje** nakon pregleda vašeg izbora.

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigurišite vezu za Dun & Bradstreet

Morate biti administrator da biste konfigurisali veze. Izaberite **Dodaj vezu** prilikom konfigurisanja obogaćenja ili *idite* na **administrativne** > **veze i** izaberite **stavku** Podešavanje na pločici Dun & Bradstreet.

1. Izaberite **Prvi koraci**.

1. Unesite naziv veze u polje **Ime za prikaz**.

1. Obezbedite važeće Dun & Bradstreet akreditive i Dun & Bradstreet detalje projekta *Region, Drop putanja fascikle i ime Drop fascikle*. Ovu [informaciju dobijate](#setting-up-your-dun--bradstreet-project) iz projekta Dun & Bradstreet.

1. Pregledajte i dajte saglasnost za **Privatnost podataka i usklađenost** izborom opcije **Slažem se**.

1. Izaberite **Verifikuj** da biste proverili valjanost konfiguracije.

1. Po završetku verifikacije, izaberite **Sačuvaj**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet konekcija konekcija.":::

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Nakon osvežavanja obogaćivanja, možete pregledati novo obogaćene podatke kompanije u delu [Moja obogaćenja](enrichment-hub.md). Možete pronaći vreme poslednjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite prenos Dynamics 365 Customer Insights podataka u Dun & Bradstreet, dozvoljavate prenos podataka izvan granice usaglašenosti za, uključujući Dynamics 365 Customer Insights potencijalno osetljive podatke kao što su Lični podaci. Microsoft će preneti takve podatke po vašem uputstvu, ali vi ste odgovorni za to da obezbedite da Dun & Bradstreet ispuni sve obaveze privatnosti ili bezbednosti koje možda imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.

[!INCLUDE[footer-include](includes/footer-banner.md)]
