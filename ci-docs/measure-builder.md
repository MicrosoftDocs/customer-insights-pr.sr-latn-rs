---
title: Kreiranje novih mera pomoću izrade mera
description: Izgradite mere od početka da biste analizirali ključne metrike o svom poslovanju.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: f3ec86806074a12c1107648303ed2d65e97ebc69
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083023"
---
# <a name="create-new-measures-with-the-measure-builder"></a>Kreiranje novih mera pomoću izrade mera

Ovaj članak sadrži objašnjenja o tome kako da kreirate novu [meru od](measures.md) početka. Izrada mera vam omogućava da definišete izračunavanja pomoću matematičkih operatora, funkcija agregacije i filtera. Meru možete da napravite sa atributima iz entiteta koji su povezani sa objedinjeni entitet *kupca*.

Stvaranje mera u okruženjima od Bi-Bi-Bi-Si i B-to-B funkcioniše na isti način. Međutim, ako okruženje B-na-B koristi naloge sa [hijerarhijama](relationships.md#set-up-account-hierarchies), možete odabrati da agregirajte meru preko srodnih pod-naloga.

Meru možete brzo da kreirate i tako što ćete odabrati skup najčešće korišćenih i unapred definisanih mera. Više informacija potražite u članku [Korišćenje predloška za izradu mere](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

Mere možete kreirati na nivou pojedinačnih kupaca (atribut kupca, mera kupca) ili na nivou preduzeća/organizacije (poslovna mera). Atribut kupca i mera kupca su dve vrste koje vam omogućavaju praćenje performansi po kupcu. Na primer, ukupna potrošnja svakog kupca. Poslovne mere vam omogućavaju da pratite performanse po preduzeću. Na primer, ukupan prihod preduzeća.

- Atribut kupca: Generiše izlaz kao novi atribut koji se čuva kao nova kolona u sistemski generisani entitet pod imenom *Customer_Measure*. Prilikom osvežavanja atributa kupca, svi ostali atributi kupca *u Customer_Measure* istovremeno osvežavaju entitet. Pored toga, atributi kupca su prikazani na kartici profila kupca. Kada se pokrene ili sačuva, atribut kupca ne možete da ga promenite u meru kupca.

- Mera kupca: Generiše izlaz kao sopstveni entitet i ne možete ga promeniti u atribut kupca kada se jednom pokrene ili sačuva. Mere kupca se ne prikazuju na kartici profila kupca.

- Poslovna mera: Generiše izlaz kao sopstveni entitet i pokazuje na matičnoj stranici okruženja uvida kupaca.

1. Idite **na mere**.

1. Izaberite **Nova** i birajte **Napravite sopstvenu**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Prazan ekran za konfiguraciju za meru od B do C." lightbox="media/measure-b2c.png":::

1. Da biste pratili performanse na poslovnom nivou, prebacite **tip mere** na **nivo preduzeća**. **Nivo kupca** je podrazumevano izabran. **Nivo kupca** automatski dodaje atribut *"ID kupca* " dimenzijama **dok ga** nivo poslovanja automatski uklanja.

1. U oblasti konfiguracije odaberite funkciju agregacije iz padajuće menija **Funkcije** Izaberite. Agregatne funkcije uključuju:
   - **Sum**
   - **Prosek**
   - **Brojanje**
   - **Broj jedinstvenih**
   - **Maksimalna**
   - **Min**
   - **Prvi**: uzima prvu vrednost zapisa podataka
   - **Poslednji**: uzima poslednju vrednost koja je dodata u zapis podataka
   - **ArgMax**: pronalazi zapis podataka koji daje maksimalnu vrednost iz ciljne funkcije
   - **ArgMin**: pronalazi zapis podataka koji daje minimalnu vrednost iz ciljne funkcije

1. Izaberite **Dodaj atribut** da biste izabrali podatke koji su vam potrebni za kreiranje ove mere.

   1. Izaberite karticu **Atributi**.
   1. Entitet podataka: Izaberite entitet koji uključuje atribut koji želite da merite.
   1. Atribut podataka: Izaberite atribut koji želite da koristite u agregatnoj funkciji za izračunavanje mere. Istovremeno možete da izaberete samo jedan atribut.
   1. Takođe možete izabrati atribut podataka iz postojeće mere izborom kartice **Mere** ili možete da pretražite naziv entiteta ili naziv mere.
   1. Izaberite **Dodaj** da biste meri dodali izabrani atribut.

1. Da biste izgradili složenije mere, možete dodati više atributa ili koristiti matematičke operatore na svojoj funkciji mere.

1. Da biste dodali filtere, izaberite **Filter** u oblasti konfiguracije. Primena filtera će koristiti samo zapise koji se podudaraju sa filterima za izračunavanje mere.
  
   1. U odeljku **Dodaj atribut** okna **Filteri**, izaberite atribut koji želite da koristite za kreiranje filtera.
   1. Postavite operatore filtera da definišu filter za svaki izabrani atribut.
   1. Izaberite **Primeni** da biste meri dodali filtere.

1. Izaberite **dimenziju** da biste odabrali više polja koja se dodaju kao kolone izlaznom entitetu mere.

   1. Izaberite **Uređivanje dimenzija** da biste dodavali atribute podataka po kojima želite da grupišete vrednosti mere. Na primer, grad ili pol.
   > [!TIP]
   > Ako ste izabrali **nivo kupca** kao **meru,** *atribut "ID kupca*" je već dodat. Ako uklonite atribut, tip mere **će se** prebaciti na nivo **"Posao"**.
   1. Izaberite **Gotovo** da biste meri dodali dimenzije.

1. Ako u vašim podacima postoje vrednosti koje morate zameniti celim brojem, izaberite **Pravila**. Konfigurišite pravilo i obavezno odaberite samo cele brojeve kao zamenu. Na primer, zamenite *nula* sa *0*.

1. Ako postoji više putanja između entiteta podataka koji ste mapirali i entiteta *Klijent*, morate odabrati jednu od identifikovanih [putanja relacija između entiteta](relationships.md). Rezultati merenja mogu se razlikovati u zavisnosti od izabrane putanje.

   1. Izaberite **Putanja odnosa** i izaberite putanju entiteta koju treba koristiti za identifikaciju mere. Ako postoji samo jedan put do entiteta *Klijent*, ova kontrola se neće prikazati.
   1. Izaberite **Gotovo** da primenite svoj izbor.

1. Da biste dodali još proračuna za meru, izaberite **Novi proračun**. Entitete na istoj putanji entiteta možete koristiti samo za nove proračune. Više proračuna će se prikazati kao nove kolone u izlaznom entitetu mere.

1. Izaberite vertikalnu elipsu (&vellip;) u izračunavanju u "Dupliranje **", "** Preimenuj **·**" **ili "Ukloni** izračunavanje" iz mere.

1. U oblasti **Pregled** videćete šemu podataka izlaznog entiteta mere, uključujući filtere i dimenzije. Pregled dinamički reaguje na promene u konfiguraciji.

1. Izaberite **uredi** detalje pored mere bez naslova. Navedite ime za meru. Opcionalno, [dodajte](work-with-tags-columns.md#manage-tags) oznake u meru.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dijalog &quot;Uređivanje detalja&quot;.":::

1. Izaberite **Pokreni** da biste izračunali rezultate za konfigurisanu meru. Izaberite **Sačuvaj i zatvori** ako želite da zadržite trenutnu konfiguraciju i pokrenete meru kasnije.

1. Idite na **Mere** da biste na listi videli novokreiranu meru.

# <a name="business-accounts-b-to-b"></a>[Poslovni nalozi (B-to-B)](#tab/b2b)

Mere možete kreirati na nivou pojedinačnih konta (mera kupca) ili na nivou svih konta (poslovna mera).

- Mera kupca: Generiše izlaz kao sopstveni entitet. Mere kupca se ne prikazuju na kartici profila kupca.

- Poslovna mera: Generiše izlaz kao sopstveni entitet i pokazuje na matičnoj stranici okruženja uvida kupaca.

1. Idite **na mere**.

1. Izaberite **Novo**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Prazan ekran za konfiguraciju za meru od B do B.":::

1. U oblasti konfiguracije odaberite funkciju agregacije iz padajuće menija **Funkcije** Izaberite. Agregatne funkcije uključuju:
   - **Sum**
   - **Prosek**
   - **Brojanje**
   - **Broj jedinstvenih**
   - **Maksimalna**
   - **Min**
   - **Prvi**: uzima prvu vrednost zapisa podataka
   - **Poslednji**: uzima poslednju vrednost koja je dodata u zapis podataka

1. Izaberite **Dodaj atribut** da biste izabrali podatke koji su vam potrebni za kreiranje ove mere.

   1. Izaberite karticu **Atributi**.
   1. Entitet podataka: Izaberite entitet koji uključuje atribut koji želite da merite.
   1. Atribut podataka: Izaberite atribut koji želite da koristite u agregatnoj funkciji za izračunavanje mere. Istovremeno možete da izaberete samo jedan atribut.
   1. Takođe možete izabrati atribut podataka iz postojeće mere izborom kartice **Mere** ili možete da pretražite naziv entiteta ili naziv mere.
   1. Izaberite **Dodaj** da biste meri dodali izabrani atribut.

1. Da biste izgradili složenije mere, možete dodati više atributa ili koristiti matematičke operatore na svojoj funkciji mere.

1. Da biste dodali filtere, izaberite **Filter** u oblasti konfiguracije. Primena filtera će koristiti samo zapise koji se podudaraju sa filterima za izračunavanje mere.
  
   1. U odeljku **Dodaj atribut** okna **Filteri**, izaberite atribut koji želite da koristite za kreiranje filtera.
   1. Postavite operatore filtera da definišu filter za svaki izabrani atribut.
   1. Izaberite **Primeni** da biste meri dodali filtere.

1. Izaberite **dimenziju** da biste odabrali više polja koja se dodaju kao kolone izlaznom entitetu mere.

   1. Izaberite **Uređivanje dimenzija** da biste dodavali atribute podataka po kojima želite da grupišete vrednosti mere. Na primer, grad ili pol.
      > [!TIP]
      > Ako ste izabrali **nivo kupca** kao **meru,** *atribut "ID kupca*" je već dodat. Ako uklonite atribut, tip **mere se** prebacuje na nivo **"Posao"**.
   1. Izaberite **Gotovo** da biste meri dodali dimenzije.

1. Ako u vašim podacima postoje vrednosti koje morate zameniti celim brojem, izaberite **Pravila**. Konfigurišite pravilo i obavezno odaberite samo cele brojeve kao zamenu. Na primer, zamenite *nula* sa *0*.

1. Možete koristiti prekidač **Sabiranje dodatnih poslovnih kontakata** ako [koristite naloge sa hijerarhijom](relationships.md#set-up-account-hierarchies).
   - Ako je podešeno na **Isključeno**, mera se izračunava za svaki poslovni kontakt. Svaki poslovni kontakt ima svoj rezultat.
   - Ako je podešeno na **Uključeno**, izaberite **Uredi** da biste odabrali hijerarhiju poslovnih kontakata prema unetim hijerarhijama. Mera će dati samo jedan rezultat jer je objedinjena sa podnalozima.

1. Ako postoji više putanja između entiteta podataka koji ste mapirali i entiteta *Klijent*, morate odabrati jednu od identifikovanih [putanja relacija između entiteta](relationships.md). Rezultati merenja mogu se razlikovati u zavisnosti od izabrane putanje.

   1. Izaberite **Putanja odnosa** i izaberite putanju entiteta koju treba koristiti za identifikaciju mere. Ako postoji samo jedan put do entiteta *Klijent*, ova kontrola se neće prikazati.
   1. Izaberite **Gotovo** da primenite svoj izbor.

1. Izaberite vertikalnu elipsu (&vellip;) u izračunavanju u "Dupliranje **", "** Preimenuj **·**" **ili "Ukloni** izračunavanje" iz mere.

1. U oblasti **Pregled** videćete šemu podataka izlaznog entiteta mere, uključujući filtere i dimenzije. Pregled dinamički reaguje na promene u konfiguraciji.

1. Izaberite **uredi** detalje pored mere bez naslova. Navedite ime za meru. Opcionalno, [dodajte](work-with-tags-columns.md#manage-tags) oznake u meru.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dijalog &quot;Uređivanje detalja&quot;.":::

1. Izaberite **Pokreni** da biste izračunali rezultate za konfigurisanu meru. Izaberite **Sačuvaj i zatvori** ako želite da zadržite trenutnu konfiguraciju i pokrenete meru kasnije.

1. Idite na **Mere** da biste na listi videli novokreiranu meru.
