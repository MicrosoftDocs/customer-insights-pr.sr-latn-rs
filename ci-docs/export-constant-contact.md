---
title: Izvoz segmenata u Constant Contact (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvezete sadržaj u Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c0affd3ed45f462696850813bd50331061dde780
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724518"
---
# <a name="export-segments-to-constant-contact-preview"></a>Izvoz segmenata u Constant Contact (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u Constant Contact i koristite ih za marketinške aktivnosti.

## <a name="prerequisites"></a>Preduslovi

- Nalog [stalnog kontakta](https://www.constantcontact.com/account-home) i odgovarajući administratorski akreditivi.
- [ID liste stalnih kontakata](https://app.constantcontact.com/pages/contacts/ui#lists). Otvorite listu u usluzi Constant Contact da biste pronašli ID liste u URL adresi.
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Privatna veza u kombinaciji sa "Donesi sopstveno skladište" (BYOS) nije podržana.
- Do milion profila klijenata po izvozu u Stalni kontakt, što može da potraje i do sat vremena. Broj profila kupaca koje možete izvesti u "Stalni kontakt" zavisi od ugovora sa stalnim kontaktom.
- Samo segmenti.

## <a name="set-up-connection-to-constant-contact"></a>Podešavanje veze sa uslugom Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **dodaj vezu i** odaberite stavku **Stalni kontakt**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu.

1. Izaberite **Potvrdite autentičnost sa uslugom Constant Contact** i navedite administratorske akreditive za Constant Contact.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Constant Contact. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Unesite ID **liste stalnih kontakata**.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta.

1. Opcionalno, izvezite **ime** i **prezime kao dodatna** polja da biste kreirali personalizovanije e-poruke. Izaberite **Dodaj atribut** za mapiranje ovih polja.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
