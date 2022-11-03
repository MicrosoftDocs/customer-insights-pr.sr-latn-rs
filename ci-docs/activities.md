---
title: Aktivnosti kupaca ili poslovnih kontakata
description: Definišite aktivnosti kupaca ili poslovnih kontakata i prikažite ih na vremenskoj osi profila klijenata.
ms.date: 10/26/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: srivas15
ms.author: shsri
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: d8caa477278f04c3a0a95ced15f4bea2a22aa8cd
ms.sourcegitcommit: da6a2d189edacc8f2c0f2abedcb28245f26fe74c
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/27/2022
ms.locfileid: "9723798"
---
# <a name="customer-or-business-contact-activities"></a>Aktivnosti kupaca ili poslovnih kontakata

Aktivnosti klijenata su radnje ili događaji koje obavljaju klijenti ili poslovni kontakti. Na primer, transakcije, trajanje poziva podrške, pregledi Veb lokacija, kupovina ili povraćaji. Ove aktivnosti se nalaze u jednom ili više izvora podataka. Pomoću usluge "Uvidi kupaca" konsolidujte aktivnosti klijenata iz [ovih izvora podataka](data-sources.md) i povežite ih sa profilima klijenata. Ove aktivnosti se pojavljuju hronološki u vremenskoj osi profila kupca. Uključite vremensku osu u Dynamics 365 aplikacije sa rešenjem [programskog dodatka "Kartica kupca](customer-card-add-in.md) ".

## <a name="define-a-customer-activity"></a>Definisanje aktivnosti klijenta

Entitet mora imati najmanje jedan atribut tipa "Datum" da bi bio uključen **u** vremensku osu kupca. Kontrola **Dodajte aktivnost** je onemogućena ako nije pronađen takav entitet.

1. Idite na aktivnosti **sa** > **podacima**.

1. Kliknite **na dugme "Dodaj** aktivnost" da biste započeli vođeno iskustvo.

1. U koraku **podaci o** aktivnosti unesite sledeće informacije:

   - **Naziv aktivnosti**: Izaberite ime za svoju aktivnost.
   - **Entitet aktivnosti: Izaberite** entitet koji uključuje transakcione podatke ili podatke o aktivnostima.
   - **Primarni ključ**: Izaberite polje koje jedinstveno identifikuje zapis. Ono ne bi smelo da sadrži duplikate, prazne vrednosti ili vrednosti koje nedostaju.

     > [!NOTE]
     > Primarni ključ za svaki red mora ostati dosledan u izvor podataka osvežava. Ako se primarni ključ za red ažurira u osvežavanju izvor podataka, on kreira duplikate u izlaznom entitetu aktivnosti. 

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Podesite podatke o aktivnosti sa imenom, entitetom i primarnim ključem.":::

1. Izaberite **Sledeće**.

1. U koraku **Relacija** izaberite opciju **Dodaj relaciju** da biste povezali podatke o aktivnostima sa odgovarajućim zapisom klijenta. Ovaj korak vizualizuje vezu između entiteta.  

   - **Strani ključ**: Strano polje u entitetu aktivnosti koje će se koristiti za uspostavljanje odnosa sa drugim entitetom.
   - **U ime entiteta**: Odgovarajući entitet izvornog klijenta sa kojim će entitet aktivnosti biti u vezi. Možete se povezati samo sa izvornim entitetima klijenata koji se koriste u procesu objedinjavanja podataka.
   - **Ime relacije**: Ako relacija između ovog entiteta aktivnosti i izabranog entiteta izvornog klijenta već postoji, ime relacije će biti u režimu samo za čitanje. Ako takva relacija ne postoji, stvoriće se nova relacija sa imenom koje navedete u ovom polju.

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

## <a name="manage-existing-customer-activities"></a>Upravljanje postojećim aktivnostima klijenata

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

> [!NOTE]
> Filteri aktivnosti se uklanjaju kada napustite profil klijenta. Morate da ih primenite svaki put kada otvorite profil kupca.

## <a name="define-a-contact-activity"></a>Definisanje aktivnosti kontakta

Za poslovne naloge (B-na-B), koristite *entitet ContactProfile* da biste uhvatili aktivnosti kontakata. Na vremenskoj osi aktivnosti možete videti za konto koji kontakt je odgovoran za svaku aktivnost. Većina koraka sledi konfiguraciju mapiranja aktivnosti klijenta.

   > [!NOTE]
   > Da biste definisali aktivnost na nivou kontakta, *mora se kreirati entitet KontaktProfile*, bilo kao [objedinjeni profil](data-unification-contacts.md)[kontakta ili putem semantičkog mapiranja](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Morate imati ID **naloga i atribute** **"ID kontaktA** " za svaki zapis u okviru podataka o aktivnostima.
  
1. Idite na aktivnosti **sa** > **podacima**.

1. Izaberite **opciju Dodaj aktivnost**.

1. U koraku **podaci o** aktivnosti unesite sledeće informacije:

   - **Naziv aktivnosti**: Izaberite ime za svoju aktivnost.
   - **Entitet aktivnosti: Izaberite** entitet koji uključuje transakcione podatke ili podatke o aktivnostima.
   - **Primarni ključ**: Izaberite polje koje jedinstveno identifikuje zapis. Ono ne bi smelo da sadrži duplikate, prazne vrednosti ili vrednosti koje nedostaju.

     > [!NOTE]
     > Primarni ključ za svaki red mora ostati dosledan u izvor podataka osvežava. Ako se primarni ključ za red ažurira u osvežavanju izvor podataka, on kreira duplikate u izlaznom entitetu aktivnosti. 


1. U odnosi **koraku** kreirajte indirektnu relaciju između izvornih podataka aktivnosti sa nalozima, koristeći podatke o kontaktu kao posrednički entitet. Više informacija potražite u direktnim [i indirektnim putanjama odnosa](relationships.md#relationship-paths).
   - Primer relacije za aktivnost koja se zove "Nabavke *"*:
      - **Podaci o kontaktu izvorne aktivnosti** > **nabavke** na atributu ID **kontakta**
      - **Podaci o nalogu** > **podataka** kontakta na ID-u **naloga atributa**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Primer podešavanja relacija.":::

1. Kada podešavate odnosi, kliknite na dugme **"** Dalje" i dovršite konfiguraciju mapiranja aktivnosti. Detaljne korake kreiranja aktivnosti pogledajte u članku [Definisanje aktivnosti klijenta](#define-a-customer-activity).

1. Pokrenite mapiranja aktivnosti.

1. Aktivnosti na nivou kontakta će sada biti vidljive na vremenskoj osi kupca.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Konačni rezultat nakon konfigurisanja aktivnosti kontakta":::

## <a name="contact-level-activity-timeline-filtering"></a>Filtriranje vremenske ose na nivou aktivnosti na nivou kontakta

Nakon konfigurisanja mapiranja aktivnosti na nivou kontakta i njegovog pokretanja, vremenska osa aktivnosti za kupce će biti ažurirana. On uključuje njihove ID-ove ili imena, u zavisnosti od konfiguracije *ContactProfile datoteke*, za aktivnosti na kojima su delovali. Aktivnosti možete filtrirati po kontaktima na vremenskoj osi da biste videli određene kontakte koji vas interesuju. Pored toga, možete videti sve aktivnosti koje nisu dodeljene određenom kontaktu tako što ćete **izabrati stavku Aktivnosti koje nisu mapirane kontaktu**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opcije filtriranja dostupne za aktivnosti na nivou kontakta.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
