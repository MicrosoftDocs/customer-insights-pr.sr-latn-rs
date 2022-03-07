---
title: Pokretanje iOS SDK primera
description: Primer projekta za učenje o platformi iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232859"
---
# <a name="run-the-ios-sdk-sample"></a>Pokretanje iOS SDK primera

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ovaj primer iOS projekta pomaže vam da razumete kako SDK radi u aplikaciji. Nećete morati da pišete kôd. Samo dodajte ključ za unos i odmah ćete videti događaje u svom radnom prostoru.

## <a name="prerequisites"></a>Preduslovi

- [Xcode verzije 9+](https://developer.apple.com/xcode/downloads/)
- [Ključ za unos](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Preuzmite iOS SDK primer

1. [Preuzmite iOS SDK primer uvida u angažman](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Raspakujte komprimovanu datoteku `ei-ios-sample.zip`.
1. Otvorite primer projekta aplikacije u usluzi Xcode.
1. U datoteci `EIConfig.plist`, zamenite nisku `“YOUR-INGESTION-KEY”` u polju `ingestionKey` sa ključem za unos radnog prostora iz uvida u angažovanje u odeljku **Administrator** > **Radni prostor** > **Vodič za instalaciju**.
1. Da biste započeli probni projekat, izaberite **Pokreni**.
1. Pregledajte događaje u svom radnom prostoru.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
