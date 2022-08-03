---
title: Power Apps konektor (pregled)
description: Povežite se sa uslugama Power Apps i Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196917"
---
# <a name="power-apps-connector-preview"></a>Power Apps konektor (pregled)

Uvedite objedinjene korisničke profile u svoje personalizovane aplikacije pomoću programa Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Povežite Power Apps i Dynamics 365 Customer Insights

Customer Insights je jedan od mnogih [dostupnih izvora za podatke u programu Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Pogledajte Power Apps dokumentaciju da biste saznali kako da [dodate prenos podataka u aplikaciju](/powerapps/maker/canvas-apps/add-data-connection). Preporučujemo da takođe pregledate [kako Power Apps koristi delegiranje za obradu velikih skupova podataka u aplikacijama sa podlogom](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Dostupni entiteti

Nakon dodavanja uvida klijenata kao podataka za povezivanje, odaberite sledeće entitete u Power Apps:

- **Klijent**: za korišćenje podataka iz [objedinjenog profila klijenta](customer-profiles.md).
- **UnifiedActivity**: da biste prikazali [vremensku osu aktivnosti](activities.md) u aplikaciji.
- **ContactProfile**: da biste prikazali kontakte klijenta. Ovaj entitet je dostupan samo u okruženjima uvida klijenata za poslovne naloge.

## <a name="limitations"></a>Ograničenja

### <a name="retrievable-entities"></a>Povratni entiteti

Možete da preuzmete samo entitete **Klijent**, **UnifiedActivity**, **Segmenti** i **ContactProfile** kroz Power Apps konektor. ContactProfile je dostupan samo u okruženjima "Uvidi kupaca" za poslovne naloge. Drugi entiteti se prikazuju jer ih osnovni konektor podržava kroz okidače u usluzi Power Automate.

Možete da uradite najviše 100 poziva na 60 sekundi. API možete da pozovete krajnja tačka više puta pomoću parametra $skip uređaja. [Saznajte više o $skip parametru](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegiranje

Delegiranje radi za entitet **Klijent** i entitet **UnifiedActivity**.

- Delegacija **za entitet** kupca: Da biste koristili delegiranje za ovaj entitet, polja treba indeksirati u indeksu [search & filter](search-filter-index.md).  
- Delegiranje za entitet **Objedinjena aktivnost**: Delegiranje za ovaj entitet radi samo za polja **ActivityId** i **CustomerId**.  
- Delegiranje za **ContactProfile**: delegiranje za ovaj entitet funkcioniše samo za polja **ContactId** i **CustomerId**. ContactProfile je dostupan samo u okruženjima "Uvidi kupaca" za poslovne naloge.

Za više informacija o delegiranju idite na [Power Apps prenosive funkcije i operacije](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Primer kontrole galerije

Opcionalno, dodajte profile klijenata kontroli [galerije](/powerapps/maker/canvas-apps/add-gallery).

1. Dodajte kontrolu **Galerija** u aplikaciju koju gradite.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Dodajte element galerije.":::

1. Izaberite **Klijent** kao izvor podataka za stavke.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Izaberite izvor podataka.":::

1. Promenite tablu sa podacima sa desne strane da biste izabrali polje koje će entitet kupca pokazati u galeriji.

1. Ako želite da u galeriji prikažete bilo koje polje odabranog klijenta, popunite svojstvo **Tekst** oznake koristeći **{Name_of_the_gallery}.Selected.{property_name}**  
    - Na primer: _Gallery1.Selected.address1_city_

1. Da biste prikazali objedinjenu vremensku osu za klijenta, dodajte element galerije, pa dodajte svojstvo **Stavke** koristeći **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Na primer: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
