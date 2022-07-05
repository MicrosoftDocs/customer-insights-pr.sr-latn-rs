---
title: Izvoz segmenata u DotDigital (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvezete u DotDigital.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: af0cce4edb9d47247c79ae08491366349da98b1c
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082939"
---
# <a name="export-segments-to-dotdigital-preview"></a>Izvoz segmenata u DotDigital (verzija za pregled)

Izvezite segmente objedinjenih profila kupaca u DotDigital adresare i koristite ih za kampanje, marketing putem e-pošte i za izgradnju segmenata kupaca pomoću usluge DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Preduslovi za vezu

-   Imate [DotDigital nalog](https://dotdigital.com/) i kreirali ste [API korisnika](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Da biste kreirali vezu, morate da koristite akreditive API korisnika
-   Postoji postojeća publika u adresarima u usluzi DotDigital i odgovarajući ID-ovi. ID se može naći u URL-u kada odaberete i otvorite adresar. Za više informacija pogledajte [adresare za DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Konfigurisali [ste segmente u programu](segments.md) "Uvidi kupaca".
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do milion profila klijenata po izvozu u DotDigital.
- Izvoz u DotDigital je ograničen na segmente.
- Izvoz segmenata sa ukupno milion profila klijenata može potrajati do 3 sata zbog ograničenja na strani provajdera. 
- Broj profila klijenata koje možete izvesti u DotDigital zavisi i ograničen je na vaš ugovor sa DotDigital-om.

## <a name="set-up-connection-to-dotdigital"></a>Podešavanje veze u usluzi DotDigital

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **DotDigital** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoje **korisničko ime i lozinku za DotDigital API**. 

1. Unesite **[ID DotDigital adresara](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Poveži se** za inicijalizaciju veze sa uslugom DotDigital.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu. 

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka DotDigital. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.


1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta. Ponovite iste korake za druga opcionalna polja kao što su **Ime**, **Prezime**, **Puno ime**, **Pol** i **Poštanski broj**.

1. Izaberite segmente koje želite da izvezete. U usluzi DotDigital možete ukupno izvesti do 1 milion korisničkih profila.

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 
 
U usluzi DotDigital sada možete da pronađete svoje segmente u [DotDigital adresarima](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u DotDigital, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da DotDigital ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.


[!INCLUDE [footer-include](includes/footer-banner.md)]