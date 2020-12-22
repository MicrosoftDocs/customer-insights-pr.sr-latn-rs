---
title: Kreiranje okruženja i upravljanje njima
description: Saznajte kako se registrujete za uslugu i kako da upravljate okruženjima.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644150"
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

Da biste kreirali okruženja:

1. Izaberite simbol **Podešavanja** u zaglavlju aplikacije.

1. Izaberite **Novo okruženje**.

   > [!div class="mx-imgBorder"]
   > ![Podešavanja okruženja](media/environment-settings-dialog.png)

1. U dijalogu **Kreirajte novo okruženje**, izaberite **Novo okruženje**.

   Ako želite da [kopirate podatke iz trenutnog okruženja](#additional-considerations-for-copy-configuration-preview), izaberite **Kopiraj iz postojećeg okruženja**. Videćete listu svih dostupnih okruženja u vašoj organizaciji, odakle možete kopirati podatke.

1. Navedite sledeće detalje:
   - **Naziv**: Unesite naziv ovog okruženja. Ovo polje je već popunjeno ako ste kopirali postojeće okruženje, ali možete ga promeniti.
   - **Region**: Region u kojem je usluga primenjena i hostovana.
   - **Tip**: Izaberite da li želite da kreirate proizvodno ili Sandbox okruženje.

2. Po želji možete odabrati **Napredna podešavanja**:

   - **Sačuvaj sve podatke u**: Određuje gde želite da sačuvate izlazne podatke generisane u usluzi Customer Insights. Imaćete dve mogućnosti: **Customer Insights skladište** (Azure Data Lake kojim upravlja Customer Insights tim) i **Azure Data Lake Storage Gen2** (vaš sopstveni Azure Data Lake Storage). Podrazumevano je odabrana opcija Customer Insights skladišta.

   > [!NOTE]
   > Čuvanjem podataka u usluzi Azure Data Lake Storage, slažete se da će podaci biti preneti i uskladišteni na odgovarajućoj geografskoj lokaciji za taj Azure nalog za skladištenje, koja može da se razlikuje od mesta skladištenja podataka u usluzi Dynamics 365 Customer Insights. [Saznajte više u Microsoft centru za pouzdanost.](https://www.microsoft.com/trust-center)
   >
   > Trenutno se uneti entiteti uvek čuvaju u jezeru podataka kojim upravlja Customer Insights.
   > Podržavamo samo Azure Data Lake Gen2 naloge za skladištenje iz iste Azure regije koju ste izabrali prilikom kreiranja okruženja.
   > Mi podržavamo samo naloge za skladištenje koje omogućuje Azure Data Lake Gen2 hijerarhijski prostoru imena (HNS).

   - Za opciju Azure Data Lake Storage Gen2, možete da birate između opcije zasnovane na resursima i opcije zasnovane na pretplati za potvrdu identiteta. Za više informacija pogledajte [Povezivanje uvida o korisnicima sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge](connect-service-principal.md). Naziv **kontejnera** se ne može promeniti i biće „uvidi o korisnicima“.
   
   - Ako želite da koristite [predviđanja](predictions.md), unesite URL Common Data Service instance u polje **Adresa servera** u odeljku **Koristite predviđanja**.

   Kada pokrenete procese, poput unosa podataka ili kreiranja segmenta, na nalogu za skladištenje koji ste gore naveli kreiraće se odgovarajuće mape. Datoteke podataka i datoteke model.json će biti kreirane i dodate u odgovarajuće potfasikle na osnovu procesa koji pokrećete.

   Ako kreirate više okruženja za Customer Insights i odlučite da sačuvate izlazne entitete iz tih okruženja na svom nalogu za skladištenje, kreiraće se zasebne fascikle za svako okruženje sa ci_<environmentid> u kontejneru.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Dodatna razmatranja za konfiguraciju kopija (pregled)

Kopiraju se sledeća podešavanja konfiguracije:

- Konfiguracije funkcija
- Obrađeni/uvezeni izvori podataka
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
- Izvori podataka iz fascikle Common Data Model i Common Data Service upravljanog jezera. Te izvore podataka ćete morati da kreirate ručno, s istim nazivom kao u izvornom okruženju.

Kada kopirate okruženje, videćete poruku potvrde da je kreirano novo okruženje. Izaberite **Idite na izvore podataka** da biste videli listu izvora podataka.

Svi izvori podataka će pokazati status **Potrebni su akreditivi**. Uredite izvore podataka i unesite akreditive da biste ih osvežili.

> [!div class="mx-imgBorder"]
> ![Kopirani izvori podataka](media/data-sources-copied.png)

Nakon osvežavanja izvora podataka, idite na **Podaci** > **Objedini**. Ovde ćete pronaći podešavanja iz izvornog okruženja. Uredite ih po potrebi ili izaberite **Pokreni** da biste pokrenuli proces objedinjavanja podataka i kreirali objedinjeni entitet klijenta.

Kada objedinjavanje podataka bude dovršeno, idite na **Mere** i **Segmenti** da osvežite i njih.

## <a name="edit-an-existing-environment"></a>Uređivanje postojećeg okruženja

Možete da izmenite neke detalje postojećih okruženja.

1. Idite u **Administracija** > **Sistem** > **Osnovni podaci**.

2. Izaberite **Uredi**.

3. Možete da ažurirate **Ime za prikaz** okruženja, ali ne možete da promenite **Region** ni **Tip**.

4. Ako je okruženje konfigurisano za čuvanje podataka Azure Data Lake Storage Gen2, možete da ažurirate **Ključ naloga**. Međutim, ne možete promeniti **Ime naloga** ni ime **kontejnera**.

5. Po želji možete da ažurirate sa veze ključa naloga na vezu zasnovanu na resursima ili pretplati. Kada ih nadogradite, ne možete se vratiti na ključ naloga nakon ažuriranja. Za više informacija pogledajte [Povezivanje uvida o korisnicima sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge](connect-service-principal.md). Ne možete promeniti informacije o **kontejneru** prilikom ažuriranja veze.

## <a name="reset-an-existing-environment"></a>Uspostavljanje početnih vrednosti postojećeg okruženja

Možete da vratite okruženje na prazno stanje ako želite da izbrišete sve konfiguracije i uklonite unete podatke.

1.  Idite u **Administracija** > **Sistem** > **Osnovni podaci**.

2.  Izaberite **Resetuj**. 

3.  Da biste potvrdili brisanje, unesite ime okruženja i izaberite **Resetuj**.


## <a name="delete-an-existing-environment"></a>Brisanje postojećeg okruženja

1. Idite u **Administracija** > **Sistem** > **Osnovni podaci**.

1. Izaberite **Izbriši**.

1. Da biste potvrdili brisanje, unesite naziv okruženja i izaberite **Izbriši**.
