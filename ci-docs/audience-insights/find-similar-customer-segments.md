---
title: Pronađi slične klijente sa AI (Video)
description: Pronađite slične segmente klijenta pomoću veštačke inteligencije.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7999c4964773c3b5c49537027a2ed67f0ad57ec5
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 12/10/2021
ms.locfileid: "7903908"
---
# <a name="similar-customers-preview"></a>Slični kupci (verzija za pregled)

Ova funkcija vam omogućava da pronađete slične klijente u svojoj korisničkoj bazi koristeći veštačku inteligenciju. Da biste koristili ovu funkciju, morate da imate bar jedan kreiran segment. Proširenje kriterijuma postojećeg segmenta pomaže u pronalaženju klijenata koji su slični tom segmentu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Pronađite slične kupce* koristi automatizovana sredstva za procenu podataka i pravljenje predviđanja na osnovu tih podataka, pa se zato može koristiti kao način profilisanja, termin koji je definisan Opštom uredbom o zaštiti podataka („GDPR“). Klijentovo korišćenje ove funkcije za obradu podataka može da bude podložno GDPR-u ili drugim zakonima ili propisima. Odgovorni ste za to da koristite Dynamics 365 Customer Insights, uključujući predviđanja, u skladu sa svim važećim zakonima i propisima, uključujući zakone koji se odnose na privatnost, lične podatke, biometrijske podatke, zaštitu podataka i poverljivost komunikacija.

## <a name="finding-similar-customers"></a>Pronalaženje sličnih klijenata

1. U uvidima o korisnicima idite na **Segmenti** i izaberite segment na kojem želite da zasnivate novi segment. To je vaš *izvorni segment*.

1. Na traci radnji izaberite **Pronađi slične kupce**.

1. Pregledajte predloženi naziv za svoj novi segment i promenite ga ako je potrebno.

1. Pregledajte polja koja definišu vaš novi segment. Ova polja definišu osnovu na kojoj će sistem pokušati da nađe kupce slične vašem izvornom segmentu. Sistem će podrazumevano izabrati preporučena polja.
  Polja koja mogu značajno smanjiti performanse modela automatski se isključuju:
  
   - Polja sa sledećim tipovima podataka: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Polja sa kardinalnošću (broj elemenata u polju) manjom od 2 ili više od 30

1. Izaberite da li želite da uključite **Sve kupce** ili samo neke kupce u **Specifični postojeći segment** u vašem novom segmentu.

1. Isključite kupce iz svog izvornog segmenta izborom polja za potvrdu **Izuzmi sve iz izvornog segmenta**.

1. Sistem podrazumevano predlaže da u izlaznu vrednost uključite samo 20% ciljne grupe. Uredite ovu graničnu vrednost po potrebi. Povećanje granične vrednosti će smanjiti preciznost.

1. Izaberite **Pokreni** u dnu stranice da biste započeli zadatak binarne klasifikacije (vid mašinskog učenja) koji analizira skup podataka.

## <a name="view-the-similar-segment"></a>Prižažite sličan segment

Nakon obrade sličnog segmenta, novi segment ćete naći navedenog stranici **Segmenti**.

> [!div class="mx-imgBorder"]
> ![Segment sličnih klijenata.](media/expanded-segment.png "Segment sličnih klijenata")

Izaberite **Prikaži** na traci sa radnjama da biste otvorili detalje segmenta. Ovaj prikaz sadrži informacije o raspodeli rezultata kroz [ocene sličnosti](#about-similarity-scores). Takođe ćete naći sličnosti u vrednostima rezultata u **Pregled članova segmenta**.

## <a name="use-the-output-of-a-similar-segment"></a>Koristite izlaz sličnog segmenta

Možete da [radite sa izlaznom vrednošću sličnog segmenta](segments.md) kao i kod drugih segmenata. Na primer, izveite segment ili izgradite meru.

## <a name="refresh-and-edit-a-similar-segment"></a>Osvežite i uredite sličan segment

Da biste osvežili sličan segment, izaberite ga na stranici **Segmenti**, a zatim izaberite **Osveži** sa trake radnji.

Uređivanjem sličnog segmenta ponovo ćete obraditi vaše podatke. Prethodno kreiran segment se ažurira uz osvežene podatke.    
Da biste uredili sličan segment, izaberite ga na stranici **Segmenti**, a zatim izaberite **Uredi** sa trake radnji. Primenite promene i izaberite **Pokreni** da biste započeli obradu.

## <a name="delete-a-similar-segment"></a>Izbrišite sličan segment

Izaberite segment na stranici **Segmenti**, a zatim izaberite **Izbriši** sa trake radnji. Zatim potvrdite brisanje.

## <a name="about-similarity-scores"></a>O ocenama sličnosti

Model mašinskog učenja binarne klasifikacije dodeljuje rezultat kupcima u sličnom segmentu. Rezultat je zasnovan na sličnosti sa kupcima u izvornom segmentu.

- Rezultati sličnosti ispod 0,55 su kupci koje je sistem klasifikovo kao *nije slično* sa kupcima u izvornom segmentu
- Rezultati sličnosti između 0,55 - 0,7 klasifikovani su kao *pomalo slično*
- Rezultati sličnosti između 0,7 - 0,85 klasifikovani su kao *slično*
- Rezultati sličnosti između 0,85 - 1 su kupci koje je sistem klasifikovo *vrlo slično*

Kupci sa rezultatima sličnosti ispod 0,4 nisu uključeni u izlaznu vrednost modela. Sistem ih ne smatra dovoljno sličnim izvornim segmentima.


[!INCLUDE[footer-include](../includes/footer-banner.md)]