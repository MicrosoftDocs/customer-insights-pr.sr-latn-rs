---
title: Aktivnosti klijenta
description: Definišite aktivnosti klijenata i prikažite ih u vremenskoj osi na profilima klijenata.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: bcb8d42963719f5d225556c31b3fc06db8573e5b
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673155"
---
# <a name="customer-activities"></a>Aktivnosti klijenta

Kombinujte aktivnosti klijenata iz [raznih izvora podataka](data-sources.md) u usluzi Dynamics 365 Customer Insights kako biste kreirali vremensku osu koja hronološki navodi aktivnosti. Uključite hronologiju u Dynamics 365 aplikacije sa rešenjem [Programski dodatak za korisničku karticu](customer-card-add-in.md) ili u Power BI kontrolnoj tabli.

## <a name="define-an-activity"></a>Definišite aktivnost

Vaši izvori podataka mogu da uključe entitete koji imaju podatke o transakcijama i aktivnostima iz više izvora podataka. Identifikujte ove entitete i izaberite aktivnosti koje želite da vidite na vremenskoj osi klijenta. Odaberite entitet koji uključuje vaše ciljne aktivnosti ili aktivnosti.

Entitet mora imati najmanje jedan atribut tipa **Datum** da bi bio uključeni u vremensku osu klijenta i dodavati entitete koji nemaju polja tipa **Datum**. Kontrola **Dodajte aktivnost** je onemogućena ako nije pronađen takav entitet.

1. U uvidima o korisnicima idite na **Podaci** > **Aktivnosti**.

1. Izaberite **Dodaj aktivnost** da biste započeli vođeno iskustvo za postupak podešavanja aktivnosti.

1. U koraku **Podaci o aktivnostima**, podesite vrednosti za sledeća polja:

   - **Naziv aktivnosti**: Izaberite ime za svoju aktivnost.
   - **Entitet**: Odaberite entitet koji uključuje podatke o transakcijama ili aktivnostima.
   - **Primarni ključ**: Izaberite polje koje jedinstveno identifikuje zapis. Ono ne bi smelo da sadrži duplikate, prazne vrednosti ili vrednosti koje nedostaju.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Podesite podatke o aktivnosti sa imenom, entitetom i primarnim ključem.":::

1. Izaberite **Sledeće** da pređete na sledeći korak.

1. U koraku **Odnos**, konfigurišite detalje za povezivanje podataka o aktivnostima sa odgovarajućim zapisom klijenta. Ovaj korak vizualizuje vezu između entiteta.  

   - **Prvi**: Strano polje u entitetu aktivnosti koje će se koristiti za uspostavljanje relacije sa drugim entitetom.
   - **Drugi**: Odgovarajući izvorni entitet klijenta sa kojim će vaš entitet aktivnosti biti u relaciji. Možete se povezati samo sa izvornim entitetima klijenata koji se koriste u procesu objedinjavanja podataka.
   - **Treći**: Ako relacija između ovog entiteta aktivnosti i izabranog izvornog entiteta klijenta već postoji, naziv relacije će biti u režimu samo za čitanje. Ako takva relacija ne postoji, stvoriće se nova relacija sa imenom koje navedete u ovom polju.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definisanje relacije između entiteta.":::

   > [!TIP]
   > U B-to-B okruženjima možete izabrati između entiteta poslovnog kontakta i drugih entiteta. Ako izaberete entitet poslovnog kontakta, putanja odnosa se automatski postavlja. Za druge entitete morate definisati putanju odnosa preko jednog ili više posredničkih entiteta dok ne dođete do entiteta poslovnog kontakta.

1. Izaberite **Sledeće** da pređete na sledeći korak. 

1. U koraku **Objedinjavanje aktivnosti**, odaberite događaj aktivnosti i vreme početka aktivnosti. 
   - **Obavezna polja**
      - **Aktivnost događaja**: Polje koje je događaj za ovu aktivnost.
      - **Vremenska oznaka**: Polje koje predstavlja vreme početka vaše aktivnosti.

   - **Opcionalna polja**
      - **Dodatni detalj**: Polje sa relevantnim informacijama za ovu aktivnost.
      - **Ikona**: Ikona koja najbolje predstavlja ovu vrstu aktivnosti.
      - **Veb-adresa**: Polje koje sadrži URL adresu sa informacijama o ovoj aktivnosti. Na primer, transakcioni sistem koji je izvor ove aktivnosti. Ova URL adresa može biti bilo koje polje iz izvora podataka ili se može napraviti kao novo polje pomoću Power Query transformacije. Podaci o URL adresi biće sačuvani u entitetu *Objedinjena aktivnost*, koji se može posledično koristiti pomoću [API-ja](apis.md).

   - **Prikaži na vremenskoj osi**
      - Odaberite da li želite da prikazujete ovu aktivnost u prikazu vremenske ose profila klijenata. Izaberite **Da** kako biste prikazali aktivnost na vremenskoj osi ili **Ne** da biste je sakrili.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Navedite podatke o aktivnostima klijenata u entitetu Ujedinjene aktivnosti.":::

