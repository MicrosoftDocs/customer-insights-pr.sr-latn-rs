---
title: Uvidi u segmente (verzija za pregled)
description: Steknite uvid u postojeće segmente da biste videli razlike i zajedničke karakteristike.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171020"
---
# <a name="segment-insights-preview"></a>Uvidi u segmente (verzija za pregled)

Otkrijte dodatne informacije i uvide o vašim postojećim segmentima. Otkrijte šta razlikuje dva segmenta ili šta imaju zajedničko.

## <a name="segment-overlap"></a>Preklapanje segmenata

Analiza preklapanja segmenata pokazuje koliko i koji su klijenti zajednički za dva ili više segmenata. Na primer, kako se segment čestih klijenata preklapa sa segmentom koji sadrži klijente koji su zadovoljni uslugom ili proizvodom.
Takođe možete da analizirate kako se preklapanje menja za određene atribute.

### <a name="run-an-overlap-analysis"></a>Pokrenite analizu preklapanja

1. Idite na **Segmenti**, a zatim izaberite karticu **Uvidi (verzija za pregled)**.

1. Izaberite **Novo**, a zatim odaberite opciju **Preklapanje** u oknu **Izaberite tip uvida**.

1. Odaberite segmente koji vas zanimaju i izaberite **Sledeći**.

1. Opcionalno, odaberite jedno ili više polja od interesa da biste analizirali preklapanja za svaku moguću vrednost polja, a zatim izaberite **Sledeći**.

1. Navedite ime za analizu preklapanja, izborni ime za prikaz i opis.

1. Izaberite **Sačuvaj** za početak analize. Analiza preklapanja je spremna kada se status promeni iz Osvežavanje u Uspešno.

### <a name="view-and-optimize-an-overlap-analysis"></a>Pregled i optimizacija analize preklapanja

1. Po završetku analize pronađite detalje o ovom uvidu u **Segmenti** > **Uvidi (verzija za pregled)**.

   :::image type="content" source="media/segment-overlap.png" alt-text="Detalji uvida u preklapanje segmenata.":::

1. Izaberite uvid da biste videli rezultate analize:

   - Broj članova koji se preklapaju sa segmentima odabranim za analizu.
   - Broj članova koji su uključeni u jedan od segmenata, ali ne i u ostalim segmentima.
   - Ako ste tokom konfigurisanja analize preklapanja izabrali polja, naći ćete ih u odgovarajućim karticama. Pomoću padajućeg menija filtera možete odabrati bilo koji nivo atributa koji vas zanima, a tabela na dnu će prikazati odgovarajuće podatke.

## <a name="segment-differentiators"></a>Diferencijatori segmenta

Razlike između segmenata vam pomažu da otkrijete šta razlikuje segment od ostalih klijenata ili nekog drugog segmenta. Izaberite segment i sistem identifikuje atribute profila i mere koje razlikuju izabrani segment.

### <a name="run-a-differentiator-analysis"></a>Pokrenite analizu razlika

1. Idite na **Segmenti**, a zatim izaberite karticu **Uvidi (verzija za pregled)**.

1. Izaberite **opciju** Novo i odaberite **opciju "Razlikovači** " u oknu **"Odaberi tip uvida** ".

1. Odaberite segment koji želite da analizirate kao **Primarni segment**, a zatim izaberite **Sledeći**.

1. Odaberite **Svi kupci** ili **Sekundarni segment** sa kojim biste uporedili svoj primarni segment, a zatim izaberite **Sledeći**.

1. Opcionalno, odaberite jedno ili više polja od interesa da biste analizu fokusirali na određene atribute, a zatim izaberite **Sledeći**.

1. Navedite ime za analizu razlikujevača, opcionalnu ime za prikaz i opis.

1. Izaberite **Sačuvaj** za početak analize. Analiza razlikujevača je spremna kada se status promeni iz "Osvežavanje" u "Uspešno".

### <a name="view-and-optimize-a-differentiators-analysis"></a>Pogledajte i optimizujte analizu razlika

1. Kada dovršite analizu, idite na " **Uvidi u segmente** > **" (pregled)**.

   :::image type="content" source="media/segment-differentiators.png" alt-text="Detalji uvida u razlike između segmenata.":::

1. Izaberite uvid da biste videli rezultate analize. Analiza razlika uključuje dve kartice. Kartica **Atributi** navodi atribute profila koji se smatraju razlikama. Kartica **Mere** navodi razlike. Svaka kartica sadrži sledeće detalje:

   - Rangiranu listu razlika, sortiranu po razlici bodovanja.
   - **Bodovanje razlike** za svaku razliku. Rezultat razlike predstavlja stepen razlikovanja atributa u dva segmenta. Što je veće bodovanje razlike, to se atributi više razlikuju između dva segmenta. Izaberite bodovanje da biste otvorili okno **Bodovanje razlike** sa raspodelom vrednosti za taj atribut.

## <a name="manage-segment-insights"></a>Upravljanje uvidima u segmente

Idite na **uvide u** > **segmente (pregled) da** biste prikazali uvide u segmente i upravljali njima. Izaberite uvid u segment da biste prikazali dostupne radnje.

- **Prikaz** analize uvida
- **Uređivanje** uvida radi promene svojstava
- **Osvežite** uvid da biste ponovo pokrenuli analizu
- **Preimenuj** uvid
- **Brisanje** uvida

[!INCLUDE [footer-include](includes/footer-banner.md)]
