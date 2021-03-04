---
title: Izvezite Customer Insights podatke u Azure Data Lake Storage Gen2
description: Saznajte kako da konfigurišete vezu sa uslugom Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477196"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="3bfd0-103">Konektor za Azure Data Lake Storage Gen2 (pregled)</span><span class="sxs-lookup"><span data-stu-id="3bfd0-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="3bfd0-104">Skladištite podatke Customer Insights podataka u uslugu Azure Data Lake Storage Gen2 ili ih koristite za prenos podataka u druge aplikacije.</span><span class="sxs-lookup"><span data-stu-id="3bfd0-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="3bfd0-105">Konfigurišite konektor za Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="3bfd0-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="3bfd0-106">U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="3bfd0-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3bfd0-107">Uz odeljku **Azure Data Lake Storage Gen2** izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="3bfd0-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="3bfd0-108">Dajte odredištu prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="3bfd0-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="3bfd0-109">Unesite **Naziv poslovnog kontakta**, **Ključ poslovnog kontakta** i **Kontejner** za vaš Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="3bfd0-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="3bfd0-110">Da biste saznali kako da napravite nalog za skladištenje sa kojim ćete koristiti Azure Data Lake Storage Gen2, pogledajte članak [Kreiranje naloga za skladištenje](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="3bfd0-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="3bfd0-111">Da biste saznali više o tome kako da pronađete ime poslovnog kontakta za Azure Data Lake Gen2 skladište, pogledajte članak [Upravljanje podešavanjima naloga za skladištenje na Azure portalu](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="3bfd0-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="3bfd0-112">Izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="3bfd0-112">Select **Next**.</span></span>

1. <span data-ttu-id="3bfd0-113">Izaberite polje pored svakog entiteta koji želite da izvezete na ovo odredište.</span><span class="sxs-lookup"><span data-stu-id="3bfd0-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="3bfd0-114">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="3bfd0-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3bfd0-115">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="3bfd0-115">Export the data</span></span>

<span data-ttu-id="3bfd0-116">Možete da [izvezete podatke na zahtev](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3bfd0-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="3bfd0-117">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3bfd0-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
