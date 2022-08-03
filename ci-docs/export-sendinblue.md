---
title: Izvoz segmenata u Sendinblue (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvezete je u uslugu Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 816a3b242fadaa5a75db878adf0a76baf638e41c
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196963"
---
# <a name="export-segments-to-sendinblue-preview"></a>Izvoz segmenata u Sendinblue (verzija za pregled)

Izvezite segmente ujednačenih profila klijenata da biste generisali kampanje, obezbedili marketing e-poštom i koristili određene grupe klijenata sa uslugom Sendinblue.

## <a name="prerequisites"></a>Preduslovi

- Nalog [sendinblue i odgovarajuće](https://www.sendinblue.com/) akreditive administratora.
- [SendinBlue API ključ](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Postojeće liste u sendinblue i odgovarajućim ID-ovima.
- [Konfigurisani segmenti](segments.md).
- Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milion profila klijenata po izvozu u Sendinblue, što može da potraje i do 90 minuta. Broj profila kupaca koje možete da izvezete u Sendinblue zavisi od ugovora sa sendinblue.
- Samo segmenti.

## <a name="set-up-connection-to-sendinblue"></a>Podešavanje veze sa uslugom Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Kliknite **na dugme Dodaj** vezu i odaberite **stavku Pošalji**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **API ključ za SendinBlue**.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, izaberite vezu iz odeljka Sendinblue. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Unesite **ID** liste sendinblue.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta.

1. Opcionalno, izvezite **ime**, **prezime i** telefon da biste **kreirali** personalizovanije e-poruke. Izaberite **Dodaj atribut** za mapiranje ovih polja.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
