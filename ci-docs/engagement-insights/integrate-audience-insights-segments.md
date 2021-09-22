---
title: Koristite segmente uvida u ciljnu grupu da filtrirate izveštaje o uvidu u angažovanje
description: Koristite segmente uvida u ciljnu grupu u interaktivnim analizama podataka o ponašanju prikupljenih uvidom u angažovanje na veb-lokaciji klijenta.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bdd5641bb17384725491f22f70ae967ad90b1696
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461075"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Koristite segmente uvida u ciljnu grupu da filtrirate izveštaje o uvidu u angažovanje

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Pomoću uvida u angažovanje, možete da koristite segmente uvida u ciljnu grupu u interaktivnim analizama podataka o ponašanju prikupljenih uvidima u angažovanje na vašim veb-lokacijama.

## <a name="prerequisite"></a>Preduslov

- Okruženje uvida u angažovanje u kojem imate podatke o segmentima uvida u ciljnu grupu povezane sa okruženjem uvida u ciljnu grupu gde se kreiraju profili klijenata. Još informacija: [Kreiranje veze između uvida u ciljne grupe i uvida u angažovanje](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Kreiranje segmenata uvida u ciljnu grupu 

> [!IMPORTANT]
> Da bi se segmenti uvida u ciljnu grupu prikazali u uvidima u angažovanje, morate prvo [pokrenuti objedinjavanja i posledične procese](../audience-insights/merge-entities.md). Posledični procesi su važni jer generišu jedinstvenu tabelu koja priprema segmente uvida u ciljnu grupu za deljenje sa uvidima u angažovanje. (Ako je osvežavanje sistema zakazano, automatski će uključiti posledične procese.)

Možete da koristite segmente uvida u ciljnu grupu u gotovim izveštajima o uvidima u angažovanje ili u prilagođenim izveštajima koje ste kreirali. Za više informacija, pogledajte članak [Izveštaji o gotovim profilima](profile-reports.md) i [Kreiranje i uređivanje prilagođenih izveštaja](custom-reports.md).

**Kako se koriste segmenti uvida u ciljnu grupu u izveštajima o uvidima u angažovanje**

1. Na stranici **Radni prostor** izaberite **Podaci**, a zatim izaberite karticu **Segmenti**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Izaberite karticu Segmenti.":::

   >[!NOTE]
   > Odabirom segmenta uvida u ciljnu grupu vodi vas do uvida u ciljnu grupu, gde možete saznati kako je taj segment kreiran u smislu pravila i logike. Za više informacija o segmentima uvida u ciljnu grupu, idite na [Prikaz i kreiranje segmenata](../audience-insights/segments.md).

2. Izaberite gotov izveštaj ili [napravite prilagođeni izveštaj](custom-reports.md), a zatim izaberite **Dodaj uslov**. (Za ovaj primer smo odabrali izveštaj **Prikazi stranice**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Dodajte uslov.":::

3. Izaberite **Filtriraj po segmentima**, proširite listu **Tip segmenta**, a zatim izaberite **Demografski**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Izaberite tip demografskog segmenta.":::

4. Proširite listu **Naziv segmenta**, a zatim izaberite segment uvida u ciljnu grupu.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Odaberite segment.":::

5. Možete da primenite jedan ili više segmenata, uključujući segmente ponašanja (uvidi u angažovanje) i demografske segmente (uvidi u ciljnu grupu). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Izveštaj o prikazima stranica ograničen je na korisnike iz SAD i segmente početne stranice.":::

Na prethodnoj slici, izabrani su segmenti **Klijenti iz SAD** i **Početna stranica**, što ograničava izveštaj **Prikazi stranice** na prikaz samo ta dva segmenta. 


>[!NOTE]
> Možete da koristite segmente uvida u ciljnu grupu da filtrirate gotove izveštaje, prilagođene izveštaje i tokove prodaje u uvidima o angažovanju. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]