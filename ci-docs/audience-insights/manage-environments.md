---
title: Kreiranje okruženja i upravljanje njima
description: Saznajte kako se registrujete za uslugu i kako da upravljate okruženjima.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e3f99f8f151aea5f120084382babd5e46e109545a4f63aafc51c3ecb1400cc33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034194"
---
# <a name="manage-environments"></a>Upravljanje okruženjima

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Zamena okruženja

Izaberite kontrolu **Okruženje** u gornjem desnom uglu stranice da biste promenili okruženje.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Snimak ekrana kontrole za promenu okruženja.":::

Administratori mogu da [kreiraju](get-started-paid.md) okruženja i upravljaju njima.

## <a name="edit-an-existing-environment"></a>Uređivanje postojećeg okruženja

Možete da izmenite neke detalje postojećih okruženja.

1.  Izaberite birač **Okruženje** u zaglavlju aplikacije.

2.  Izaberite ikonu **Uređivanje**.

3. U okviru **Uredi okruženje** možete ažurirati okruženje **Ime za prikaz** okruženja, ali ne možete da promenite **Region** ili **Tip**.

4. Ako je okruženje konfigurisano za čuvanje podataka u usluzi Azure Data Lake Storage, možete ažurirati **Ključ naloga**. Međutim, ne možete promeniti **Ime naloga** ni ime **kontejnera**.

5. Po želji možete da ažurirate sa veze ključa naloga na vezu zasnovanu na resursima ili pretplati. Kada ih nadogradite, ne možete se vratiti na ključ naloga nakon ažuriranja. Za više informacija pogledajte [Povezivanje uvida o korisnicima sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge](connect-service-principal.md). Ne možete promeniti informacije o **kontejneru** prilikom ažuriranja veze.

6. Opcionalno, možete da navedete URL adresu Microsoft Dataverse okruženja u odeljku **Konfigurišite deljenje podataka sa platformom Microsoft Dataverse i omogućite dodatne mogućnosti**. Ove mogućnosti uključuju deljenje podataka sa aplikacijama i rešenjima zasnovanim na platformi Microsoft Dataverse, unošenje podataka iz lokalnih izvora podataka ili upotrebu [predviđanja](predictions.md). Izaberite **Omogući deljenje podataka** da biste delili Customer Insights izlazne podatke pomoću usluge Microsoft Dataverse Managed Data Lake.

   > [!NOTE]
   > - Deljenje podataka pomoću usluge Microsoft Dataverse Managed Data Lake trenutno nije podržano kada sve podatke čuvate u sopstvenom Azure Data Lake Storage.
   > - [Predviđanje vrednosti koje nedostaju u entitetu](predictions.md) i PowerBI ugrađene izveštaje u uvidima u ciljnu grupu (ako je omogućeno u vašem okruženju) trenutno nisu podržani kada omogućite deljenje podataka sa Microsoft Dataverse upravljanim jezerom podataka.

   Kada omogućite deljenje podataka sa platformom Microsoft Dataverse, pokrenuće se potpuno osvežavanje izvora podataka i drugih procesa. Ako se procesi trenutno izvode, nećete videti opciju za omogućavanje deljenja podataka sa platformom Microsoft Dataverse. Sačekajte da se ti procesi dovrše ili ih otkažite da biste omogućili deljenje podataka. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Opcije konfiguracije za omogućavanje deljenja podataka sa platformom Microsoft Dataverse.":::
   
   Kada pokrenete procese, poput unosa podataka ili kreiranja segmenta, na nalogu za skladištenje koji ste gore naveli kreiraće se odgovarajuće mape. Datoteke podataka i datoteke model.json će se kreirati i dodati u odgovarajuće potfascikle, u zavisnosti od procesa koji pokrećete.

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
- Izvori podataka iz Common Data Model fascikle i Dataverse upravljane usluge Data Lake. Te izvore podataka ćete morati da kreirate ručno, s istim nazivom kao u izvornom okruženju.

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
