---
title: Obogaćivanje uz SFTP prilagođeni uvoz
description: Opšte informacije o obogaćivanju SFTP prilagođenog uvoza.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568495"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="85e76-103">Obogatite profile klijenata uz prilagođene podatke (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="85e76-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="85e76-104">Secure File Transfer Protocol (SFTP) prilagođeni uvoz vam omogućava da uvezete podatke koji ne moraju da prolaze kroz proces objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="85e76-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="85e76-105">To je fleksibilan, siguran i lak način unosa podataka.</span><span class="sxs-lookup"><span data-stu-id="85e76-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="85e76-106">SFTP prilagođeni uvoz se može koristiti u kombinaciji sa [SFTP izvozom](export-sftp.md) koji vam omogućava izvoz podataka o profilu klijenata potrebnih za obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="85e76-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="85e76-107">Podaci se zatim mogu obraditi, obogatiti i SFTP prilagođeni uvoz može se koristiti za vraćanje obogaćenih podataka u mogućnost uvida o korisnicima usluge Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="85e76-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="85e76-108">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="85e76-108">Prerequisites</span></span>

<span data-ttu-id="85e76-109">Da biste konfigurisali SFTP prilagođeni uvoz, moraju biti ispunjeni sledeći preduslovi:</span><span class="sxs-lookup"><span data-stu-id="85e76-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="85e76-110">Imate korisničke akreditive (korisničko ime i lozinku) za SFTP lokaciju odakle će se podaci uvoziti.</span><span class="sxs-lookup"><span data-stu-id="85e76-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="85e76-111">Imate URL i broj porta (obično 22) za STFP host.</span><span class="sxs-lookup"><span data-stu-id="85e76-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="85e76-112">Imate ime datoteke i lokaciju datoteke koju treba uvesti na SFTP host.</span><span class="sxs-lookup"><span data-stu-id="85e76-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="85e76-113">Postoji *model.json* datoteka koja navodi šemu za podatke koji se uvoze.</span><span class="sxs-lookup"><span data-stu-id="85e76-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="85e76-114">Ova datoteka mora biti u istom direktorijumu kao i datoteka koju treba uvesti.</span><span class="sxs-lookup"><span data-stu-id="85e76-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="85e76-115">Imate [administratorsku](permissions.md#administrator) dozvolu.</span><span class="sxs-lookup"><span data-stu-id="85e76-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="85e76-116">Konfigurisanje</span><span class="sxs-lookup"><span data-stu-id="85e76-116">Configuration</span></span>

1. <span data-ttu-id="85e76-117">Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.</span><span class="sxs-lookup"><span data-stu-id="85e76-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="85e76-118">Na **pločici SFTP prilagođenog uvoza**, izaberite **Obogati moje podatke**.</span><span class="sxs-lookup"><span data-stu-id="85e76-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="85e76-119">![Pločica SFTP prilagođenog uvoza](media/SFTP_Custom_Import_tile.png "Pločica SFTP prilagođenog uvoza")</span><span class="sxs-lookup"><span data-stu-id="85e76-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="85e76-120">Izaberite **Započnite** i navedite akreditive i adresu za SFTP server.</span><span class="sxs-lookup"><span data-stu-id="85e76-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="85e76-121">Na primer, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="85e76-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="85e76-122">Unesite ime datoteke koja sadrži podatke i putanju do datoteke na SFTP serveru ako nije u osnovnoj fascikli.</span><span class="sxs-lookup"><span data-stu-id="85e76-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="85e76-123">Potvrdite sve unose izborom opcije **Povežite se sa prilagođenim uvozom**.</span><span class="sxs-lookup"><span data-stu-id="85e76-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="85e76-124">![Potpaleta konfiguracije SFTP prilagođenog uvoza](media/SFTP_Custom_Import_Configuration_flyout.png "Potpaleta konfiguracije SFTP prilagođenog uvoza")</span><span class="sxs-lookup"><span data-stu-id="85e76-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="85e76-125">Definisanje mapiranja polja</span><span class="sxs-lookup"><span data-stu-id="85e76-125">Defining field mappings</span></span> 

<span data-ttu-id="85e76-126">Direktorijum koji sadrži datoteku za uvoz na SFTP server takođe mora sadržati *model.json* datoteku.</span><span class="sxs-lookup"><span data-stu-id="85e76-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="85e76-127">Ova datoteka definiše šemu koja će se koristiti za uvoz podataka.</span><span class="sxs-lookup"><span data-stu-id="85e76-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="85e76-128">Šema mora da koristi [Common Data Model](https://docs.microsoft.com/common-data-model/) za određivanje mapiranja polja.</span><span class="sxs-lookup"><span data-stu-id="85e76-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="85e76-129">Jednostavan primer datoteke model.json izgleda ovako:</span><span class="sxs-lookup"><span data-stu-id="85e76-129">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="85e76-130">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="85e76-130">Enrichment results</span></span>

<span data-ttu-id="85e76-131">Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake.</span><span class="sxs-lookup"><span data-stu-id="85e76-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="85e76-132">Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="85e76-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="85e76-133">Vreme obrade zavisiće od veličine podataka koji se uvoze i veze sa SFTP serverom.</span><span class="sxs-lookup"><span data-stu-id="85e76-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="85e76-134">Po završetku procesa obogaćivanja, možete pregledati svoje novouvezene prilagođene podatke obogaćivanja pod **Moja obogaćenja**.</span><span class="sxs-lookup"><span data-stu-id="85e76-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="85e76-135">Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="85e76-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="85e76-136">Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.</span><span class="sxs-lookup"><span data-stu-id="85e76-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="85e76-137">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="85e76-137">Next steps</span></span>

<span data-ttu-id="85e76-138">Nadogradite na obogaćenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="85e76-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="85e76-139">Kreirajte [segmente](segments.md), [mere](measures.md) i [izvezite podatke](export-destinations.md) da biste klijentima pružili personalizovana iskustva.</span><span class="sxs-lookup"><span data-stu-id="85e76-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


