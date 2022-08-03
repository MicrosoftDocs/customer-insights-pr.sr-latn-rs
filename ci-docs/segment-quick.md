---
title: Kreiranje jednostavnih segmenata pomoću brzih segmenata
description: Kreirajte jednostavne segmente kupaca da biste ih grupisanje na osnovu različitih atributa.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171164"
---
# <a name="create-simple-segments-with-quick-segments"></a>Kreiranje jednostavnih segmenata pomoću brzih segmenata

Brzi segmenti vam omogućavaju brzu izgradnju jednostavnih segmenata pomoću jednog operatora za brže uvide. Brzi segmenti su podržani samo u okruženjima za **individualne klijente**.

## <a name="create-a-new-segment-with-quick-segments"></a>Kreiranje novog segmenta pomoću brzih segmenata

1. Idite na **Segmenti**.

1. Izaberite **stavku Novo** > **kreiranje iz**.
   - Izaberite opciju **Profili** da izgradite segment koji je zasnovan na entitetu *objedinjenog klijenta*.
   - Izaberite opciju **Mere** za izgradnju segmenta oko mera koje ste prethodno kreirali.
   - Izaberite opciju **Obaveštavanje** da izgradite segment oko jednog od izlaznih entiteta koje ste generisali koristeći mogućnosti **Predviđanja** ili **Prilagođeni modeli**.

1. U dijalogu **Novi brzi segment** izaberite atribut iz padajuće liste **Polje**. Na osnovu vaše selekcije, sistem obezbeđuje različite vrednosti.
   - Za kategorična polja prikazuje se 10 najboljih računa kupaca. Odaberite **Vrednost** i izabrali **Pregled**.
   - Za numerički atribut, sistem prikazuje koja vrednost atributa spada u percentil svakog kupca. Odaberite **Operator** i **Vrednost**, a zatim izaberite **Pregled**.

1. Sistem obezbeđuje procenjenu **veličinu segmenta**. Odaberite da li želite da generišete segment koji ste definisali ili se vratite da odaberete drugo polje.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Naziv i procena za brzi segment.":::

1. Navedite **ime** i **ime izlaznog entiteta** za segment. Opcionalno, dodajte [oznake](work-with-tags-columns.md#manage-tags).

1. Izaberite **Sačuvaj** da biste kreirali segment. Prikazaće **se stranica "** Segmenti".

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Sledeći koraci

[Izvezite segment](export-destinations.md) i istražite članak [Integracija korisničke kartice](customer-card-add-in.md) da biste koristili segmente u drugim aplikacijama.

[!INCLUDE [footer-include](includes/footer-banner.md)]
