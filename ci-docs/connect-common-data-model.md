---
title: Povežite se sa Common Data Model fasciklom koja koristi Azure Data Lake nalog
description: Radite sa Common Data Model podacima koristeći Azure Data Lake Storage.
ms.date: 05/30/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: b1cdcb46df17d722ad49d361ae4c7ab34c83eeb1
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082267"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Povežite se sa podacima u usluzi Azure Data Lake Storage

Unestite podatke Dynamics 365 Customer Insights u svoj Azure Data Lake Storage Gen2 nalog. Unošenje podataka može biti puno ili postepeno.

## <a name="prerequisites"></a>Preduslovi

- Unošenje podataka podržava Azure Data Lake Storage *isključivo Gen2* naloge. Ne možete da koristite Data Lake Storage Gen1 naloge da biste uneli podatke.

- Nalog Azure Data Lake Storage mora imati [omogućen hijerarhijski prostor za ime](/azure/storage/blobs/data-lake-storage-namespace). Podaci moraju biti uskladišteni u hijerarhijski fascikli koji definiše osnovnu fasciklu i ima potfascikle za svaki entitet. Potfascikle mogu da imaju pune podatke ili postepene fascikle sa podacima.

- Da biste potvrdili identitet pomoću principala usluge Azure, uverite se da je konfigurisan u vašem zakupcu. Više informacija potražite u članku [Povezivanje sa Azure Data Lake Storage Gen2 nalogom pomoću direktora Azure usluge](connect-service-principal.md).

- Podaci Azure Data Lake Storage iz kojih želite da povežete i iz kojih unosite podatke mora da bude u istoj Azure oblasti kao i Dynamics 365 Customer Insights okruženje. Ne podržavaju se veze sa Common Data Model fasciklom iz jezera podataka u drugom Azure regionu. Da biste znali Azurnu oblast okruženja, posetite lokaciju **Admin** > **System** > **About** in Customer Insights.

