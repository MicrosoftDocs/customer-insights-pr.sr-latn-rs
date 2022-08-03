---
title: Izvoz segmenata u ActiveCampaign
description: Saznajte kako da konfigurišete vezu i izvezete je u uslugu ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 178d2df8edf1abcec72664e19d73a88f2b97f12d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195584"
---
# <a name="export-segments-to-activecampaign-preview"></a>Izvoz segmenata u ActiveCampaign (verzija za pregled)

Izvezite segmente objedinjenih profila kupaca u ActiveCampaign i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduslovi

- ActiveCampaign [nalog i](https://www.activecampaign.com/) odgovarajući administratorski akreditivi.
- ID [liste aktivnogcampaigna](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- ActiveCampaign [API Key](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) i REST krajnja tačka Hostname.
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milion profila klijenata po izvozu u ActiveCampaign, što može da potraje i do 90 minuta. Broj profila klijenata koje možete izvesti u ActiveCampaign zavisi od vašeg ugovora sa ActiveCampaign-om.
- Samo segmenti.

## <a name="set-up-connection-to-activecampaign"></a>Podesite vezu sa uslugom ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **dodaj vezu** i odaberite **ActiveCampaign**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj ActiveCampaign API ključ i ime hosta REST krajnje tačke. Ime hosta REST krajnje tačke je samo ime hosta, bez https://.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, izaberite vezu iz odeljka ActiveCampaign. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Unesite **ID** liste aktivnogcampaign.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta.

1. Opcionalno, izvezite **ime**, **prezime i** telefon da biste **kreirali** personalizovanije e-poruke. Izaberite **Dodaj atribut** za mapiranje ovih polja.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
