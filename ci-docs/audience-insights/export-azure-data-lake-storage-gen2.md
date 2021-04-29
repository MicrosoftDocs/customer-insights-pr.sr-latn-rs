---
title: Izvezite Customer Insights podatke u Azure Data Lake Storage Gen2
description: Saznajte kako da konfigurišete vezu sa uslugom Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760068"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="caacb-103">Podešavanje veze sa aplikacijom Azure Data Lake Storage Gen2 (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="caacb-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="caacb-104">Idite na **Administrator** > **Veze**.</span><span class="sxs-lookup"><span data-stu-id="caacb-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="caacb-105">Izaberite **Dodaj vezu** i birajte **Azure Data Lake Gen 2** da biste konfigurisali vezu.</span><span class="sxs-lookup"><span data-stu-id="caacb-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="caacb-106">Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="caacb-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="caacb-107">Ime za prikaz i vrsta veze opisuju ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="caacb-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="caacb-108">Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.</span><span class="sxs-lookup"><span data-stu-id="caacb-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="caacb-109">Odaberite ko može da koristi ovu vezu.</span><span class="sxs-lookup"><span data-stu-id="caacb-109">Choose who can use this connection.</span></span> <span data-ttu-id="caacb-110">Ako ništa ne preduzmete, podrazumevani će biti Administratori.</span><span class="sxs-lookup"><span data-stu-id="caacb-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="caacb-111">Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="caacb-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="caacb-112">Unesite **Naziv poslovnog kontakta**, **Ključ poslovnog kontakta** i **Kontejner** za vaš Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="caacb-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="caacb-113">Da biste saznali kako da napravite nalog za skladištenje sa kojim ćete koristiti Azure Data Lake Storage Gen2, pogledajte članak [Kreiranje naloga za skladištenje](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="caacb-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="caacb-114">Da biste saznali više o nazivu naloga Azure Data Lake Gen2 skladišta i ključu skladišta, pogledajte [Upravljanje podešavanjima naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="caacb-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="caacb-115">Izaberite **Sačuvaj** da biste kreirali vezu.</span><span class="sxs-lookup"><span data-stu-id="caacb-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="caacb-116">Konfigurisanje izvoza</span><span class="sxs-lookup"><span data-stu-id="caacb-116">Configure an export</span></span>

<span data-ttu-id="caacb-117">Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste.</span><span class="sxs-lookup"><span data-stu-id="caacb-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="caacb-118">Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="caacb-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="caacb-119">Idite na **Podaci** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="caacb-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="caacb-120">Da biste kreirali novi izvoz, izaberite **Dodaj izvoz**.</span><span class="sxs-lookup"><span data-stu-id="caacb-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="caacb-121">U polju **Veza za izvoz**, odaberite vezu iz odeljka **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="caacb-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="caacb-122">Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.</span><span class="sxs-lookup"><span data-stu-id="caacb-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="caacb-123">Izaberite polje pored svakog entiteta koji želite da izvezete na ovo odredište.</span><span class="sxs-lookup"><span data-stu-id="caacb-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="caacb-124">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="caacb-124">Select **Save**.</span></span>

<span data-ttu-id="caacb-125">Čuvanje izvoza ne pokreće izvoz odmah.</span><span class="sxs-lookup"><span data-stu-id="caacb-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="caacb-126">Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="caacb-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="caacb-127">Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="caacb-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="caacb-128">Izvezeni podaci se čuvaju u Azure Data Lake Gen 2 kontejneru za skladištenje koji ste konfigurisali.</span><span class="sxs-lookup"><span data-stu-id="caacb-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
