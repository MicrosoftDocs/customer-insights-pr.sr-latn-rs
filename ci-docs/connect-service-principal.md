---
title: Povezivanje sa Azure Data Lake Storage nalogom korišćenjem principala usluge
description: Za povezivanje sa sopstvenim jezerom podataka, koristite principala usluge Azure.
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 1dd99edc327bd41b0442b390f2e4f8664269f553
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643353"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Povezivanje sa Azure Data Lake Storage nalogom korišćenjem Azure principala usluge

Ovaj članak govori o tome kako da se povežete Dynamics 365 Customer Insights sa nalogom Azure Data Lake Storage pomoću direktora Azure usluge umesto ključeva naloga za skladištenje. 

Automatizovani alati koji koriste Azure usluge uvek bi trebalo da imaju ograničene dozvole. Umesto da se aplikacije prijavljuju kao potpuno privilegovani korisnik, Azure nudi principale usluga. Principalne usluge možete da koristite za bezbedno [dodavanje ili uređivanje fascikle "Uobičajeni model podataka" kao izvor podataka](connect-common-data-model.md) ili [kreiranje ili ažuriranje okruženja](create-environment.md).

> [!IMPORTANT]
> - Data Lake Storage nalog koji će koristiti glavnicu usluge mora biti Gen2 i [hijerarhijski prostor za ime](/azure/storage/blobs/data-lake-storage-namespace). Azure Data Lake Gen1 nalozi za skladištenje nisu podržani.
> - Potrebne su vam administratorske dozvole za Azure pretplatu da biste kreirali glavnicu usluge.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Kreiranje principala usluge Azure za Customer Insights

Pre nego što kreirate novog direktora servisa za uvide klijenata, proverite da li on već postoji u vašoj organizaciji.

### <a name="look-for-an-existing-service-principal"></a>Potražite postojeći principal usluge

1. Idite na [Azure portal za administraciju](https://portal.azure.com) i prijavite se u svoju organizaciju.

2. Na stranici **Azure usluge** izaberite **Azure Active Directory**.

3. U odeljku **Upravljanje**, izaberite **Poslovne aplikacije**.

4. Potražite ID Microsoft aplikacije `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` sa imenom `Dynamics 365 AI for Customer Insights`.

5. Ako pronađete odgovarajući zapis, to znači da principal usluge već postoji. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snimak ekrana koji prikazuje postojećeg principala usluge.":::
   
6. Ako se ne prikažu rezultati, kreirajte nov principal usluge.

### <a name="create-a-new-service-principal"></a>Kreiraj nov principal usluge

1. Instalirajte najnoviju verziju usluge Azure Active Directory PowerShell for Graph. Za više informacija pogledajte članak [Instaliranje usluge Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Na računaru izaberite taster Windows na tastaturi i potražite **Windows PowerShell** i izaberite **Pokreni kao administrator**.
   
   1. U PowerShell prozoru koji se otvori unesite `Install-Module AzureAD`.

2. Kreirajte principala usluge za Customer Insights pomoću Azure AD PowerShell modula.

   1. U PowerShell prozor unesite `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Zamenite *[ID kataloga] pravim* ID-om direktorijuma Azure pretplate gde želite da kreirate glavnicu usluge. Parametar naziva okruženja `AzureEnvironmentName` je opcionalan.
  
   1. Unesite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ova komanda kreira glavnicu usluge za uvide klijenata u izabranoj Azure pretplati. 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Dodelite dozvole principalu usluge za pristup nalogu za skladištenje

Idite na portal Azure da biste dodelili dozvole direktoru usluge za nalog za skladištenje koji želite da koristite u uvidima klijenata.

1. Idite na [Azure portal za administraciju](https://portal.azure.com) i prijavite se u svoju organizaciju.

1. Otvorite nalog za skladište kojem želite da glavnica usluge za uvide klijenata ima pristup.

1. U levom oknu izaberite **Kontrola pristupa (IAM)**, a zatim izaberite **Dodavanje** > **Dodaj dodelu uloge**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snimak ekrana koji prikazuje Azure portal dok dodajete dodelu uloge.":::

1. U oknu **Dodaj dodelu uloge** podesite sledeća svojstva:
   - Uloga: **Saradnik za podatke skladišta blob objekta**
   - Dodelite pristup: **Korisnik, grupa ili principal usluge**
   - Izaberite članove: **Dynamics 365 AI za uvide klijenata** (glavnica [usluge koju](#create-a-new-service-principal) ste kreirali ranije u ovoj proceduri)

1.  Izaberite **Redigovanje + dodeli**.

Prenos promena može trajati do 15 minuta.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Unesite ID Azure resursa ili detalje Azure pretplate u prilog naloga za skladištenje u fascikli "Uvidi kupaca"

Nalog skladišta "Data Lake" možete priložiti u uvidima kupaca da biste [uskladištili izlazne](manage-environments.md) podatke [ili ih koristili kao izvor podataka](connect-dataverse-managed-lake.md). Ova opcija vam omogućava da birate između pristupa zasnovanog na resursima ili pristupa zasnovanog na pretplati. U zavisnosti od pristupa koji izaberete, sledite postupak u jednom od sledećih odeljaka.

### <a name="resource-based-storage-account-connection"></a>Povezivanje naloga za skladištenje zasnovano na resursima

1. Idite na [Azure portal za administraciju](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite nalog za skladištenje.

1. U levom oknu idite na **Podešavanja** > **Svojstva**.

1. Kopirajte vrednost ID-a resursa naloga za skladištenje.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopirajte ID resursa naloga za skladištenje.":::

1. U okviru "Uvidi kupaca" umetnite ID resursa u polje resursa prikazano na ekranu za povezivanje naloga za skladištenje.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Unesite informacije o ID-u resursa naloga za skladištenje.":::   

1. Nastavite sa preostalim koracima u uvidima klijenata da biste priložili nalog za skladištenje.

### <a name="subscription-based-storage-account-connection"></a>Povezivanje naloga za skladištenje zasnovanog na pretplatama

1. Idite na [Azure portal za administraciju](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite nalog za skladištenje.

1. U levom oknu idite na **Podešavanja** > **Svojstva**.

1. Pregledajte **pretplatu**, grupu **resursa** i ime **naloga** za skladištenje da biste se uverili da ste izabrali prave vrednosti u uvidima klijenata.

1. U prozoru Uvidi kupaca odaberite vrednosti za odgovarajuća polja prilikom prilaganja naloga za skladištenje.

1. Nastavite sa preostalim koracima u uvidima klijenata da biste priložili nalog za skladištenje.


[!INCLUDE [footer-include](includes/footer-banner.md)]