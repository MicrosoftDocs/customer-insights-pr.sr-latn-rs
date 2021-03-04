---
title: Izvezite Customer Insights podatke u Dynamics 365 Sales
description: Saznajte kako da konfigurišete vezu sa uslugom Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269025"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Konektor za Dynamics 365 Sales (pregled)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Koristite podatke o klijentima da biste kreirali marketinške spiskove, pratili tokove posla i slali promocije sa uslugom Dynamics 365 Sales.

## <a name="prerequisite"></a>Preduslov

1. Zapisi kontakata moraju biti prisutni u usluzi Dynamics 365 Sales da biste mogli da izvezete segment iz usluge Customer Insights u Sales. Pročitajte više o tome kako se unose kontakti u [Dynamics 365 Sales pomoću usluge Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Izvoz segmenata iz uvida o korisnicima u Sales neće kreirati nove zapise kontakata u instancama usluge Sales. Evidencija kontakata iz usluge Sales mora se uneti u uvid o korisnicima i koristiti kao izvor podataka. Takođe ih treba uključiti u jedinstveni entitet klijenta da bi se ID-ovi klijenata mapirali u ID-ove kontakata da bi segmenti mogli da se izvezu.

## <a name="configure-the-connector-for-sales"></a>Konfigurišite konektor za Sales

1. U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.

1. U odeljku **Dynamics 365 Sales** izaberite **Podesi**.

1. Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.

1. Unesite URL organizacije za Sales u polje **Adresa servera**.

1. U odeljku **Administratorski nalog na serveru**, izaberite **Prijavite se** i izaberite Dynamics 365 Sales nalog.

1. Mapirajte polje korisničkog ID-a sa Dynamics 365 ID-om kontakta.

1. Izaberite **Sledeće**.

1. Izaberite jedan ili više segmenata.

1. Izaberite stavku **Sačuvaj**.

## <a name="export-the-data"></a>Izvoz podataka

Možete da [izvezete podatke na zahtev](export-destinations.md). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]