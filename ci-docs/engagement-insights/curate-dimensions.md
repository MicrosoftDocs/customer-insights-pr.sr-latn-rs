---
title: Koristite demografske aspekte za razdvajanje podataka o ponašanju (održavani aspekti)
description: Koristite održavane aspekte objedinjenih profila da biste omogućili svojstva profila klijenta uvida u ciljnu grupu.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 50bb800c9e097d03cc6f26f79819c741ab5e8baf
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461120"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Koristite demografske aspekte za razdvajanje podataka o ponašanju

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Korišćenjem demografskih aspekata objedinjenih profila, uvidima u angažovanje korisnici mogu da pristupaju svojstvima profila uvida u ciljnu grupu. Zatim možete koristiti ta svojstva u interaktivnim analizama podataka o ponašanju, uključujući podatke prikupljene uvidom u angažovanje na vašoj veb-lokaciji ili u aplikaciji za mobilne uređaje.

>[!NOTE]
> Uvid u angažovanje uključuje gotove aspekte za svojstva događaja. Još informacija: [Prikaz i kreiranje aspekata](dimensions.md)

## <a name="prerequisite"></a>Preduslov

- Okruženje uvida u angažovanje u kojem imate podatke o korisničkom profilu povezane sa okruženjem uvida u ciljnu grupu gde se kreiraju profili klijenata. Još informacija: [Kreiranje veze između uvida u ciljne grupe i uvida u angažovanje](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Kada kreirate vezu između okruženja uvida u ciljnu grupu i uvida u angažovanje, možda će vam trebati samo podaci specifični za svojstva profila korisnika, koji mogu biti korisni kao dimenzije u uvidima u angažovanje. Za više informacija, idite na [Omogućavanje atributa i segmenata objedinjenih profila uvida u ciljnu grupu](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).<!--note from editor: Suggested. -->

## <a name="create-a-new-custom-report"></a>Kreiranje novog prilagođenog izveštaja

1. U levom oknu izaberite **Prilagođeno** > **Novi izveštaj**, a zatim izaberite željenu metriku. (Za ovaj primer smo odabrali **Broj pregleda stranice po satu**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Izaberite metriku.":::

2. U uređivaču vizualizacije, izaberite **Aspekti**, a zatim izaberite **Demografski** u padajućem meniju **Tip aspekta**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Izaberite demografsku kategoriju.":::

3. Izaberite aspekt **Signal.Customer.*xxx***. (Ovaj primer prikazuje Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Izaberite aspekt.":::
  
## <a name="limitations"></a>Ograničenja

Trenutno možete da koristite samo demografske aspekte za razdvajanje podataka o ponašanju.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
