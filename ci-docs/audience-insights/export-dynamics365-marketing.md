---
title: Izvezite Customer Insights podatke u Dynamics 365 Marketing
description: Saznajte kako da konfigurišete vezu sa uslugom Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597620"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Konektor za Dynamics 365 Marketing (pregled)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Koristite [segmente](segments.md) da biste generisali kampanje i kontaktirali određene grupe klijenata pomoću usluge Dynamics 365 Marketing. Više informacija potražite u članku [Korišćenje segmenata iz usluga Dynamics 365 Customer Insights uz Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Preduslov

- Zapisi kontakata moraju biti prisutni u usluzi Dynamics 365 Marketing da biste mogli da izvezete segment iz usluge Customer Insights u Marketing. Pročitajte više o tome kako se unose kontakti u [Dynamics 365 Marketing pomoću usluge Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Izvoz segmenata iz uvida o korisnicima u Marketing neće kreirati nove zapise kontakata u instancama usluge Marketing. Evidencija kontakata iz usluge Marketing mora se uneti u uvid o korisnicima i koristiti kao izvor podataka. Takođe ih treba uključiti u jedinstveni entitet klijenta da bi se ID-ovi klijenata mapirali u ID-ove kontakata da bi segmenti mogli da se izvezu.

## <a name="configure-the-connector-for-marketing"></a>Konfigurišite konektor za Marketing

1. U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.

1. U odeljku **Dynamics 365 Marketing** izaberite **Podesi**.

1. Dajte odredištu za izvoz prepoznatljivo ime u polju **Ime za prikaz**.

1. Unesite URL organizacije za Marketing u polje **Adresa servera**.

1. U odeljku **Administratorski nalog na serveru**, izaberite **Prijavite se** i izaberite Dynamics 365 Marketing nalog.

1. Mapirajte polje korisničkog ID-a sa Dynamics 365 ID-om kontakta.

1. Izaberite **Sledeće**.

1. Izaberite jedan ili više segmenata.

1. Izaberite stavku **Sačuvaj**.

## <a name="export-the-data"></a>Izvoz podataka

Možete da [izvezete podatke na zahtev](export-destinations.md). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]