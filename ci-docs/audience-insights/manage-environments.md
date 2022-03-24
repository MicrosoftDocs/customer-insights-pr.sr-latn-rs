---
title: Kreiranje okruženja i upravljanje njima
description: Saznajte kako se registrujete za uslugu i kako da upravljate okruženjima.
ms.date: 02/09/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 4f4e5a8415f6c2128b0480edf67f317124eeeba9
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376893"
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

Da biste koristili [gotove modele predviđanja](predictions-overview.md#out-of-box-models), konfigurišite deljenje podataka sa uslugom Dataverse. Ili možete omogućiti unos podataka iz lokalnih izvora podataka,obezbeđujući URL adresu Microsoft Dataverse okruženja kojim upravlja vaša organizacija.

> [!IMPORTANT]
> Uvidi klijenata i Dataverse moraju da budu u istom regionu da bi omogućili deljenje podataka.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Opcije konfiguracije za omogućavanje deljenja podataka sa platformom Microsoft Dataverse.":::

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

## <a name="change-the-owner-of-an-environment"></a>Promena vlasnika okruženja

Dok nekoliko korisnika može da ima administratorske dozvole u programu Customer Insights, samo jedan korisnik je vlasnik okruženja. Po podrazumevanoj vrednosti, administrator je taj koji u početku kreira okruženje. Kao administrator okruženja, možete da dodelite vlasništvo drugom korisniku sa administratorske dozvole.

1. Izaberite birač **Okruženje** u zaglavlju aplikacije.

1. Izaberite ikonu **Uređivanje**.

1. U okviru **Uredi okruženje** pređite na osnovni **informacioni** korak.

1. U polju **Promeni vlasnika okruženja** odaberite novog vlasnika okruženja.  

1. Izaberite rediguj **i završi**, a zatim **ažuriraj** da biste primenili promene. 

## <a name="claim-ownership-of-an-environment"></a>Tražite vlasništvo nad okruženjem

Ako vlasnik okruženja napusti organizaciju ili je njihov korisnički nalog izbrisan, okruženje neće imati vlasnika. Korisnik sa administratorske dozvole može da preuzme vlasništvo i postane novi vlasnik. Oni mogu da nastave da poseduju životnu sredinu [ili da promene vlasništvo u drugog administratora](#change-the-owner-of-an-environment). 

Da biste preuzeli vlasništvo, izaberite dugme **"Preuzmi vlasništvo** " koje se prikazuje na vrhu svake stranice u "Uvidima kupaca" kada je originalni vlasnik napustio organizaciju.

## <a name="reset-an-existing-environment"></a>Uspostavljanje početnih vrednosti postojećeg okruženja

Kao vlasnik okruženja, možete da uspostavite početne vrednosti okruženja na prazno stanje ako želite da izbrišete sve konfiguracije i uklonite unete podatke.

1.  Izaberite birač **Okruženje** u zaglavlju aplikacije. 

2.  Izaberite okruženje koje želite da resetujete i izaberite tri tačke (**...**). 

3. Izaberite opciju **Resetuj**. 

4.  Da biste potvrdili brisanje, unesite ime okruženja i izaberite **Resetuj**.

## <a name="delete-an-existing-environment"></a>Brisanje postojećeg okruženja

Kao vlasnik okruženja, možete da izbrišete okruženje kojim upravljate.

1.  Izaberite birač **Okruženje** u zaglavlju aplikacije.

2.  Izaberite okruženje koje želite da resetujete i izaberite tri tačke (**...**). 

3. Odaberite opciju **Izbriši**. 

4.  Da biste potvrdili brisanje, unesite naziv okruženja i izaberite **Izbriši**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
