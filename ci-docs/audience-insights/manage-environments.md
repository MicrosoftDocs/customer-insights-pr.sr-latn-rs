---
title: Kreiranje okruženja i upravljanje njima
description: Saznajte kako se registrujete za uslugu i kako da upravljate okruženjima.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304897"
---
# <a name="manage-environments"></a>Upravljanje okruženjima

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Ovaj članak objašnjava kako da kreirate novu organizaciju i obezbedite okruženje.

## <a name="sign-up-and-create-an-organization"></a>Registrujte se i napravite organizaciju

1. Idite na veb-lokaciju [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Izaberite **Prvi koraci**.

3. Odaberite željeni scenario prijave i izaberite odgovarajuću vezu.

4. Prihvatite uslove i odredbe i izaberite **Nastavi** da biste započeli kreiranje organizacije.

5. Nakon kreiranja okruženja, bićete preusmereni na [Customer Insights](https://home.ci.ai.dynamics.com).

6. Koristite demo okruženje da istražite aplikaciju ili kreirajte novo okruženje prateći korake u sledećem odeljku.

7. Kada navedete podešavanja okruženja, izaberite **Kreiraj**.

8. Bićete prijavljeni nakon što je okruženje uspešno kreirano.

## <a name="create-an-environment-in-an-existing-organization"></a>Kreirajte okruženje u postojećoj organizaciji

Postoje dva načina za kreiranje novog okruženja. Možete da navedete potpuno novu konfiguraciju ili da kopirate neka podešavanja konfiguracije iz postojećeg okruženja.

> [!NOTE]
> Organizacije mogu da kreiraju *dva* okruženja za svaku Customer Insights licencu. Ako vaša organizacija više puta kupi licencu, [kontaktirajte naš tim za podršku](https://go.microsoft.com/fwlink/?linkid=2079641) da biste povećali broj dostupnih okruženja. Za više informacija o kapacitetu i dodatnom kapacitetu, preuzmite [Dynamics 365 vodič za licenciranje](https://go.microsoft.com/fwlink/?LinkId=866544).

Da biste kreirali okruženja:

1. Izaberite birač **Okruženje** u zaglavlju aplikacije.

1. Izaberite **Novo**.

   > [!div class="mx-imgBorder"]
   > ![Podešavanja okruženja.](media/environment-settings-dialog.png)

1. U dijalogu **Kreiranje okruženja**, izaberite **Novo okruženje**.

   Ako želite da [kopirate podatke iz trenutnog okruženja](#considerations-for-copy-configuration-preview), izaberite **Kopiraj iz postojećeg okruženja**. Videćete listu svih dostupnih okruženja u vašoj organizaciji, odakle možete kopirati podatke.

1. Navedite sledeće detalje:
   - **Naziv**: Unesite naziv ovog okruženja. Ovo polje je već popunjeno ako ste kopirali postojeće okruženje, ali možete ga promeniti.
   - **Tip**: Izaberite da li želite da kreirate proizvodno ili Sandbox okruženje.
   - **Region**: Region u kojem je usluga primenjena i hostovana.
   
1. Po želji možete odabrati **Napredna podešavanja**:

   - **Sačuvaj sve podatke u**: Određuje gde želite da sačuvate izlazne podatke generisane u usluzi Customer Insights. Imaćete dve mogućnosti: **Customer Insights skladište** (Azure Data Lake kojim upravlja Customer Insights tim) i **Azure Data Lake Storage** (vaš sopstveni Azure Data Lake Storage). Podrazumevano je odabrana opcija Customer Insights skladišta.

     > [!NOTE]
     > Čuvanjem podataka u usluzi Azure Data Lake Storage, slažete se da će podaci biti preneti i uskladišteni na odgovarajućoj geografskoj lokaciji za taj Azure nalog za skladištenje, koja može da se razlikuje od mesta skladištenja podataka u usluzi Dynamics 365 Customer Insights. [Saznajte više u Microsoft centru za pouzdanost.](https://www.microsoft.com/trust-center)
     >
     > Trenutno se uneti entiteti uvek čuvaju u Customer Insights upravljanoj usluzi Data Lake. 
     > 
     > Podržavamo samo Azure Data Lake Storage naloge iz istog Azure regiona koji ste izabrali prilikom kreiranja okruženja. 
     > 
     > Podržavamo samo Azure Data Lake Storage naloge koji imaju omogućen hijerarhijski prostor imena.


   - Za opciju Azure Data Lake Storage, možete odabrati između opcije zasnovane na resursima i opcije zasnovane na pretplati za potvrdu identiteta. Za više informacija pogledajte [Povezivanje uvida o korisnicima sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge](connect-service-principal.md). Naziv **kontejnera** se ne može promeniti i biće `customerinsights`.
   
   - Ako želite da koristite [predviđanja](predictions.md), konfigurišite razmenu podataka sa platformom Microsoft Dataverse ili omogućite unošenje podataka iz lokalnih izvora podataka, navedite URL adresu Microsoft Dataverse okruženja u odeljku **Konfigurišite deljenje podataka sa platformom Microsoft Dataverse i omogućite dodatne mogućnosti**. Izaberite **Omogući deljenje podataka** da biste delili Customer Insights izlazne podatke pomoću usluge Microsoft Dataverse Managed Data Lake.

     > [!NOTE]
     > - Deljenje podataka pomoću usluge Microsoft Dataverse Managed Data Lake trenutno nije podržano kada sve podatke čuvate u sopstvenom Azure Data Lake Storage.
     > - [Predviđanje vrednosti koje nedostaju u entitetu](predictions.md) trenutno nije podržano kada omogućite deljenje podataka sa uslugom Microsoft Dataverse Managed Data Lake.

     > [!div class="mx-imgBorder"]
     > ![Opcije konfiguracije za omogućavanje deljenja podataka sa platformom Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)

   Kada pokrenete procese, poput unosa podataka ili kreiranja segmenta, na nalogu za skladištenje koji ste gore naveli kreiraće se odgovarajuće mape. Datoteke podataka i datoteka model.json će se kreirati i dodati u fascikle u zavisnosti od naziva procesa.

   Ako kreirate više okruženja za Customer Insights i odlučite da sačuvate izlazne entitete iz tih okruženja na svom nalogu za skladištenje, kreiraće se zasebne fascikle za svako okruženje sa ci_<environmentid> u kontejneru.

### <a name="considerations-for-copy-configuration-preview"></a>Razmatranja oko konfiguracije kopija (verzija za pregled)

Kopiraju se sledeća podešavanja konfiguracije:

- Konfiguracije funkcija
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

Sledeća podešavanja se *ne* kopiraju:

- Profili klijenata.
- Akreditivi izvora podataka. Moraćete da dostavite akreditive za svaki izvor podataka i ručno osvežite izvore podataka.
- Izvori podataka iz Common Data Model fascikle i Dataverse upravljane usluge Data Lake. Te izvore podataka ćete morati da kreirate ručno, s istim nazivom kao u izvornom okruženju.

Kada kopirate okruženje, videćete poruku potvrde da je kreirano novo okruženje. Izaberite **Idite na izvore podataka** da biste videli listu izvora podataka.

Svi izvori podataka će pokazati status **Potrebni su akreditivi**. Uredite izvore podataka i unesite akreditive da biste ih osvežili.

> [!div class="mx-imgBorder"]
> ![Izvori podataka su kopirani.](media/data-sources-copied.png)

Nakon osvežavanja izvora podataka, idite na **Podaci** > **Objedini**. Ovde ćete pronaći podešavanja iz izvornog okruženja. Uredite ih po potrebi ili izaberite **Pokreni** da biste pokrenuli proces objedinjavanja podataka i kreirali objedinjeni entitet klijenta.

Kada objedinjavanje podataka bude dovršeno, idite na **Mere** i **Segmenti** da osvežite i njih.

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
   > - [Predviđanje vrednosti koje nedostaju u entitetu](predictions.md) trenutno nije podržano kada omogućite deljenje podataka sa uslugom Microsoft Dataverse Managed Data Lake.

   Kada omogućite deljenje podataka sa platformom Microsoft Dataverse, pokrenuće se potpuno osvežavanje izvora podataka i drugih procesa. Ako se procesi trenutno izvode, nećete videti opciju za omogućavanje deljenja podataka sa platformom Microsoft Dataverse. Sačekajte da se ti procesi dovrše ili ih otkažite da biste omogućili deljenje podataka. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Opcije konfiguracije za omogućavanje deljenja podataka sa platformom Microsoft Dataverse.":::
   
   Kada pokrenete procese, poput unosa podataka ili kreiranja segmenta, na nalogu za skladištenje koji ste gore naveli kreiraće se odgovarajuće mape. Datoteke podataka i datoteke model.json će se kreirati i dodati u odgovarajuće potfascikle, u zavisnosti od procesa koji pokrećete.

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
