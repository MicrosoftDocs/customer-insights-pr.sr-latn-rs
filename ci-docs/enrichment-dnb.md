---
title: Obogatite profile kompanije sa Dun & Bradstreet (pregled)
description: Opšte informacije o obogaćivanju treće strane Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 51f2e4e46aa25d10502d0feb5ea42eb7d2d637b9
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082561"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Obogatite profile kompanije sa Dun & Bradstreet (pregled)

Dun & Bradstreet pruža komercijalne podatke, analitiku i uvide za preduzeća. Omogućuje klijentima sa objedinjenim profilima klijenata za kompanije da obogaćuju svoje podatke. Obogaćivanje uključuje atribute kao što su DUNS broj, veličina kompanije, lokacija, industrija i još mnogo toga.

## <a name="prerequisites"></a>Preduslovi

- Aktivna [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) licenca.
- [Objedinjeni profili klijenata](customer-profiles.md) za preduzeća.
- Postavljen je Dun & Bradstreet [projekat](#set-up-your-dun--bradstreet-project).
- Dun & Bradstreet [vezu](connections.md)[je konfigurisao](#configure-a-connection-for-dun--bradstreet) administrator.

## <a name="set-up-your-dun--bradstreet-project"></a>Postavite svoj Dun & Bradstreet projekat

Kao licencirani korisnik Dun & Bradstreet, projekat možete podesiti u [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Prijavite se na [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Vratite lozinku u prethodno stanje da [biste preuzeli akreditive](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Preuzmite [naš csv template fajl](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) koji će se koristiti za mapiranje polja Customer Insights u odgovarajuća polja Dun & Bradstreet.

1. Upload the file in the **Upload data** step of the Dun & Bradstreet project creation experience.

1. Izaberite horizontalne tačke ispod relevantnog izvora **u** novokreiranom projektu Dun & Bradstreet da biste videli dostupne opcije.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Screenshot of dots in a Dun & Bradstreet project.":::

1. Odaberite **stavku Nabavi S3 detalje**. Uskladištite ove informacije na bezbedno mesto. Biće vam potreban da biste podesili [vezu za bogaćenje u uvidima](#configure-a-connection-for-dun--bradstreet) kupaca.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Screenshot izbora s3 informacija u Dun & Bradstreet projektu.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigurišite vezu za Dun & Bradstreet

Morate biti administrator u [Customer](permissions.md#admin) Insights i imati akreditive od Dun & Bradstreet Connect.

1. Izaberite **Dodaj vezu** prilikom konfigurisanja obogaćenja ili idite na **administrativne** > **veze i** izaberite **stavku** Podešavanje na pločici Dun & Bradstreet.

1. Unesite ime za vezu.

1. Obezbedite važeće Dun & Bradstreet akreditive i Dun & Bradstreet detalje projekta *Region, Drop putanja fascikle i ime Drop fascikle*. Ovu [informaciju dobijate](#set-up-your-dun--bradstreet-project) iz projekta Dun & Bradstreet.

1. Pregledajte i dajte saglasnost za [Privatnost podataka i usklađenost](#data-privacy-and-compliance) izborom opcije **Slažem se**.

1. Izaberite **opciju** Proveri da biste proverili valjanost konfiguracije, a zatim kliknite na dugme **Sačuvaj**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet konekcija konekcija.":::

### <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite prenos Dynamics 365 Customer Insights podataka u Dun & Bradstreet, dozvoljavate prenos podataka izvan granice usaglašenosti za, uključujući Dynamics 365 Customer Insights potencijalno osetljive podatke kao što su Lični podaci. Microsoft će preneti takve podatke po vašem uputstvu, ali vi ste odgovorni za to da obezbedite da Dun & Bradstreet ispuni sve obaveze privatnosti ili bezbednosti koje možda imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.

## <a name="supported-countries-or-regions"></a>Podržane zemlje ili regioni

Trenutno podržavamo sledeće opcije zemlje/regiona: Kanada (engleski) ili Sjedinjene Države (engleski).

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.

1. Izaberite **Obogati moje podatke** o **podacima kompanije** za Dun & Bradstreet pločicu.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Screenshot of the Dun & Bradstreet pločica.":::

1. Pregledajte pregled, a zatim kliknite na dugme **Dalje**.

1. Izaberite vezu i potvrdite. Obratite se administratoru ako nije dostupan.

1. Izaberite **Sledeće**.

1. Izaberite opciju **Skup podataka i** odaberite profil ili segment koji želite da obogatite podacima kompanije iz dun & bradstreet. Entitet *kupca* obogaćuje sve profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

1. Definišite koji tip polja iz vaših objedinjenih profila treba koristiti za podudaranje podataka kompanije iz dun & bradstreet. Obavezno je barem jedno od polja **Ime i adresa**, **Telefon** ili **E-pošta**.

1. Izaberite **Sledeće**

1. Mapirajte svoja polja na podatke kompanije iz Dun & Bradstreet. Broj **DUNS-a** ili **polja "Ime preduzeća** **" i** "Zemlja" su obavezni.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet okno za mapiranje polja.":::

1. Izaberite **Sledeće** da biste dovršili mapiranje polja.

1. Navedite **ime** za bogaćenje i ime **entiteta izlaza**.

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

1. Kliknite **na dugme** "Pokreni" da biste započeli proces obogaćivanja ili blizu da biste se vratili na stranicu **"Obogaćivanje** ".

## <a name="view-enrichment-results"></a>Prikaži rezultate obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
