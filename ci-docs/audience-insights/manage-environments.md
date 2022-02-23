---
title: Kreiranje okruženja i upravljanje njima
description: Saznajte kako se registrujete za uslugu i kako da upravljate okruženjima.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8251cac9f95455b61eb0300b6c72cd4ab2969591
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046350"
---
# <a name="manage-environments"></a>Upravljanje okruženjima



## <a name="switch-environments"></a>Zamena okruženja

Izaberite kontrolu **Okruženje** u gornjem desnom uglu stranice da biste promenili okruženje.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Snimak ekrana kontrole za promenu okruženja.":::

Administratori mogu da [kreiraju](create-environment.md) okruženja i upravljaju njima.

## <a name="edit-an-existing-environment"></a>Uređivanje postojećeg okruženja

Možete da izmenite neke detalje postojećih okruženja.

1.  Izaberite birač **Okruženje** u zaglavlju aplikacije.

2.  Izaberite ikonu **Uređivanje**.

3. U okviru **Uređivanje okruženja**, možete ažurirati podešavanja okruženja.

Više informacija o podešavanjima okruženja potražite u članku [Kreiranje novog okruženja](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Povezivanje sa sistemom Microsoft Dataverse
   
Korak **Microsoft Dataverse** vam omogućava da povežete Customer Insights sa vašim Dataverse okruženjem.

Da biste koristili [gotove modele predviđanja](predictions-overview.md#out-of-box-models), konfigurišite deljenje podataka sa uslugom Dataverse. Ili možete omogućiti unos podataka iz lokalnih izvora podataka,obezbeđujući URL adresu Microsoft Dataverse okruženja kojim upravlja vaša organizacija. Izaberite **Omogući deljenje podataka** da biste delili Customer Insights izlazne podatke pomoću Dataverse upravljanog jezera podataka.

> [!IMPORTANT]
> Uvidi klijenata i Dataverse moraju da budu u istom regionu da bi omogućili deljenje podataka.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Opcije konfiguracije za omogućavanje deljenja podataka sa platformom Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights ne podržava sledeće scenarije deljenja podataka:
> - Ako sve podatke sačuvate u sopstvenoj usluzi Azure Data Lake Storage, nećete moći da omogućite deljenje podataka sa Dataverse upravljanim jezerom podataka.
> - Ako omogućite deljenje podataka sa uslugom Dataverse, nećete moći da [kreirate predviđene ili vrednosti koje nedostaju u entitetu](predictions.md).

## <a name="copy-the-environment-configuration"></a>Kopiranje konfiguracije okruženja

Kada kreirate novo okruženje, možete izabrati da kopirate konfiguraciju iz postojećeg okruženja. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Snimak ekrana opcija podešavanja u podešavanjima okruženja.":::

Videćete listu svih dostupnih okruženja u vašoj organizaciji, odakle možete kopirati podatke.

Kopiraju se sledeća podešavanja konfiguracije:

- Uneseni/uvezeni izvori podataka
- Konfiguracija objedinjavanja podataka (mapa, podudaranje, spajanje)
- Segmenti
- Mere
- Odnosi
- Aktivnosti
- Indeks pretrage i filtriranja
- Odredišta za izvoz
- Planirano osvežavanje
- Obogaćivanja
- Upravljanje modelima
- Dodela uloga

Sledeći podaci se *ne* kopiraju:

- Profili klijenata.
- Akreditivi izvora podataka. Moraćete da dostavite akreditive za svaki izvor podataka i ručno osvežite izvore podataka.

- Izvori podataka iz Common Data Model fascikle i Dataverse upravljanog jezera podataka. Te izvore podataka ćete morati da kreirate ručno, s istim nazivom kao u izvornom okruženju.

Kada kopirate okruženje, videćete poruku potvrde da je kreirano novo okruženje. Izaberite **Idite na izvore podataka** da biste videli listu izvora podataka.

Svi izvori podataka će pokazati status **Potrebni su akreditivi**. Uredite izvore podataka i unesite akreditive da biste ih osvežili.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista izvora podataka koji su kopirani i kojima je potrebna potvrda identiteta.":::

Nakon osvežavanja izvora podataka, idite na **Podaci** > **Objedini**. Ovde ćete pronaći podešavanja iz izvornog okruženja. Uredite ih po potrebi ili izaberite **Pokreni** da biste pokrenuli proces objedinjavanja podataka i kreirali objedinjeni entitet klijenta.

Kada objedinjavanje podataka bude dovršeno, idite na **Mere** i **Segmenti** da osvežite i njih.

## <a name="reset-an-existing-environment"></a>Uspostavljanje početnih vrednosti postojećeg okruženja

Kao administrator, možete da vratite okruženje na prazno stanje ako želite da izbrišete sve konfiguracije i uklonite unete podatke.

1.  Izaberite birač **Okruženje** u zaglavlju aplikacije. 

2.  Izaberite okruženje koje želite da resetujete i izaberite tri tačke (**...**). 

3. Izaberite opciju **Resetuj**. 

4.  Da biste potvrdili brisanje, unesite ime okruženja i izaberite **Resetuj**.

## <a name="delete-an-existing-environment"></a>Brisanje postojećeg okruženja

Kao administrator možete da izbrišete okruženje kojim administrirate.

1.  Izaberite birač **Okruženje** u zaglavlju aplikacije.

2.  Izaberite okruženje koje želite da resetujete i izaberite tri tačke (**...**). 

3. Odaberite opciju **Izbriši**. 

4.  Da biste potvrdili brisanje, unesite naziv okruženja i izaberite **Izbriši**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
