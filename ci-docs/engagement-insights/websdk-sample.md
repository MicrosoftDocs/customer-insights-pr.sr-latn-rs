---
title: Pokretanje veb SDK uzorka
description: Saznajte kako da personalizujete i pokrenete veb SDK uzorak.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606264"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Pokrenite veb SKD uzorak za Dynamics 365 Customer Insights mogućnost uvida u angažovanje

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Veb SDK biblioteka mogućnosti uvida u angažovanje je JavaScript biblioteka sa uzorkom koda koji možete da koristite na vašoj veb-lokaciji.

## <a name="prerequisites"></a>Preduslovi

- Instalirajte [Visual Studio Code](https://code.visualstudio.com/).
- [Instalirajte Live Server proširenje](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) u Visual Studio Code uređivaču i upoznajte se kako da pokrećete Live Server.
- Morate imati [radni prostor uvidi u angažovanje](create-workspace.md).

## <a name="run-sample"></a>Pokretanje uzorka

1. [Preuzmite veb SDK uzorak](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Raspakujte komprimovanu datoteku `ei_websdk_sample.zip`.

1. Otvorite raspakovanu fasciklu u Visual Studio Code.

1. Idite na portal uvida u angažovanje za svoj radni prostor. Izaberite **Administrator** > **Radni prostor** i onda **Uputstvo za instalaciju**. Pratite prvu opciju i izaberite **Kopiraj kod** da biste kopirali JavaScript isečak koda.

1. U datoteci `ei_websdk_sample.html`, ispod ove linije nalepite isečak koda koji ste upravo kopirali:

   - <-- NALEPITE JAVASCRIPT ISEČAK KODA SA PORTALA UVIDA U ANGAŽOVANJE OVDE ISPOD OVE LINIJE -->

1. Otvorite `ei_websdk_sample.html` datoteku koristeći Live Server u rešenju Visual Studio Code tako što ćete izabrati **Izvedi uživo** sa statusne trake.

1. Po otvaranju stranice, trebalo bi da automatski bude poslat događa prikaza. Klikom na bilo koje dugme na stranici biće poslati događaji radnje. Dugme **Prati događaje** će takođe slati prilagođene događaje. Izborom dugmeta **Idite na Bing** poslaćete događaj radnje pre odlaska na Bing veb-lokaciju.

1. Pogledajte događaje koji teku tokom kretanja do vašeg radnog prostora. Ovaj radni prostor povezan je sa ključem za unos koji ste uneli u 4. koraku.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
