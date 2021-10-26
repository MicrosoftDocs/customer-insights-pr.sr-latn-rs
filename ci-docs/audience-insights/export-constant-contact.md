---
title: Izvoz Customer Insights podataka u Constant Contact
description: Saznajte kako da konfigurišete vezu i izvezete sadržaj u Constant Contact.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b25e4f11e21d059c2d867e925c0ae5635a87addc
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/08/2021
ms.locfileid: "7619136"
---
# <a name="export-segments-to-constant-contact-preview"></a>Izvoz segmenata u Constant Contact (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u Constant Contact i koristite ih za marketinške aktivnosti. 

## <a name="prerequisites-for-a-connection"></a>Preduslovi za vezu

-   Imate [Constant Contact nalog](https://www.constantcontact.com/account-home) i odgovarajuće akreditive administratora.
-   [Konfigurisali ste segmente](segments.md) u uvidima o korisnicima.
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Možete izvoziti do milion korisničkih profila po izvozu u Constant Contact.
- Izvoz u Constant Contact ograničen je na segmente.
- Izvoz do 1 miliona profila klijenata u Constant Contact može potrajati do 1 sata. 
- Broj profila klijenata koje možete izvesti u Constant Contact zavisi i ograničen je na vaš ugovor sa Constant Contact-om.

## <a name="set-up-connection-to-constant-contact"></a>Podešavanje veze sa uslugom Constant Contact

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **Constant Contact** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Povežite se** da bi se inicijalizovala veza sa uslugom Constant Contact.

1. Izaberite **Potvrdite autentičnost sa uslugom Constant Contact** i navedite administratorske akreditive za Constant Contact. 

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Constant Contact. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. Unesite [**ID Constant Contact liste**](https://app.constantcontact.com/pages/contacts/ui#lists). Otvorite listu u usluzi Constant Contact da biste pronašli ID liste u URL adresi.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje koje predstavlja e-adresu klijenta. To je potrebno da izvezete segmente u Constant Contact.

1. Po želji možete da izvezete Ime i Prezime kao dodatna polja za stvaranje personalizovanih e-poruka. Izaberite **Dodaj atribut** za mapiranje ovih polja.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite Dynamics 365 Customer Insights za prenos podataka u Constant Contact, dozvoljavate prenos podataka izvan granica usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Constant Contact ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.
