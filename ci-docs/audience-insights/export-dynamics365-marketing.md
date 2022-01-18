---
title: Izvezite Customer Insights podatke u Dynamics 365 Marketing
description: Saznajte kako da konfigurišete vezu i izvezete u Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2c673c432f308efa289625a159de608d07f8d2b3
ms.sourcegitcommit: f988114ac7a288ccadf2db35b02dbef5cacea4d9
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 01/14/2022
ms.locfileid: "7975141"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Korišćenje segmenata u usluzi Dynamics 365 Marketing (verzija za pregled)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Koristite [segmente](segments.md) da biste generisali kampanje i kontaktirali određene grupe klijenata pomoću usluge Dynamics 365 Marketing. Više informacija potražite u članku [Korišćenje segmenata iz usluge Dynamics 365 Customer Insights u usluzi Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Ako koristite nove mogućnosti usluge Dynamics 365 Marketing za orkestraciju puta koji pređe korisnik u realnom vremenu u Dataverse organizaciji, ne morate da kreirate standardni izvoz u Dynamics 365 Marketing. Kontakti i segmenti iz uvida u ciljnu grupu dostupni su direktno u usluzi Dynamics 365 Marketing nakon povezivanja usluga Marketing i Customer Insights. Pre nego što izbrišete postojeće izvoze, pregledajte dokumentaciju o tome [kako da povežete uvide u ciljnu grupu i Dynamics 365 Marketing orkestraciju puta koji pređe korisnik](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Preduslov za vezu

- Zapisi kontakata moraju biti prisutni u usluzi Dynamics 365 Marketing da biste mogli da izvezete segment iz usluge Customer Insights u Marketing. Pročitajte više o tome kako se unose kontakti u [Dynamics 365 Marketing pomoću usluge Microsoft Dataverse](connect-power-query.md).

  > [!NOTE]
  > Izvoz segmenata iz uvida o korisnicima u Marketing neće kreirati nove zapise kontakata u instancama usluge Marketing. Evidencija kontakata iz usluge Marketing mora se uneti u uvid o korisnicima i koristiti kao izvor podataka. Takođe ih treba uključiti u jedinstveni entitet klijenta da bi se ID-ovi klijenata mapirali u ID-ove kontakata da bi segmenti mogli da se izvezu.

## <a name="set-up-connection-to-marketing"></a>Podešavanje veze za Marketing

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **Dynamics 365 Marketing** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite URL organizacije za Marketing u polje **Adresa servera**.

1. U odeljku **Administratorski nalog na serveru**, izaberite **Prijavite se** i izaberite Dynamics 365 Marketing nalog.

1. Mapiraj polje ID kontakta u entitetu kupca u Dynamics 365 ID kontakta.

1. Izaberite **Sačuvaj** da biste kreirali vezu. 

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Dynamics 365 Marketing. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. Izaberite jedan ili više segmenata.

1. Izaberite stavku **Sačuvaj**.

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
