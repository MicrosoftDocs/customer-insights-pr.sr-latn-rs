---
title: Kreiranje veze između uvida u ciljne grupe i uvida u angažovanje
description: Kreirajte aktivnu vezu između uvida u ciljnu grupu i uvida u angažovanje da biste omogućili dvosmerno deljenje podataka.
ms.date: 09/08/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 56adc206d83bc6e34a55f11383393b5ac66da531
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229889"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Kreiranje veze između uvida u ciljne grupe i uvida u angažovanje

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Integracija između uvida u angažovanje i uvida u ciljnu grupu povezuje okruženja iz obe mogućnosti i omogućava međusobno deljenje podataka u oba smera.

Koristite objedinjene profile i segmente iz uvida u ciljnu grupu za više opcija analize u uvidima u angažovanje. Izvezite događaje koji imaju visoku poslovnu vrednost iz uvida u angažovanje. Pomoću ovih događaja dodajte podatke u objedinjene profile u uvidima u ciljnu grupu.

## <a name="prerequisites"></a>Preduslovi

- Korisnici profili moraju biti uskladišteni u nalogu Azure Data Lake Storage koji posedujete ili u upravljano jezero sa [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash; podacima. 
- Vaše okruženje uvida u ciljnu grupu bi trebalo da ima pridruženo Dataverse okruženje. A ako i to okruženje koristi Dataverse za skladištenje podataka, proverite da li je označena opcija **Omogući deljenje podataka** u uvidima u ciljnu grupu. Za još informacija pogledajte [Kreiranje i konfigurisanje okruženja u uvidima u ciljnu grupu](../audience-insights/create-environment.md).
- Potrebne su vam administratorske dozvole za okruženja za uvide u angažovanje i za uvida u ciljnu grupu.
- Povezana okruženja moraju biti u istom geografskom regionu.

> [!NOTE]
> - Ako je vaša pretplata na uvide u ciljnu grupu u probnoj verziji koja koristi interno upravljano jezero podataka za uvide u ciljnu grupu, kontaktirajte [pirequest@microsoft.com](mailto:pirequest@microsoft.com) za pomoć. 
> - Ako vaše okruženje za uvid u ciljnu grupu koristi vašu uslugu Azure Data Lake Storage da biste uskladištili podatke, morate da dodate principala usluge Azure uvida u angažovanje na nalog za skladištenje. Za detalje, pogledajte članak [Povežite se sa Azure Data Lake Storage nalogom s principalom usluge Azure za uvide u ciljnu grupu](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Kreiranje veze okruženja

Vezu okruženja možete da kreirate ažuriranjem podešavanja **Administrator** > **Okruženje** u uvidima u angažovanje.

**Kako se uspostavlja aktivna veza između uvida u ciljne grupe i uvida u angažovanje**

1. Na stranici **Administrator okruženja** izaberite karticu **Povežite okruženja**.

    :::image type="content" source="media/integrate1.png" alt-text="Konfigurišite okruženje.":::

1. Izaberite **Podešavanja okruženja** u gornjem levom uglu ili pri dnu ekrana.

     :::image type="content" source="media/integrate2.png" alt-text="Izaberite okruženje uvida u ciljnu grupu.":::

1. Izaberite okruženje uvida u ciljnu grupu, a zatim izaberite **Sledeće** da biste završili. Sada možete da izaberete opcionalne funkcije za povezana okruženja.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Omogućavanje atributa i segmenata objedinjenih profila uvida u ciljnu grupu

Kada povežete okruženja, možete da izaberete opcionalne funkcije za povezana okruženja. Ove funkcije omogućavaju atribute i segmente objedinjenih profila iz uvida u ciljnu grupu za interaktivnu analizu podataka o klijentima.

> [!IMPORTANT]
> Da bi se segmenti uvida u ciljnu grupu prikazali u uvidima u angažovanje, morate prvo [pokrenuti objedinjavanja i posledične procese](../audience-insights/merge-entities.md). Posledični procesi su važni jer generišu jedinstvenu tabelu koja priprema segmente uvida u ciljnu grupu za deljenje sa uvidima u angažovanje. (Ako je osvežavanje sistema zakazano, automatski će uključiti posledične procese.)

**Kako se analiziraju veb-podaci u uvidima u angažovanje**

1. Na stranici **Administrator okruženja**, uključite prekidač **Delite podatke iz uvida u ciljnu grupu sa uvidima u angažovanje**, a zatim izaberite **Sledeće**.

    :::image type="content" source="media/integrate4.png" alt-text="Izaberite funkcije.":::

1. Izaberite atribute objedinjenih profila koji će postati aspekti u uvidima u angažovanje. (Nisu svi atributi korisni aspekti. Na primer, nije verovatno da će vam trebati **Ime** ili **Prezime** kao atribut za analizu događaja na vašoj veb-lokaciji.)

    :::image type="content" source="media/integrate5.png" alt-text="Uređivanje aspekata.":::

   >[!NOTE]
   > Svi atributi profila uvida u ciljnu grupu koji predstavljaju identifikatore (kao što su **ID** i **alternativni ID**) filtriraju se iz dostupnih atributa i postaju aspekti uvida u angažovanje.

1. Kada završite sa odabirom atributa, izaberite **Sledeće**.
1. Dodajte korisnike koji mogu da vide aspekte i segmente profila uvida u ciljnu grupu u uvidima u angažovanje.

    :::image type="content" source="media/integrate6.png" alt-text="Upravljajte pristupom podacima o klijentu.":::

   > [!IMPORTANT]
   > Ako u ovom koraku ne dodate korisnike izričito, podaci će biti sakriveni od korisnika u uvidima u angažovanje.
   > Da bi se segmenti uvida u ciljnu grupu prikazali u uvidima u angažovanje, morate prvo [pokrenuti objedinjavanja i posledične procese](../audience-insights/merge-entities.md). Posledični procesi su važni jer generišu jedinstvenu tabelu koja priprema segmente uvida u ciljnu grupu za deljenje sa uvidima u angažovanje. (Ako je osvežavanje sistema zakazano, automatski će uključiti posledične procese.)

1. Pregledajte izabrane stavke, pa izaberite **Završi**.

    :::image type="content" source="media/integrate7.png" alt-text="Pregledajte podešavanja podataka o klijentima.":::

## <a name="export-refined-events-to-audience-insights"></a>Izvoz preciziranih događaja u uvide u ciljnu grupu

Kada kreirate vezu između okruženja, možete da izvezete precizirane događaje iz uvida u angažovanje u uvide u ciljnu grupu i unesete ih kao novi izvor podataka. 

Za više informacija, pogledajte članak [Integracija veb-podataka iz uvida u angažovanje u uvidima u ciljnu grupu](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
