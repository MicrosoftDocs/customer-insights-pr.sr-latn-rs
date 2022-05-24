---
title: Upravljanje podrazumevanim pravilima pristanka na segmente
description: Uz mogućnost upravljanja pristankom možete onemogućiti ili promeniti podrazumevana pravila pristanka ako su omogućena zamenivanja.
ms.date: 12/01/2021
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 764eeca9d99c95a34d9bd4c11d79f8b8e90701e2
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755233"
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
