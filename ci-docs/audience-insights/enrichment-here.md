---
title: Obogaćivanje putem nezavisnog obogaćivanja HERE Technologies
description: Opšte informacije o HERE Technologies obogaćivanju treće strane.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 61fba6bbf9d33ee8d9c725133f0f7f304c1ca79e
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618492"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Obogaćivanje profila klijenata uz HERE Technologies (verzija za pregled)

verzija za pregled je kompanija za platformu lokacije koja pruža podatke i usluge usmerene na lokaciju. Pomoću usluga obogaćivanja podataka kompanije HERE Technologies možete da izgradite preciznije razumevanje lokacije svojih klijenata pomoću normalizacije adresa, izdvajanja geografske širine i dužine i još mnogo toga.

## <a name="prerequisites"></a>Preduslovi

Da biste konfigurisali verzija za pregled obogaćivanja, moraju biti ispunjeni sledeći preduslovi:

- Morate imati aktivnu pretplatu za HERE Technologies. Da biste dobili pretplatu, možete [da se registrujete ovde](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ili direktno [kontaktirajte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Saznajte više o HERE Technologies obogaćivanju lokacije.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [veza](connections.md) je dostupna *ili* imate dozvole [administratora](permissions.md#administrator) i HERE Technologies API ključ.

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite na **Podaci** > **Obogaćivanje**. 

1. Izaberite **Obogati moje podatke** na pločici HERE Technologies i izaberite **Započni**.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies pločica.](media/HERE-tile.png "HERE Technologies pločica")

1. Izaberite [vezu](connections.md) sa padajuće liste. Ako veza nije dostupna, obratite se administratoru. Ako ste administrator, vezu možete da napravite izborom **Dodaj vezu**. Odaberite **HERE Technologies** sa padajuće liste. 

1. Izaberite **Povežite se sa HERE Technologies** da potvrdite izbor.

1.  Izaberite **Sledeće** i odaberite **Skup podataka klijenta** koji želite da obogatite sa podacima o lokaciji kompanije HERE Technologies. Možete izabrati entitet **Klijent** da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Snimak ekrana prilikom odabira skupa podataka o klijentima.":::

1. Odaberite da li želite da mapirate polja sa primarnom i/ili sekundarnom adresom. Možete odrediti mapiranje polja za obe adrese i obogatiti profile za obe adrese zasebno. Na primer, ako postoje kućna i poslovna adresa. Izaberite **Sledeće**.

1. Definišite koja polja iz vaših objedinjenih profila treba koristiti za podudaranje podataka o lokaciji od kompanije HERE Technologies. Polja **Ulica 1** i **Poštanski broj** su obavezna za odabranu primarnu i/ili sekundarnu adresu. Za veću preciznost podudaranja može se dodati više polja.

   > [!div class="mx-imgBorder"]
   > ![Stranica za konfiguraciju HERE Technologies obogaćivanja.](media/enrichment-HERE-configuration.png "Stranica za konfiguraciju HERE Technologies obogaćivanja")

1. Izaberite **Sledeće** da biste dovršili mapiranje polja.

1. Navedite naziv obogaćivanja. 

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurišite vezu za HERE Technologies 

Morate biti administrator da biste konfigurisali veze. Izaberite **Dodaj vezu** prilikom konfigurisanja obogaćivanja *ili* idite na **Administrator** > **Veze** i izaberite **Podešavanje** na pločici HERE Technologies.

1. Unesite naziv veze u polje **Ime za prikaz**.

1. Navedite važeći HERE Technologies API ključ.

1. Pregledajte i dajte saglasnost za **Privatnost podataka i usklađenost** izborom opcije **Slažem se**.

1. Izaberite **Verifikuj** da biste proverili valjanost konfiguracije.

1. Po završetku verifikacije, izaberite **Sačuvaj**.

   > [!div class="mx-imgBorder"]
   > ![Stranica za konfiguraciju veze za HERE Technologies.](media/enrichment-HERE-connection.png "Stranica za konfiguraciju veze za HERE Technologies")

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake. Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab). Vreme obrade zavisiće od veličine podataka o klijentima i vremena odziva API-ja kompanije HERE Technologies.

Nakon završetka procesa obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod opcijom **Moja obogaćivanja**. Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u HERE Technologies, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da HERE Technologies ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
