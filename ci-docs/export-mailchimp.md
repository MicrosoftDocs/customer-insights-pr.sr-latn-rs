---
title: Izvoz segmenata u Mailchimp (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvezete u Mailchimp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d74672768afec94e899ff0aec8c118c2afcde368
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725049"
---
# <a name="export-segments-to-mailchimp-preview"></a>Izvoz segmenata u Mailchimp (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u Mailchimp da biste kreirali biltene i kampanje e-pošte.

## <a name="prerequisites"></a>Preduslovi

- Mailchimp [nalog i](https://mailchimp.com/) odgovarajući administratorski akreditivi.
- [Postojeće grupe korisnika lokacije u programu Mailchimp](https://mailchimp.com/help/create-audience/) i [odgovarajućim korisnici ID-ovima](https://mailchimp.com/help/find-audience-id/).
- [Konfigurisani segmenti](segments.md).
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Privatna veza u kombinaciji sa "Donesi sopstveno skladište" (BYOS) nije podržana.
- Do milion profila klijenata po izvozu u Mailchimp, što može da potraje i do tri sata. Broj profila klijenata koje možete da izvezete u Mailchimp zavisi od ugovora sa Mailchimp-om.
- Samo segmenti.

## <a name="set-up-connection-to-mailchimp"></a>Podešavanje veze sa uslugom Mailchimp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **dodaj vezu i** odaberite **Mailchimp**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu.

1. Izaberite **Potvrdite identitet u usluzi Mailchimp** i navedite akreditive za Mailchimp.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Mailchimp. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Unesite **svoj Mailchimp korisnici ID**.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta.

1. Opcionalno, izvezite **ime** i **prezime biste kreirali** personalizovanije e-poruke. Izaberite **Dodaj atribut** za mapiranje ovih polja.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
