---
title: Početni koraci u radu sa Android SDK
description: Saznajte kako da personalizujete i pokrenete Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036935"
---
# <a name="get-started-with-the-android-sdk"></a>Početni koraci u radu sa Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ovo uputstvo vas vodi kroz proces opremanja Android aplikacije sa Dynamics 365 Customer Insights SDK za uvide u angažovanje. Događaje na portalu počećete da vidite za pet minuta ili pre.

## <a name="configuration-options"></a>Opcije konfiguracije
Sledeće opcije konfiguracije mogu se proslediti SDK-u:

- **ingestionKey**: Ključ za unos koji se koristi za slanje događaja u vaš radni prostor.

## <a name="prerequisites"></a>Preduslovi

- Android Studio

- Minimalni nivo za Android API: 16 (Jelly Bean)

- Ključ za unos (pogledajte u nastavku uputstvo za dobijanje)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Korak 1. Integrišite SDK u svoju aplikaciju
Započnite postupak odabirom radnog prostora u, odabirom Android mobilne platforme i preuzimanjem Android SDK.

- Koristite preklopnik radnog prostora u levom oknu za navigaciju da biste izabrali radni prostor.

- Ako nemate postojeći radni prostor, izaberite **Novi radni prostor** i sledite korake da kreirate [novi radni prostor](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>Korak 2. Konfigurisanje SDK

1. Kada kreirate radni prostor, idite na **Administrator** > **Radni prostor**, a zatim izaberite **Vodič za instalaciju**. 

1. Preuzmite [Android SDK za uvide u angažovanje](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) i postavite datoteku `eiandroidsdk-debug.aar` u fasciklu `libs`.

1. Otvorite datoteku `build.gradle` na nivou projekta i dodajte sledeće isečke:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Podesite konfiguraciju SDK za uvide u angažovanje putem vaše datoteke `AndroidManifest.xml` koja se nalazi u fascikli `manifests`. 
1. Kopirajte XML isečak iz **vodiča za instalaciju**. `Your-Ingestion-Key` bi trebalo da se popuni automatski.

   > [!NOTE]
   > Ne morate da zamenite odeljak `${applicationId}`. On se popunjava automatski.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Omogućite ili onemogućite automatsko nalaženje događaja `View` podešavanjem vrednosti `true` ili `false` u gorenavedenom polju `autoCapture`.

1. (Opcionalno) Ostale konfiguracije uključuju podešavanje URL adrese sakupljača krajnjih tačaka. Mogu se dodati pod metapodacima ključa za unos u datoteci `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Korak 3. Pokretanje SDK iz MainActivity 

Kada pokrenete SDK, možete raditi sa događajima i njihovim svojstvima u MainActivity okruženju.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Podesite svojstvo za sve događaje (opcionalno)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Sledeći tipovi su podržani za svojstva događaja konteksta:
- String
- Datum
- Dvostruka vrednost
- Dugačak
- Bulov
- UUID

### <a name="track-an-event"></a>Praćenje događaja

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Podesite korisničke detalje za događaj (opcionalno)

SDK vam omogućava da definišete informacije o korisniku koje možete poslati uz svaki događaj. Informacije o korisniku možete odrediti pozivanjem `setUser(user: User)` API-ja na nivou `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Klasa podataka `User` sadrži sledeća svojstva za nisku:

- **localId**: lokalni ID korisnika.
- **authId**: ID korisnika sa potvrđenim identitetom.
- **authType**: Tip potvrde identiteta koji se koristi za dobijanje potvrđenog ID-a korisnika.
- **name**: ime korisnika.
- **email**: adresa e-pošte korisnika.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
