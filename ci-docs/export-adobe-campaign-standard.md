---
title: Izvoz segmenata uvida kupaca u Adobe standard kampanje (pregled)
description: Saznajte kako da koristite segmente "Uvidi kupaca" u standardnoj Adobe kampanji.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195537"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Izvoz segmenata uvida kupaca u Adobe standard kampanje (pregled)

Izvezite segmente koji ciljaju relevantne grupe korisnika lokacije Adobe u standard kampanje.

:::image type="content" source="media/ACS-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a>Preduslovi

- Licenca Adobe za standard kampanje.
- Ime [Azure Blob Storage naloga](/azure/storage/blobs/create-data-lake-storage-account) i ključ naloga. Da biste pronašli ime i ključ, pogledajte članak Upravljanje [postavkama naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).
- Azure [Blob skladišni kontejner](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Pregled kampanje

Da bismo bolje razumeli kako možete da koristite segmente iz "Uvida kupaca" Adobe Experience Platform u, pogledajmo fiktivnu probnu kampanju.

Pretpostavimo da vaše preduzeće nudi mesečnu uslugu zasnovanu na pretplati za klijente u Sjedinjenim Državama. Želite da identifikujete klijente koji treba da obnove pretplate u narednih osam dana, ali još uvek nisu obnovili pretplatu. Da biste zadržali ove klijente, treba da im pošaljete promotivnu ponudu putem e-pošte koristeći Adobe Campaign Standard.

U ovom primeru želimo da jednom pokrenemo promotivnu kampanju e-pošte. Ovaj članak ne pokriva slučaj korišćenja sa više pokretanja kampanje. Međutim, uvidi klijenata i Adobe standard kampanje mogu da se konfigurišu tako da rade i za periodični scenario kampanje.

## <a name="identify-your-target-audience"></a>Identifikujte svoju ciljnu grupu

U našem scenariju, pretpostavljamo da su e-adrese klijenata dostupne u uvidima klijenata i da su njihove promotivne preferencije analizirane kako bi se identifikovali članovi segmenta.

Segment [koji ste definisali u "Uvidima kupaca"](segments.md) zove se **ChurnProneCustomers i planirate** da ovim korisnicima pošaljete promociju e-pošte.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimak ekrana stranice segmenata sa kreiranim segmentom ChurnProneCustomers.":::

E-poruka sa ponudom koju želite da pošaljete sadrži ime, prezime i datum završetka pretplate klijenta. Poruka obaveštava klijente o popustu koji će dobiti ako obnove pretplatu pre nego što se završi.

## <a name="export-your-target-audience"></a>Izvezite svoju ciljnu grupu

### <a name="set-up-connection-to-adobe-campaign"></a>Podešavanje veze sa kampanjom Adobe

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **dodaj vezu i** odaberite stavku **Adobe Kampanja**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite **ime naloga**, **ključ naloga** i kontejner **za** nalog za skladištenje bloba.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimak ekrana konfiguracije naloga skladišta. ":::

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

### <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Adobe Campaign. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Odaberite segment koje želite da izvezete. U ovom primeru, to je **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimak ekrana korisničkog interfejsa za odabir segmenta sa izabranim segmentom ChurnProneCustomers.":::

1. Izaberite **Sledeće**.

1. Mapiraj **polja** Izvor iz segmenta "Uvidi kupaca" u **imena** polja "Cilj" u šemi Adobe profila standardne kampanje.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapiranje polja za Adobe Campaign Standard konektor.":::

   Ako želite da dodate još atributa, izaberite **Dodaj atribut**. Ciljno ime se može razlikovati od imena izvornog polja tako da i dalje možete mapirati izlaz segmenta iz "Uvidi kupaca Adobe " u standard kampanje ako polja nemaju isto ime u dva sistema.

   > [!NOTE]
   > E-adresa se koristi kao polje identiteta, ali možete da koristite bilo koji drugi identifikator iz profila klijenta da biste mapirali podatke u standard Adobe kampanje.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Uverite se da je broj zapisa u izvezenom segmentu unutar dozvoljenog ograničenja vaše licence za uslugu Adobe Campaign Standard.

Izvezeni podaci se čuvaju u kontejneru Azure skladišta blob objekta koji ste ranije konfigurisali. U kontejneru se automatski kreira sledeća putanja fascikle: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurisanje usluge Adobe Campaign Standard

Izvezeni segmenti sadrže kolone koje ste izabrali prilikom konfigurisanja izvoza. Ovi podaci se mogu koristiti za [kreiranje profila u usluzi Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Da biste koristili segment u standardnoj Adobe kampanji, proširite [šemu profila u standardnoj](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing)Adobe kampanji da biste uključili dva dodatna polja.

U našem primeru, ova polja su ime segmenta i datum segmenta. Ova polja ćemo koristiti za identifikaciju profila u usluzi Adobe Campaign Standard koji želimo da ciljamo za ovu kampanju.

Ako u standardnoj kampanji nema drugih Adobe zapisa, osim onoga što ćete uvesti, preskočite ovaj korak.

## <a name="import-data-into-adobe-campaign-standard"></a>Uvoz podataka u Adobe Campaign Standard

Uvezite pripremljene korisnici iz uvida klijenata u Adobe standard kampanje da biste kreirali [profile pomoću toka posla](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Tok posla uvoza na slici ispod konfigurisan je tako da radi svakih osam sati i traži izvezene segmente uvida kupaca (.csv datoteka u Azure skladištu bloba). Tok posla izdvaja sadržaj .csv datoteke u navedenom redosledu kolona. Ovaj tok posla je napravljen da izvrši osnovno rukovanje greškama i da obezbedi da svaki zapis ima adresu e-pošte pre nego što unese podatke u Adobe Campaign Standard. Tok posla takođe izdvaja naziv segmenta iz naziva datoteke pre dodavanja u podatke o Adobe Campaign Standard profilu.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Snimak ekrana toka posla uvoza u korisnički interfejs usluge Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Preuzimanje ciljne grupe u usluzi Adobe Campaign Standard

Kada se podaci uvezu u standard kampanje, kreirajte Adobe [tok](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) posla i [ispitate kupce](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) na osnovu imena segmenta i datuma segmenta da biste izabrali profile koji su identifikovani za našu probnu kampanju.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Kreiranje i slanje e-pošte u usluzi Adobe Campaign Standard

Kreirajte sadržaj e-poruke, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poruku.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Primer e-poruke sa ponudom za obnovu iz usluge Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