1. Izaberite **Sledeće** da biste prešli na sledeći korak. Možete izabrati **Završite i pregledaj** da biste sada sačuvali aktivnost sa tipom aktivnosti podešenim na **Ostalo**. 

1. U koraku **Tip aktivnosti**, odaberite tip aktivnosti i opcionalno odaberite ako želite da semantički mapirate neke od vrsta aktivnosti za upotrebu u drugim oblastima usluge Customer Insights. Trenutno, tipovi aktivnosti *Povratne informacije*, *Lojalnost*, *SalesOrder*, *SalesOrderLine* i *Pretplata* se mogu semantički mapirati nakon dogovora o mapiranju polja. Ako vrsta aktivnosti nije relevantna za novu aktivnost, možete odabrati *Ostalo* ili *Kreiraj novu* za prilagođeni tip aktivnosti.

1. Izaberite **Sledeće** da biste prešli na sledeći korak. 

1. U koraku **Pregled**, potvrdite svoje izbore. Vratite se na bilo koji od prethodnih koraka i ažurirajte informacije ako je potrebno.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Pregledajte navedena polja za aktivnost.":::
   
1. Izaberite **Sačuvaj aktivnost** da biste primenili promene i izabrali **Gotovo** da biste se vratili u **Podaci** > **Aktivnosti**. Ovde vidite koje su aktivnosti postavljene da se prikazuju na vremenskoj osi. 

1. Na stranici **Aktivnosti**, izaberite **Pokreni** da biste obradili aktivnost. 

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies). Možete izabrati status procesa da biste videli detalje o toku celog posla. Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.


## <a name="manage-existing-activities"></a>Upravljanje postojećim aktivnostima

Na stranici **Podaci** > **Aktivnosti** možete da vidite sve sačuvane aktivnosti i upravljate njima. Svaka aktivnost se predstavlja u redu koji takođe uključuje detalje o izvoru, entitetu i tipu aktivnosti.

Sledeće radnje su dostupne kada izaberete aktivnost. 

- **Uredi**: Otvara podešavanje aktivnosti u koraku pregleda. U ovom koraku možete promeniti bilo koju trenutnu konfiguraciju. Kada promenite konfiguraciju, izaberite **Sačuvaj aktivnost**, a zatim izaberite **Pokreni** da biste obradili promene.

- **Preimenuj**: Otvara dijalog u koji možete uneti drugo ime za izabranu aktivnost. Izaberite **Sačuvaj** da primenite promene.

- **Izbriši**: Otvara dijalog za potvrdu brisanja izabrane aktivnosti. Takođe možete izbrisati više aktivnosti odjednom tako što ćete izabrati aktivnosti, a zatim izabrati ikonu za brisanje. Izaberite **Izbriši** da biste potvrdili brisanje.

## <a name="view-activity-timelines-on-customer-profiles"></a>Prikaz vremenskih osa aktivnosti na profilima klijenata

Nakon što ste konfigurisali aktivnosti klijenta, izaberite **Prikaži na vremenskoj osi aktivnosti** u konfiguraciji aktivnosti da biste pronašli sve aktivnosti klijenta na profilu klijentu.

Da biste otvorili vremensku osu za klijenta, idite na **Klijenti** i izaberite profil klijenta koji želite da prikažete.

Ako je klijent učestvovao u aktivnosti koju ste konfigurisali, naći ćete je u odeljku **Vremenska osa aktivnosti**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Prikažite konfigurisane aktivnosti u profilima klijenata.":::

Postoji nekoliko načina za filtriranje aktivnosti na vremenskoj osi aktivnosti:

- Možete izabrati jednu ili više ikona aktivnosti da biste precizirali rezultate tako da obuhvataju samo izabrane tipove.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrirajte aktivnosti prema tipu koristeći ikone.":::

- Možete izabrati **Filter** da biste otvorili tablu sa filterima kako biste konfigurisali filtere vremenske ose.

   1. Možete filtrirati prema *ActivityType* i *Datum*
   1. Izaberite **Primeni** da biste koristili filtere na vremenskoj osi aktivnosti.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Koristite tablu filtera za konfigurisanje uslova filtera.":::

Da biste uklonili filtere, izaberite **x** pored svakog filtera primenjenog na vremensku osu ili izaberite **Obriši filtere**.


> [!NOTE]
> Filteri aktivnosti se uklanjaju kada napustite profil klijenta. Morate ih primeniti svaki put kada otvorite profil klijenta.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
