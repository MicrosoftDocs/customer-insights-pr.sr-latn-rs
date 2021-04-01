---
title: Power Apps konektor
description: Povežite se sa uslugama Power Apps i Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598172"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps konektor (pregled)

Uvedite objedinjene korisničke profile u svoje personalizovane aplikacije pomoću programa Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Povežite Power Apps i Dynamics 365 Customer Insights

Customer Insights je jedan od mnogih [dostupnih izvora za podatke u programu Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Pogledajte Power Apps dokumentaciju da biste saznali kako da [dodate prenos podataka u aplikaciju](/powerapps/maker/canvas-apps/add-data-connection). Preporučujemo da takođe pregledate [kako Power Apps koristi delegiranje za obradu velikih skupova podataka u aplikacijama sa podlogom](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Dostupni entiteti

Kada dodate uslugu Customer Insights kao vezu za prenos podataka, možete izabrati sledeće entitete u programu Power Apps:

- Klijent: da koristite podatke iz [objedinjenog profila klijenta](customer-profiles.md).
- UnifiedActivity: da prikazujete [vremensku osu aktivnosti](activities.md) u aplikaciji.

## <a name="limitations"></a>Ograničenja

### <a name="retrievable-entities"></a>Povratni entiteti

Možete da povratite samo entitete **Klijent**, **Objedinjena aktivnost** i **Segmenti** kroz Power Apps konektor. Drugi entiteti se prikazuju jer ih osnovni konektor podržava kroz okidače u usluzi Power Automate.  

### <a name="delegation"></a>Delegiranje

Delegiranje radi za entitet Klijent i entitet Objedinjena aktivnost. 

- Delegiranje za entitet **Klijent**: Da biste koristili delegiranje za ovaj entitet, polja treba indeksirati u odeljku [Indeks pretrage i filtriranja](search-filter-index.md).  

- Delegiranje za entitet **Objedinjena aktivnost**: Delegiranje za ovaj entitet radi samo za polja **ActivityId** i **CustomerId**.  

- Za više informacija o delegiranju, pogledajte [Power Apps prenosive funkcije i operacije](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Primer kontrole galerije

Na primer, dodajete profile klijenata u [kontrolu galerije](/powerapps/maker/canvas-apps/add-gallery).

1. Dodajte kontrolu **Galerija** u aplikaciju koju gradite.

> [!div class="mx-imgBorder"]
> ![Dodajte element galerije](media/connector-powerapps9.png "Dodajte element galerije")

1. Izaberite **Klijent** kao izvor podataka za stavke.

    > [!div class="mx-imgBorder"]
    > ![Izaberite izvor podataka](media/choose-datasource-powerapps.png "Izaberite izvor podataka")

1. Možete da promenite tablu sa podacima na desnoj strani da biste izabrali polje koje će entitet Klijent prikazati u galeriji.

1. Ako želite da u galeriji prikažete bilo koje polje odabranog klijenta, popunite svojstvo Tekst oznake: **{Name_of_the_gallery}.Selected.{property_name}**

    Primer: Gallery1.Selected.address1_city

1. Da biste prikazali objedinjenu vremensku osu za klijenta, dodajte element Galerija i dodajte svojstvo Stavke: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Primer: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]