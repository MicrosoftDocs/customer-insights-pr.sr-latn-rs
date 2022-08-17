---
title: Obogaćivanje profila preduzeća pomoću programa Leadspace (pregled)
description: Opšte informacije o Leadspace obogaćivanju treće strane.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f45fabc036775e11fc439f69513678d0607729d0
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237967"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Obogaćivanje profila preduzeća pomoću programa Leadspace (pregled)

Leadspace je kompanija koja se bavi naukom o podacima koja pruža B-to-B platformu sa podacima klijenata. Omogućava okruženjima sa objedinjenim profilima klijenata na osnovu poslovnih kontakata da obogate svoje podatke. Obogatite *Profile klijenata* sa atributima kao što su veličina kompanije, lokacija ili delatnost. Obogatite *Profili kontakata* sa atributima kao što su titula, funkcija ili e-pošta za verifikaciju.

## <a name="prerequisites"></a>Preduslovi

- Aktivna licenca potencijalnog klijenta.
- [Objedinjeni profili klijenata](customer-profiles.md) zasnovani na nalozima.
- Administrator konfiguriše [vezu](connections.md) [potencijalnog](#configure-the-connection-for-leadspace) klijenta. Kontaktirajte [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) direktno da biste saznali detalje o njihovom proizvodu.

## <a name="configure-the-connection-for-leadspace"></a>Konfigurišite vezu za Leadspace

Morate biti administrator u [uvidima](permissions.md#admin) klijenata i imati "večiti ključ" (naziva se oznaka potencijalnog **prostora**).

1. Izaberite **opciju Dodaj** vezu prilikom konfigurisanja obogaćenja ili idite na **administratorske** > **veze i** izaberite stavku **Podešavanje na** pločici "Glavni prostor".

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Stranica za konfiguraciju veze za Leadspace.":::

1. Unesite ime za vezu i važeći oznaku potencijalnog prostora.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Izaberite **opciju** Proveri da biste proverili valjanost konfiguracije, a zatim kliknite na dugme **Sačuvaj**.

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.

1. Izaberite **obogati moje podatke** na podacima **kompanije sa** pločice "Glavni prostor".

   :::image type="content" source="media/leadspace-tile.png" alt-text="Snimak ekrana Leadspace pločice.":::

1. Pregledajte pregled, a zatim kliknite na dugme **Dalje**.

1. Izaberite vezu. Ako veza nije dostupna, obratite se administratoru.

1. Izaberite **Sledeće**.

1. Izaberite opciju **Skup podataka i odaberite** profil ili segment koji želite da obogatite podacima preduzeća iz programa Leadspace. Entitet *kupca* obogaćuje sve profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Snimak ekrana prilikom odabira skupa podataka o klijentima.":::

1. Definišite tip polja iz objedinjenih profila koja ćete koristiti za podudaranje: primarnu i/ili sekundarnu adresu. Možete odrediti mapiranje polja za obe adrese i obogatiti profile za obe adrese zasebno. Na primer, za kućnu adresu i poslovnu adresu. Izaberite **Sledeće**.

1. Mapirajte polja na podatke preduzeća iz prostora potencijalnog klijenta. Polje **Ime kompanije** je obavezno. Za veću preciznost podudaranja, do dva druga polja, **Veb-lokacija kompanije** i **Lokacija kompanije**, mogu se dodati.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Okno za mapiranje polja Leadspace.":::

1. Izaberite **Sledeće** da biste dovršili mapiranje polja.

1. Izaberite polje za potvrdu ako imate *Profili kontakata* koje biste želeli da obogatite. Uvidi kupaca će automatski mapirati potrebna polja.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Obogaćivanje zapisa o kontaktima u usluzi Leadspace.":::

1. Izaberite **Sledeće**.

1. Navedite **ime** za bogaćenje i ime **entiteta izlaza**.

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

1. Kliknite **na dugme** "Pokreni" da biste započeli proces obogaćivanja ili blizu da biste se vratili na stranicu **"Obogaćivanje** ".

## <a name="view-enrichment-results"></a>Prikaži rezultate obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Više informacija potražite u članku [Leadspace API-ji](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
