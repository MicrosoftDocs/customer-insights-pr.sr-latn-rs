---
title: Android SDK primer
description: Primer projekta za upoznavanje platforme Android SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229935"
---
# <a name="run-the-android-sdk-sample"></a>Pokretanje Android SDK primera

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ovaj primer Android projekta pomaže vam da razumete kako SDK radi u aplikaciji. Nećete morati da pišete kôd. Samo dodajte ključ za unos i odmah ćete videti događaje u svom radnom prostoru.

## <a name="prerequisites"></a>Preduslovi

- [Android Studio](https://developer.android.com/studio)
- [Ključ za unos](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Preuzmite Android SDK primer

1. [Preuzmite Android SDK primer uvida u angažovanje](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Raspakujte komprimovanu datoteku `ei-android-sample.zip`.
1. Otvorite raspakovanu fasciklu u usluzi Android Studio.
1. U datoteci `AndroidManifest.xml`, zamenite nisku `"Your-Ingestion-Key"` sa ključem za unos radnog prostora iz uvida u angažovanje u odeljku **Administrator** > **Radni prostor** > **Vodič za instalaciju**. 

   > [!NOTE]
   > Ne morate da zamenite odeljak `${applicationId}`. On se popunjava automatski.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Da biste započeli probni projekat, izaberite **Pokreni**.
1. Pregledajte događaje u svom radnom prostoru.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
