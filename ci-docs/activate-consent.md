---
title: Aktiviranje pravila saglasnosti za segmente
description: Sledite ove korake da biste povezali podatke o pristanku i aktivirali provere saglasnosti Dynamics 365 Customer Insights. Administrator takođe može da onemogući provere pristanka.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bfa03f4b7b56b300a74ebd04721cd64b893879f1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643119"
---
# <a name="activate-consent-rules"></a>Aktiviranje pravila pristanka

Centar [za saglasnost (pregled) vam pomaže](consent-management/overview.md) da uskladite podatke o pristanku iz različitih izvora. Koristite objedinjeni *entitet* saglasnosti da biste primenili podrazumevane provere saglasnosti. Nakon uvoza podataka o saglasnosti u Centar za saglasnost i konfigurisanja pravila za podatke, *entitet* saglasnosti se automatski sinhronizuje sa programom Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Omogući provere saglasnosti

Sa podacima o pristanku uvezenim u Centar za saglasnost (pregled) i podešenim pravilima, možete da omogućite proveru pristanka. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Kartica &quot;Saglasnost&quot; u postavkama &quot;Uvid u kupce&quot; sa aktiviranim podacima o pristanku.":::

1. U usluzi Customer Insights idite na **Administrator** > **Sistem**.

1. Izaberite karticu **Saglasnost (pregled**).

1. U odeljku **Omogućavanje provere** saglasnosti postavite preklopnik na **"Dalje** " za sve oblasti koje želite da omogućite.

1. Potvrdite izbor **u polju za potvrdu Dozvoli za zamjenu podrazumevanih** pravila pristanka da biste uklonili podrazumevane provere saglasnosti koje se sprovode u određenom segmentu. 

1. U padajućem meniju izaberite gde želite da dozvolite zamenu.     

1. U odeljku **Povezivanje saglasnosti sa profilima klijenata** odaberite atribut koji se koristi kao identifikator za povezivanje podataka o pristanku sa podacima o klijentima. To će verovatno biti broj telefona ili e-adresa. 

1. Kliknite na **dugme "** Sačuvaj" da biste primenili postavke.

## <a name="disable-consent-checks"></a>Onemogući provere pristanka

Da bi prestao da koristi podatke o pristanku u programu Customer Insights, administrator mora da ažurira postavke sistema u skladu sa tim.

1. U usluzi Customer Insights idite na **Administrator** > **Sistem**.

1. Izaberite karticu **Saglasnost (pregled**).

1. U odeljku **Omogućavanje provere pristanka** postavite preklopnik na **isključeno**.

> [!TIP]
> Da biste prestali da koristite mogućnost upravljanja pristankom, pogledajte [postavke sistema u Centru za saglasnost (pregled)](consent-management/system-settings.md).
