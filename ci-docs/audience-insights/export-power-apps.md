---
title: Power Apps konektor
description: Povežite se sa uslugama Power Apps i Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 18cc32a169e79794d2d3203d462620ab41efaafe
ms.sourcegitcommit: d168a738a08adb8b4b2e410bdaa3716d7b63cc9b
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455969"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps konektor (pregled)

Uvedite objedinjene korisničke profile u svoje personalizovane aplikacije pomoću programa Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Povežite Power Apps i Dynamics 365 Customer Insights

Customer Insights je jedan od mnogih [dostupnih izvora za podatke u programu Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Pogledajte Power Apps dokumentaciju da biste saznali kako da [dodate prenos podataka u aplikaciju](/powerapps/maker/canvas-apps/add-data-connection). Preporučujemo da takođe pregledate [kako Power Apps koristi delegiranje za obradu velikih skupova podataka u aplikacijama sa podlogom](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Dostupni entiteti

Kada dodate uslugu Customer Insights kao vezu za prenos podataka, možete izabrati sledeće entitete u programu Power Apps:

- **Klijent**: za korišćenje podataka iz [objedinjenog profila klijenta](customer-profiles.md).
- **UnifiedActivity**: da biste prikazali [vremensku osu aktivnosti](activities.md) u aplikaciji.
- **ContactProfile**: da biste prikazali kontakte klijenta. Ovaj entitet je dostupan samo u okruženjima uvida u ciljnu grupu za poslovne naloge.

## <a name="limitations"></a>Ograničenja

### <a name="retrievable-entities"></a>Povratni entiteti

Možete da preuzmete samo entitete **Klijent**, **UnifiedActivity**, **Segmenti** i **ContactProfile** kroz Power Apps konektor. ContactProfile je dostupan samo u instanci uvida u ciljnu grupu za poslovne naloge. Drugi entiteti se prikazuju jer ih osnovni konektor podržava kroz okidače u usluzi Power Automate.

Možete da uradite najviše 100 poziva na 60 sekundi. API možete da pozovete krajnja tačka više puta pomoću parametra $skip uređaja. [Saznajte više o $skip parametru](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegiranje

Delegiranje radi za entitet **Klijent** i entitet **UnifiedActivity**. 

- Delegiranje za entitet **Klijent**: Da biste koristili delegiranje za ovaj entitet, polja treba indeksirati u odeljku [Indeks pretrage i filtriranja](search-filter-index.md).  
- Delegiranje za entitet **Objedinjena aktivnost**: Delegiranje za ovaj entitet radi samo za polja **ActivityId** i **CustomerId**.  
- Delegiranje za **ContactProfile**: delegiranje za ovaj entitet funkcioniše samo za polja **ContactId** i **CustomerId**. ContactProfile je dostupan samo u okruženjima uvida u ciljnu grupu za poslovne naloge.

Za više informacija o delegiranju idite na [Power Apps prenosive funkcije i operacije](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Primer kontrole galerije

Možete dodati profile klijenata u [kontrolu galerije](/powerapps/maker/canvas-apps/add-gallery).

1. Dodajte kontrolu **Galerija** u aplikaciju koju gradite.

    > [!div class="mx-imgBorder"]
    > ![Dodajte element galerije.](media/connector-powerapps9.png "Dodajte element galerije.")

2. Izaberite **Klijent** kao izvor podataka za stavke.

    > [!div class="mx-imgBorder"]
    > ![Izaberite izvor podataka.](media/choose-datasource-powerapps.png "Izaberite izvor podataka.")

3. Možete da promenite tablu sa podacima na desnoj strani da biste izabrali polje koje će entitet Klijent prikazati u galeriji.

4. Ako želite da u galeriji prikažete bilo koje polje odabranog klijenta, popunite svojstvo **Tekst** oznake koristeći **{Name_of_the_gallery}.Selected.{property_name}**  
    - Na primer: _Gallery1.Selected.address1_city_

5. Da biste prikazali objedinjenu vremensku osu za klijenta, dodajte element galerije, pa dodajte svojstvo **Stavke** koristeći **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Na primer: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE[footer-include](../includes/footer-banner.md)]
