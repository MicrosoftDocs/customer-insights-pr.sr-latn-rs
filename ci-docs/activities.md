---
title: Aktivnosti klijenta
description: Definišite aktivnosti klijenata i prikažite ih u vremenskoj osi na profilima klijenata.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188156"
---
# <a name="customer-activities"></a>Aktivnosti klijenta

Aktivnosti klijenata su radnje ili događaji koje obavljaju kupci. Na primer, transakcije, trajanje poziva podrške, pregledi Veb lokacija, kupovina ili povraćaji. Ove aktivnosti se nalaze u jednom ili više izvora podataka. Pomoću usluge "Uvidi kupaca" konsolidujte aktivnosti klijenata iz [ovih izvora podataka](data-sources.md) i povežite ih sa profilima klijenata. Ove aktivnosti se pojavljuju hronološki u vremenskoj osi profila kupca. Uključite vremensku osu u Dynamics 365 aplikacije sa rešenjem [programskog dodatka "Kartica kupca](customer-card-add-in.md) ".

## <a name="define-an-activity"></a>Definišite aktivnost

Entitet mora imati najmanje jedan atribut tipa "Datum" da bi bio uključen **u** vremensku osu kupca. Kontrola **Dodajte aktivnost** je onemogućena ako nije pronađen takav entitet.

1. Idite na aktivnosti **sa** > **podacima**.

1. Kliknite **na dugme "Dodaj** aktivnost" da biste započeli vođeno iskustvo.

1. U koraku **podaci o** aktivnosti unesite sledeće informacije:

   - **Ime aktivnosti**: Ime vaše aktivnosti.
   - **Entitet aktivnosti: Entitet** koji uključuje transakcione podatke ili podatke o aktivnostima.
   - **Primarni** ključ: Polje koje jedinstveno identifikuje zapis. Ono ne bi smelo da sadrži duplikate, prazne vrednosti ili vrednosti koje nedostaju.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Podesite podatke o aktivnosti sa imenom, entitetom i primarnim ključem.":::

1. Izaberite **Sledeće**.

1. U koraku **Relacija** izaberite opciju **Dodaj relaciju** da biste povezali podatke o aktivnostima sa odgovarajućim zapisom klijenta. Ovaj korak vizualizuje vezu između entiteta.  

   - **Strani ključ iz entiteta**: Polje u entitetu aktivnosti koje će se koristiti za uspostavljanje relacije sa drugim entitetom.
   - **U ime entiteta**: Odgovarajući entitet izvornog klijenta sa kojim će entitet aktivnosti biti u vezi. Možete se povezati samo sa izvornim entitetima klijenata koji se koriste u procesu objedinjavanja podataka.
   - **Ime relacije**: Ime koje identifikuje relaciju između entiteta. Ako relacija između ovog entiteta aktivnosti i izabranog entiteta izvornog klijenta već postoji, ime relacije je samo za čitanje.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definisanje relacije između entiteta.":::

   > [!TIP]
   > U B-to-B okruženjima možete izabrati između entiteta poslovnog kontakta i drugih entiteta. Ako izaberete entitet poslovnog kontakta, putanja odnosa se automatski postavlja. Za druge entitete morate definisati putanju odnosa preko jednog ili više posredničkih entiteta dok ne dođete do entiteta poslovnog kontakta.

1. Kliknite **na dugme** "Primeni" da biste kreirali relaciju.

1. Izaberite **Sledeće**.

1. U koraku **Objedinjavanje aktivnosti**, odaberite događaj aktivnosti i vreme početka aktivnosti.
   - **Obavezna polja**
      - **Aktivnost događaja**: Polje koje je događaj za ovu aktivnost.
      - **Vremenska oznaka**: Polje koje predstavlja vreme početka vaše aktivnosti.

   - **Opcionalna polja**
      - **Dodatni detalj**: Polje sa relevantnim informacijama za ovu aktivnost.
      - **Ikona**: Ikona koja najbolje predstavlja ovu vrstu aktivnosti.
      - **Veb-adresa**: Polje koje sadrži URL adresu sa informacijama o ovoj aktivnosti. Na primer, transakcioni sistem koji je izvor ove aktivnosti. Ova URL adresa može biti bilo koje polje iz izvor podataka ili se može konstruisati kao novo polje pomoću transformacije Power Query. Podaci o URL adresi biće sačuvani u entitetu *Objedinjena aktivnost*, koji se može posledično koristiti pomoću [API-ja](apis.md).

   - **Prikaži na vremenskoj osi**
      - Odaberite da li želite da prikazujete ovu aktivnost u prikazu vremenske ose profila klijenata. Izaberite **Da** kako biste prikazali aktivnost na vremenskoj osi ili **Ne** da biste je sakrili.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Navedite podatke o aktivnostima klijenata u entitetu Ujedinjene aktivnosti.":::

1. Kliknite **na dugme** "Dalje" da biste odabrali tip aktivnosti ili kliknite na dugme **"Završi" i rediguj** da biste sačuvali aktivnost sa tipom aktivnosti postavljenim na " **Ostalo"**.

1. U koraku **Tip aktivnosti**, odaberite tip aktivnosti i opcionalno odaberite ako želite da semantički mapirate neke od vrsta aktivnosti za upotrebu u drugim oblastima usluge Customer Insights. Trenutno, tipovi aktivnosti *povratnih* informacija *·*, lojalnosti *·*, prodavca, *linije prodavca* i *aktivnosti* pretplate podržavaju semantiku nakon što ste pristali da mapirate polja. Ako vrsta aktivnosti nije relevantna za novu aktivnost, možete odabrati *Ostalo* ili *Kreiraj novu* za prilagođeni tip aktivnosti.

1. Izaberite **Sledeće**.

1. U koraku **Pregled**, potvrdite svoje izbore. Vratite se na bilo koji od prethodnih koraka i ažurirajte informacije ako je potrebno.

1. Izaberite **Sačuvaj aktivnost** da biste primenili promene i izabrali **Gotovo** da biste se vratili u **Podaci** > **Aktivnosti**. Prikazuje se kreirana aktivnost.

1. Nakon kreiranja svih aktivnosti, izaberite pokrenite da **biste** ih obradili.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Upravljanje postojećim aktivnostima

Idite na **aktivnosti** > **sa podacima** da biste prikazali sačuvane aktivnosti, njihov izvorni entitet, tip aktivnosti i ako su one uključene u vremensku osu kupca. Listu aktivnosti možete da sortirate po bilo kojoj koloni ili da koristite polje za pretragu da biste pronašli aktivnost kojom želite da upravljate.

Izaberite aktivnost da biste prikazali dostupne radnje.

- **Uredite** aktivnost da biste je promenili. Konfiguracija će se otvoriti na koraku redigode. Kada promenite konfiguraciju, izaberite **Sačuvaj aktivnost**, a zatim izaberite **Pokreni** da biste obradili promene.
- **Preimenujte** aktivnost. Izaberite **Sačuvaj** da primenite promene.
- **Izbrišite** aktivnost. Da biste izbrisali više aktivnosti odjednom, izaberite aktivnosti, a zatim **izbrišite**. Potvrdite brisanje.

## <a name="view-activity-timelines-on-customer-profiles"></a>Prikaz vremenskih osa aktivnosti na profilima klijenata

1. Ako ste u konfiguraciji **aktivnosti izabrali opciju "Prikaži vremensku** osu aktivnosti", **idite na stavku "Kupci** " i izaberite profil kupca da biste videli aktivnosti kupca u odeljku Vremenska **osa** aktivnosti.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Prikažite konfigurisane aktivnosti u profilima klijenata.":::

1. Da biste filtrirali aktivnosti na vremenskoj osi aktivnosti:

   - Izaberite jednu ili više ikona aktivnosti da biste pročistili rezultate da biste uključili samo izabrane tipove.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrirajte aktivnosti prema tipu koristeći ikone.":::

   - Izaberite **opciju "Filter** " da biste otvorili tablu sa filterima da biste podesili filtere vremenske ose. Filtrirajte po *tipu aktivnosti* i/ili *datumu*. Izaberite **Primeni**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Koristite tablu filtera za konfigurisanje uslova filtera.":::

1. Da biste uklonili filtere, potvrdite izbor u polju **za potvrdu Obriši** **filtere** ili potvrdite izbor u polju za potvrdu Filter i opozovite izbor u polju za potvrdu filter.

> [!NOTE]
> Filteri aktivnosti se uklanjaju kada napustite profil klijenta. Morate da ih primenite svaki put kada otvorite profil kupca.

[!INCLUDE [footer-include](includes/footer-banner.md)]
