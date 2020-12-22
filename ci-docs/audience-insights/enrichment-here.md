---
title: Obogaćivanje pomoću obogaćivanja treće strane HERE Technologies
description: Opšte informacije o HERE Technologies obogaćivanju treće strane.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668695"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Obogaćivanje profila klijenata uz HERE Technologies (verzija za pregled)

verzija za pregled je kompanija za platformu lokacije koja pruža podatke i usluge usmerene na lokaciju. Pomoću usluga obogaćivanja podataka kompanije HERE Technologies možete da izgradite preciznije razumevanje lokacije svojih klijenata pomoću normalizacije adresa, izdvajanja geografske širine i dužine i još mnogo toga.

## <a name="prerequisites"></a>Preduslovi

Da biste konfigurisali verzija za pregled obogaćivanja, moraju biti ispunjeni sledeći preduslovi:

- Morate imati aktivnu pretplatu za HERE Technologies. Da biste dobili pretplatu, možete [da se registrujete ovde](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ili [kontaktirajte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direktno. [Saznajte više o HERE Technologies obogaćivanju lokacije.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Imate HERE Technologies API ključ.

- Imate [administratorske](permissions.md#administrator) dozvole.

## <a name="configuration"></a>Konfigurisanje

1. Idite na **Podaci** > **Obogaćivanje**.

1. Na HERE Technologies pločici izaberite **Obogati moje podatke**.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies pločica](media/HERE-tile.png "HERE Technologies pločica")

1. Unesite aktivan **HERE Technologies API ključ**. Pregledajte i dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**. 

1. Potvrdite oba ulaza izborom opcije **Povežite se na HERE**.

1. Izaberite **Dodajte podatke** i odaberite da li želite da mapirate polja sa primarnom i/ili sekundarnom adresom. Možete da navedete mapiranje polja za obe adrese (na primer, kućnu i poslovnu adresu) i zasebno obogatiti profile za obe adrese. Izaberite **Sledeće**.

1. Definišite koja polja iz vaših objedinjenih profila treba koristiti za podudaranje podataka o lokaciji od kompanije HERE Technologies. Polja **Ulica 1** i **Poštanski broj** su obavezna za odabranu primarnu i/ili sekundarnu adresu. Za veću preciznost podudaranja može se dodati više polja.

   > [!div class="mx-imgBorder"]
   > ![Stranica za konfiguraciju HERE Technologies obogaćivanja](media/enrichment-HERE-configuration.png "Stranica za konfiguraciju HERE Technologies obogaćivanja")

1. Izaberite **Primeni** da dovršite mapiranje polja.

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake. Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab). Vreme obrade zavisiće od veličine podataka o klijentima i vremena odziva API-ja kompanije HERE Technologies.

Nakon završetka procesa obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod opcijom **Moja obogaćivanja**. Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.

## <a name="next-steps"></a>Sledeći koraci

Nadogradite na obogaćenim podacima o klijentima. Kreirajte [segmente](segments.md), [mere](measures.md), pa čak i [izvezite podatke](export-destinations.md) da biste pružili personalizovana iskustva svojim klijentima.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u HERE Technologies, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da HERE Technologies ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.
