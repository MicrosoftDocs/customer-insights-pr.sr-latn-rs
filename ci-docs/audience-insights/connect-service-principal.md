---
title: Povezivanje sa Azure Data Lake Storage nalogom korišćenjem principala usluge
description: Za povezivanje sa sopstvenim jezerom podataka, koristite principala usluge Azure.
ms.date: 09/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b901d799dbd73841a6ddbae754c4e4275f61146a
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645189"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Povezivanje sa Azure Data Lake Storage nalogom korišćenjem Azure principala usluge

Automatizovani alati koji koriste Azure usluge uvek bi trebalo da imaju ograničene dozvole. Umesto da se aplikacije prijavljuju kao potpuno privilegovani korisnik, Azure nudi principale usluga. Čitajte dalje da biste saznali kako da povežete uslugu Dynamics 365 Customer Insights sa Azure Data Lake Storage nalogom koristeći principala usluge Azure umesto ključeva naloga za skladištenje. 

Možete koristiti principala usluge da bezbedno [dodate ili uredite Common Data Service fasciklu kao izvor podataka](connect-common-data-model.md) ili da [kreirate ili ažurirate okruženje](create-environment.md).

> [!IMPORTANT]
> - Data Lake Storage nalog koji će koristiti principala usluge mora imati [omogućen hijerarhijski prostor za ime](/azure/storage/blobs/data-lake-storage-namespace).
> - Potrebne su vam administratorske dozvole za Azure pretplatu da biste kreirali principal usluge.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Kreiranje principala usluge Azure za Customer Insights

Pre nego što kreirate novog principala usluge za uvide u ciljnu grupu ili uvide u angažovanje, proverite da li već postoji u vašoj organizaciji.

### <a name="look-for-an-existing-service-principal"></a>Potražite postojeći principal usluge

1. Idite na [Azure portal za administraciju](https://portal.azure.com) i prijavite se u svoju organizaciju.

2. Na stranici **Azure usluge** izaberite **Azure Active Directory**.

3. U odeljku **Upravljanje**, izaberite **Poslovne aplikacije**.

4. Potražite ID Microsoft aplikacije:
   - Uvidi u ciljnu grupu: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` pod nazivom `Dynamics 365 AI for Customer Insights`
   - Uvidi u angažovanje: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` pod nazivom `Dynamics 365 AI for Customer Insights engagement insights`

5. Ako pronađete odgovarajući zapis, to znači da principal usluge već postoji. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snimak ekrana koji prikazuje postojećeg principala usluge.":::
   
6. Ako se ne prikažu rezultati, kreirajte nov principal usluge.

>[!NOTE]
>Da biste iskoristili svu moć usluge Dynamics 365 Customer Insights, predlažemo da obe aplikacije dodate principalu usluge.

### <a name="create-a-new-service-principal"></a>Kreiraj nov principal usluge

1. Instalirajte najnoviju verziju usluge Azure Active Directory PowerShell for Graph. Za više informacija pogledajte članak [Instaliranje usluge Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Na računaru izaberite taster Windows na tastaturi i potražite **Windows PowerShell** i izaberite **Pokreni kao administrator**.
   
   1. U PowerShell prozoru koji se otvori unesite `Install-Module AzureAD`.

2. Kreirajte principala usluge za Customer Insights pomoću Azure AD PowerShell modula.

   1. U PowerShell prozor unesite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Zamenite *[svoj ID zakupca]* stvarnim ID-om vašeg zakupca tamo gde želite da napravite principal usluge. Parametar naziva okruženja `AzureEnvironmentName` je opcionalan.
  
   1. Unesite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ova naredba kreira principal usluge za uvide o korisnicima na izabranom zakupcu. 

   1. Unesite `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Ova komanda kreira principala za uvide u angažovanje na izabranom zakupcu.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Dodelite dozvole principalu usluge za pristup nalogu za skladištenje

Idite na Azure portal da biste dodelili dozvole principalu usluge za nalog za skladištenje koji želite da koristite u uvidima o korisnicima.

1. Idite na [Azure portal za administraciju](https://portal.azure.com) i prijavite se u svoju organizaciju.

1. Otvorite nalog za skladištenje kojem želite da principal usluge za uvide o korisnicima ima pristup.

1. U levom oknu izaberite **Kontrola pristupa (IAM)**, a zatim izaberite **Dodavanje** > **Dodaj dodelu uloge**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snimak ekrana koji prikazuje Azure portal dok dodajete dodelu uloge.":::

1. U oknu **Dodaj dodelu uloge** podesite sledeća svojstva:
   - Uloga: **Saradnik za podatke skladišta blob objekta**
   - Dodelite pristup: **Korisnik, grupa ili principal usluge**
   - Izaberite: **Dynamics 365 AI for Customer Insights** i **Uvidi u angažovanje u usluzi Dynamics 365 AI for Customer Insights** (dva [principala usluga](#create-a-new-service-principal) koja ste kreirali ranije u ovoj proceduri)

1.  Izaberite stavku **Sačuvaj**.

Prenos promena može trajati do 15 minuta.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Unesite ID Azure resursa ili detalje o Azure pretplati u prilogu naloga za skladištenje u uvidima o ciljnoj grupi

Možete da priložite Data Lake Storage nalog u uvide o ciljnoj grupi u [izlazne podatke za skladištenje](manage-environments.md) ili ih [koristite kao izvor podataka](connect-common-data-service-lake.md). Ova opcija vam omogućava da birate između pristupa zasnovanog na resursima ili pristupa zasnovanog na pretplati. U zavisnosti od pristupa koji izaberete, sledite postupak u jednom od sledećih odeljaka.

### <a name="resource-based-storage-account-connection"></a>Povezivanje naloga za skladištenje zasnovano na resursima

1. Idite na [Azure portal za administraciju](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite nalog za skladištenje.

1. U levom oknu idite na **Podešavanja** > **Svojstva**.

1. Kopirajte vrednost ID-a resursa naloga za skladištenje.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopirajte ID resursa naloga za skladištenje.":::

1. U uvidima o ciljnoj grupi, umetnite ID resursa u polje resursa prikazano na ekranu za povezivanje naloga za skladištenje.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Unesite informacije o ID-u resursa naloga za skladištenje.":::   

1. Nastavite sa preostalim koracima u uvidima o korisnicima da biste priložili nalog za skladištenje.

### <a name="subscription-based-storage-account-connection"></a>Povezivanje naloga za skladištenje zasnovanog na pretplatama

1. Idite na [Azure portal za administraciju](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite nalog za skladištenje.

1. U levom oknu idite na **Podešavanja** > **Svojstva**.

1. Pregledajte **Pretplata**,**Grupa resursa** i **Ime** naloga za skladištenje kako biste bili sigurni da ste izabrali prave vrednosti u uvidima o korisnicima.

1. U uvidima o ciljnoj grupi, odaberite vrednosti za odgovarajuća polja prilikom prilaganja naloga za skladištenje.

1. Nastavite sa preostalim koracima u uvidima o korisnicima da biste priložili nalog za skladištenje.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
