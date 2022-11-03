---
title: Izvoz segmenata u Facebook Ads Manager (pregled) (sadrži video)
description: Saznajte kako da konfigurišete vezu i izvezete u Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724633"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Izvoz segmenata u Facebook Menadžer za oglase (pregled)

Izvezite segmente objedinjenih korisničkih profila u Facebook menadžer oglasa za kreiranje kampanja na Facebook i Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Preduslovi

- Nalog [Facebook oglasa](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) koji uključuje poslovni [Facebook nalog](https://business.facebook.com/).
- Administratorske privilegije na Nalogu [Facebook oglasa](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- Prilagođene korisnici potrebno je prihvatiti od strane korisnika koji podešava vezu u "Uvidima kupaca".

## <a name="known-limitations"></a>Poznata ograničenja

- Do 10 miliona profila klijenata po izvozu u Facebook Ads Manager, što može da potraje i do 90 minuta.
- Samo segmenti.
- Facebook Integracija oglasa ne podržava korisnike sa više od 25 oglasnih naloga.
- Facebook *tip liste kupaca* samo u [prilagođenim korisnicima](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) lokacije.
  > [!NOTE]
  > U nekim slučajevima možete videti prilagođene grupe različitih tipova na padajuće liste. Ako izaberete neki drugi tip osim liste *kupaca*, izvoz neće uspeti.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Podešavanje veze sa uslugom Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **dodaj vezu i** odaberite Menadžer **Facebook za oglase**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Potvrdite verodostojnost pomoću usluge Facebook Ads:

   1. Izaberite **Nastavi sa Facebook-om** da biste se prijavili na svoj Facebook Ads nalog.

   1. Dajte dozvolu **ads_management** nakon potvrde identiteta sa uslugom Facebook.

   1. Izaberite **Facebook nalog za oglašavanje** sa kojim želite da radite.

   1. Izaberite **Postojeća prilagođena ciljna grupa** sa padajuće liste ili kreirajte **novu prilagođenu ciljnu grupu**.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz** odaberite vezu iz odeljka Menadžer Facebook za oglase. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. U polju Povezivanje **podataka** izaberite e-poštu **·**, ime **i adresu** ili telefon koji **ćete** poslati menadžeru Facebook oglasa.

1. Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za izabrani identifikator ključa.
   > [!TIP]
   > Najbolje šanse za podudaranje nastaju ako odaberete opciju **E-pošta** kao ključni identifikator. Dodavanje dodatnih identifikatora može poboljšati podudaranje.

1. Izaberite **Dodaj atribut** da biste mapirali više atributa za slanje u Facebook Ads Manager. Atributi iz usluge Facebook Ads Manager se preslikavaju na sledeća imena prilagođena korisniku: **FN** = **Ime**, **LN** = **Prezime**, **FI** = **Prvo slovo imena**, **PHONE** = **Telefon**, **GEN** = **Pol**, **DOB** = **Datum rođenja**, **ST** = **Država**, **CT** = **Grad**, **ZIP** = **Poštanski broj**, **COUNTRY** = **Zemlja**

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
