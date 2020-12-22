---
title: Inkrementalno osvežavanje za izvore podataka zasnovane na usluzi Power Query
description: Osvežite nove i ažurirane podatke za velike izvore podataka na osnovu usluge Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406811"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="7cc44-103">Inkrementalno osvežavanje za izvore podataka zasnovane na usluzi Power Query</span><span class="sxs-lookup"><span data-stu-id="7cc44-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="7cc44-104">Inkrementalno osvežavanje izvora podataka pruža sledeće prednosti:</span><span class="sxs-lookup"><span data-stu-id="7cc44-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="7cc44-105">**Brža osvežavanja** – Osvežavaju se samo podaci koji su promenjeni.</span><span class="sxs-lookup"><span data-stu-id="7cc44-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="7cc44-106">Na primer, možete da osvežite samo proteklih pet dana skupa podataka iz prethodnog perioda.</span><span class="sxs-lookup"><span data-stu-id="7cc44-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="7cc44-107">**Povećana pouzdanost** – Uz manje osvežavanja, ne morate dugo da održavate veze sa sistemima sa promenljivim izvorima, smanjujući rizik od problema sa povezivanjem.</span><span class="sxs-lookup"><span data-stu-id="7cc44-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="7cc44-108">**Smanjena potrošnja resursa** – Osvežavanje samo podskupa ukupnih podataka dovodi do efikasnijeg korišćenja računarskih resursa i smanjenja uticaja na životnu sredinu.</span><span class="sxs-lookup"><span data-stu-id="7cc44-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="7cc44-109">Konfigurisanje postepenog osvežavanja</span><span class="sxs-lookup"><span data-stu-id="7cc44-109">Configure incremental refresh</span></span>

<span data-ttu-id="7cc44-110">Uvidi o korisnicima omogućavaju inkrementalno osvežavanje za izvore podataka uvezene preko usluge Power Query koja podržava inkrementalni unos.</span><span class="sxs-lookup"><span data-stu-id="7cc44-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="7cc44-111">Na primer, Azure SQL baze podataka sa poljima datuma i vremena, koja pokazuju kada su zapisi datuma poslednji put ažurirani.</span><span class="sxs-lookup"><span data-stu-id="7cc44-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="7cc44-112">[Napravite novi izvor podataka na osnovu usluge Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="7cc44-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="7cc44-113">Navedite naziv za izvor podataka.</span><span class="sxs-lookup"><span data-stu-id="7cc44-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="7cc44-114">Izaberite izvor podataka koji podržava postepeno osvežavanje, kao što je Azure SQL baza podataka.</span><span class="sxs-lookup"><span data-stu-id="7cc44-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="7cc44-115">Izaberite entitete ili tabele za unos.</span><span class="sxs-lookup"><span data-stu-id="7cc44-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="7cc44-116">Dovršite korake transformacije i izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="7cc44-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="7cc44-117">U dijalogu **Podesite postepeno osvežavanje** izaberite **Podesi** da otvorite **Podešavanja postepenog osvežavanja**.</span><span class="sxs-lookup"><span data-stu-id="7cc44-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="7cc44-118">Ako izaberete **Preskoči**, izvor podataka će osvežiti celokupni skup podataka.</span><span class="sxs-lookup"><span data-stu-id="7cc44-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="7cc44-119">Kasnije možete primeniti i postepeno osvežavanje uređivanjem postojećeg izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="7cc44-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="7cc44-120">U **podešavanjima postepenog osvežavanja**, konfigurisaćete postepeno osvežavanje za sve entitete koje ste izabrali prilikom kreiranja izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="7cc44-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7cc44-121">![Konfigurisanje entiteta u izvoru podataka za postepeno osvežavanje](media/incremental-refresh-settings.png "Konfigurisanje entiteta u izvoru podataka za postepeno osvežavanje")</span><span class="sxs-lookup"><span data-stu-id="7cc44-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="7cc44-122">Izaberite entitet i navedite sledeće detalje:</span><span class="sxs-lookup"><span data-stu-id="7cc44-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="7cc44-123">**Definišite primarni ključ**: Izaberite primarni ključ entiteta ili tabele.</span><span class="sxs-lookup"><span data-stu-id="7cc44-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="7cc44-124">**Definišite polje „poslednji put ažurirano“**: Ovo polje će prikazivati samo atribute tipa datuma ili vremena.</span><span class="sxs-lookup"><span data-stu-id="7cc44-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="7cc44-125">Izaberite atribut koji pokazuje kada su zapisi poslednji put ažurirani.</span><span class="sxs-lookup"><span data-stu-id="7cc44-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="7cc44-126">Koristiće se za identifikaciju zapisa koji spadaju u vremenski okvir za inkrementalno osvežavanje.</span><span class="sxs-lookup"><span data-stu-id="7cc44-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="7cc44-127">**Proveri da li postoje ispravke na svakih**: Navedite koliko dug vremenski okvir za postepeno osvežavanje želite da bude.</span><span class="sxs-lookup"><span data-stu-id="7cc44-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="7cc44-128">Izaberite **Sačuvaj** da biste dovršili kreiranje izvora podataka.</span><span class="sxs-lookup"><span data-stu-id="7cc44-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="7cc44-129">Početno osvežavanje podataka biće potpuno osveženje.</span><span class="sxs-lookup"><span data-stu-id="7cc44-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="7cc44-130">Nakon toga, inkrementalno osvežavanje podataka dešava se kao što je konfigurisano u prethodnom koraku.</span><span class="sxs-lookup"><span data-stu-id="7cc44-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
