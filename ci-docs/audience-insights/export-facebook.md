---
title: Izvoz podataka o uvidu kupaca Facebook u Ads Manager (sadrži video)
description: Saznajte kako da konfigurišete vezu i izvezete u Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce1e63f7b20b757780f05895b725003e286f9dac
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 12/18/2021
ms.locfileid: "7935041"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Izvoz segmenata u Facebook Ads Manager (verzija za pregled)

Izvezite segmente objedinjenih korisničkih profila u Facebook menadžer oglasa za kreiranje kampanja na Facebook i Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Preduslovi za vezu

- Potrebno je da imate [**Facebook Ads nalog**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) koji uključuje [**Facebook poslovni nalog**](https://business.facebook.com/).
- Morate biti administrator [**Facebook Ads naloga**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Poznata ograničenja

- Do 10 miliona profila klijenata po izvozu u Facebook Ads Manager.
- Izvoz u Facebook Ads Manager je ograničen na segmente.
- Napravite ili ažurirajte prilagođenu ciljnu grupu u Facebook samo tipa *lista klijenata*.
- Izvoz segmenata sa ukupno 10 miliona profila klijenata može potrajati do 90 minuta.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Podešavanje veze sa uslugom Facebook Ads Manager

Da bi korisnici mogli da naprave izvoz, administrator mora da konfiguriše vezu sa uslugom i dozvoli saradnicima da koriste vezu.

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **Facebook Ads Manager** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Potvrdite verodostojnost pomoću usluge Facebook Ads: 

   1. Izaberite **Nastavi sa Facebook-om** da biste se prijavili na svoj Facebook Ads nalog.

   1. Dajte dozvolu **ads_management** nakon potvrde identiteta sa uslugom Facebook.

   1. Izaberite **Facebook nalog za oglašavanje** sa kojim želite da radite.

   1. Izaberite **Postojeća prilagođena ciljna grupa** sa padajuće liste ili kreirajte **novu prilagođenu ciljnu grupu**. Za više informacija pogledajte [**Publika u Facebook menadžeru oglasa**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Ovim izvozom u usluzi Facebook možete samo da kreirate ili ažurirate prilagođenu ciljnu grupu tipa *lista klijenata*. U nekim slučajevima, na padajućoj listi vidite prilagođenu ciljnu grupu različitih vrsta. Izbor nekog drugog tipa umesto *liste klijenata* dovešće do neuspelog izvoza. 

1. Pregledajte **Privatnost podataka i usklađenost** i izaberite **Slažem se**.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**. 

1. U polju **Veza za izvoz** odaberite vezu iz odeljka **Facebook Ads Manager**. Ako ne vidite naziv ovog odeljka, tada vam nisu dostupne veze ovog tipa.

1. U **Izaberite polje identifikatora ključa**, izaberite **E-pošta**, **Ime i adresa** ili **Telefon** koji biste poslali u Facebook menadžer oglasa. 

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.

1. Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za izabrani identifikator ključa.
   > [!TIP]
   > Najbolje šanse za podudaranje nastaju ako odaberete opciju **E-pošta** kao ključni identifikator. Dodavanje dodatnih identifikatora može poboljšati podudaranje.

1. Izaberite **Dodaj atribut** da biste mapirali više atributa za slanje u Facebook Ads Manager. Atributi iz usluge Facebook Ads Manager se preslikavaju na sledeća imena prilagođena korisniku: **FN** = **Ime**, **LN** = **Prezime**, **FI** = **Prvo slovo imena**, **PHONE** = **Telefon**, **GEN** = **Pol**, **DOB** = **Datum rođenja**, **ST** = **Država**, **CT** = **Grad**, **ZIP** = **Poštanski broj**, **COUNTRY** = **Zemlja**

1. Izaberite segmente koje želite da izvezete.

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). 

Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u menadžer Facebook oglasa, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Facebook oglasi ispunjavaju sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
