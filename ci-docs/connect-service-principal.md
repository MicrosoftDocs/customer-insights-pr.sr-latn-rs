---
title: Povezivanje sa Azure Data Lake Storage nalogom korišćenjem Azure principala usluge
description: Za povezivanje sa sopstvenim jezerom podataka, koristite principala usluge Azure.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 949caa73578dbe0a511726ec045c0fd5f4621de4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082246"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Povezivanje sa Azure Data Lake Storage nalogom korišćenjem Azure principala usluge

Ovaj članak govori o tome kako da se povežete Dynamics 365 Customer Insights sa nalogom Azure Data Lake Storage pomoću direktora Azure usluge umesto ključeva naloga za skladištenje.

Automatizovani alati koji koriste Azure usluge uvek bi trebalo da imaju ograničene dozvole. Umesto da se aplikacije prijavljuju kao potpuno privilegovani korisnik, Azure nudi principale usluga. Principalne usluge možete da koristite za bezbedno [dodavanje ili uređivanje fascikle "Uobičajeni model podataka" kao izvor podataka](connect-common-data-model.md) ili [kreiranje ili ažuriranje okruženja](create-environment.md).

> [!IMPORTANT]
>
> - Data Lake Storage nalog koji će koristiti glavnicu usluge mora biti Gen2 i [hijerarhijski prostor za ime](/azure/storage/blobs/data-lake-storage-namespace). Azure Data Lake Gen1 nalozi za skladištenje nisu podržani.
> - Potrebne su vam administratorske dozvole za Azure zakupac da biste kreirali glavnicu usluge.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Kreiranje principala usluge Azure za Customer Insights

Pre nego što kreirate novog direktora servisa za uvide klijenata, proverite da li on već postoji u vašoj organizaciji.

### <a name="look-for-an-existing-service-principal"></a>Potražite postojeći principal usluge

