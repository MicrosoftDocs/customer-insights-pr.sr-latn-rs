---
title: Robot za Microsoft Teams
description: Potražite objedinjene profile klijenata u usluzi Microsoft Teams uz pomoć robota.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267969"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="142c1-103">Teams robot za Dynamics 365 Customer Insights (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="142c1-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="142c1-104">Povežite se sa uslugom Microsoft Teams da biste dozvolili robotu da traži objedinjene profile klijenata na Teams kanalima.</span><span class="sxs-lookup"><span data-stu-id="142c1-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="142c1-105">![Teams robot koji prikazuje zapis klijenta](media/teams-bot.png "Teams robot koji prikazuje zapis klijenta")</span><span class="sxs-lookup"><span data-stu-id="142c1-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="142c1-106">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="142c1-106">Prerequisites</span></span>

<span data-ttu-id="142c1-107">Da biste postavili i konfigurisali robota, moraju se ispuniti sledeći preduslovi:</span><span class="sxs-lookup"><span data-stu-id="142c1-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="142c1-108">Postoji bar jedan [dodat izvor podataka](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="142c1-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="142c1-109">[Proces objedinjavanja](data-unification.md) je dovršen.</span><span class="sxs-lookup"><span data-stu-id="142c1-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="142c1-110">Polja su dodata u [indeks pretrage i filtera](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="142c1-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="142c1-111">Customer Insights i Teams su u istoj organizaciji.</span><span class="sxs-lookup"><span data-stu-id="142c1-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="142c1-112">Konfigurisanje robota</span><span class="sxs-lookup"><span data-stu-id="142c1-112">Configure the bot</span></span>

1. <span data-ttu-id="142c1-113">U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="142c1-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="142c1-114">Na pločici Microsoft Teams izaberite **Postaviti**.</span><span class="sxs-lookup"><span data-stu-id="142c1-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="142c1-115">Preusmereni ste na oblast **Aplikacije** u usluzi Teams.</span><span class="sxs-lookup"><span data-stu-id="142c1-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="142c1-116">Takođe možete otvoriti Teams i izabrati **Aplikacije** u donjem levom uglu ili ga direktno [preuzeti sa lokacije AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="142c1-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="142c1-117">Potražite **Customer Insights** i izaberite aplikaciju.</span><span class="sxs-lookup"><span data-stu-id="142c1-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="142c1-118">Izaberite **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="142c1-118">Select **Add**.</span></span>
1. <span data-ttu-id="142c1-119">Kada se prijavite u Customer Insights u usluzi Teams, videćete poruku dobrodošlice i tada možete početi.</span><span class="sxs-lookup"><span data-stu-id="142c1-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="142c1-120">Stvari koje možete da uradite uz robota</span><span class="sxs-lookup"><span data-stu-id="142c1-120">Things you can do with the bot</span></span>

<span data-ttu-id="142c1-121">Robot pruža mogućnosti pronalaženja za objedinjene profile klijenata.</span><span class="sxs-lookup"><span data-stu-id="142c1-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="142c1-122">Unesite **pretraga** nakon čega sledi ime, adresa e-pošte ili bilo koje drugo polje na objedinjenom profilu klijenta koje se dodaje indeksu pretrage i filtera.</span><span class="sxs-lookup"><span data-stu-id="142c1-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="142c1-123">Dobićete karticu sa do 15 polja iz rezultujućeg profila klijenta.</span><span class="sxs-lookup"><span data-stu-id="142c1-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="142c1-124">Više podudaranja vraća listu rezultata na kojima možete odabrati profil.</span><span class="sxs-lookup"><span data-stu-id="142c1-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="142c1-125">Možete dodati termin za pretragu u dvostrukim navodnicima da biste potražili tačno podudaranje.</span><span class="sxs-lookup"><span data-stu-id="142c1-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="142c1-126">Ako vaša organizacija održava više Customer Insights okruženja u istoj organizaciji, možete da unesete **switchinstance** da biste izabrali sa kojim okruženjem želite da povežete robota.</span><span class="sxs-lookup"><span data-stu-id="142c1-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="142c1-127">Unesite **pomoć** da biste videli listu dostupnih komandi za robota.</span><span class="sxs-lookup"><span data-stu-id="142c1-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]