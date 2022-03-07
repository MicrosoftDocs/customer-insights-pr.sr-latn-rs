---
title: Napredni veb SDK scenariji
description: Napredni scenariji koje treba uzeti u obzir prilikom opremanja veb-lokacije pomoću SDK-a.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227215"
---
# <a name="advanced-web-sdk-instrumentation"></a>Napredno veb SDK opremanje

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ovaj članak vas vodi kroz napredne scenarije koje treba razmotriti kada [opremate vašu veb-lokaciju](instrument-website.md) sa SDK-om Dynamics 365 Customer Insights mogućnosti uvida u angažovanje.

## <a name="setting-user-details-for-your-event"></a>Podešavanje detalja o korisniku za vaš događaj

SDK vam omogućava da definišete informacije o korisniku koje možete poslati uz svaki događaj. Možete navesti detalje o korisniku u svojstvu koje pod nazivom `user` (očekivani podaci za ovo svojstvo su objekat `IUser`), slično kao `src`,`name` i `cfg` u konfiguraciji isečka koda.

Objekat `IUser` sadrži sledeća svojstva niza:

- **localId**: lokalni ID korisnika.
- **authId**: ID korisnika sa potvrđenim identitetom.
- **authType**: tip potvrde identiteta koji se koristi za dobijanje ID-a korisnika sa potvrđenim identitetom.
- **name**: ime korisnika.
- **email**: adresa e-pošte korisnika.

Sledeći primer prikazuje isečak koda koji šalje informacije o korisniku. Tamo gde vidite funkcije kojima prethodi simbol zvezdice *, zamenite funkciju prilagođenom primenom:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Korisničke podatke možete navesti i pozivanjem `setUser(user: IUser)` API-ja. Telemetrija poslata nakon pozivanja `setUser` API-ja sadržaće informacije o korisniku.

## <a name="adding-custom-properties-for-each-event"></a>Dodavanje prilagođenih svojstava za svaki događaj

SDK vam omogućava da navedete prilagođena svojstva koja možete poslati uz svaki događaj. Možete odrediti prilagođena svojstva kao objekat koji sadrži parove ključ/vrednost (vrednost može biti tipa `string | number | boolean`). Objekat možete dodati u svojstvo koje se zove `props`, slično kao i `src`, `name` i `cfg` u konfiguraciji fragmenta koda.

Sledeći primer prikazuje isečak koda koji šalje prilagođena svojstva:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Prilagođena svojstva možete navesti pojedinačno i pozivanjem `setProperty(name: string, value: string | number | boolean)` API-ja.

## <a name="sending-custom-events"></a>Slanje prilagođenih događaja

SDK možete da koristite za slanje prilagođenih događaja. Morate navesti naziv događaja i svojstva koja će biti poslata uz događaj.

Sledeći primer prikazuje isečak koda koji prati prilagođeni događaj. „NAZIV“ je vrednost u `name` ključu u konfiguraciji isečka koda. To je takođe naziv promenljive u objektu prozora u koji se učitava SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
