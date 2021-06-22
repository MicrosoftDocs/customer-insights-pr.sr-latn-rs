---
title: Izvoz Customer Insights podataka u Microsoft Advertising
description: Saznajte kako da konfigurišete vezu i izvezete sadržaj u Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124543"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Izvoz segmenata u Microsoft Advertising (verzija za pregled)

Izvezite Customer Insights segmente u Microsoft Advertising da biste kreirali ciljne grupe za podudaranje klijenata. Koristite ove ciljne grupe za svoje oglasne kampanje.

## <a name="prerequisites"></a>Preduslovi

-   Imate [Microsoft Advertising nalog](https://ads.microsoft.com/) i odgovarajuće akreditive administratora.
-   Prihvatili ste uslove korišćenja za podudaranje klijenata. 
-   [Konfigurisani segmenti](segments.md) u uvidima u ciljnu grupu.
-   Objedinjeni korisnički profili u izvezenim segmentima sadrže polje sa adresom e-pošte.

## <a name="known-limitations"></a>Poznata ograničenja

- Možete izvesti do 500.000 profila po izvozu u Microsoft Advertising.
- Izvoz u Microsoft Advertising ograničen je na segmente.
- Izvoz do 500.000 profila u Microsoft Advertising može potrajati do 10 minuta. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Podešavanje veze sa uslugom Microsoft Advertising

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **Microsoft Advertising** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Povežite se** da biste pokrenuli vezu sa uslugom Microsoft Advertising.

1. Izaberite **Potvrdi identitet pomoću usluge Microsoft Advertising** i obezbedite svoje administratorske akreditive za Microsoft Advertising.

1. Izaberite **Dodajte sebe kao korisnika za izvoz** i obezbedite svoje akreditive za Customer Insights.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Microsoft Advertising. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. Izaberite segmente za izvoz. Ciljne grupe za podudaranje klijenata u usluzi Microsoft Advertising automatski se kreira sa nazivom segmenata izabranih za izvoz. Svaki segment će rezultirati zasebnom ciljnom grupom za podudaranje klijenata. 

1. Unesite svoj **ID Microsoft Advertising klijenta i ID naloga**. Možete pronaći ID klijenta (`cid`) i ID poslovnog kontakta (`aid`) u parametrima URL adrese kada se prijavite u Microsoft Advertising.

1. U odeljku **Podudaranje podataka**, u polju **E-pošta**, izaberite polje u vašem objedinjenom profilu klijenta sa e-adresom klijenta. Potrebno je da izvezete segmente u Microsoft Advertising.

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite Dynamics 365 Customer Insights za prenos podataka u Microsoft Advertising, dozvoljavate prenos podataka izvan granica usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Microsoft Advertising ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.