- Podaci uskladišteni u uslugama na mreži mogu se uskladištiti na drugoj lokaciji od mesta gde se podaci obrađuju ili skladište u programu Dynamics 365 Customer Insights.Uvozom ili povezivanjem sa podacima uskladištenim u uslugama na mreži slažete se da se podaci mogu prenositi i skladištiti sa programom Dynamics 365 Customer Insights. [Saznajte više u Microsoft centru za pouzdanost](https://www.microsoft.com/trust-center).

- Glavnica usluge "Uvidi kupaca" mora biti u jednoj od sledećih uloga da bi pristupila nalogu za skladištenje. Više informacija potražite u članku [Dodeljivanje dozvola direktoru usluge za pristup nalogu za skladištenje](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Čitač podataka skladišta blob objekta
  - Vlasnik podataka skladišta blob objekta
  - Saradnik za podatke skladišta blob objekta

- Podaci u skladištu jezera podataka treba da prate standard Common Data Model za skladištenje podataka i da imaju zajednički manifest modela podataka koji predstavlja šemu datoteka sa podacima (*.csv ili *.parket). Manifest mora da pruži detalje entiteta kao što su kolone entiteta i tipovi podataka, kao i lokaciju datoteke sa podacima i tip datoteke. Više informacija potražite u manifestu [Uobičajeni model podataka](/common-data-model/sdk/manifest). Ako manifest nije prisutan, administratorski korisnici sa vlasnikom podataka Storage Blob ili Storage Blob Data saradnik mogu da definišu šemu prilikom unosa podataka.

## <a name="connect-to-azure-data-lake-storage"></a>Povezivanje sa uslugom Azure Data Lake Storage

1. Idite na **Podaci** > **Izvori podataka**.

1. Izaberite **Dodaj izvor podataka**.

1. Izaberite **Azure skladište jezera sa podacima**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Dijalog za unos detalja veze za Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Unesite **ime** za izvor podataka i opcionalni **opis**. Ime jedinstveno identifikuje izvor podataka upućuje na nizvodne procese i ne može se menjati.

1. Odaberite jednu od sledećih opcija za povezivanje **skladišta pomoću**. Više informacija potražite u članku [Povezivanje uvida klijenata sa Azure Data Lake Storage Gen2 nalogom pomoću Azure servisnog direktora](connect-service-principal.md).

   - **Azure resurs:** Unesite **ID resursa**. Opcionalno, ako želite da unosite podatke iz naloga za skladištenje putem Azure privatne veze, izaberite opciju Omogući **privatnu vezu**. Više informacija potražite u članku [Privatne veze](security-overview.md#private-links-tab).
   - **Azure pretplate**: Izaberite pretplatu **, a** zatim nalog **grupe resursa** **i skladišta**. Opcionalno, ako želite da unosite podatke iz naloga za skladištenje putem Azure privatne veze, izaberite opciju Omogući **privatnu vezu**. Više informacija potražite u članku [Privatne veze](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Potrebna vam je jedna od sledećih uloga kontejnera ili naloga za skladištenje da biste kreirali izvor podataka:
   >
   >  - Podaci o skladištenju čitalac su dovoljni za čitanje sa naloga za skladištenje i unos podataka u uvide klijenata. 
   >  - Podaci o skladištenju saradnik ili vlasnik su potrebni ako želite da uredite manifestne datoteke direktno u uvidima kupaca.  
  
1. Odaberite ime kontejnera koji **sadrži podatke i šemu (model.json ili manifest.json datoteka) iz kojeg želite da uvezete podatke, a zatim kliknite na dugme Dalje** **.**
   > [!NOTE]
   > Nijedna datoteka model.json ili manifest.json povezana sa drugim izvorom podataka u okruženju neće se prikazati na listi. Međutim, ista datoteka model.json ili manifest.json može se koristiti za izvore podataka u više okruženja.

1. Da biste kreirali novu šemu, idite na [stavku Kreiranje nove datoteke šeme](#create-a-new-schema-file).

1. Da biste koristili postojeću šemu, dođite do fascikle koja sadrži datoteku model.json ili manifest.cdm.json. Možete da pretražujete u katalogu da biste pronašli datoteku.

1. Izaberite json datoteku i kliknite na dugme **Dalje**. Prikazaće se lista dostupnih entiteta.

   :::image type="content" source="media/review-entities.png" alt-text="Dijalog liste entiteta za izbor":::

1. Izaberite entitete koje želite da uključite.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dijalog koji prikazuje potreban za primarni ključ":::

   > [!TIP]
   > Da biste uredili entitete u interfejsu za uređivanje JSON-a, izaberite prikaži **više Edit** > **datoteke šeme**. Izvršite promene i izaberite **Sačuvaj**.

1. Za izabrane entitete koji zahtevaju postepeno unošenje, potrebni ekrani **u okviru** postepenog **osvežavanja**. Za svaki od ovih entiteta pogledajte članak [Konfigurisanje postepenog osvežavanja za Azure Data Lake izvore podataka](incremental-refresh-data-sources.md).

1. Za izabrane entitete u kojima primarni ključ nije definisan, potrebni prikazi **u okviru** primarnog **ključa**. Za svaki od ovih entiteta:
   1. Izaberite **potrebnu**. Prikazuje **se tabla "Uređivanje** entiteta".
   1. Odaberite **primarni ključ**. Primarni ključ je atribut jedinstven za entitet. Da bi atribut bio važeći primarni ključ, ne bi trebalo da sadrži duplirane vrednosti, nedostajuće vrednosti ili prazne vrednosti. Atributi tipa niska, ceo broj i GUID tip podataka su podržani kao primarni ključevi.
   1. Opcionalno, promenite obrazac particije.
   1. Kliknite na **dugme "** Zatvori" da biste sačuvali i zatvorili tablu.

1. Izaberite broj atributa **za** svaki uključeni entitet. Prikazaće **se stranica "Upravljanje** atributima".

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dijalog za izbor profilisanja podataka.":::

   1. Kreirajte nove atribute, uredite ili izbrišite postojeće atribute. Možete da promenite ime, format podataka ili da dodate semantički tip.
   1. Da biste omogućili analitiku i druge mogućnosti, izaberite **profilisanje** podataka za ceo entitet ili za određene atribute. Podrazumevano nijedan entitet nije omogućen za profilisanje podataka.
   1. Izaberite **Gotovo**.

1. Izaberite **Sačuvaj**. Otvoriće **se stranica "Izvori podataka" koja prikazuje novu izvor podataka statusu "Osvežavanje** **·**".

### <a name="create-a-new-schema-file"></a>Kreiranje nove datoteke šeme

1. Izaberite **novu datoteku šeme**.

1. Unesite ime datoteke i izaberite **sačuvaj**.

1. Izaberite **novi entitet**. Prikazaće **se tabla** "Novi entitet".

1. Unesite ime entiteta i odaberite lokaciju datoteka **sa podacima**.
   - **Više .csv ili .parketa**: Potražite osnovnu fasciklu, izaberite tip šare i unesite izraz.
   - **Pojedinačne .csv ili .parket**: Potražite datoteku .csv ili .parketa i izaberite je.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Dijalog za kreiranje novog entiteta sa istaknutom lokacijom datoteka sa podacima.":::

1. Izaberite **Sačuvaj**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Dijalog za definisanje ili automatsko generisanje atributa.":::

1. Potvrdite **izbor u ovom polju za potvrdu** definišite atribute da biste ručno dodali atribute ili izaberite automatsko **generisanje**. Da biste definisali atribute, unesite ime, izaberite format podataka i opcionalni semantički tip. Za automatski generisane atribute:

   1. Nakon što se atributi automatski generišu, izaberite stavku **Rediguj atribute**. Prikazaće **se stranica "Upravljanje** atributima".

   1. Uverite se da je format podataka ispravan za svaki atribut.

   1. Da biste omogućili analitiku i druge mogućnosti, izaberite **profilisanje** podataka za ceo entitet ili za određene atribute. Podrazumevano nijedan entitet nije omogućen za profilisanje podataka.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dijalog za izbor profilisanja podataka.":::

   1. Izaberite **Gotovo**. Prikazaće **se stranica "Izbor** entiteta".

1. Nastavite da dodajete entitete i atribute, ako je primenljivo.

1. Nakon što dodate sve entitete, izaberite opciju **Uključi** da biste uključili entitete u izvor podataka ingestion.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dijalog koji prikazuje potreban za primarni ključ":::

1. Za izabrane entitete koji zahtevaju postepeno unošenje, potrebni ekrani **u okviru** postepenog **osvežavanja**. Za svaki od ovih entiteta pogledajte članak [Konfigurisanje postepenog osvežavanja za Azure Data Lake izvore podataka](incremental-refresh-data-sources.md).

1. Za izabrane entitete u kojima primarni ključ nije definisan, potrebni prikazi **u okviru** primarnog **ključa**. Za svaki od ovih entiteta:
   1. Izaberite **potrebnu**. Prikazuje **se tabla "Uređivanje** entiteta".
   1. Odaberite **primarni ključ**. Primarni ključ je atribut jedinstven za entitet. Da bi atribut bio važeći primarni ključ, ne bi trebalo da sadrži duplirane vrednosti, nedostajuće vrednosti ili prazne vrednosti. Atributi tipa niska, ceo broj i GUID tip podataka su podržani kao primarni ključevi.
   1. Opcionalno, promenite obrazac particije.
   1. Kliknite na **dugme "** Zatvori" da biste sačuvali i zatvorili tablu.

1. Izaberite **Sačuvaj**. Otvoriće **se stranica "Izvori podataka" koja prikazuje novu izvor podataka statusu "Osvežavanje** **·**".


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Uređivanje Azure Data Lake Storage izvor podataka

Pomoću opcije možete da *ažurirate nalog za povezivanje sa* skladištem. Više informacija potražite u članku [Povezivanje uvida klijenata sa Azure Data Lake Storage Gen2 nalogom pomoću Azure servisnog direktora](connect-service-principal.md). Da biste se povezali na drugi kontejner sa naloga za skladištenje ili da promenite ime naloga, [kreirajte novu vezu sa izvorom podataka](#connect-to-azure-data-lake-storage).

1. Idite na **Podaci** > **Izvori podataka**.

1. Pored izvor podataka želite da ažurirate, izaberite stavku **Uredi**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Dijalog za uređivanje Azure Data Lake izvor podataka.":::

1. Promenite neku od sledećih informacija:

   - **Opis**
   - **Povežite skladište koristeći informacije** o vezi i vezi. Ne možete promeniti informacije o **kontejneru** prilikom ažuriranja veze.
      > [!NOTE]
      > Jedna od sledećih uloga mora biti dodeljena nalogu za skladištenje ili kontejneru:
        > - Čitač podataka skladišta blob objekta
        > - Vlasnik podataka skladišta blob objekta
        > - Saradnik za podatke skladišta blob objekta

   - **Omogućite privatnu** vezu ako želite da unosite podatke sa naloga za skladištenje putem Azure privatne veze. Više informacija potražite u članku [Privatne veze](security-overview.md#private-links-tab).

1. Izaberite **Sledeće**.
1. Promenite nešto od sledećeg:
   - Krećite se do druge datoteke model.json ili manifest.json sa različitim skupom entiteta iz kontejnera.
   - Izaberite novi entitet da biste dodali dodatne entitete **u jelo**.
   - Izaberite entitet i Izbriši da biste uklonili sve već izabrane entitete ako nema **zavisnosti**.
      > [!IMPORTANT]
      > Ako postoje zavisnosti od postojeće datoteke model.json ili manifest.json i skupa entiteta, videćete poruku o grešci i ne možete da izaberete drugu datoteku model.json ili manifest.json. Uklonite te zavisnosti pre promene datoteke model.json ili manifest.json ili kreirajte novi izvor podataka sa datotekom model.json ili manifest.json koju želite da koristite da biste izbegli uklanjanje zavisnosti.
   - Da biste promenili lokaciju datoteke sa podacima ili primarni ključ, kliknite na dugme " **Uredi"**.
   - Da biste promenili postepene podatke o brisanju, pogledajte [konfigurisanje postepenog osvežavanja za Azure Data Lake izvore podataka](incremental-refresh-data-sources.md)

1. Izaberite **atribute da** biste dodali ili promenili atribute ili da biste omogućili profilisanje podataka. Zatim izaberite **Gotovo**.

1. Kliknite **na dugme** "Sačuvaj" da biste primenili promene i vratili se na **stranicu "Izvori podataka** ".
