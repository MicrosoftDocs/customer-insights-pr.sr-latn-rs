---
title: Izvoz segmenata u Dynamics 365 prodaju (pregled)
description: Saznajte kako da konfigurišete vezu i izvezete u Dynamics 365 Sales.
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
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195998"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Izvoz segmenata u Dynamics 365 prodaju (pregled)

Koristite podatke o klijentima da biste kreirali marketinške spiskove, pratili tokove posla i slali promocije sa uslugom Dynamics 365 Sales.

## <a name="prerequisites"></a>Preduslovi

Zapisi kontakata moraju biti prisutni u usluzi Dynamics 365 Sales da biste mogli da izvezete segment iz usluge Customer Insights u Sales. Pročitajte više o tome kako da ugestite kontakte iz [sistema Dynamics 365 Prodaja koristeći Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Izvoz segmenata iz uvida kupca u prodaju neće kreirati nove zapise kontakata u instancama prodaje. Zapisi kontakata iz prodaje moraju biti uneti u uvide kupaca i koristiti se kao izvor podataka. Takođe ih treba uključiti u jedinstveni entitet klijenta da bi se ID-ovi klijenata mapirali u ID-ove kontakata da bi segmenti mogli da se izvezu.

## <a name="known-limitations"></a>Poznata ograničenja

Izvoz u Dynamics 365 Prodaja je ograničena na 100.000 po segmentu, što može potrajati do 3 sata.

## <a name="set-up-connection-to-sales"></a>Podešavanje veze sa prodajom

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i odaberite **Dynamics 365 prodaju**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite URL organizacije za Sales u polje **Adresa servera**.

1. U odeljku **Administratorski nalog na serveru**, izaberite **Prijavite se** i izaberite Dynamics 365 Sales nalog.

1. Mapirajte polje korisničkog ID-a sa Dynamics 365 ID-om kontakta.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Dynamics 365 Sales. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Izaberite polje ID kontakta u entitetu kupca koje se podudara sa Dynamics 365 ID-om kontakta.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite stavku **Sačuvaj**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
