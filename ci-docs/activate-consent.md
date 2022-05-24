---
title: Aktiviranje pravila saglasnosti za segmente
description: Sledite ove korake da biste povezali podatke o pristanku i aktivirali provere saglasnosti Dynamics 365 Customer Insights. Administrator takođe može da onemogući provere pristanka.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755187"
---
# <a name="activate-consent-rules"></a>Aktiviranje pravila pristanka

Centar [za saglasnost (pregled) vam pomaže](consent-management/overview.md) da uskladite podatke o pristanku iz različitih izvora. Koristite objedinjeni *entitet* saglasnosti da biste primenili podrazumevane provere saglasnosti. Nakon uvoza podataka o pristanku i konfigurisanja pravila mape *, entitet* saglasnosti se automatski sinhronizuje sa programom Dynamics 365 Customer Insights.

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
