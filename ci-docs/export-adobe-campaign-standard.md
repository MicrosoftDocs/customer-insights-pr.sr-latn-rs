---
title: Izvoz segmenata uvida kupaca u Adobe standard kampanje (pregled)
description: Saznajte kako da koristite segmente "Uvidi kupaca" u standardnoj Adobe kampanji.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 9915591cd969bf825f5d1669de43ed4f9953f898
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082351"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Izvoz segmenata uvida kupaca u Adobe standard kampanje (pregled)

Kao korisnik, možda Dynamics 365 Customer Insights ste kreirali segmente da biste marketinške kampanje bili efikasniji ciljanjem relevantnih korisnika lokacije. Da biste koristili segment iz uvida klijenata u i Adobe Experience Platform aplikacije kao što je Adobe Standard kampanje, potrebno je da sledite nekoliko koraka navedenih u ovom članku.

:::image type="content" source="media/ACS-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a>Preduslovi

- Dynamics 365 Customer Insights licenca
- Licenca za Adobe Campaign Standard
- Nalog Azure skladišta blob objekta

## <a name="campaign-overview"></a>Pregled kampanje

Da bismo bolje razumeli kako možete da koristite segmente iz "Uvida kupaca" Adobe Experience Platform u, pogledajmo fiktivnu probnu kampanju.

Pretpostavimo da vaše preduzeće nudi mesečnu uslugu zasnovanu na pretplati za klijente u Sjedinjenim Državama. Želite da identifikujete klijente koji treba da obnove pretplate u narednih osam dana, ali još uvek nisu obnovili pretplatu. Da biste zadržali ove klijente, treba da im pošaljete promotivnu ponudu putem e-pošte koristeći Adobe Campaign Standard.

U ovom primeru želimo da jednom pokrenemo promotivnu kampanju e-pošte. Ovaj članak ne pokriva slučaj korišćenja sa više pokretanja kampanje. Međutim, uvidi klijenata i Adobe standard kampanje mogu da se konfigurišu tako da rade i za periodični scenario kampanje.

## <a name="identify-your-target-audience"></a>Identifikujte svoju ciljnu grupu

U našem scenariju, pretpostavljamo da su e-adrese klijenata dostupne i da su analizirane njihove promotivne preferencije kako bi se identifikovali članovi segmenta.

Segment [koji ste definisali u "Uvidima kupaca"](segments.md) zove se **ChurnProneCustomers i planirate** da ovim korisnicima pošaljete promociju e-pošte.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimak ekrana stranice segmenata sa kreiranim segmentom ChurnProneCustomers.":::

E-poruka sa ponudom koju želite da pošaljete sadrži ime, prezime i datum završetka pretplate klijenta. Poruka obaveštava klijente o popustu koji će dobiti ako obnove pretplatu pre nego što se završi.

## <a name="export-your-target-audience"></a>Izvezite svoju ciljnu grupu

### <a name="configure-a-connection"></a>Konfigurisanje veze

Sa identifikovanim korisnici ciljnim datotekama, možemo da konfigurišemo izvoz na Azure Blob Storage nalog.

1. U uvidima klijenata idite na **administratorski** > **konekciju**.

