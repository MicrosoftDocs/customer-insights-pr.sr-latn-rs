---
title: Entiteti i skupovi podataka
description: Pogledajte podatke na stranici Entiteti.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406787"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="7f1a9-103">Entiteti u uvidima o korisnicima</span><span class="sxs-lookup"><span data-stu-id="7f1a9-103">Entities in audience insights</span></span>

<span data-ttu-id="7f1a9-104">Kada [konfigurišete izvore podataka](data-sources.md), idite na stranicu **Entiteti** da procenite kvalitet unetih podataka.</span><span class="sxs-lookup"><span data-stu-id="7f1a9-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="7f1a9-105">Entiteti se smatraju skupovima podataka.</span><span class="sxs-lookup"><span data-stu-id="7f1a9-105">Entities are considered datasets.</span></span> <span data-ttu-id="7f1a9-106">Više mogućnosti usluge Dynamics 365 Customer Insights napravljeno je na osnovu ovih entiteta.</span><span class="sxs-lookup"><span data-stu-id="7f1a9-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="7f1a9-107">Njihov pažljiv pregled može vam pomoći da potvrdite valjanost ishoda tih mogućnosti.</span><span class="sxs-lookup"><span data-stu-id="7f1a9-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="7f1a9-108">Stranica **Entiteti** navodi entitete i sadrži nekoliko kolona:</span><span class="sxs-lookup"><span data-stu-id="7f1a9-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="7f1a9-109">**Naziv**: Naziv vašeg entiteta podataka.</span><span class="sxs-lookup"><span data-stu-id="7f1a9-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="7f1a9-110">Ako vidite simbol upozorenja pored naziva entiteta, to znači da se podaci za taj entitet nisu uspešno učitali.</span><span class="sxs-lookup"><span data-stu-id="7f1a9-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="7f1a9-111">**Izvor**: Vrsta izvora podataka koji su uneti u entitet</span><span class="sxs-lookup"><span data-stu-id="7f1a9-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="7f1a9-112">**Autor**: Ime osobe koja je kreirala entitet</span><span class="sxs-lookup"><span data-stu-id="7f1a9-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="7f1a9-113">**Kreirano**: Datum i vreme stvaranja entiteta</span><span class="sxs-lookup"><span data-stu-id="7f1a9-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="7f1a9-114">**Autor izmene**: Ime osobe koja je ažurirala entitet</span><span class="sxs-lookup"><span data-stu-id="7f1a9-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="7f1a9-115">**Vreme poslednje izmene**: Datum i vreme poslednjeg ažuriranja entiteta</span><span class="sxs-lookup"><span data-stu-id="7f1a9-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="7f1a9-116">**Poslednje osvežavanje**: Datum i vreme poslednjeg osvežavanja podataka</span><span class="sxs-lookup"><span data-stu-id="7f1a9-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="7f1a9-117">Istraživanje podataka određenog entiteta</span><span class="sxs-lookup"><span data-stu-id="7f1a9-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="7f1a9-118">Izaberite entitet da biste istražili različita polja i zapise koji su uključeni u taj entitet.</span><span class="sxs-lookup"><span data-stu-id="7f1a9-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7f1a9-119">![Izaberite entitet](media/data-manager-entities-data.png "Izaberite entitet")</span><span class="sxs-lookup"><span data-stu-id="7f1a9-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="7f1a9-120">Kartica **Podaci** je podrazumevano izabrana i prikazuje tabelu u kojoj su navedeni detalji o pojedinačnim zapisima entiteta.</span><span class="sxs-lookup"><span data-stu-id="7f1a9-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7f1a9-121">![Tabela polja](media/data-manager-entities-fields.PNG "Tabela polja")</span><span class="sxs-lookup"><span data-stu-id="7f1a9-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="7f1a9-122">Kartica **Polja** prikazuje tabelu za pregled detalja za odabrani entitet, kao što su imena polja, tipovi podataka i tipovi.</span><span class="sxs-lookup"><span data-stu-id="7f1a9-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="7f1a9-123">Kolona **Tip** prikazuje tipove povezane sa Common Data Model, koje sistem automatski prepoznaje ili ih korisnici [ručno mapiraju](map-entities.md).</span><span class="sxs-lookup"><span data-stu-id="7f1a9-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="7f1a9-124">Ovo su semantički tipovi koji se mogu razlikovati od tipova podataka atributa – na primer, polje *E-pošta* u nastavku je tipa podataka *Tekst*, ali njegov (semantički) Common Data Model tip može biti *E-pošta* ili *Adresa e-pošte*.</span><span class="sxs-lookup"><span data-stu-id="7f1a9-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="7f1a9-125">Obe tabele prikazuju samo uzorak podataka vašeg entiteta.</span><span class="sxs-lookup"><span data-stu-id="7f1a9-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="7f1a9-126">Da biste videli ceo skup podataka, idite na stranicu **Izvori podataka**, izaberite entitet, izaberite **Uredi**, a zatim pregledajte podatke ovog entiteta pomoću Power Query uređivača, kao što je objašnjeno u članku [Izvori podataka](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="7f1a9-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="7f1a9-127">Da biste saznali više o podacima koji se unose u entitet, kolona **Rezime** vam pruža neke važne karakteristike podataka, kao što su polja bez vrednosti, nedostajuće vrednosti, jedinstvene vrednosti, brojevi i distribucije, kako je već primenjivo na podatke.</span><span class="sxs-lookup"><span data-stu-id="7f1a9-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="7f1a9-128">Izaberite ikonu grafikona da biste videli rezime podataka.</span><span class="sxs-lookup"><span data-stu-id="7f1a9-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7f1a9-129">![Simbol rezimea](media/data-manager-entities-summary.png "Tabela sa rezimeom podataka")</span><span class="sxs-lookup"><span data-stu-id="7f1a9-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="7f1a9-130">Sledeći korak</span><span class="sxs-lookup"><span data-stu-id="7f1a9-130">Next step</span></span>

<span data-ttu-id="7f1a9-131">Pogledajte temu [Ujednačavanje](data-unification.md) da biste saznali kako da *mapirate*, *podudarate* i *spajate* unete podatke.</span><span class="sxs-lookup"><span data-stu-id="7f1a9-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>
