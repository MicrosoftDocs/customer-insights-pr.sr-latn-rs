---
title: Obogaćivanje uz SFTP prilagođeni uvoz
description: Opšte informacije o obogaćivanju SFTP prilagođenog uvoza.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304667"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="7d3b1-103">Obogatite profile klijenata uz prilagođene podatke (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="7d3b1-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="7d3b1-104">Secure File Transfer Protocol (SFTP) prilagođeni uvoz vam omogućava da uvezete podatke koji ne moraju da prolaze kroz proces objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="7d3b1-105">To je fleksibilan, siguran i lak način unosa podataka.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="7d3b1-106">SFTP prilagođeni uvoz se može koristiti u kombinaciji sa [SFTP izvozom](export-sftp.md) koji vam omogućava izvoz podataka o profilu klijenata potrebnih za obogaćivanje.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="7d3b1-107">Podaci se zatim mogu obrađivati i obogaćivati, a SFTP prilagođeni uvoz može se koristiti za vraćanje obogaćenih podataka u mogućnost uvida u ciljnu grupu u usluzi Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7d3b1-108">Preduslovi</span><span class="sxs-lookup"><span data-stu-id="7d3b1-108">Prerequisites</span></span>

<span data-ttu-id="7d3b1-109">Da biste konfigurisali SFTP prilagođeni uvoz, moraju biti ispunjeni sledeći preduslovi:</span><span class="sxs-lookup"><span data-stu-id="7d3b1-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="7d3b1-110">Imate naziv datoteke i lokaciju (putanju) datoteke koju treba uvesti na SFTP host.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="7d3b1-111">Postoji datoteka *model.json* koja navodi [šemu zajedničkog modela podataka](/common-data-model/) za uvoz podataka.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="7d3b1-112">Ova datoteka mora biti u istom direktorijumu kao i datoteka koju treba uvesti.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="7d3b1-113">Administrator je već konfigurisao SFTP vezu *ili* imate dozvole [administratora](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="7d3b1-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="7d3b1-114">Trebaće vam korisnički akreditivi, URL adresa i broj porta za SFTP lokaciju odakle želite da uvezete podatke.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="7d3b1-115">Konfigurisanje uvoza</span><span class="sxs-lookup"><span data-stu-id="7d3b1-115">Configure the import</span></span>

1. <span data-ttu-id="7d3b1-116">Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="7d3b1-117">Na **pločici za SFTP prilagođeni uvoz** izaberite **Obogati moje podatke**, a zatim izaberite **Započni**.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Pločica SFTP prilagođenog uvoza.":::

1. <span data-ttu-id="7d3b1-119">Izaberite [vezu](connections.md) sa padajuće liste.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="7d3b1-120">Ako veza nije dostupna, obratite se administratoru.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="7d3b1-121">Ako ste administrator, vezu možete da napravite izborom **Dodaj vezu** i birajući **SFTP prilagođeni uvoz** sa padajuće liste.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="7d3b1-122">Izaberite **Povežite sa prilagođenim uvozom** da biste potvrdili izabranu vezu.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="7d3b1-123">Izaberite **Sledeće** i unesite **Putanju** i **Naziv dokumenta** datoteke podataka koju želite da uvezete.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Snimak ekrana prilikom unosa lokacije podataka.":::

1. <span data-ttu-id="7d3b1-125">Izaberite **Sledeće** i obezbedite naziv za obogaćivanje i naziv za izlazni entitet.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="7d3b1-126">Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="7d3b1-127">Konfigurisanje veze za SFTP prilagođenim uvozom</span><span class="sxs-lookup"><span data-stu-id="7d3b1-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="7d3b1-128">Morate biti administrator da biste konfigurisali veze.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="7d3b1-129">Izaberite **Dodaj vezu** prilikom konfigurisanja obogaćivanja *ili* idite na **Administrator** > **Veze** i izaberite **Podešavanje** na pločici Custom Import.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="7d3b1-130">Unesite naziv veze u polje **Ime za prikaz**.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="7d3b1-131">Unesite važeće korisničko ime, lozinku i URL hosta za SFTP server na kojem se nalaze podaci koje treba uvesti.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="7d3b1-132">Pregledajte i dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="7d3b1-133">Izaberite **Verifikuj** da biste proverili valjanost konfiguracije.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="7d3b1-134">Po završetku verifikacije, vezu možete sačuvati ako izaberete **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7d3b1-135">![Experian stranica konfiguracije veze](media/enrichment-SFTP-connection.png "Experian stranica konfiguracije veze")</span><span class="sxs-lookup"><span data-stu-id="7d3b1-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="7d3b1-136">Definisanje mapiranja polja</span><span class="sxs-lookup"><span data-stu-id="7d3b1-136">Defining field mappings</span></span> 

<span data-ttu-id="7d3b1-137">Direktorijum koji sadrži datoteku za uvoz na SFTP server takođe mora sadržati *model.json* datoteku.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="7d3b1-138">Ova datoteka definiše šemu koja će se koristiti za uvoz podataka.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="7d3b1-139">Šema treba da koristi [Common Data Model](/common-data-model/) da odredi mapiranje polja.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="7d3b1-140">Jednostavan primer datoteke model.json izgleda ovako:</span><span class="sxs-lookup"><span data-stu-id="7d3b1-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="7d3b1-141">Rezultati obogaćivanja</span><span class="sxs-lookup"><span data-stu-id="7d3b1-141">Enrichment results</span></span>

<span data-ttu-id="7d3b1-142">Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="7d3b1-143">Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7d3b1-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7d3b1-144">Vreme obrade zavisiće od veličine podataka koji se uvoze i veze sa SFTP serverom.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="7d3b1-145">Po završetku procesa obogaćivanja, možete pregledati svoje novouvezene prilagođene podatke obogaćivanja pod **Moja obogaćenja**.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="7d3b1-146">Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="7d3b1-147">Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7d3b1-148">Sledeći koraci</span><span class="sxs-lookup"><span data-stu-id="7d3b1-148">Next steps</span></span>

<span data-ttu-id="7d3b1-149">Nadogradite na obogaćenim podacima o klijentima.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="7d3b1-150">Kreirajte [segmente](segments.md) i [mere](measures.md), kao i [izvoz podataka](export-destinations.md) da pružite personalizovana iskustva svojim klijentima.</span><span class="sxs-lookup"><span data-stu-id="7d3b1-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
