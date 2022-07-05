---
title: Obogatite profile klijenata podaci o lokaciji Azure mape (pregled)
description: Opšte informacije o Azure Maps direktnom obogaćivanju.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: dfadc08f67beac3fded1a97e557ee9e1880664e0
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052624"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Obogatite profile klijenata podaci o lokaciji Azure mape (pregled)

Azure mape obezbeđuju lokacijsko-centrične podatke i usluge za pružanje iskustava na osnovu geospatialnih podataka sa ugrađenom lokacijskom inteligencijom. Usluge Azure Maps obogaćivanja podataka poboljšavaju preciznost informacija o lokaciji vaših klijenata. One donose mogućnosti poput normalizacije adresa i ekstrakcije geografske širine i dužine u uslugu Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Preduslovi

- Aktivna pretplata na Azure mape. Da biste dobili pretplatu, prijavite [se ili dobijte besplatnu probnu godinu](https://azure.microsoft.com/services/azure-maps/).

- Azure mape [vezu](connections.md) [je konfigurisao](#configure-the-connection-for-azure-maps) administrator.

## <a name="configure-the-connection-for-azure-maps"></a>Konfigurišite vezu za Azure Maps

Morate biti administrator u " [Uvidima](permissions.md#admin) klijenata" i imati aktivni API ključ za Azure mape.

1. Izaberite **Dodaj vezu** kada konfigurišete obogaćivanje ili idite na **Administrator** > **Veze** i izaberite **Podesi** na pločici Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Stranica za konfiguraciju veze sa uslugom Azure Maps.":::

1. Unesite ime za vezu i važeći API ključ Azure mape.

1. Pregledajte i dajte saglasnost za [Privatnost podataka i usklađenost](#data-privacy-and-compliance) izborom opcije **Slažem se**.

1. Izaberite **opciju** Proveri da biste proverili valjanost konfiguracije, a zatim kliknite na dugme **Sačuvaj**.

### <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite Dynamics 365 Customer Insights za prenos podataka u Azure Maps, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će preneti takve podatke na vaše uputstvo, ali vi ste odgovorni za to da obezbedite da Azure mape ispunjavaju sve obaveze privatnosti ili bezbednosti koje možda imate. Za još informacija posetite članak [Microsoft izjava o privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.

1. Izaberite **stavku Obogati moje podatke** na pločici **"Lokacija** iz Microsoft Azure mapa".

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps pločica.":::

1. Pregledajte pregled, a zatim kliknite na dugme **Dalje**.

1. Izaberite vezu. Ako veza nije dostupna, obratite se administratoru.

1. Izaberite **Sledeće**.

1. Izaberite opciju **Skup podataka i odaberite** profil ili segment koji želite da obogatite podacima korporacije Microsoft. Entitet *kupca* obogaćuje sve profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

1. Definišite tip polja iz objedinjenih profila koja ćete koristiti za podudaranje: primarnu i/ili sekundarnu adresu. Možete odrediti mapiranje polja za obe adrese i obogatiti profile za obe adrese zasebno. Na primer, za kućnu adresu i poslovnu adresu. Izaberite **Sledeće**.

1. Mapirajte polja na podaci o lokaciji Azure mape. Polja **Ulica 1** i **Poštanski broj** su obavezna za odabranu primarnu i/ili sekundarnu adresu. Za veću tačnost podudaranja dodajte još polja.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Mapiranje atributa Azure mape.":::

1. Izaberite **Sledeće** da biste dovršili mapiranje polja.

1. Pregledajte **više opcija za** postavke koje nude maksimalnu fleksibilnost za rukovanje predmetima napredne upotrebe. Međutim, sledeće podrazumevane vrednosti obično ne moraju da se menjaju.

   - **Tip adresa: najbolje podudaranje** adresa se vraća čak i ako je nepotpuno. Da biste dobili samo potpune adrese – na primer, adrese koje uključuju kućni broj – obrišite sva polja za potvrdu osim **Adrese tačaka**.
   - **Jezik**: Adrese se vraćaju na jezik zasnovan na oblasti adresa. Da biste primenili standardizovani jezik adrese, izaberite jezik iz padajućeg menija. Na primer, izbor engleskog **jezika** vraća **Kopenhagen, Dansku** umesto **København, Danmark**.
   - **Maksimalan broj rezultata**: broj rezultata po adresi.

1. Izaberite **Sledeće**.

1. Navedite **ime** za bogaćenje i ime **entiteta izlaza**.

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

1. Kliknite **na dugme** "Pokreni" da biste započeli proces obogaćivanja ili blizu da biste se vratili na stranicu **"Obogaćivanje** ".

## <a name="view-enrichment-results"></a>Prikaži rezultate obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Broj **kupaca obogaćenih poljem obezbeđuje** dubinsku analizu pokrivenosti svakog obogaćenog polja.

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]