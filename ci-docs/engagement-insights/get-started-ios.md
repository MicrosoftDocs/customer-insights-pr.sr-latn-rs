---
title: Početni koraci u radu sa iOS SDK
description: Saznajte kako da personalizujete i pokrenete iOS SDK
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 879a71175a2e7d44a54d25fd8efb9f12927cea5a
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977540"
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

- Kada kreirate radni prostor, idite na **Administrator** > **Radni prostor** a zatim izaberite **Vodič za instalaciju**.

## <a name="configure-the-sdk"></a>Konfigurisanje SDK

Kada preuzmete SDK, možete raditi s njim na platformi Xcode da biste omogućili i definisali događaje. Postoje dva načina da to uradite

### <a name="option-1-using-cocoapods-recommended"></a>1. opcija: Korišćenje CocoaPods (preporučeno)
CocoaPods je menadžer zavisnosti za Swift i Objective-C Cocoa projekte. NJegova upotreba olakšava integraciju SDK-a za uvide u angažovanje za iOS. CocoaPods vam takođe omogućava nadogradnju na najnoviju verziju SDK-a za uvide u angažovanje. Evo kako se koristi CocoaPods za integraciju SDK za uvide u angažovanje u vašem Xcode projektu. 

1. Instalirajte CocoaPods. 

1. Kreirajte novu datoteku pod nazivom Podfile unutar osnovnog direktorijuma vašeg projekta i dodajte joj sledeće izjave. Zamenite NAZIV_VAŠEG_CILJNOG_PROJEKTA nazivom vašeg Xcode projekta. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
Gorenavedena pod konfiguracija sadrži verzije za otklanjanje grešaka i verziju izdanja SDK-a. Odaberite ono što je najbolje za vaš projekat.

1. Instalirajte pod izvršavanjem sledeće komande: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>2. opcija: Korišćenje veze za preuzimanje

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
