---
title: Izvezite Customer Insights podatke u SFTP hostove
description: Naučite kako da konfigurišete vezu na SFTP hostom.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268015"
---
# <a name="connector-for-sftp-preview"></a>Konektor za SFTP (pregled)

Koristite podatke o klijentima u nezavisnim aplikacijama tako što ćete ih izvesti na Secure File Transfer Protocol (SFTP) host.

## <a name="prerequisites"></a>Preduslovi

- Dostupnost SFTP hosta i odgovarajućih akreditiva.

## <a name="connect-to-sftp"></a>Povezivanje sa SFTP

1. Idite na **Administrator** > **Odredišta za izvoz**.

1. Pod **SFTP**, izaberite **Postavi**.

1. Dajte odredištu prepoznatljivo ime u polju **Ime za prikaz**.

1. Navedite **korisničko ime**, **lozinku**, **ime hosta** i **fasciklu za izvoz** za SFTP nalog.

1. Izaberite **Verifikuj** da testirate vezu.

1. Nakon uspešne verifikacije, izaberite da li želite da izvezete podatke u obliku **Gzipped** ili **Raspakovano** i izaberite **graničnik polja** za izvezene datoteke.

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Sledeće** da biste započeli konfigurisanje izvoza.

## <a name="configure-the-export"></a>Konfigurisanje izvoza

1. Izaberite entitete, na primer segmente koje želite da izvezete.

   > [!NOTE]
   > Svaki izabrani entitet će imati do pet izlaznih datoteka prilikom izvoza. 

1. Izaberite stavku **Sačuvaj**.

## <a name="export-the-data"></a>Izvoz podataka

Možete da [izvezete podatke na zahtev](export-destinations.md). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).

## <a name="known-limitations"></a>Poznata ograničenja

- Vreme izvoženja zavisi od performansi vašeg sistema. Preporučujemo dva jezgra procesora i 1 GB memorije kao minimalnu konfiguraciju vašeg servera. 
- Izvoz entiteta sa do 100 miliona korisničkih profila može potrajati 90 minuta kada se koristi preporučena minimalna konfiguracija sa dva jezgra procesora i 1 GB memorije. 

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke putem SFTP-a, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da odredište za izvoz ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]