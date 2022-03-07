---
title: Povežite Common Data Model podatke sa Azure Data Lake nalogom
description: Radite sa Common Data Model podacima koristeći Azure Data Lake Storage.
ms.date: 01/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 1e3b28316c06d6a15dd5690837c365b0677a882e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354944"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Povežite se sa Common Data Model fasciklom koja koristi Azure Data Lake nalog

Ovaj članak pruža informacije o tome kako unositi podatke iz Common Data Model fascikle pomoću Azure Data Lake Storage Gen2 naloga.

## <a name="important-considerations"></a>Važna razmatranja

- Podaci u vašem Azure Data Lake treba da prate uobičajeni standard Common Data Model. Drugi formati trenutno nisu podržani.

- Unos podataka podržava samo Azure Data Lake *Gen2* naloge za skladištenje. Ne možete da koristite Azure Data Lake Gen1 naloge za skladištenje za unos podataka.

- Azure Data Lake nalog za skladištenje mora da [ima hijerarhijski za ime omogućen](/azure/storage/blobs/data-lake-storage-namespace).

- Da biste potvrdili identitet pomoću principala usluge Azure, uverite se da je konfigurisan u vašem zakupcu. Za više informacija pogledajte [Povezivanje uvida o korisnicima sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge](connect-service-principal.md).

- Azure Data Lake sa kojim želite da se povežete i unesete podatke mora biti u istom Azure regionu kao i Dynamics 365 Customer Insights okruženje. Ne podržavaju se veze sa Common Data Model fasciklom iz jezera podataka u drugom Azure regionu. Da biste saznali Azure region okruženja, posetite **Administrator** > **Sistem** > **Osnovni podaci** u uvidima o korisnicima.

- Podaci uskladišteni u uslugama na mreži mogu se uskladištiti na drugoj lokaciji od mesta gde se podaci obrađuju ili skladište u programu Dynamics 365 Customer Insights.Uvozom ili povezivanjem sa podacima uskladištenim u uslugama na mreži slažete se da se podaci mogu prenositi i skladištiti sa programom Dynamics 365 Customer Insights. [Saznajte više u Microsoft centru za pouzdanost](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Povezivanje u fasciklu Common Data Model

1. U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.

1. Izaberite **Dodaj izvor podataka**.

1. Izaberite **Azure skladište jezera sa podacima**, unesite ime za **izvor podataka, a** zatim kliknite na dugme **Dalje**.

   - Ako budete upitani, izaberite jedan od probnih skupova podataka koji se odnose na vašu industriju, a zatim kliknite na dugme **Dalje**. 

1. Možete da birate između korišćenja opcije zasnovane na resursima i opcije zasnovane na pretplati za potvrdu identiteta. Za više informacija pogledajte [Povezivanje uvida o korisnicima sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge](connect-service-principal.md). Unesite adresu **servera**, izaberite stavku **Prijavi se, a zatim** kliknite na dugme **Dalje**.
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

1. Listu dostupnih entiteta videćete u izabranoj datoteci model.json ili manifest.json. Redigujte i izaberite sa liste dostupnih entiteta, a zatim kliknite na dugme **Sačuvaj**. Svi izabrani entiteti biće uneti iz novog izvora podataka.
   > [!div class="mx-imgBorder"]
   > ![Dijalog koji prikazuje listu entiteta iz datoteke model.json.](media/review-entities.png)

8. Naznačite entitete podataka koje želite da omogućite profilisanje podataka, a zatim kliknite na dugme **Sačuvaj**. Profilisanje podataka omogućava analitiku i druge mogućnosti. Možete odabrati čitav entitet koji bira sve atribute iz entiteta ili odabrati određene atribute po svom izboru. Podrazumevano nijedan entitet nije omogućen za profilisanje podataka.
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
