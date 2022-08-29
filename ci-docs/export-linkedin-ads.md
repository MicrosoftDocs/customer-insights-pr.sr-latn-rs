---
title: Izvoz segmenata u LinkedIn Ads (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvozite u LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304720"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Izvoz segmenata u LinkedIn Ads (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u LinkedIn Ads da biste kreirali podudarnu ciljnu grupu. Koristite podudarnu ciljnu grupu za ciljanje preduzeća i ciljanje kontakata.

## <a name="prerequisites"></a>Preduslovi

- Nalog [LinkedIn Campaign Manager i](https://business.linkedin.com/marketing-solutions/ads) odgovarajuće akreditive administratora.
- ID [LinkedIn Campaign Manager naloga](https://www.linkedin.com/help/lms/answer/a424270).
- [Konfigurisani segmenti u uvidima](segments.md) kupaca.
- Izvezenim segmentima je potrebno najmanje jedno određeno polje u zavisnosti od toga da li birate [ciljanje kontakta](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ili [ciljanje preduzeća na](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) LinkedIn. Moguća polja su navedena u koraku podudaranja **sa** podacima [prilikom konfigurisanja izvoza](#configure-an-export).

## <a name="known-limitations"></a>Poznata ograničenja

- Do 100.000 profila kupaca po izvozu na LinkedIn Oglase, što može da potraje i do 10 minuta.
- Samo segmenti. Segment mora da sadrži najmanje 300 jedinstvenih profila.

## <a name="set-up-connection-to-linkedin-ads"></a>Podešavanje veze sa LinkedIn oglasima

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **dodaj vezu i** odaberite **LinkedIn Oglase**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite ID LinkedIn Campaign Manager naloga.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Kliknite **na dugme** "Poveži" da biste povezali vezu.

1. Izaberite **Potvrdite identitet pomoću usluge LinkedIn** i obezbedite svoje administratorske akreditive za LinkedIn Campaign Manager.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka LinkedIn Ads. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Odaberite da li želite da izvezete podatke da obavite [kontakt ciljanje](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ili [ciljanje kompanije](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) u usluzi LinkedIn.

1. U odeljku **Podudaranje podataka**, za ciljanje kontakata izaberite najmanje jedno polje koje predstavlja e-adresu klijenta, Apple Ad ID, ID Google oglasa, Google ID korisnika, ili ime i prezime. Ako odaberete ciljanje preduzeća, izaberite barem jedno polje koje predstavlja naziv preduzeća, domen e-pošte, URL LinkedIn stranice, simbol akcije ili veb-lokaciju.

1. Opcionalno, dodajte polja da biste dodatno definisali izvoz. Izaberite **Dodaj atribut** za mapiranje ovih polja.

1. Izaberite segmente koje želite da izvezete. Publika koja se podudara u usluzi LinkedIn Campaign Manager automatski će se kreirati sa nazivom segmenata koje ste izabrali za izvoz. Svaki segment će rezultirati zasebnom podudarnom ciljnom grupom.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
