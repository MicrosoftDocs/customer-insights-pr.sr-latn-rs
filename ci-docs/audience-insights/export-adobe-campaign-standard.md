---
title: Izvezite Customer Insights podatke u Adobe Campaign Standard
description: Saznajte kako se koriste segmenti uvida u korisnike u usluzi Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596332"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Korišćenje Customer Insights segmenata u usluzi Adobe Campaign Standard (verzija za pregled)

Kao korisnik uvida o korisnicima za Dynamics 365 Customer Insights, možda ste kreirali segmente da biste marketinške kampanje učinili efikasnijim tako što ćete ciljati relevantne ciljne grupe. Da biste koristili segment iz uvida o korisnicima u Adobe platformi iskustva i aplikacijama poput Adobe Campaign Standard, potrebno je da sledite nekoliko koraka navedenih u ovom članku.

:::image type="content" source="media/ACS-flow.png" alt-text="Dijagram procesa koraka opisanih u ovom članku.":::

## <a name="prerequisites"></a>Preduslovi

-   Dynamics 365 Customer Insights licenca
-   Licenca za Adobe Campaign Standard
-   Nalog Azure skladišta blob objekta

## <a name="campaign-overview"></a>Pregled kampanje

Da biste bolje razumeli kako možete da koristite segmente iz uvida o korisnicima u Adobe platformi iskustva, pogledajmo fiktivni primer kampanje.

Pretpostavimo da vaše preduzeće nudi mesečnu uslugu zasnovanu na pretplati za klijente u Sjedinjenim Državama. Želite da identifikujete klijente koji treba da obnove pretplate u narednih osam dana, ali još uvek nisu obnovili pretplatu. Da biste zadržali ove klijente, treba da im pošaljete promotivnu ponudu putem e-pošte, koristeći Adobe Campaign Standard.

U ovom primeru želimo da jednom pokrenemo promotivnu kampanju e-pošte. Ovaj članak ne pokriva slučaj korišćenja sa više pokretanja kampanje. Međutim, uvidi u korisnike i Adobe Campaign Standard mogu se konfigurisati da rade i za ponavljajući scenario kampanje.

## <a name="identify-your-target-audience"></a>Identifikujte svoju ciljnu grupu

U našem scenarij,u pretpostavljamo da su adrese e-pošte klijenata dostupne u uvidima o korisnicima i da su analizirane njihove promotivne željene opcije kako bi se identifikovali članovi segmenta.

[Segment koji ste definisali uvidom o korisnicima](segments.md) se zove **ChurnProneCustomers** i planirate da ovim klijentima pošaljete e-poruku sa promocijom.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snimak ekrana stranice segmenata sa kreiranim segmentom ChurnProneCustomers.":::

E-poruka sa ponudom koju želite da pošaljete sadrži ime, prezime i datum završetka pretplate klijenta. Poruka obaveštava klijente o popustu koji će dobiti ako obnove pretplatu pre nego što se završi.

## <a name="export-your-target-audience"></a>Izvezite svoju ciljnu grupu

Kada je identifikovana ciljna grupa, možemo da konfigurišemo izvoz iz uvida o korisnicima na nalog Azure skladišta blob objekta.

1. U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.

1. Na pločici **Adobe Campaign** izaberite **Podesi**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Pločica za konfiguraciju za Adobe Campaign Standard.":::

