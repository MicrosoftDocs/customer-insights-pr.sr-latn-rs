---
title: Izvezi podatke o uvidima kupaca u HubSpot
description: Saznajte kako da konfigurišete vezu i izvezete u HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588936"
---
# <a name="export-segments-to-hubspot-preview"></a>Izvoz segmenata u HubSpot (pregled)

Izvezite segmente objedinjenih profila kupaca u HubSpot i koristite ih za marketing e-pošte.

## <a name="prerequisites-for-a-connection"></a>Preduslovi za vezu

- HubSpot [nalog i](https://www.hubspot.com/) odgovarajući administratorski akreditivi.
- [API ključ iz](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) HubSpot-a.
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.

## <a name="known-limitations"></a>Poznata ograničenja

- Do 100'000 profila kupaca po izvozu u HubSpot, što može da potraje i do 15 minuta. Broj profila klijenata koje možete da izvezete u HubSpot zavisi i ograničen je na ugovor sa hubSpot-om.
- Samo segmenti.

## <a name="set-up-connection-to-hubspot"></a>Podešavanje veze sa hubSpot-om

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Kliknite **na dugme Dodaj** vezu i odaberite **HubSpot da** biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite HubSpot akreditive kada se to od vas zatraži.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu sa hubSpotom.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odeljka HubSpot. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta. Ponovite iste korake za druga opcionalna polja.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