1. Idite na [Azure portal za administraciju](https://portal.azure.com) i prijavite se u svoju organizaciju.

2. Na stranici **Azure usluge** izaberite **Azure Active Directory**.

3. U okviru Upravljanje izaberite **Microsoft aplikaciju**.**·**

4. Dodajte filter za **ID aplikacije započnite**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` sa ili potražite ime `Dynamics 365 AI for Customer Insights`.

5. Ako pronađete odgovarajući zapis, to znači da principal usluge već postoji.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snimak ekrana koji prikazuje postojećeg principala usluge.":::

6. Ako rezultati ne budu vraćeni, možete kreirati [novog direktora usluge](#create-a-new-service-principal). U većini slučajeva već postoji i potrebno je samo da dodelite dozvole za pristup glavnom nalogu usluge.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Dodelite dozvole principalu usluge za pristup nalogu za skladištenje

Idite na portal Azure da biste dodelili dozvole direktoru usluge za nalog za skladištenje koji želite da koristite u uvidima klijenata. Jedna od sledećih uloga mora biti dodeljena nalogu za skladištenje ili kontejneru:

|Akreditiv|Zahtevi|
|----------|------------|
|Trenutno prijavljeni korisnik|**Uloga**: Skladištenje Blob podataka čitalac, Storage Blob saradnik ili Storage Blob Owner.<br>**Nivo**: Dozvole se mogu dodeliti na nalogu za skladištenje ili kontejneru.</br>|
|Glavnica usluge uvida kupaca -<br>Korišćenje Azure Data Lake Storage kao izvor podataka</br>|Opcija 1<ul><li>**Uloga**: Storage Blob Data čitalac, Storage Blob Data saradnik ili Storage Blob Data Owner.</li><li>**Nivo**: Dozvole treba da budu dodeljene na nalogu za skladištenje.</li></ul>Opcija 2 *(bez deljenja usluge Principalni pristup nalogu za skladištenje)*<ul><li>**Uloga 1**: Skladištenje Blob podataka čitalac, Storage Blob Data saradnik ili Storage Blob Vlasnik podataka.</li><li>**Nivo**: Dozvole treba da budu dodeljene u kontejneru.</li><li>**Uloga 2**: Delegator podataka blob skladišta.</li><li>**Nivo**: Dozvole treba da budu dodeljene na nalogu za skladištenje.</li></ul>|
|Glavnica usluge uvida kupaca - <br>Korišćenje Azure Data Lake Storage kao izlaz ili odredište</br>|Opcija 1<ul><li>**Uloga**: Skladištenje Blob podataka saradnik vlasnik skladišta bloba.</li><li>**Nivo**: Dozvole treba da budu dodeljene na nalogu za skladištenje.</li></ul>Opcija 2 *(bez deljenja usluge Principalni pristup nalogu za skladištenje)*<ul><li>**Uloga**: Skladištenje Blob podataka saradnik vlasnik skladišta bloba.</li><li>**Nivo**: Dozvole treba da budu dodeljene u kontejneru.</li><li>**Uloga 2**: Delegator skladišta Blob.</li><li>**Nivo**: Dozvole treba da budu dodeljene na nalogu za skladištenje.</li></ul>|

1. Idite na [Azure portal za administraciju](https://portal.azure.com) i prijavite se u svoju organizaciju.

1. Otvorite nalog za skladište kojem želite da glavnica usluge za uvide klijenata ima pristup.

1. U levom oknu izaberite **Kontrola pristupa (IAM)**, a zatim izaberite **Dodavanje** > **Dodaj dodelu uloge**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snimak ekrana koji prikazuje Azure portal dok dodajete dodelu uloge.":::

1. U oknu **Dodaj dodelu uloge** podesite sledeća svojstva:
   - Uloga: Skladištenje Blob podataka čitalac, Storage Blob saradnik ili Storage Blob Owner na osnovu gorenavedenih akreditiva.
   - Dodelite pristup: **Korisnik, grupa ili principal usluge**
   - Izaberite članove: **Dynamics 365 AI za uvide klijenata** ([glavnica usluge](#create-a-new-service-principal) koju ste tražili ranije u ovoj proceduri)

1. Izaberite **Redigovanje + dodeli**.

Prenos promena može trajati do 15 minuta.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Unesite ID Azure resursa ili detalje Azure pretplate u prilog naloga za skladištenje u fascikli "Uvidi kupaca"

Nalog skladišta "Data Lake" možete priložiti u uvidima kupaca da biste [uskladištili izlazne](manage-environments.md) podatke [ili ih koristili kao izvor podataka](connect-dataverse-managed-lake.md). Ova opcija vam omogućava da birate između pristupa zasnovanog na resursima ili pristupa zasnovanog na pretplati. U zavisnosti od pristupa koji izaberete, sledite postupak u jednom od sledećih odeljaka.

### <a name="resource-based-storage-account-connection"></a>Povezivanje naloga za skladištenje zasnovano na resursima

1. Idite na [Azure portal za administraciju](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite nalog za skladištenje.

1. U levom oknu idite na krajnje **tačke** > **postavki**.

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

### <a name="create-a-new-service-principal"></a>Kreiraj nov principal usluge

1. Instalirajte najnoviju verziju usluge Azure Active Directory PowerShell for Graph. Za više informacija pogledajte članak [Instaliranje usluge Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Na računaru pritisnite taster Windows na tastaturi i potražite **Windows PowerShell i izaberite** Pokreni **kao administrator**.

   1. U PowerShell prozoru koji se otvori unesite `Install-Module AzureAD`.

2. Kreirajte principala usluge za Customer Insights pomoću Azure AD PowerShell modula.

   1. U PowerShell prozor unesite `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Zamenite *[ID kataloga] pravim* ID-om direktorijuma Azure pretplate gde želite da kreirate glavnicu usluge. Parametar naziva okruženja `AzureEnvironmentName` je opcionalan.
  
   1. Unesite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ova komanda kreira glavnicu usluge za uvide klijenata u izabranoj Azure pretplati.

[!INCLUDE [footer-include](includes/footer-banner.md)]
