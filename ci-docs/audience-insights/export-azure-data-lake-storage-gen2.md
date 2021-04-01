---
title: Izvezite Customer Insights podatke u Azure Data Lake Storage Gen2
description: Saznajte kako da konfigurišete vezu sa uslugom Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596655"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="a25b1-103">Konektor za Azure Data Lake Storage Gen2 (pregled)</span><span class="sxs-lookup"><span data-stu-id="a25b1-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="a25b1-104">Skladištite podatke Customer Insights podataka u uslugu Azure Data Lake Storage Gen2 ili ih koristite za prenos podataka u druge aplikacije.</span><span class="sxs-lookup"><span data-stu-id="a25b1-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="a25b1-105">Konfigurišite konektor za Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="a25b1-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="a25b1-106">U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="a25b1-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a25b1-107">Uz odeljku **Azure Data Lake Storage Gen2** izaberite **Podesi**.</span><span class="sxs-lookup"><span data-stu-id="a25b1-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="a25b1-108">Dajte odredištu prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="a25b1-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a25b1-109">Unesite **Naziv poslovnog kontakta**, **Ključ poslovnog kontakta** i **Kontejner** za vaš Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="a25b1-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="a25b1-110">Da biste saznali kako da napravite nalog za skladištenje sa kojim ćete koristiti Azure Data Lake Storage Gen2, pogledajte članak [Kreiranje naloga za skladištenje](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="a25b1-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="a25b1-111">Da biste saznali više o tome kako da pronađete ime poslovnog kontakta za Azure Data Lake Gen2 skladište, pogledajte članak [Upravljanje podešavanjima naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="a25b1-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="a25b1-112">Izaberite **Sledeće**.</span><span class="sxs-lookup"><span data-stu-id="a25b1-112">Select **Next**.</span></span>

1. <span data-ttu-id="a25b1-113">Izaberite polje pored svakog entiteta koji želite da izvezete na ovo odredište.</span><span class="sxs-lookup"><span data-stu-id="a25b1-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="a25b1-114">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="a25b1-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a25b1-115">Izvoz podataka</span><span class="sxs-lookup"><span data-stu-id="a25b1-115">Export the data</span></span>

<span data-ttu-id="a25b1-116">Možete da [izvezete podatke na zahtev](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a25b1-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="a25b1-117">Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a25b1-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>