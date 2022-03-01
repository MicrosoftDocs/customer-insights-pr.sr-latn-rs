---
title: Pokretanje veb SDK uzorka
description: Saznajte kako da personalizujete i pokrenete veb SDK uzorak.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036620"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Pokrenite veb SKD uzorak za Dynamics 365 Customer Insights mogućnost uvida u angažovanje

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Veb SDK biblioteka mogućnosti uvida u angažovanje je JavaScript biblioteka sa uzorkom koda koji možete da koristite na vašoj veb-lokaciji.

## <a name="prerequisites"></a>Preduslovi

- Instalirajte [Visual Studio Code](https://code.visualstudio.com/).
- [Instalirajte Live Server proširenje](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) u Visual Studio Code uređivaču i upoznajte se kako da pokrećete Live Server.
- Morate imati [ključ za unos](instrument-website.md).

## <a name="run-sample"></a>Pokretanje uzorka

1. [Preuzmite veb SDK uzorak](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Raspakujte komprimovanu datoteku `ei_websdk_sample.zip`.

1. Otvorite raspakovanu fasciklu u Visual Studio Code.

1. U `ei_websdk_sample.html` datoteci, zamenite nisku „KLJUČ ZA UNOS“ ključem za unos sa portala mogućnosti uvida u angažovanje, a nisku „NAZIV“ globalnim nazivom za koji želite da vežete SDK instancu. Obavezno zamenite na svim mestima.

1. Otvorite `ei_websdk_sample.html` datoteku koristeći Live Server u rešenju Visual Studio Code tako što ćete izabrati **Izvedi uživo** sa statusne trake.

1. Po otvaranju stranice, trebalo bi da automatski bude poslat događa prikaza. Klikom na bilo koje dugme na stranici biće poslati događaji radnje. Dugme **Prati događaje** će takođe slati prilagođene događaje. Izborom dugmeta **Idite na Bing** poslaćete događaj radnje pre odlaska na Bing veb-lokaciju.

1. Pogledajte događaje koji teku tokom kretanja do vašeg radnog prostora. Ovaj radni prostor povezan je sa ključem za unos koji ste uneli u 4. koraku.


[!INCLUDE[footer-include](../includes/footer-banner.md)]