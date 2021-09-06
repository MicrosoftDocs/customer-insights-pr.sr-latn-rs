---
title: Izvezite Customer Insights podatke u SendGrid
description: Saznajte kako da konfigurišete vezu i izvezete u SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 03df2ab5fce1da1f4f662e1975533f2b538b47dbdd5cf96aae4f1007163e3729
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036118"
---
# <a name="export-segments-to-sendgrid-preview"></a>Izvoz segmenata u SendGrid (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u SendGrid liste kontakata i koristite ih za kampanje i marketing u usluzi SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Preduslovi za vezu

-   Imate [SendGrid nalog](https://sendgrid.com/) i odgovarajuće akreditive administratora.
-   Postoje postojeće liste kontakata u usluzi SendGrid i odgovarajući ID-ovi. Za više informacija pogledajte [SendGrid – Upravljanje kontaktima](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   [Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Ukupno do 100.000 profila u SendGrid.
- Izvoz u SendGrid je ograničen na segmente.
- Izvoz do 100.000 profila u SendGrid može da potraje do nekoliko sati. 
- Broj profila koje možete da izvezete u SendGrid zavisi od vašeg ugovora sa kompanijom SendGrid i ograničen je njime.

## <a name="set-up-connection-to-sendgrid"></a>Podešavanje veze u usluzi SendGrid

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **SendGrid** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite svoj **SendGrid API ključ** [SendGrid API ključ](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Poveži se** za inicijalizaciju veze sa uslugom SendGrid.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka SendGrid. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. Unesite **[ID SendGrid liste](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta. Ponovite iste korake za druga opcionalna polja kao što su **Ime**, **Prezime**, **Zemlja/Region**, **Država**, **Grad** i **Poštanski broj**.

1. Izaberite segmente koje želite da izvezete. Izričito **preporučujemo da ne izvozite ukupno više od 100.000 profila klijenata** u SendGrid. 

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u SendGrid, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da SendGrid ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]