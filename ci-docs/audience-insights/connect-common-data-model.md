---
title: Povežite Common Data Model podatke sa Azure Data Lake nalogom
description: Radite sa Common Data Model podacima koristeći Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 49bab0605197912cd4b81ff193b914599a092792
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554911"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Povežite se sa Common Data Model fasciklom koja koristi Azure Data Lake nalog

Ovaj članak pruža informacije o tome kako unositi podatke iz Common Data Model fascikle pomoću Azure Data Lake Storage Gen2 naloga.

## <a name="important-considerations"></a>Važna razmatranja

- Podaci u vašem Azure Data Lake treba da prate uobičajeni standard Common Data Model. Drugi formati trenutno nisu podržani.

- Unos podataka podržava samo Azure Data Lake *Gen2* naloge za skladištenje. Ne možete da koristite Azure Data Lake Gen1 naloge za skladištenje za unos podataka.

- Da biste potvrdili identitet pomoću principala usluge Azure, uverite se da je konfigurisan u vašem zakupcu. Za više informacija pogledajte [Povezivanje uvida o korisnicima sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge](connect-service-principal.md).

- Azure Data Lake sa kojim želite da se povežete i unesete podatke mora biti u istom Azure regionu kao i Dynamics 365 Customer Insights okruženje. Ne podržavaju se veze sa Common Data Model fasciklom iz jezera podataka u drugom Azure regionu. Da biste saznali Azure region okruženja, posetite **Administrator** > **Sistem** > **Osnovni podaci** u uvidima o korisnicima.

- Podaci koji se čuvaju u uslugama na mreži mogu se čuvati na lokaciji koja se razlikuje od one na kojoj se podaci obrađuju ili čuvaju u usluzi Dynamics 365 Customer Insights. Uvozom ili povezivanjem podataka uskladištenih u mrežnoj usluzi, slažete se da se podaci mogu preneti i skladištiti u usluzi Dynamics 365 Customer Insights. [Saznajte više u Microsoft centru za pouzdanost.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Povezivanje u fasciklu Common Data Model

1. U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.

1. Izaberite **Dodaj izvor podataka**.

1. Izaberite **Povežite se sa Common Data Model fasciklom**, unesite **Ime** za izvor podataka i izaberite **Sledeće**. Smernice za nazive: 
   - Započnite slovom.
   - Koristite samo slova i brojeve. Posebni znakovi i razmaci nisu dozvoljeni.
   - Koristite između 3 i 64 znaka.

1. Možete da birate između korišćenja opcije zasnovane na resursima i opcije zasnovane na pretplati za potvrdu identiteta. Za više informacija pogledajte [Povezivanje uvida o korisnicima sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge](connect-service-principal.md). Unesite informacije o **Kontejneru** i izaberite **Sledeće**.
   > [!div class="mx-imgBorder"]
   > ![Dijalog za unos novih detalja veze za Azure Data Lake.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Potrebna vam je jedna od sledećih uloga u kontejneru ili nalogu za skladištenje pomenutom gore da biste mogli da se povežete i kreirate izvor podataka:
   >  - Čitač podataka skladišta blob objekta
   >  - Vlasnik podataka skladišta blob objekta
   >  - Saradnik za podatke skladišta blob objekta

1. U dijalogu **Izaberite Common Data Model fasciklu**, izaberite datoteku model.json ili manifest.json iz koje želite da uvezete podatke, pa izaberite **Sledeće**.
   > [!NOTE]
   > Nijedna datoteka model.json ili manifest.json povezana sa drugim izvorom podataka u okruženju neće se prikazati na listi.

1. Listu dostupnih entiteta dobićete u izabranoj datoteci model.json ili manifest.json. Možete da pregledate entitete i izaberete ih sa liste dostupnih entiteta, pa izaberite **Sačuvaj**. Svi izabrani entiteti biće uneti iz novog izvora podataka.
   > [!div class="mx-imgBorder"]
   > ![Dijalog koji prikazuje listu entiteta iz datoteke model.json.](media/review-entities.png)

8. Navedite entitete podataka za koje želite da omogućite profilisanje podataka i izaberite **Sačuvaj**. Profilisanje podataka omogućava analitiku i druge mogućnosti. Možete odabrati čitav entitet koji bira sve atribute iz entiteta ili odabrati određene atribute po svom izboru. Podrazumevano nijedan entitet nije omogućen za profilisanje podataka.
   > [!div class="mx-imgBorder"]
   > ![Dijalog koji prikazuje profilisanje podataka.](media/dataprofiling-entities.png)

9. Kada sačuvate izabrane opcije, otvoriće se stranica **Izvori podataka**. Sada bi trebalo da vidite vezu Common Data Model fascikle kao izvor podataka.

> [!NOTE]
> Datoteka model.json ili manifest.json može se povezati samo sa jednim izvorom podataka u istom okruženju. Međutim, ista datoteka model.json ili manifest.json može se koristiti za izvore podataka u više okruženja.

## <a name="edit-a-common-data-model-folder-data-source"></a>Uredite izvor podataka Common Data Model fascikle

Možete da ažurirate pristupni ključ za nalog za skladištenje koji sadrži Common Data Model fasciklu. Takođe možete promeniti datoteku model.json ili manifest.json. Da biste se povezali na drugi kontejner sa naloga za skladištenje ili da promenite ime naloga, [kreirajte novu vezu sa izvorom podataka](#connect-to-a-common-data-model-folder).

1. U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.

2. Pored izvora podataka koji želite da ažurirate, izaberite tri tačke.

3. Izaberite opciju **Uredi** sa liste.

4. Opcionalno, ažurirajte **Ključ za pristup** i izaberite **Sledeće**.

   ![Dijalog za uređivanje i ažuriranje ključa za pristup za postojeći izvor podataka.](media/edit-access-key.png)

5. Po želji možete da ažurirate sa veze ključa naloga na vezu zasnovanu na resursima ili pretplati. Za više informacija pogledajte [Povezivanje uvida o korisnicima sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge](connect-service-principal.md). Ne možete promeniti informacije o **kontejneru** prilikom ažuriranja veze.
   > [!div class="mx-imgBorder"]

   > ![Dijalog za unos detalja veze usluge Azure Data Lake sa postojećim nalogom za skladištenje.](media/enter-existing-storage-details.png)

   > [!NOTE]
   > Potrebna vam je jedna od sledećih uloga u kontejneru ili nalogu za skladištenje pomenutom gore da biste mogli da se povežete i kreirate izvor podataka:
   >  - Čitač podataka skladišta blob objekta
   >  - Vlasnik podataka skladišta blob objekta
   >  - Saradnik za podatke skladišta blob objekta


6. Opcionalno, odaberite drugu datoteku model.json ili manifest.json sa različitim skupom entiteta iz kontejnera.

7. Po želji možete odabrati dodatne entitete za unos. Takođe možete ukloniti sve već odabrane entitete ako nema zavisnih elemenata.

   > [!IMPORTANT]
   > Ako postoje zavisnosti od postojeće datoteke model.json ili manifest.json i skupa entiteta, videćete poruku o grešci i ne možete da izaberete drugu datoteku model.json ili manifest.json. Uklonite te zavisnosti pre promene datoteke model.json ili manifest.json ili kreirajte novi izvor podataka sa datotekom model.json ili manifest.json koju želite da koristite da biste izbegli uklanjanje zavisnosti.

8. Po želji možete odabrati dodatne atribute ili entitete kako biste omogućili profilisanje podataka ili onemogućili već odabrane.   


[!INCLUDE[footer-include](../includes/footer-banner.md)]