---
title: Izvezite Customer Insights podatke u menadžer Facebook oglasa
description: Naučite kako da konfigurišete vezu u okviru Facebook menadžera oglasa.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596700"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Konektor za Facebook menadžer oglasa (verzija za pregled)

Izvezite segmente objedinjenih korisničkih profila u Facebook menadžer oglasa za kreiranje kampanja na Facebook i Instagram.

## <a name="prerequisites"></a>Preduslovi

- Morate da imate [**Facebook** nalog za oglašavanje](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) koji uključuje [**Facebook poslovni nalog**](https://business.facebook.com/).
- Morate da budete administrator na [**Facebook nalogu za oglašavanje**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Povezivanje sa Facebook menadžerom oglasa

1. Idite na **Administrator** > **Odredišta za izvoz**.

1. Pod **Facebook menadžer oglasa**, izaberite **Postavi**.

1. Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.

1. Izaberite **Nastavi sa Facebook** da se prijavite na svoj Facebook nalog za oglašavanje.

1. Dajte dozvolu **ads_management** nakon potvrde identiteta sa uslugom Facebook.

1. Izaberite **Facebook nalog za oglašavanje** sa kojim želite da radite.

1. Izaberite **Postojeća prilagođena ciljna grupa** sa padajuće liste ili kreirajte **Novu prilagođenu ciljnu grupu**. Za više informacija pogledajte [**Publika u Facebook menadžeru oglasa**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Sledeće** da biste konfigurisali izvoz.

## <a name="configure-the-connector"></a>Konfigurisanje konektora

1. U **Izaberite polje identifikatora ključa**, izaberite **E-pošta**, **Ime i adresa** ili **Telefon** koji biste poslali u Facebook menadžer oglasa.

1. Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za izabrani identifikator ključa.
   > [SAVET] Najbolje šanse za podudaranje nastaju ako odaberete **E-pošta** kao ključni identifikator. Dodavanje dodatnih identifikatora može poboljšati podudaranje.

1. Izaberite **Dodaj atribut** da biste mapirali dodatne atribute koje treba poslati u Facebook menadžer oglasa. Atributi iz Facebook menadžera oglasa se preslikavaju na sledeća imena prilagođena korisniku: **IME** = **Ime**, **PR** = **Prezime**, **PS** = **Prvo slovo imena**, **TEL** = **Telefon**, **POL** = **Pol**, **ROĐ** = **Datum rođenja**, **DRŽ** = **Država**, **GR** = **Grad**, **P. BR.** = **Poštanski broj**, **ZMLJ** = **Zemlja/Region**

1. Izaberite segmente koje želite da izvezete.

1. Izaberite stavku **Sačuvaj**.

## <a name="export-the-data"></a>Izvoz podataka

Možete da [izvezete podatke na zahtev](export-destinations.md). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).

## <a name="known-limitations"></a>Poznata ograničenja

- Do 10 miliona profila kupaca po izvozu u menadžeru Facebook oglasa 
- Izvoz u menadžer Facebook oglasa je ograničen na segmente
- Izvoz segmenata sa ukupno 10 miliona profila može trajati do 90 minuta dok se ne završi

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u menadžer Facebook oglasa, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Facebook oglasi ispunjavaju sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]