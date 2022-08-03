---
title: Pronalaženje sličnih klijenata sa AI (pregled) (sadrži video)
description: Pronađite slične segmente klijenta pomoću veštačke inteligencije.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170744"
---
# <a name="find-similar-customers-with-ai-preview"></a>Pronađi slične klijente sa AI (pregled)

Pronađite slične klijente u svojoj korisničkoj bazi koristeći veštačku inteligenciju. Potreban vam je najmanje jedan segment kreiran da biste koristili ovu funkciju. Razvijanje kriterijuma postojećeg segmenta pomaže u pronalaženju kupaca koji su slični tom segmentu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Pronalaženje sličnih klijenata* koristi automatizovana sredstva za procenu podataka i predviđanja na osnovu podataka. Stoga ima mogućnost da se koristi kao metod profilisanja, jer je taj termin definisan Opštom uredbom o zaštiti podataka ("GDPR"). Klijentovo korišćenje ove funkcije za obradu podataka može da bude podložno GDPR-u ili drugim zakonima ili propisima. Odgovorni ste za to da koristite Dynamics 365 Customer Insights, uključujući predviđanja, u skladu sa svim važećim zakonima i propisima, uključujući zakone koji se odnose na privatnost, lične podatke, biometrijske podatke, zaštitu podataka i poverljivost komunikacija.

## <a name="find-similar-customers"></a>Pronađi slične klijente

1. Idite na **segmente** i izaberite segment na kojem želite da zasnujete novi segment. To je vaš *izvorni segment*.

1. Izaberite **stavku Pronađi slične kupce**.

1. Pregledajte predloženi naziv za svoj novi segment i promenite ga ako je potrebno.

1. Opcionalno, [dodajte](work-with-tags-columns.md#manage-tags) oznake novom segmentu.

1. Pregledajte polja koja definišu vaš novi segment. Ova polja definišu osnovu na kojoj će sistem pokušati da nađe kupce slične vašem izvornom segmentu. Sistem podrazumevano bira preporučena polja. Ako je potrebno, dodajte još polja.
  Polja koja mogu značajno smanjiti performanse modela automatski se isključuju:
  
   - Polja sa sledećim tipovima podataka: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Polja sa kardinalnošću (broj elemenata u polju) manjom od 2 ili više od 30

1. Odaberite da li želite da uključite **sve** kupce osim izvornog segmenta ili samo kupce u **drugi segment** u novom segmentu.

1. Sistem podrazumevano predlaže da u izlaznu vrednost uključite samo 20% ciljne grupe. Uredite ovu graničnu vrednost po potrebi. Povećanje granične vrednosti će smanjiti preciznost.

1. Uključite kupce u izvorni segment tako što ćete izabrati polje **za potvrdu Uključi članove iz izvornog segmenta pored kupaca sa sličnim** atributima.

1. Kliknite **na** dugme "Pokreni" na dnu stranice da biste [započeli zadatak binarne](#about-similarity-scores) klasifikacije (metod Mašinsko učenje) koji analizira skup podataka.

## <a name="view-the-similar-segment"></a>Prižažite sličan segment

Nakon obrade sličnog segmenta, novi segment ćete pronaći naveden na stranici " **Segmenti** " sa vrstom "Proširenje **"**.

U pregledu članova **segmenta izaberite stavku Prikaz da biste** videli raspodelu rezultata [preko rezultata sličnosti i](#about-similarity-scores) vrednosti rezultata sličnosti **.**

:::image type="content" source="media/expanded-segment.png" alt-text="Segment sličnih klijenata.":::

## <a name="manage-a-similar-segment"></a>Upravljanje sličnim segmentom

[Radite sa sličnim segmentom i upravljajte njima](segments.md#manage-existing-segments) kao i sa drugim segmentima. Na primer, izveite segment ili izgradite meru.

Uredite, osvežite, preimenujte, preuzmite i izbrišite sličan segment. Uređivanje sličnog segmenta ponovoprocesira vaše podatke. Prethodno kreiran segment se ažurira uz osvežene podatke.

## <a name="about-similarity-scores"></a>O ocenama sličnosti

Model mašinskog učenja binarne klasifikacije dodeljuje rezultat kupcima u sličnom segmentu. Rezultat je zasnovan na sličnosti sa kupcima u izvornom segmentu.

- Rezultati sličnosti ispod 0,55 su kupci koje je sistem klasifikovo kao *nije slično* sa kupcima u izvornom segmentu
- Rezultati sličnosti između 0,55 - 0,7 klasifikovani su kao *pomalo slično*
- Rezultati sličnosti između 0,7 - 0,85 klasifikovani su kao *slično*
- Rezultati sličnosti između 0,85 - 1 su kupci koje je sistem klasifikovo *vrlo slično*

Kupci sa rezultatima sličnosti ispod 0,4 nisu uključeni u izlaznu vrednost modela. Sistem ih ne smatra dovoljno sličnim izvornim segmentima.

[!INCLUDE [footer-include](includes/footer-banner.md)]
