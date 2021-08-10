---
title: Izvezite Customer Insights podatke u Mailchimp
description: Saznajte kako da konfigurišete vezu i izvezete u Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ac6642c0ce02f1a92458a16250fd3b4cdef5fd1c
ms.sourcegitcommit: adb9c43ddaba25e511535d78a4bcf8815f154a7b
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/06/2021
ms.locfileid: "6362526"
---
# <a name="export-segments-to-mailchimp-preview"></a>Izvoz segmenata u Mailchimp (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u Mailchimp da biste kreirali biltene i kampanje e-pošte.

## <a name="prerequisites-for-connection"></a>Preduslovi za vezu

-   Imate [Mailchimp nalog](https://mailchimp.com/) i odgovarajuće akreditive administratora.
-   Postoji postojeća publika u usluzi Mailchimp i odgovarajući ID-ovi. Za više informacija pogledajte [Mailchimp korisnici](https://mailchimp.com/help/create-audience/).
-   Imate [konfigurisane segmente](segments.md)
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do 1 milion profila po izvozu u usluzi Mailchimp.
- Izvoz u Mailchimp je ograničen na segmente.
- Izvoz segmenata sa 1 milion profila može trajati do tri sata. 
- Broj profila koje možete da izvezete u Mailchimp zavisi od i ograničen je vašim ugovorom sa kompanijom Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Podešavanje veze sa uslugom Mailchimp

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **Mailchimp** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Povežite se** da bi se inicijalizovala veza sa uslugom Mailchimp.

1. Izaberite **Potvrdite identitet u usluzi Mailchimp** i navedite akreditive za Mailchimp.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu. 

## <a name="configure-the-connector"></a>Konfigurisanje konektora

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci**> **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Mailchimp. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. Unesite **[ID ciljne grupe za Mailchimp](https://mailchimp.com/help/find-audience-id/)**

3. U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta. 

1. Opcionalno, možete da izvezete **Ime** i **Prezime** da biste kreirali personalizovanije e-poruke. Izaberite **Dodaj atribut** za mapiranje ovih polja.

1. Izaberite segmente koje želite da izvezete. U usluzi Mailchimp možete ukupno izvesti do 1 milion korisničkih profila.

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Mailchimp, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Mailchimp ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
