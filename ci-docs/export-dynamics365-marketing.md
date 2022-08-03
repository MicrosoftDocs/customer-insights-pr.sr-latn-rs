---
title: Izvoz segmenata u Dynamics 365 marketing (pregled)
description: Saznajte kako da konfigurišete vezu i izvezete u Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196641"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Izvoz segmenata u Dynamics 365 marketing (pregled)

Koristite [segmente](segments.md) za generisanje kampanja i kontakt sa određenim grupama kupaca pomoću [Dynamics 365 marketinga](/dynamics365/marketing/customer-insights-segments).

Ako koristite nove mogućnosti usluge Dynamics 365 Marketing za orkestraciju puta koji pređe korisnik u realnom vremenu u Dataverse organizaciji, ne morate da kreirate standardni izvoz u Dynamics 365 Marketing. Kontakti i segmenti iz uvida klijenata dostupni su direktno u dynamics 365 marketingu nakon povezivanja marketinga i uvida kupaca. Pre nego što izbrišete postojeći izvoz, pregledajte dokumentaciju o tome kako [da povežete uvide klijenata i Dynamics 365 marketing put koji pređe korisnik orkestraciju](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Preduslov

Zapisi kontakata moraju biti prisutni u usluzi Dynamics 365 Marketing da biste mogli da izvezete segment iz usluge Customer Insights u Marketing. Pročitajte više o tome kako se unose kontakti u [Dynamics 365 Marketing pomoću usluge Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Izvoz segmenata iz uvida kupaca u marketing neće kreirati nove zapise kontakata u marketinškim instancama. Zapisi kontakata iz marketinga moraju biti uneti u uvide klijenata i koristiti se kao izvor podataka. Takođe ih treba uključiti u jedinstveni entitet klijenta da bi se ID-ovi klijenata mapirali u ID-ove kontakata da bi segmenti mogli da se izvezu.

## <a name="set-up-connection-to-marketing"></a>Podešavanje veze za Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **dodaj vezu** i odaberite **Dynamics 365 marketing**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite URL organizacije za Marketing u polje **Adresa servera**.

1. U odeljku **Administratorski nalog na serveru**, izaberite **Prijavite se** i izaberite Dynamics 365 Marketing nalog.

1. Mapiraj polje ID kontakta u entitetu kupca u Dynamics 365 ID kontakta.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Dynamics 365 Marketing. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Izaberite polje ID kontakta u entitetu kupca koje se podudara sa Dynamics 365 ID-om kontakta.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
