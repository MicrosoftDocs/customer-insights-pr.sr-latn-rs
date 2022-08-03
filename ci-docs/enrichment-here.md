---
title: Obogatite profile klijenata pomoću HERE tehnologija (pregled)
description: Opšte informacije o HERE Technologies obogaćivanju treće strane.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 26de9fce863c9832b70adf3ce39cb2ae0ce43d0e
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196273"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Obogatite profile klijenata pomoću HERE tehnologija (pregled)

verzija za pregled je kompanija za platformu lokacije koja pruža podatke i usluge usmerene na lokaciju. Usluge obogaćivanja podataka HERE tehnologije poboljšavaju preciznost informacija o lokaciji vaših klijenata. On obezbeđuje normalizaciju adrese, geografsku širinu i izvlačenje dužine i još mnogo toga.

## <a name="prerequisites"></a>Preduslovi

- Aktivna pretplata na HERE Tehnologije. Da biste dobili pretplatu, [prijavite se ovde](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ili [se direktno obratite here Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Saznajte više o HERE Technologies obogaćivanju lokacije.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [vezu](connections.md)[je konfigurisao](#configure-the-connection-for-here-technologies) administrator.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurišite vezu za HERE Technologies

Morate biti administrator u korisničkim [uvidima](permissions.md#admin) i imati aktivan API ključ HERE tehnologije.

1. Izaberite **opciju** Dodaj vezu prilikom konfigurisanja bogaćenja ili idite **na administratorske** > **veze** i izaberite **stavku** Podešavanje na pločici HERE tehnologije.

1. Unesite ime za vezu i važeći API ključ HERE tehnologije.

1. Pregledajte i dajte saglasnost za [Privatnost podataka i usklađenost](#data-privacy-and-compliance) izborom opcije **Slažem se**.

1. Izaberite **opciju** Proveri da biste proverili valjanost konfiguracije, a zatim kliknite na dugme **Sačuvaj**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Stranica za konfiguraciju veze za HERE Technologies.":::

### <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u HERE Technologies, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da HERE Technologies ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.

1. Izaberite **stavku Obogati moje podatke** na **pločici** Lokacija iz here tehnologije.

   :::image type="content" source="media/HERE-tile.png" alt-text="HERE Technologies pločica.":::

1. Pregledajte pregled, a zatim kliknite na dugme **Dalje**.

1. Izaberite vezu. Ako veza nije dostupna, obratite se administratoru.

1. Izaberite **Sledeće**.

1. Izaberite opciju **skup podataka i** odaberite profil ili segment koji želite da obogatite podacima iz here tehnologije. Entitet *kupca* obogaćuje sve profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

1. Definišite tip polja iz objedinjenih profila koja ćete koristiti za podudaranje: primarnu i/ili sekundarnu adresu. Možete odrediti mapiranje polja za obe adrese i obogatiti profile za obe adrese zasebno. Na primer, za kućnu adresu i poslovnu adresu. Izaberite **Sledeće**.

1. Mapirajte polja na podatke iz here tehnologije. Polja **Ulica 1** i **Poštanski broj** su obavezna za odabranu primarnu i/ili sekundarnu adresu. Dodajte još polja za veću tačnost podudaranja.

1. Izaberite **Sledeće** da biste dovršili mapiranje polja.

1. Navedite **ime** za bogaćenje i ime **entiteta izlaza**.

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

1. Kliknite **na dugme** "Pokreni" da biste započeli proces obogaćivanja ili blizu da biste se vratili na stranicu **"Obogaćivanje** ".

## <a name="view-enrichment-results"></a>Prikaži rezultate obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Broj **kupaca obogaćenih poljem obezbeđuje** dubinsku analizu pokrivenosti svakog obogaćenog polja.

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
