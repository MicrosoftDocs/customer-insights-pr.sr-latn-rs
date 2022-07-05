---
title: Izvoz podataka u Salesforce Marketing Cloud (pregled)
description: Saznajte kako da konfigurišete vezu i izvezete je u Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c3a6a40d9b9f08c8ebca8cb4a9196a1a79f03afa
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082624"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Izvoz podataka u Salesforce Marketing Cloud (pregled)

Koristite podatke o klijentima u usluzi Salesforce Marketing Cloud tako što ćete ih izvesti putem lokacije protokola sigurnog prenosa datoteka (SFTP).

## <a name="prerequisites-for-connection"></a>Preduslovi za vezu

- Dostupnost SFTP hosta i odgovarajućih administratorskih akreditiva. [Kako postaviti SFTP lokacije za Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Podešavanje veze sa uslugom Salesforce Marketing Cloud

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i izaberite **Salesforce Marketing Cloud** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Navedite **korisničko ime**, **lozinku**, **ime hosta** i **fasciklu za izvoz** za SFTP nalog.

1. Izaberite **Verifikuj** da testirate vezu.

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka SFTP. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. Odaberite da li želite da izvezete podatke **spakovano** ili **raspakovano** i **separator polja** za izvezene datoteke.

1. Izaberite entitete, na primer segmente koje želite da izvezete.

   > [!NOTE]
   > Svaki izabrani entitet biće podeljen na do pet izlaznih datoteka prilikom izvoza. 

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Izvezite Customer Insights podatke u sa SFTP lokacije Salesforce Marketing Cloud

1. Kreirajte [proširenja podataka u usluzi Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) za uvoz Customer Insights datoteke podataka sa SFTP lokacije.

2. [Uvezite podatke sa SFTP lokacije](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) u Salesforce Marketing Cloud proširenje podataka. 

3. Podesite automatizaciju za uvoz podataka u proširenja podataka. Saznajte više o [automatizacijama otpuštanja datoteka i zakazanim automatizacijama](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definišite [automatizaciju otpuštanja datoteka](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ili [zakazanu automatizaciju](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Evo primera [automatizacije sa SFTP-om](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke putem SFTP-a, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da odredište za izvoz ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.

[!INCLUDE [footer-include](includes/footer-banner.md)]
