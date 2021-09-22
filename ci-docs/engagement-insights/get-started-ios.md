---
title: Početni koraci u radu sa iOS SDK
description: Saznajte kako da personalizujete i pokrenete iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036890"
---
# <a name="get-started-with-the-ios-sdk"></a>Početni koraci u radu sa iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ovo uputstvo vas vodi kroz proces opremanja iOS aplikacije sa Dynamics 365 Customer Insights SDK za uvide u angažovanje. Događaje na portalu počećete da vidite za pet minuta ili pre.

## <a name="configuration-options"></a>Opcije konfiguracije

Sledeće opcije konfiguracije mogu se proslediti SDK-u putem obezbeđene `EIConfig.plist` datoteke:

- **ingestionKey**: Ključ za unos koji se koristi za slanje događaja u vaš projekat.
- **autocollectAction**: Logička vrednost za omogućavanje ili onemogućavanje automatskog opremanja događaja radnje.
- **autocollectView**: Logička vrednost za omogućavanje ili onemogućavanje automatskog opremanja događaja prikaza.
- **endpointUrl**: URL adresa krajnje tačke na koju će događaji biti usmereni.

## <a name="prerequisites"></a>Preduslovi

- Xcode verzije 9+
- iOS verzije 8.2+
- Ključ za unos (pogledajte uputstva u nastavku za dobijanje)

## <a name="integrate-the-sdk-into-your-application"></a>Integrišite SDK u svoju aplikaciju

Započnite postupak odabirom radnog prostora u kojem ćete raditi, odabirom iOS mobilne platforme i preuzimanjem SDK.

- Koristite preklopnik radnog prostora u levom oknu za navigaciju da biste izabrali radni prostor.

- Ako nemate postojeći radni prostor, izaberite **Novi radni prostor** i sledite korake da kreirate [novi radni prostor](create-workspace.md).

## <a name="configure-the-sdk"></a>Konfigurisanje SDK

Kada preuzmete SDK, možete raditi s njim na platformi Xcode da biste omogućili i definisali događaje.

1. Kada kreirate radni prostor, idite na **Administrator** > **Radni prostor** a zatim izaberite **Vodič za instalaciju**.

1. Preuzmite [iOS SDK uvide u angažovanje](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) i postavite datoteku `EIObjC.xcframework` u fasciklu `Frameworks`.

1. Ako fascikla `Frameworks` ne postoji, napravite je u fascikli projekta.

## <a name="enable-auto-instrumentation"></a>Omogućavanje automatskog opremanja
 
Možete lako omogućiti automatsko opremanje bez kodiranja. Kada se projekat pokrene, automatski će pratiti događaje `view` i `action` pomoću konfigurisanog ključa za unos. 

1. Ažurirajte i uključite obezbeđenu datoteku `EIConfig.plist` u fascikli direktorijuma projekta za sledeća polja:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = DA
    - autocollectAction = DA

2. Zatim dodajte datoteku `EIConfig.plist` u svoj projekat na platformi Xcode. 



Da biste onemogućili automatsko opremanje, u obuhvaćenoj datoteci `EIConfig.plist` u fascikli direktorijuma projekta ažurirajte sledeća polja: 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Primena prilagođenih događaja

1. Otvorite projekat u platformi Xcode i idite na podešavanja **Opšti podaci**. 
1. Dodajte `EIObjC.xcframework` projektu u odeljku „Radni okviri, biblioteke i ugrađeni sadržaj“.

1. Uvezite datoteku zaglavlja okvira u AppDelegate.m sa sledećim isečkom:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Pokrenite SDK za uvide u angažovanje iz aplikacije: didFinishLaunchingWithOptions.
1. Kopirajte XML isečak iz **vodiča za instalaciju**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Praćenje događaja:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Podesite korisničke detalje za događaj

SDK vam omogućava da definišete informacije o korisniku koje možete poslati uz svaki događaj. Informacije o korisniku možete odrediti pozivanjem `setUser:(nonnull EIUser *)user` API-ja na SDK-u.

Navođenje korisničkih detalja na nivou `Analytics` znači da će sve telemetrije imati ove informacije. Međutim, ako navedete na nivou događaja pozivanjem `setUser:(nonnull EIUser *)user` API-ja na objektu EIEvent, samo će taj određeni događaj sadržati informacije.

Klasa podataka `EIUser` sadrži sledeća svojstva za NSString:

- **localId**: lokalni ID korisnika.
- **authId**: ID korisnika sa potvrđenim identitetom.
- **authType**: tip potvrde identiteta koji se koristi za dobijanje ID-a korisnika sa potvrđenim identitetom.
- **name**: ime korisnika.
- **email**: adresa e-pošte korisnika.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
