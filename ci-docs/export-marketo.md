---
title: Izvoz segmenata u Marketo (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvezete u Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195261"
---
# <a name="export-segments-to-marketo-preview"></a>Izvoz segmenata u Marketo (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata da biste generisali kampanje, obezbedili marketing e-poštom i koristili određene grupe klijenata sa uslugom Marketo.

## <a name="prerequisites"></a>Preduslovi

- [Marketo nalog i](https://login.marketo.com/) odgovarajući administratorski akreditivi.
- ID [Marketo klijenta, Tajna klijenta i REST krajnja tačka Hostname](https://developers.marketo.com/rest-api/authentication/).
- [Postojeće liste u marketu](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) i odgovarajućiM ID-ovima.
- [Konfigurisani segmenti](segments.md).
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milion profila kupaca po izvozu na Marketo, što može da potraje i do 3 sata. Broj profila klijenata koje možete da izvezete na Marketo zavisi od ugovora sa Marketom.
- Samo segmenti.

## <a name="set-up-connection-to-marketo"></a>Podešavanje veze za Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu i** odaberite **Marketo**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **ID klijenta marketa, tajnu klijenta i rest krajnja tačka Hostname**. Ime hosta REST krajnje tačke je samo ime hosta, bez https://. Primer: xyz-abc-123.mktorest.com.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Marketo. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Unesite **ID Marketo liste**. ID liste je čisto numerička vrednost. Na primer, ako je ID Marketo liste ST12345A7, uklonite znak pre i posle brojeva i unesite *12345*.

1. U odeljku **Podudaranje** podataka izaberite najmanje jedno polje koje predstavlja e-adresu kupca ili Marketo ID kupca.

1. Opcionalno, izvezite ime, prezime **, grad**, **državu** **i državu**/region da biste kreirali **personalizovanije e-poruke.** **·** Izaberite **Dodaj atribut** za mapiranje ovih polja.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

U marketu pronađite svoje segmente u okviru [Marketo lista](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
