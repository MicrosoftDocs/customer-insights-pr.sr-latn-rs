---
title: Uvid u segmente za postojeće segmente
description: Steknite uvid u postojeće segmente da biste videli razlike i zajedničke karakteristike.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1f90b0d18331584fce306da38bd31faea93ef97e
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732329"
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

Po završetku analize pronađite detalje o ovom uvidu u **Segmenti** > **Uvidi (verzija za pregled)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Detalji uvida u preklapanje segmenata.":::

Izaberite uvid da biste videli rezultate analize:

- Broj članova koji se preklapaju sa segmentima odabranim za analizu.
- Broj članova koji su uključeni u jedan od segmenata, ali ne i u ostalim segmentima.
- Ako ste tokom konfigurisanja analize preklapanja izabrali polja, naći ćete ih u odgovarajućim karticama. Pomoću padajućeg menija filtera možete odabrati bilo koji nivo atributa koji vas zanima, a tabela na dnu će prikazati odgovarajuće podatke.

## <a name="segment-differentiators"></a>Diferencijatori segmenta

Razlike između segmenata vam pomažu da otkrijete šta razlikuje segment od ostalih klijenata ili nekog drugog segmenta. Morate samo izabrati segment i sistem će prepoznati atribute profila i mere koje razlikuju izabrani segment.

### <a name="run-a-differentiator-analysis"></a>Pokrenite analizu razlika

1. Idite na **Segmenti**, a zatim izaberite karticu **Uvidi (verzija za pregled)**.

1. Izaberite **Novo**, a zatim odaberite opciju **Preklapanje** u oknu **Izaberite tip uvida**.

1. Odaberite segment koji želite da analizirate kao **Primarni segment**, a zatim izaberite **Sledeći**.

1. Odaberite **Svi kupci** ili **Sekundarni segment** sa kojim biste uporedili svoj primarni segment, a zatim izaberite **Sledeći**.

1. Opcionalno, odaberite jedno ili više polja od interesa da biste analizu fokusirali na određene atribute, a zatim izaberite **Sledeći**.

1. Navedite ime za analizu preklapanja, izborni ime za prikaz i opis.

1. Izaberite **Sačuvaj** za početak analize. Analiza preklapanja je spremna kada se status promeni iz Osvežavanje u Uspešno.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Pogledajte i optimizujte analizu razlika

Po završetku analize pronađite detalje o ovom uvidu u **Segmenti** > **Uvidi (verzija za pregled)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Detalji uvida u razlike između segmenata.":::

Izaberite uvid da biste videli rezultate analize. Analiza razlika uključuje dve kartice. Kartica **Atributi** navodi atribute profila koji se smatraju razlikama. Kartica **Mere** navodi razlike. Svaka kartica sadrži sledeće detalje:

- Rangiranu listu razlika, sortiranu po razlici bodovanja.
- **Bodovanje razlike** za svaku razliku. Rezultat razlike predstavlja stepen razlikovanja atributa u dva segmenta. Što je veće bodovanje razlike, to se atributi više razlikuju između dva segmenta. Izaberite bodovanje da biste otvorili okno **Bodovanje razlike** sa raspodelom vrednosti za taj atribut.

## <a name="manage-segment-insights"></a>Upravljanje uvidima u segmente

Možete da koristite sledeće opcije na uvidima iz komandne trake:

- **Nazad** da biste vratili listu uvida
- **Osveži** da biste ponovo pokrenuli analizu
- **Izbriši** da biste uklonili ovaj uvid


[!INCLUDE[footer-include](../includes/footer-banner.md)]
