---
title: Aktivnosti klijenta
description: Definišite aktivnosti klijenata i pregledajte ih na vremenskoj osi klijenata.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596746"
---
# <a name="customer-activities"></a>Aktivnosti klijenta

Kombinujte aktivnosti klijenata iz [raznih izvora podataka](data-sources.md) u usluzi Dynamics 365 Customer Insights da biste kreirali vremensku osu klijenata koja navodi aktivnosti u hronološkom redosledu. Vremensku osu možete uključiti u aplikacije za angažovanje korisnika u sistemu Dynamics 365 preko [programskog dodatka kartice klijenta](customer-card-add-in.md) ili u Power BI kontrolnoj tabli.

## <a name="define-an-activity"></a>Definišite aktivnost

Vaši izvori podataka uključuju entitete koji imaju podatke o transakcijama i aktivnostima iz više izvora podataka. Identifikujte ove entitete i izaberite aktivnosti koje želite da vidite na vremenskoj osi klijenta. Odaberite entitet koji uključuje vaše ciljne aktivnosti ili aktivnosti.

1. U uvidima o korisnicima idite na **Podaci** > **Aktivnosti**.

1. Izaberite **Dodaj aktivnost**.

   > [!NOTE]
   > Entitet mora imati najmanje jedan atribut tipa **Datum** da bi bio uključeni u vremensku osu klijenta i dodavati entitete koji nemaju polja tipa **Datum**. Kontrola **Dodajte aktivnost** je onemogućena ako nije pronađen takav entitet.

1. U oknu **Dodajte aktivnost**, postavite vrednosti za sledeća polja:

   - **Entitet**: Odaberite entitet koji uključuje podatke o transakcijama ili aktivnostima.
   - **Primarni ključ**: Izaberite polje koje jedinstveno identifikuje zapis. Ono ne bi smelo da sadrži duplikate, prazne vrednosti ili vrednosti koje nedostaju.
   - **Vremenska oznaka**: Izaberite polje koje predstavlja vreme početka vaše aktivnosti.
   - **Događaj**: Izaberite polje koje je događaj za aktivnost.
   - **Veb-adresa**: Izaberite polje koje predstavlja URL adresu koja pruža dodatne informacije o ovoj aktivnosti. Na primer, transakcioni sistem koji je izvor ove aktivnosti. Ova URL adresa može biti bilo koje polje iz izvora podataka ili se može napraviti kao novo polje pomoću Power Query transformacije. Podaci ove URL adrese će biti sačuvani u entitetu objedinjenih aktivnosti, koji može da se koristi na nižem toku pomoću API-ja.
   - **Detalji**: Po želji, odaberite polje koje ćete dodati za dodatne detalje.
   - **Ikona**: Po želji odaberite ikonu koja predstavlja ovu aktivnost.
   - **Tip aktivnosti**: Definišite referencu tipa aktivnosti na Common Data Model koji najbolje opisuje semantičku definiciju aktivnosti.

1. U odeljku **Uspostavite odnos**, konfigurišite detalje da biste povezali podatke o aktivnostima sa odgovarajućim klijentom.

    - **Polje entiteta aktivnosti**: Izaberite polje u vašem entitetu aktivnosti koje će se koristiti za uspostavljanje veze sa drugim entitetom.
    - **Entitet klijenta**: Izaberite odgovarajući entitet korisnika sa kojim će vaš odnos biti u relaciji. Možete se odnositi samo na one izvorne entitete klijenata koji se koriste u postupku objedinjavanja podataka.
    - **Polje entiteta klijenta**: Ovo polje prikazuje primarni ključ izvornog entiteta klijenta kako je izabran u procesu mapiranja. Ovo polje primarnog ključa u izvornom entitetu klijenta koristi se za uspostavljanje relacije sa entitetom aktivnosti.
    - **Naziv**: Ako relacija između ovog entiteta aktivnosti i izabranog izvornog entiteta klijenta već postoji, naziv relacije će biti u režimu samo za čitanje. Ako takva relacija ne postoji, stvoriće se nova relacija sa ovde navedenim nazivom.
   
   > [!div class="mx-imgBorder"]
   > ![Definisanje relacije entiteta](media/activities-entities-define.png "Definisanje relacije entiteta")

1. Izaberite **Sačuvaj** da primenite promene.

1. Na stranici **Aktivnosti**, izaberite **Pokreni**.

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies). Možete izabrati status procesa da biste videli detalje o toku celog posla. Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.

## <a name="edit-an-activity"></a>Uređivanje aktivnosti

1. U uvidima o korisnicima idite na **Podaci** > **Aktivnosti**.

2. Izaberite entitet aktivnosti koji želite da izmenite i izaberite **Uređuj**. Ili možete da zadržite pokazivač preko reda entiteta i izaberite ikonu **Uređuj**.

3. Kliknite na ikonu **Uređuj**.

4. U oknu **Uređivanje aktivnosti**, ažurirajte vrednosti i izaberite **Sačuvaj**.

5. Na stranici **Aktivnosti**, izaberite **Pokreni**.

## <a name="delete-an-activity"></a>Izbriši aktivnost

1. U uvidima o korisnicima idite na **Podaci** > **Aktivnosti**.

2. Izaberite entitet aktivnosti koji želite da uklonite i izaberite **Izbriši**. Ili možete da zadržite pokazivač preko reda entiteta i izaberite ikonu **Izbriši**. Pored toga, možete izabrati više entiteta aktivnosti koje ćete istovremeno izbrisati.
   > [!div class="mx-imgBorder"]
   > ![Uređivanje ili brisanje relacija između entiteta](media/activities-entities-edit-delete.png "Uređivanje ili brisanje relacija između entiteta")

3. Izaberite ikonu **Izbriši**.

4. Potvrdite brisanje.


[!INCLUDE[footer-include](../includes/footer-banner.md)]