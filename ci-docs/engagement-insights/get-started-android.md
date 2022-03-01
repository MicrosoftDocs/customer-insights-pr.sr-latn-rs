---
title: Prvi koraci sa Android SDK-om
description: Saznajte kako da personalizujete i pokrenete Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c678c2dafbb77926269b5602bca363c678ec6b3f
ms.sourcegitcommit: ef823f3d7fa28d3a90cfde9409be9465ffa2cf09
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/19/2021
ms.locfileid: "7655359"
---
# <a name="get-started-with-the-android-sdk"></a>Prvi koraci u Android SDK-u

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ovo uputstvo vas vodi kroz proces instrumenata vaše Android aplikacije sa Dynamics 365 Customer Insights uvidom UDK. Događaje na portalu počećete da vidite za pet minuta ili pre.

## <a name="configuration-options"></a>Opcije konfiguracije
Sledeće opcije konfiguracije mogu se proslediti SDK-u:

- **ingestionKey**: Ključ za unos koji se koristi za slanje događaja u vaš radni prostor.

## <a name="prerequisites"></a>Preduslovi

- Android Studio

- Minimalni Android API nivo: 16 (Jelly Bean)

- Ključ za unos (pogledajte u nastavku uputstvo za dobijanje)

## <a name="integrate-the-sdk-into-your-application"></a>Integrišite SDK u svoju aplikaciju
Započnite proces izborom radnog prostora, izborom Android mobilne platforme i preuzimanjem Android SDK- a.

- Koristite preklopnik radnog prostora u levom oknu za navigaciju da biste izabrali radni prostor.

- Ako nemate postojeći radni prostor, izaberite **Novi radni prostor** i sledite korake da kreirate [novi radni prostor](create-workspace.md).

- Kada kreirate radni prostor, idite na **Administrator** > **Radni prostor**, a zatim izaberite **Vodič za instalaciju**.

## <a name="configure-the-sdk"></a>Konfigurisanje SDK

Kada preuzmete SDK, možete da radite sa njim u Android Studio biste omogućili i definisali događaje. Postoje dva načina da to uradite:
### <a name="option-1-use-jitpack-recommended"></a>Opcija 1: Koristite JitPack (preporučuje se)
1. Dodajte JitPack spremište svom korenu `build.gradle`:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Dodajte zavisnost:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>Opcija 2: Korišćenje veze za preuzimanje
1. Preuzmite [uvide o Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) i stavite `eiandroidsdk-debug.aar` datoteku u `libs` fasciklu.

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

## <a name="enable-auto-instrumentation"></a>Omogućavanje automatskog opremanja

1. Dodajte dozvolu za mrežu i internet u svoju `AndroidManifest.xml` datoteku koja se nalazi u fascikli `manifests`.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Podesite konfiguraciju SDK za uvide u angažovanje putem vaše datoteke `AndroidManifest.xml`.

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

   >[!NOTE]
   >`Action` događaje treba dodati ručno.

1. (Opcionalno) Ostale konfiguracije uključuju podešavanje URL adrese sakupljača krajnjih tačaka. Oni se mogu dodati ispod metapodataka ključa za ingestion u programu `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Primena prilagođenih događaja

Kada pokrenete SDK, možete raditi sa događajima i njihovim svojstvima u `MainActivity` okruženju.


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

## <a name="set-user-details-for-your-event-optional"></a>Podesite korisničke detalje za događaj (opcionalno)

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
