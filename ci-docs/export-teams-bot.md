---
title: Robot za Microsoft Teams
description: Potražite objedinjene profile klijenata u usluzi Microsoft Teams uz pomoć robota.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 89a293d5b6f9f5452b2ccba495d2475002806019
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643905"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teams robot za Dynamics 365 Customer Insights (verzija za pregled)

Povežite se sa uslugom Microsoft Teams da biste dozvolili robotu da traži objedinjene profile klijenata na Teams kanalima.

> [!div class="mx-imgBorder"]
> ![Teams robot koji prikazuje zapis klijenta.](media/teams-bot.png "Teams robot koji prikazuje zapis klijenta")

## <a name="prerequisites"></a>Preduslovi

Da biste postavili i konfigurisali robota, moraju se ispuniti sledeći preduslovi:

- Postoji bar jedan [dodat izvor podataka](data-sources.md).
- [Proces objedinjavanja](data-unification.md) je dovršen.
- Polja su dodata u [indeks pretrage i filtera](search-filter-index.md).
- Customer Insights i Teams su u istoj organizaciji.
- Vaše okruženje ima primarnu ciljnu grupu postavljenu za pojedinačne klijente. Poslovni nalozi nisu podržani.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Konfigurisanje robota

1. Idite na **odredišta za AdminExport** > **·**.
1. Na pločici Microsoft Teams izaberite **Postaviti**.
1. Preusmereni ste na oblast **Aplikacije** u usluzi Teams. Takođe možete otvoriti Teams i izabrati **Aplikacije** u donjem levom uglu ili ga direktno [preuzeti sa lokacije AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Potražite **Customer Insights** i izaberite aplikaciju.
1. Izaberite **Dodaj**.
1. Kada se prijavite u Customer Insights u usluzi Teams, videćete poruku dobrodošlice i tada možete početi.

## <a name="things-you-can-do-with-the-bot"></a>Stvari koje možete da uradite uz robota

Robot pruža mogućnosti pronalaženja za objedinjene profile klijenata.

- Unesite **pretraga** nakon čega sledi ime, adresa e-pošte ili bilo koje drugo polje na objedinjenom profilu klijenta koje se dodaje indeksu pretrage i filtera.

  Dobićete karticu sa do 15 polja iz rezultujućeg profila klijenta. Više podudaranja vraća listu rezultata na kojima možete odabrati profil. Možete dodati termin za pretragu u dvostrukim navodnicima da biste potražili tačno podudaranje.

- Ako vaša organizacija održava više Customer Insights okruženja u istoj organizaciji, možete da unesete **switchinstance** da biste izabrali sa kojim okruženjem želite da povežete robota.

- Unesite **pomoć** da biste videli listu dostupnih komandi za robota.  


[!INCLUDE [footer-include](includes/footer-banner.md)]