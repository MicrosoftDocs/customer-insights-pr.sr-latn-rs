---
title: Upravljanje podrazumevanim pravilima pristanka na segmente
description: Uz mogućnost upravljanja pristankom možete onemogućiti ili promeniti podrazumevana pravila pristanka ako su omogućena zamenivanja.
ms.date: 12/01/2021
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 43f03ea97765e112a8ea2a7da97cc548c8c84dfc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643209"
---
# <a name="disable-or-change-default-consent-rules"></a>Onemogućavanje ili menjanje podrazumevanih pravila pristanka

Ako vaše organizacije koriste mogućnost upravljanja [pristankom sa](consent-management/overview.md), Dynamics 365 Customer Insights administratori [mogu da primene pravila saglasnosti](activate-consent.md) za segmente. 

Uz primenjena pravila saglasnosti u oblasti segmenta, svaki segment obaveštava o stanju provere saglasnosti i pravila. Ako je dozvoljeno zamenu, podrazumevana pravila pristanka su isključena za određene segmente. Svaki autor segmenta može da doda još pravila pristanka povrh podrazumevanih pravila segmentu. 

## <a name="for-administrators"></a>Za administratore

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Izrada segmenta sa opcijama pravila saglasnosti.":::

**Da biste deaktivirali podrazumevana pravila pristanka:**

1. U obaveštenju **o pravilima** saglasnosti izaberite **pogledajte detalje**. 

1. Postavite podrazumevana **pravila pristanka preklopnik** na **isključeno**.

**Da biste dodali još pravila pristanka:**

1. U obaveštenju **o pravilima** saglasnosti izaberite **pogledajte detalje**. 

1. Izaberite **opciju Dodaj pravila pristanka** i odaberite pravilo saglasnosti iz padajuće **listu sa tipom podataka** "Izaberi saglasnost".

1. Kliknite **na** dugme "Sačuvaj" da biste primenili novo pravilo na segment.

## <a name="for-contributors"></a>Za saradnike

Da biste kreirali segment bez primenjenih pravila pristanka, morate da radite sa administratorom da biste ih onemogućili u segmentu. Međutim, možete da dodate sopstvena pravila pristanka segmentima koje posedujete i kojima upravljate.

To je proces od tri koraka: 
1. [Kreirajte segment u fascikli](segments.md) "Uvidi kupaca" i sačuvajte ga. 

1. Delite ime segmenta sa administratorom i zamolite ih [da omoguće premošćište za vaš segment](activate-consent.md). 

1. Ponovo otvorite segmente. U obaveštenju **o pravilima** saglasnosti izaberite pogledajte **detalje** i dodajte pravila saglasnosti koja želite da primenite. Zatim sačuvajte **i** **pokrenite** svoj segment.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
