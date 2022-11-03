---
title: Izvoz segmenata u Omnisend (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvozite u Omnisend.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fb57e2bd70592f4ce4e1a13e21901dc69734f6bf
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725187"
---
# <a name="export-segments-to-omnisend-preview"></a>Izvoz segmenata u Omnisend (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u Omnisend i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduslovi

- [Omnisend nalog i odgovarajući](https://www.omnisend.com/) administratorski akreditivi.
- [Omnisend API kljuи](https://support.omnisend.com/en/articles/1061890-generating-api-key).
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Privatna veza u kombinaciji sa "Donesi sopstveno skladište" (BYOS) nije podržana.
- Do milion profila kupaca po izvozu u Omnisend, što može da potraje i do četiri sata. Broj profila klijenata koje možete izvesti u Omnisend zavisi od vašeg ugovora sa Omnisend-om.
- Samo segmenti.

## <a name="set-up-connection-to-omnisend"></a>Podešavanje veze u usluzi Omnisend

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Kliknite **na dugme Dodaj** vezu i odaberite **Omnisend**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj API ključ za Omnisend.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Omnisend. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta.

1. Opcionalno, izvezite ime, prezime **, adresu**, **državu**/region **,** državu **,** grad **i poštanski broj da** biste **kreirali personalizovanije e-poruke**.**·** Izaberite **Dodaj atribut** za mapiranje ovih polja.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
