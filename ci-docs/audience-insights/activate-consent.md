---
title: Aktiviranje pravila saglasnosti za segmente
description: Sledite ove korake da biste povezali podatke o pristanku i aktivirali provere saglasnosti korisnici uvide. Administrator takođe može da onemogući provere pristanka.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 45899738d39bd5caa433e123f9fe59020e831998
ms.sourcegitcommit: 79b09498d1328e5551fb8684c44af1fb149f9881
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/10/2021
ms.locfileid: "7818787"
---
# <a name="activate-consent-rules"></a>Aktiviranje pravila pristanka

Centar [za saglasnost (pregled) vam](../consent-management/overview.md) pomaže da uskladite podatke o pristanku iz različitih izvora. Koristite *objedinjeni* entitet saglasnosti da biste primenili podrazumevane provere saglasnosti. Nakon uvoza podataka o saglasnosti u Centar za saglasnost i konfigurisanja pravila za podatke, entitet saglasnosti se automatski *sinhronizuje* sa korisnici uvidima.

## <a name="enable-consent-checks"></a>Omogući provere saglasnosti

Sa podacima o pristanku uvezenim u Centar za saglasnost (pregled) i podešenim pravilima, možete da omogućite proveru pristanka. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Kartica Pristanak korisnici postavke sa aktiviranim podacima o pristanku.":::

1. U uvidima o korisnicima idite na **Administrator** > **Sistem**.

1. Izaberite **karticu Saglasnost** (pregled).

1. U **odeljku Omogućavanje provere** saglasnosti postavite preklopnik **na** "Dalje" za sve oblasti koje želite da omogućite.

1. Potvrdite izbor **u polju za potvrdu Dozvoli za zamjenu** podrazumevanih pravila pristanka da biste uklonili podrazumevane provere saglasnosti koje se sprovode u određenom segmentu. 

1. U padajućem meniju izaberite gde želite da dozvolite zamenu.     

1. U **odeljku Povezivanje saglasnosti sa profilima** klijenata odaberite atribut koji se koristi kao identifikator za povezivanje podataka o pristanku sa podacima o klijentima. To će verovatno biti broj telefona ili e-adresa. 

1. Kliknite na **dugme** "Sačuvaj" da biste primenili postavke.

## <a name="disable-consent-checks"></a>Onemogući provere pristanka

Da bi prestao da koristi podatke o pristanku korisnici uvidima, administrator mora da ažurira postavke sistema u skladu sa tim.

1. U uvidima o korisnicima idite na **Administrator** > **Sistem**.

1. Izaberite **karticu Saglasnost** (pregled).

1. U odeljku **Omogućavanje provere** pristanka postavite preklopnik na **isključeno**.
