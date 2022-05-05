---
title: Pretraga i filtriranje profila klijenata
description: Brzo pronađite informacije o objedinjenim profilima klijenata i filtrirajte prema određenim atributima.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: 35bfd6530b9b80a4b0ec8ff992d9014534721907
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643565"
---
# <a name="customer-profiles-search--filter-index"></a>Profili klijenata: Indeks za pretraživanje i filtriranje

Rezultat objedinjavanja podataka o klijentima je entitet profila klijenta koji pruža jedinstven pogled na vašu ukupnu korisničku bazu. Da biste brzo [pronašli informacije o određenom klijentu ili grupi klijenata](customer-profiles.md), možete da konfigurišete mogućnosti **pretrage** i **filtriranja** na stranici **Klijenti**. Čitajte dalje kako biste saznali kako administratori mogu da uređuju atribute na stranici **Indeks pretrage i filtriranja**, koje su na raspolaganju korisnicima za pretraživanje i filtriranje.

   :::image type="content" source="media/search-filter.png" alt-text="Filter pretrage":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>Dodajte polja i odredite atribute

Ako kao administrator prvi put definišete atribute koji se mogu pretraživati, prvo morate definisati indeksirana polja. Predlažemo vam da odaberete sve atribute po kojima korisnici mogu da pretražuju i filtriraju klijente na stranici **Klijenti**. Možete odrediti samo one atribute koji postoje u entitetu Profil klijenta koji ste kreirali tokom postupka objedinjavanja podataka.

1. Otvorite stranicu **Klijenti** i izaberite **Indeks pretrage i filtriranja**.

2. Izaberite **+ Dodaj** da biste naveli indeksirana polja.

3. Izaberite atribute u listi koju želite da dodate kao indeksirana polja. Uvek možete dodati više atributa ako izaberete **Dodaj**. Takođe možete ukloniti sve odabrane atribute ako izaberete simbol **Ukloni**.

## <a name="explore-the-indexed-customer-fields-table"></a>Istražite tabelu sa indeksiranim poljima klijenata

Sledeće informacije su predstavljene u tabeli.

- **Ime**: Predstavlja ime atributa onako kako je prikazano u entitetu Profil klijenta.
- **Tip podataka**: Određuje da li je tip podataka niska, broj ili datum.
- **Uključeno u pretragu**: Određuje da li se ovaj atribut može koristiti za pretraživanje klijenata na stranici **Klijenti** pomoću polja **Pretraga**.
- **Dodaj filter**: Kontrola za definisanje kako se ovaj atribut može koristiti za filtriranje na stranici **Klijenti**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Uređivanje opcija filtriranja za određeni atribut

Meni **Filter** na stranici **Klijenti** može da sadrži različit broj nivoa atributa (npr. različite starosne grupe po kojima se klijenti filtriraju).

1. Izaberite **Dodaj filter** za dati atribut na stranici **Indeks pretrage i filtriranja**. Možete definisati broj rezultata i redosled po kome će oni biti organizovani. U zavisnosti od tipa podataka atributa, pojavljuje se jedno od sledećih okana.

- Atributi tipa niske: Navedite broj željenih rezultata u oknu **Opcije filtriranja niski** i smernice za redosled po kom će biti organizovani.

- Atributi numeričkog tipa: Navedite obuhvaćene intervale u oknu **Opcije filtriranja brojeva** i smernice za redosled po kom će biti organizovani.

- Atributi datuma tipa: Navedite obuhvaćene intervale u oknu **Opcije filtriranja datuma** i smernice za redosled po kom će biti organizovani.

2. Izaberite **Sačuvaj** da primenite promene.

3. Izaberite **Pokreni** kada budete spremni da primenite svoja podešavanja. Nakon obrade promena, naći ćete ih u [karticama klijenata na stranici Klijent](customer-profiles.md). 

## <a name="next-steps"></a>Sledeći koraci

Pregledajte [stranicu objedinjenih profila](customer-profiles.md) da potražite profile ili koristite indeksirana polja da vidite podskup svih objedinjenih profila.


[!INCLUDE [footer-include](includes/footer-banner.md)]
