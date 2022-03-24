---
title: Obogatite profile klijenata podacima o lokaciji iz programa Azure Maps
description: Opšte informacije o Azure Maps direktnom obogaćivanju.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 2cc44f7b453d2aca328c397b14787c8a02c5e490
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376663"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Obogaćivanje profila klijenata uz Azure Maps (verzija za pregled)

Azure Maps pruža podatke i usluge usredsređene na lokaciju kako bi pružio iskustva zasnovana na prostornim podacima sa ugrađenim obaveštavanjem o lokaciji. Usluge Azure Maps obogaćivanja podataka poboljšavaju preciznost informacija o lokaciji vaših klijenata. One donose mogućnosti poput normalizacije adresa i ekstrakcije geografske širine i dužine u uslugu Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Preduslovi

Da biste konfigurisali Azure Maps obogaćivanje podataka, moraju biti ispunjeni sledeći preduslovi:

- Imate aktivnu pretplatu na Azure Maps. Da biste dobili pretplatu, možete da se [registrujete ili dobijete besplatnu probnu verziju](https://azure.microsoft.com/services/azure-maps/).

- Azure Maps [veza](connections.md) je dostupna *ili* imate dozvolu [Administratora](permissions.md#admin) i aktivni Azure Maps API ključ.

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite na **Podaci** > **Obogaćivanje**. 

1. Na pločici **Lokacija** izaberite **Obogati moje podatke**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps pločica.":::

1. Izaberite [vezu](connections.md) sa padajuće liste. Obratite se administratoru ako nije dostupna veza sa uslugom Azure Maps. Ako ste administrator, možete da [konfigurišete vezu za Azure Maps](#configure-the-connection-for-azure-maps). 

1. Izaberite **Sledeće** da biste potvrdili izbor.

1. Odaberite **Skup podataka o klijentima** koji želite da obogatite sa podacima o lokaciji iz usluge Azure Maps. Možete da izaberete entitet **Klijent** za obogaćivanje svih vaših objedinjenih profila klijenata ili da izaberete entitet segmenta za obogaćivanje samo profila klijenata sadržanih u tom segmentu.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Snimak ekrana pri izboru skupa podataka o klijentima.":::

1. Odaberite želite li da mapirate polja na primarnu i/ili sekundarnu adresu. Možete navesti mapiranje polja za obe adrese i zasebno obogatiti profile za obe adrese – na primer, za kućnu adresu i poslovnu adresu. Izaberite **Sledeće**.

1. Definišite koja polja iz vaših objedinjenih profila da koristite za podudaranje podataka o lokaciji iz usluge Azure Maps. Polja **Ulica 1** i **Poštanski broj** su obavezna za izabranu primarnu i sekundarnu adresu. Za veću preciznost podudaranja, možete dodati još polja.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Stranica za konfiguraciju obogaćivanja uslugom Azure Maps.":::

1. Izaberite **Sledeće** da biste dovršili mapiranje polja.

1. Procenite da li želite da izmenite **Napredna podešavanja**. Ona su obezbeđena da pruže maksimalnu fleksibilnost u radu sa naprednim slučajevima upotrebe, ali podrazumevane vrednosti će u većini slučajeva biti odgovarajuće:
   - **Tip adresa**: podrazumevano ponašanje je da će obogaćivanje vratiti najbolje podudaranje adrese čak i ako je nepotpuno. Da biste dobili samo potpune adrese – na primer, adrese koje uključuju kućni broj – obrišite sva polja za potvrdu osim **Adrese tačaka**. 
   - **Jezik**: podrazumevano se adrese vraćaju na jeziku za region za koji je utvrđeno da pripada. Da biste primenili standardizovani jezik adrese, izaberite jezik iz padajućeg menija. Na primer, ako izaberete **Engleski** vratiće **Copenhagen, Denmark** umesto **København, Danmark**.

1. Navedite naziv obogaćivanja.

1. Pregledajte izbore, a zatim izaberite **Sačuvaj obogaćivanje**.

## <a name="configure-the-connection-for-azure-maps"></a>Konfigurišite vezu za Azure Maps

Morate biti administrator u uvidima u ciljnu grupu da biste konfigurisali veze. Izaberite **Dodaj vezu** kada konfigurišete obogaćivanje ili idite na **Administrator** > **Veze** i izaberite **Podesi** na pločici Azure Maps.

1. U polje **Ime za prikaz**, unesite naziv veze.

1. Navedite važeći Azure Maps API ključ.

1. Pregledajte i dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**

1. Izaberite **Verifikuj** da biste proverili valjanost konfiguracije.

1. Po završetku verifikacije, izaberite **Sačuvaj**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Stranica za konfiguraciju veze sa uslugom Azure Maps.":::

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake. Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab). Vreme obrade će zavisiti od veličine vaših podataka o klijentu i vremena odgovora API-ja.

Nakon završetka procesa obogaćivanja, možete pregledati podatke o novoobogaćenim profilima klijenata u okviru opcije **Moja obogaćivanja**. Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite Dynamics 365 Customer Insights za prenos podataka u Azure Maps, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Azure Maps ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za još informacija posetite članak [Microsoft izjava o privatnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