1. Izaberite **Dodaj vezu** i birajte **Adobe kampanja** da biste konfigurisali vezu ili izaberite **Podešavanje** na pločici **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Pločica konfiguracije za Adobe Campaign Standard.":::

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Unesite **Naziv naloga**, **Ključ naloga** i **Kontejner** za vaš nalog za Azure skladište blob objekta u koji želite da izvezete segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimak ekrana konfiguracije naloga skladišta. "::: 

   - Da biste saznali više o pronalaženju imena i ključa naloga za Azure skladište blob objekta, pogledajte članak [Upravljanje podešavanjima naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).

   - Da biste saznali kako da kreirate kontejner, pogledajte članak [Kreiranje kontejnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Izaberite **Sačuvaj** da biste kreirali vezu.

### <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Adobe Campaign. Ako ne vidite naziv ovog odeljka, tada vam nisu dostupne veze ovog tipa.

1. Odaberite segment koje želite da izvezete. U ovom primeru, to je **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimak ekrana korisničkog interfejsa za odabir segmenta sa izabranim segmentom ChurnProneCustomers.":::

1. Izaberite **Sledeće**.

1. Sada mapiramo polja **Izvor** iz segmenta "Uvidi kupaca" u imena **polja** "Cilj" u šemi Adobe profila standardne kampanje.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapiranje polja za Adobe Campaign Standard konektor.":::

   Ako želite da dodate još atributa, izaberite **Dodaj atribut**. Ciljno ime se može razlikovati od imena izvornog polja tako da i dalje možete mapirati izlaz segmenta iz "Uvidi kupaca Adobe " u standard kampanje ako polja nemaju isto ime u dva sistema.

   > [!NOTE]
   > E-adresa se koristi kao polje identiteta, ali možete da koristite bilo koji drugi identifikator iz profila klijenta da biste mapirali podatke u standard Adobe kampanje.

1. Izaberite **Sačuvaj**.

Kada sačuvate odredište za izvoz, pronaći ćete ga u dijalogu **Podaci** > **Izvozi**.

Sada možete da [izvozite segment na zahtev](export-destinations.md#run-exports-on-demand). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md).

> [!NOTE]
> Uverite se da je broj zapisa u izvezenom segmentu unutar dozvoljenog ograničenja vaše licence za uslugu Adobe Campaign Standard.

Izvezeni podaci se čuvaju u kontejneru Azure skladišta blob objekta koji ste ranije konfigurisali. Sledeća putanja do fascikle se automatski kreira u vašem kontejneru:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurisanje usluge Adobe Campaign Standard

Izvezeni segmenti sadrže kolone koje ste izabrali prilikom definisanja odredišta izvoza u prethodnom koraku. Ovi podaci se mogu koristiti za [kreiranje profila u usluzi Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Da bismo koristili segment u usluzi Adobe Campaign Standard, moramo proširiti šemu profila u usluzi Adobe Campaign Standard tak oda uključuje dva dodatna polja. Saznajte kako da [proširite resurs profila](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) sa novim poljima u usluzi Adobe Campaign Standard.

U našem primeru, ova polja su *Naziv segmenta i Datum segmenta (opcionalno)*.

Ova polja ćemo koristiti za identifikaciju profila u usluzi Adobe Campaign Standard koji želimo da ciljamo za ovu kampanju.

Ako nema drugih zapisa u usluzi Adobe Campaign Standard osim onog koji ćete uvesti, možete preskočiti ovaj korak.

## <a name="import-data-into-adobe-campaign-standard"></a>Uvoz podataka u Adobe Campaign Standard

Sada kada je sve na svom mestu, potrebno je da uvezemo pripremljene podatke korisnici "Uvidi kupaca" u Adobe standard kampanje da bismo kreirali profile. Saznajte [kako da uvezete profile u Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) koristeći tok posla.

Tok posla uvoza na slici ispod konfigurisan je tako da radi svakih osam sati i traži izvezene segmente uvida kupaca (.csv datoteka u Azure skladištu bloba). Tok posla izdvaja sadržaj .csv datoteke u navedenom redosledu kolona. Ovaj tok posla je napravljen da izvrši osnovno rukovanje greškama i da obezbedi da svaki zapis ima adresu e-pošte pre nego što unese podatke u Adobe Campaign Standard. Tok posla takođe izdvaja naziv segmenta iz naziva datoteke pre dodavanja u podatke o Adobe Campaign Standard profilu.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Snimak ekrana toka posla uvoza u korisnički interfejs usluge Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Preuzimanje ciljne grupe u usluzi Adobe Campaign Standard

Kada se podaci uvezu u Adobe Campaign Standard, [možete kreirati tok posla](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [postaviti upit](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) klijentima na osnovu *naziva segmenta* i *datuma segmenta* da biste izabrali profile koji su identifikovani za naš primer kampanje.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Kreiranje i slanje e-pošte u usluzi Adobe Campaign Standard

Kreirajte sadržaj e-poruke, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poruku.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Primer e-poruke sa ponudom za obnovu iz usluge Adobe Campaign Standard.":::
