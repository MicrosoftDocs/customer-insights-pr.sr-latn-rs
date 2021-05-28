---
title: Izvezite Customer Insights podatke u Marketo
description: Saznajte kako da konfigurišete vezu i izvezete u Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059333"
---
# <a name="export-segments-to-marketo-preview"></a>Izvoz segmenata u Marketo (verzija za pregled)

Izvezite segmente objedinjenih profila klijenata da biste generisali kampanje, obezbedili marketing e-poštom i koristili određene grupe klijenata sa uslugom Marketo.

## <a name="prerequisites-for-connection"></a>Preduslovi za vezu

-   Imate [Marketo nalog](https://login.marketo.com/) i odgovarajuće akreditive administratora.
-   Postoje postojeće liste u usluzi Marketo i odgovarajući ID-ovi. Za više informacija pogledajte [Marketo liste](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Imate [konfigurisane segmente](segments.md).
-   Objedinjeni profili klijenata u izvezenim segmentima sadrže polje koje predstavlja adresu e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Do 1 milion profila po izvozu u usluzi Marketo.
- Izvoz u Marketo je ograničen na segmente.
- Izvoz segmenata sa ukupno 1 milion profila može trajati do 3 sata. 
- Broj profila koje možete da izvezete u Marketo zavisi od i ograničen je vašim ugovorom sa kompanijom Marketo.

## <a name="set-up-connection-to-marketo"></a>Podešavanje veze za Marketo

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **Marketo** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **[ID Marketo klijenta, tajnu klijenta i ime hosta REST krajnje tačke](https://developers.marketo.com/rest-api/authentication/)**. Ime hosta REST krajnje tačke je samo ime hosta, bez `https://`. Primer: `xyz-abc-123.mktorest.com`. 

1. Izaberite **Slažem se** da biste potvrdili **Privatnost podataka i usklađenost** i izaberite **Poveži se** radi uspostavljanja veze sa uslugom Marketo.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Marketo. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. Unesite **[ID Marketo liste](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. ID liste je čisto numerička vrednost. Na primer, ako je vaš ID Marketo liste ST12345A7, uklonite znak pre i posle brojeva i unesite `12345`. 

1. U odeljku **Podudaranje podataka**, u polju **Adresa e-pošte** izaberite polje u objedinjenom profilu klijenta koje predstavlja e-adresu klijenta. 

1. Po želji možete da izvezete **Ime**, **Prezime**, **Grad**, **Država** i **Zemlja/region** da biste kreirali personalizovanije e-poruke. Izaberite **Dodaj atribut** za mapiranje ovih polja.

1. Izaberite segmente koje želite da izvezete. U usluzi Marketo možete ukupno izvesti do 1 milion korisničkih profila.

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). U usluzi Marketo sada možete pronaći segmente u odeljku [Marketo liste](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Marketo, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Marketo ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
