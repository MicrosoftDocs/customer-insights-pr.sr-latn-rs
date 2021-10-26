---
title: Prikaz i kreiranje segmenata
description: Kako da kreirate uređujete i izbrišete segmente i gde da ih koristite.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: f6bba645a78173fb00dc75e6080f2aeda0b5a143
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623604"
---
# <a name="view-and-create-segments"></a>Prikaz i kreiranje segmenata

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Segmenti vam omogućavaju da identifikujete podskupove posetilaca na osnovu karakteristika ili interakcija na veb-lokaciji. Segmenti vam omogućavaju da primenite filtere i analizirate te podskupove. Analiza može pomoći u ispitivanju i reagovanju na trendove u vašem poslu. 

:::image type="content" source="media/segments-page.png" alt-text="Snimak ekrana aplikacije za uvide o angažovanju koji prikazuje listu postojećih segmenata u radnom prostoru.":::

## <a name="view-segments"></a>Prikaz segmenata

1. Idite na odeljak **Podaci** u levom oknu za navigaciju. 

1. Izaberite karticu **Segmenti** da biste videli listu svih segmenata u radnom prostoru. 

## <a name="create-a-segment"></a>Kreiranje segmenta

Segmenti se sastoje od pravila i uslova koji su povezani sa logičkim operatorima. Uslovi primenjuju filtere na izabrani aspekt. Svaki segment može da koristi do pet aspekata.

Sledeći primer prikazuje segment sa dva uslova u jednom pravilu. Filtrira sve događaje na veb-lokaciji gde je pregledač Chrome, a operativni sistemi su iOS ili Android.

:::image type="content" source="media/segment-sample.png" alt-text="Primeri segmenata sa dva uslova u pravilu za filtriranje događaja na veb-lokaciji.":::

Ovaj odeljak opisuje kako se kreira *prazan segment* ispočetka.

1. Idite u **Podaci** > **Segmenti**.

1. Izaberite **Novi segment**.

1. U **Biblioteci resursa**, izaberite (+) pored atributa po kome želite da filtrirate. Segmente trenutno možete da kreirate samo na osnovu aspekata.

   :::image type="content" source="media/create-new-segment.png" alt-text="Kreirajte novi segment.":::

1. U odeljku **Pravilo**, izaberite operatora i vrednost za izabrani atribut. Podržani su sledeći operatori.

   :::image type="content" source="media/choose-operator-segment.png" alt-text="Odaberite operatora za svoj novi segment.":::

   - **je**: zahteva tačno podudaranje za uključivanje vrednosti. Koristi **jednako** za jednu vrednost ili **bilo koji od** da uključi više vrednosti.
   - **nije**: zahteva tačno podudaranje za izuzimanje vrednosti. Koristi **jednako** za jednu vrednost ili **bilo koji od** da uključi više vrednosti.
   - **počinje sa**: niz sa kojim započinju odgovarajuće vrednosti.
   - **završava se sa**: niz kojim se završavaju odgovarajuće vrednosti.
   - **sadrži**: niz sadržan u podudarnim vrednostima.

1. Da biste grupi dodali još uslova, možete koristiti logičke operatore. Projektovani atributi uzimaju se u obzir kada se koriste operatori skupova.
   - Operator **I**: Oba uslova moraju da budu ispunjena kao deo procesa segmentacije. Ova opcija je najkorisnija kada definišete uslove u različitim entitetima.
   - Operator **ILI**: Bilo koji od uslova mora biti ispunjen kao deo procesa segmentacije. Ova opcija je najkorisnija kada definišete više uslova u istom entitetu.

1. Izaberite **Sačuvaj** i dajte naziv segmentu. 

Segment će biti naveden na stranici **Segmenti** i možete ga primeniti na sve izveštaje i tokove prodaje u radnom prostoru.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Koristite segment u izveštaju ili toku prodaje

Možete da primenite segmente na izveštaj ili tok prodaje da biste ih filtrirali na osnovu uslova u segmentu. Međutim, ne možete primeniti segmente na izveštaj o korišćenju u realnom vremenu.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Izveštaj o prikazima stranice sa proširenom padajućom listom za odabir segmenata koji će se primeniti.":::

Da biste primenili segment, otvorite izveštaj ili tok prodaje. Izaberite **+Dodajte uslov** i birajte **Filtriraj prema segmentu**. Odaberite segment iz liste koju želite da primenite. Segment se primenjuje na izveštaj. Ako grafikon ne podržava segment, prikazuje se greška. Za više informacija pogledajte [Kreiranje izveštaje o toku prodaje i upravljanje njima](funnel-reports.md).
 
Možete prijaviti *do tri segmenta* u izveštaj ili tok prodaje.

## <a name="edit-a-segment"></a>Uređivanje segmenta

1. Idite u **Podaci** > **Segmenti**.
1. Izaberite segment sa liste da biste ga otvorili. 
1. Promenite ili dodajte vrednosti po potrebi.
1. Izaberite **Sačuvaj** da primenite promene.

## <a name="change-the-name-of-a-segment"></a>Promeni naziv segmenta

1. Idite u **Podaci** > **Segmenti**.
1. Na listi segmenata, izaberite **Još [...]**. 
1. Sa padajuće liste odaberite **Uredi naziv**.
1. Unesite novi naziv i izaberite **Preimenuj**.

## <a name="delete-a-segment"></a>Izbrišite segment

1. Idite u **Podaci** > **Segmenti**.
1. Na listi segmenata, izaberite **Još [...]**. 
1. Sa padajuće liste odaberite **Izbriši**.
1. Izaberite **Izbriši** da biste potvrdili.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
