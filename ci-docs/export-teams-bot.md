---
title: Teams robot za Dynamics 365 Customer Insights (verzija za pregled)
description: Potražite objedinjene profile klijenata u usluzi Microsoft Teams uz pomoć robota.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195859"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teams robot za Dynamics 365 Customer Insights (verzija za pregled)

Povežite se sa uslugom Microsoft Teams da biste dozvolili robotu da traži objedinjene profile klijenata na Teams kanalima.

:::image type="content" source="media/teams-bot.png" alt-text="Teams robot koji prikazuje zapis klijenta":::

## <a name="prerequisites"></a>Preduslovi

- Dodata je [izvor podataka jedna osoba](data-sources.md).
- [Proces objedinjavanja](data-unification.md) je dovršen.
- Polja se dodaju indeksu search [& filter](search-filter-index.md).
- Customer Insights i Teams su u istoj organizaciji.
- Vaše okruženje ima primarnu ciljnu grupu postavljenu za pojedinačne klijente. Poslovni nalozi nisu podržani.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Konfigurisanje robota

1. Idite na **Administrator** > **Veze**.
1. Na pločici Microsoft Teams izaberite **Postaviti**.
1. Preusmereni ste na oblast **Aplikacije** u usluzi Teams. Takođe možete otvoriti Teams i izabrati **Aplikacije** u donjem levom uglu ili ga direktno [preuzeti sa lokacije AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Potražite **Customer Insights** i izaberite aplikaciju.
1. Izaberite **Dodaj**.
1. Prijavite se na Uvid kupca u timovima. Prikazuje se poruka dobrodošlice.

## <a name="things-you-can-do-with-the-bot"></a>Stvari koje možete da uradite uz robota

Robot pruža mogućnosti pronalaženja za objedinjene profile klijenata.

- Unesite **pretragu** praćenu imenom, e-adresom ili bilo kojim drugim poljem u objedinjenom profilu kupca koje se dodaje indeksu search & filter.

  Dobićete karticu sa do 15 polja iz rezultujućeg profila klijenta. Više podudaranja vraća listu rezultata na kojima možete odabrati profil. Da biste potražili tačno podudaranje, dodajte termin za pretragu u dvostruke navodnike.

- Ako vaša organizacija održava više okruženja za uvide klijenata u istoj organizaciji, **unesite switchinstance da** biste odabrali sa kojim okruženjem želite da povežete bota.

- Unesite **pomoć** da biste videli listu dostupnih komandi za robota.  

[!INCLUDE [footer-include](includes/footer-banner.md)]