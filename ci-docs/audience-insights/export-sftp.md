---
title: Izvezite Customer Insights podatke u SFTP hostove
description: Naučite kako da konfigurišete vezu na SFTP hostom.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643520"
---
# <a name="connector-for-sftp-preview"></a>Konektor za SFTP (pregled)

Koristite podatke o klijentima u nezavisnim aplikacijama tako što ćete ih izvesti na Secure File Transfer Protocol (SFTP) host.

## <a name="prerequisites"></a>Preduslovi

- Dostupnost SFTP hosta i odgovarajućih akreditiva.

## <a name="connect-to-sftp"></a>Povezivanje na SFTP

1. Idite na **Administrator** > **Odredišta za izvoz**.

1. Pod **SFTP**, izaberite **Postavi**.

1. Dajte odredištu prepoznatljivo ime u polju **Ime za prikaz**.

1. Navedite **Korisničko ime**, **Lozinku** i **Ime hosta** za SFTP nalog. Primer: Ako je osnovnom direktorijum vašeg SFTP servera /root/folder, a želite da se podaci izvezu u /root/folder/ci_export_destination_folder, host treba da bude sftp://<server_address>/ci_export_destination_folder".

1. Izaberite **Verifikuj** da testirate vezu.

1. Nakon uspešne verifikacije, izaberite da li želite da izvezite svoje podatke kao **Komprimovanu datoteku** ili **Raspakovati datoteku**, a zatim izaberite **znak razgraničavanja polja** za izvezene datoteke.

1. Izaberite **Prihvatam** da biste potvrdili **Privatnost podataka i usaglašenost**.

1. Izaberite **Sledeće** da biste započeli konfigurisanje izvoza.

## <a name="configure-the-connection"></a>Konfigurisanje veze

1. Izaberite **atribute klijenta** koje želite da izvezete. Možete da izvezete jedan ili više atributa.

1. Izaberite **Sledeće**.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite stavku **Sačuvaj**.

## <a name="export-the-data"></a>Izvoz podataka

Možete da [izvezete podatke na zahtev](export-destinations.md). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke putem SFTP-a, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da odredište za izvoz ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.
