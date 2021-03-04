---
title: Prikaz profila klijenata
description: Steknite kombinovani prikaz objedinjenih podataka o klijentima.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a5d928ae518f3cb1afbf8e2b197e51b27665f6e0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269761"
---
# <a name="customer-profiles"></a>Profili klijenata

Stranica **Klijenti** prikazuje kombinovani prikaz vaših klijenata na osnovu podataka sa profila prikupljenih iz [svih izvora podataka](data-sources.md). Profili klijenata su vam dostupni nakon što ste [kreirali objedinjeni entitet Klijent](data-unification.md). Obavezno dovršite postupak objedinjavanja podataka da biste stekli bogatije poglede svojih klijenata. Ova stranica takođe vam omogućava da pretražujete klijente.

Klijenti mogu biti pojedinci ili organizacije (pregled). Svaki profil klijenta ili organizacije predstavljen je pločicom. Izaberite pločicu da biste videli dodatne informacije o tom konkretnom klijentu ili organizaciji. Upotrebite kontrole za straničenje na dnu stranice da biste videli dodatne zapise.

> [!div class="mx-imgBorder"] 
> ![B2C profili klijenata](media/profiles-customers.png "B2C profili klijenata")

Organizacije (Pregled)
> [!div class="mx-imgBorder"] 
> ![B2B profili klijenata](media/profile-customers-b2b.png "B2B profili klijenata")

> [!NOTE]
> Ako ne možete da vidite pločice kada izaberete **Klijenti** u navigaciji, vaš administrator treba da [definiši barem jedan atribut se može da se pretražuje](search-filter-index.md) u odeljku **Indeks pretrage i filtriranja**.

## <a name="search-for-customers"></a>Pretraga klijenata

Pretražujte klijente unosom imena ili nekog drugog atributa u polje za pretragu. Pretraživanje funkcioniše samo u entitetu Profil klijenta koji je kreiran tokom procesa objedinjavanja podataka.

Kao administrator, možete konfigurisati atribute pretraživanja koristeći stranicu **Indeks pretrage i filtriranja**. Za više informacija, pogledajte [Upravljajte indeksom pretrage i filtriranja](search-filter-index.md).

## <a name="filter-customers"></a>Filtriranje klijenata

Možete filtrirati klijente po poljima entiteta Profil klijenta. Slično pretraživanju, vaš administrator će prvo morati da definiše polja tako da se mogu filtrirati na stranici **Indeks pretrage i filtriranja**.

1. Izaberite **Filter** na stranici **Klijenti**.

2. Označite polja pored atributa po kojima želite da filtrirate klijente.

   > [!div class="mx-imgBorder"] 
   > ![Profili klijenata](media/profiles-customers3.png "Profili klijenata")

3. Uklonite filtere izborom **Obriši filtere** na stranici **Klijenti**.

##  <a name="customer-details-page"></a>Stranica sa detaljima o klijentima

Izaberite bilo koju pločicu klijenta da biste otvorili **stranicu sa detaljima o klijentu**. Ovaj prikaz sadrži objedinjene informacije za izabranog klijenta.

Detalji o klijentu obuhvataju:

-   **Pločica profila klijenta:** Ova pločica prikazuje različite vrednosti iz entiteta objedinjenog profila klijenta. Ovi detalji mogu da uključuju adresu e-pošte, ime, grad itd. 

-   **Potencijalna interesovanja, potencijalni brendovi:** Pokazuje da li ste konfigurisali direktno obogaćivanje. Predstavlja potencijalna interesovanja i afinitete za brendove koje ima klijent sa profilom sličnim ovom klijentu. Za više informacija, pogledajte [Obogaćivanje profila klijenata afinitetima prema brendovima i interesovanjima](enrichment-microsoft-graph.md).

-   **Mere:** Pokazuje da li ste konfigurisali jednu ili više mera određene vrste: mere atributa klijenta. Uključuju izračunate KPI-jeve oko vaših klijenata na nivou pojedinačnog klijenta. Za više informacija pogledajte [Definisanje i upravljanje merama](measures.md).

-   **Vremenska osa aktivnosti:** Pokazuje da li ste konfigurisali aktivnosti. Prikaz vremenske ose sadrži hronološki sortirane aktivnosti ovog klijenta, počev od najnovije aktivnosti. Za više informacija pogledajte [aktivnosti klijenta](activities.md).

Izaberite **Povratak na klijente** da biste se vratili na stranicu za pretragu klijenata.

## <a name="next-steps"></a>Sledeći koraci

[Dodajte još izvora podataka](data-sources.md) ili [kreirajte segmente klijenata](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]