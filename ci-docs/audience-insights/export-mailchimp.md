---
title: Izvezite Customer Insights podatke u Mailchimp
description: Saznajte kako da konfigurišete vezu sa uslugom Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267190"
---
# <a name="connector-for-mailchimp-preview"></a>Konektor za Mailchimp (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata u Mailchimp da biste kreirali biltene i kampanje e-pošte.

## <a name="prerequisites"></a>Preduslovi

-   Imate [Mailchimp nalog](https://mailchimp.com/) i odgovarajuće akreditive administratora.
-   Postoji postojeća publika u Mailchimp-u i odgovarajući ID-ovi. Za više informacija pogledajte [Mailchimp korisnici](https://mailchimp.com/help/create-audience/).
-   Imate [konfigurisane segmente](segments.md)
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="connect-to-mailchimp"></a>Povežite sa uslugom Mailchimp

1. Idite na **Administrator** > **Odredišta za izvoz**.

1. Pod **Mailchimp**, izaberite **Podesi**.

1. Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Unesite **[Mailchimp ID korisnika](https://mailchimp.com/help/find-audience-id/)** i izaberite **Povežite se** da biste započeli povezivanje sa Mailchimp-om.

1. Izaberite **Potvrdite identitet u Mailchimp-u** i navedite akreditive za Mailchimp.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Izvezite snimak ekrana za vezu sa uslugom Mailchimp":::

1. Izaberite **Sledeće** da biste konfigurisali izvoz.

## <a name="configure-the-connector"></a>Konfigurisanje konektora

1. U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta. 

1. Po želji možete da izvezete **Ime** i **Prezime** kao dodatna polja za stvaranje personalizovanih e-poruka. Izaberite **Dodaj atribut** za mapiranje ovih polja.

1. Izaberite segmente koje želite da izvezete. U usluzi Mailchimp možete ukupno izvesti do 1 milion korisničkih profila.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Izaberite polja i segmente za izvoz u Mailchimp":::

1. Izaberite stavku **Sačuvaj**.

## <a name="export-the-data"></a>Izvoz podataka

Možete da [izvezete podatke na zahtev](export-destinations.md). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab). U Mailchimp-u sada možete pronaći segmente u odeljku [Mailchimp korisnici](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Poznata ograničenja

- Do 1 milion profila po izvozu u usluzi Mailchimp.
- Izvoz u Mailchimp je ograničen na segmente.
- Izvoz segmenata sa ukupno 1 milion profila može trajati do tri sata zbog ograničenja na strani dobavljača. 
- Broj profila koje možete da izvezete u Mailchimp zavisi od i ograničen je vašim ugovorom sa kompanijom Mailchimp.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Mailchimp, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Mailchimp ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]