1. Navedite **ime za prikaz** za ovo novo odredište za izvoz, a zatim unesite **Naziv naloga**, **Ključ naloga** i **Kontejner** naloga Azure skladišta blob objekta u koji želite da izvezete segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snimak ekrana konfiguracije naloga skladišta. "::: 

   - Da biste saznali više o pronalaženju imena i ključa naloga za Azure skladište blob objekta, pogledajte [Upravljajte podešavanjima naloga za skladištenje na Azure portalu](/azure/storage/common/storage-account-manage).

   - Da biste saznali kako da kreirate kontejner, pogledajte članak [Kreiranje kontejnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Izaberite **Sledeće**.

1. Odaberite segment koje želite da izvezete. U ovom primeru, to je **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snimak ekrana korisničkog interfejsa za odabir segmenta sa izabranim segmentom ChurnProneCustomers.":::

1. Izaberite **Sledeće**.

1. Sada mapiramo polja **Izvor** od segmenta uvida u korisnike do imena polja **Cilj** u šemi Adobe Campaign Standard profila.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapiranje polja za Adobe Campaign Standard konektor.":::

   Ako želite da dodate još atributa, izaberite **Dodaj atribut**. Naziv cilja može se razlikovati od imena izvornog polja, tako da i dalje možete mapirati izlaz segmenta iz uvida u korisnike u uslugu Adobe Campaign Standard ako polja nemaju isti naziv u dva sistema.

   > [!NOTE]
   > Adresa e-pošte se koristi kao polje identiteta, ali možete koristiti bilo koji drugi identifikator iz vašeg korisničkog profila za uvide u korisnike da biste mapirali podatke u Adobe Campaign Standard.

1. Izaberite stavku **Sačuvaj**.

Kada sačuvate odredište za izvoz, pronaći ćete ga na listi **Administrator** > **Izvozi** > **Moja odredišta za izvoz**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Snimak ekrana sa istaknutom listom izvoza i uzorkom segmenta.":::

Sada možete da [izvozite segment na zahtev](export-destinations.md#export-data-on-demand). Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md).

> [!NOTE]
> Uverite se da je broj zapisa u izvezenom segmentu unutar dozvoljenog ograničenja vaše Adobe Campaign Standard licence.

Izvezeni podaci se čuvaju u kontejneru Azure skladišta blob objekta koji ste ranije konfigurisali. Sledeća putanja do fascikle se automatski kreira u vašem kontejneru:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurisanje usluge Adobe Campaign Standard

Kada se izveze segment iz uvida u korisnike, on sadrži kolone koje ste izabrali prilikom definisanja odredišta izvoza u prethodnom koraku. Ovi podaci se mogu koristiti za [kreiranje profila u usluzi Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Da bismo koristili segment u usluzi Adobe Campaign Standard, treba da proširimo šemu profila u usluzi Adobe Campaign Standard tako da uključuje dva dodatna polja. Saznajte kako da [produžite resurs profila](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) sa novim poljima u usluzi Adobe Campaign Standard.

U našem primeru, ova polja su *Naziv segmenta i Datum segmenta (opcionalno).*

Ova polja ćemo koristiti za identifikaciju profila u programu Adobe Campaign Standard koje želimo da ciljamo za ovu kampanju.

Ako u programu Adobe Campaign Standard ne postoje drugi zapisi osim onih koje ćete uvoziti, možete preskočiti ovaj korak.

## <a name="import-data-into-adobe-campaign-standard"></a>Uvoz podataka u Adobe Campaign Standard

Sada kada je sve na svom mestu, moramo pripremiti podatke o korisnicima iz uvida u korisnike u usluzi Adobe Campaign Standard da bismo kreirali profile. Saznajte [kako da uvezete profile u Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) koristeći tok posla.

Tok posla uvoza na donjoj slici konfigurisan je za pokretanje svakih 8 sati i traži izvezene segmente uvida u korisnike (.csv datoteka u Azure skladištu blob objekta). Tok posla izdvaja sadržaj .csv datoteke u navedenom redosledu kolona. Ovaj tok posla napravljen je da obavi osnovno rukovanje greškama i osigura da svaki zapis ima adresu e-pošte pre popune podacima u usluzi Adobe Campaign Standard. Tok posla takođe izdvaja ime segmenta iz imena datoteke pre dodavanja u podatke ACS profila.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Snimak ekrana toka posla uvoza u korisničkom interfejsu usluge Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Preuzimanje korisnika u usluzi Adobe Campaign Standard

Kada se podaci uvezu u Adobe Campaign Standard, vi [možete da kreirate tok posla](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) i [upit](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) da bi klijenti zasnovani na *Nazivu segmenta* i *Datumu segmenta* izabrali profile koji su identifikovani za naš primer kampanje.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Kreirajte i pošaljite e-poruku koristeći Adobe Campaign Standard

Kreirajte sadržaj e-poruke, a zatim [testirajte i pošaljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poruku.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Primer e-poruke sa ponudom obnove pretplate iz usluge Adobe Campaign Standard.":::