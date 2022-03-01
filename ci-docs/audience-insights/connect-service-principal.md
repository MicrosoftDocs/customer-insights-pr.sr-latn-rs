---
title: Povežite se sa Azure Data Lake Storage Gen2 nalog pomoću principala usluge
description: Koristite principal Azure usluge za uvide u korisnike da biste se povezali sa sopstvenim jezerom podataka kada ga priložite uvidima u korisnike.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cc94ad49f12067d513db4663bff60620d6501eb0
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692130"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Povežite se sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge za uvide u ciljnu grupu

Automatizovani alati koji koriste Azure usluge uvek bi trebalo da imaju ograničene dozvole. Umesto da se aplikacije prijavljuju kao potpuno privilegovani korisnik, Azure nudi principale usluga. Čitajte dalje da biste saznali kako da povežete uvide u korisnike sa Azure Data Lake Storage Gen2 nalogom koji koristi Azure principal usluge umesto ključeva naloga za skladištenje. 

Principal usluge možete koristiti za sigurno [dodavanje ili uređivanje Common Data Model fascikle kao izvora podataka](connect-common-data-model.md) ili [kreirajte novo ili ažurirajte postojeće okruženje](get-started-paid.md).

> [!IMPORTANT]
> - Azure Data Lake Gen2 nalog za skladištenje koji namerava da koristi principala usluge mora da ima [omogućenu funkciju hijerarhijskog prostora imena (HNS)](/azure/storage/blobs/data-lake-storage-namespace).
> - Potrebne su vam administratorske dozvole za Azure pretplatu da biste kreirali principal usluge.

## <a name="create-azure-service-principal-for-audience-insights"></a>Napravite principal Azure usluge za uvide u korisnike

Pre nego što napravite nov principal usluge za uvide u korisnike, proverite da li već postoji u vašoj organizaciji.

### <a name="look-for-an-existing-service-principal"></a>Potražite postojeći principal usluge

1. Idite na [Azure portal za administraciju](https://portal.azure.com) i prijavite se u svoju organizaciju.

2. Izaberite **Azure Active Directory** iz Azure usluga.

3. U odeljku **Upravljanje**, izaberite **Poslovne aplikacije**.

4. Potražite ID direktne aplikacije uvida u korisnike `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ili ime `Dynamics 365 AI for Customer Insights`.

5. Ako pronađete odgovarajući zapis, to znači da postoji principal usluge za uvide u korisnike. Ne morate da ga ponovo kreirate.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snimak ekrana koji prikazuje postojeći principal usluge.":::
   
6. Ako se ne prikažu rezultati, kreirajte nov principal usluge.

### <a name="create-a-new-service-principal"></a>Kreiraj nov principal usluge

1. Instalirajte najnoviju verziju **Azure Active Directory PowerShell za Graph**. Za više informacija pogledajte [Instalirajte Azure Active Directory PowerShell za Graph](/powershell/azure/active-directory/install-adv2).
   - Na računaru izaberite Windows taster na tastaturi i potražite **Windows PowerShell** i **Pokreni kao administrator**.
   
   - U PowerShell prozoru koji se otvori unesite `Install-Module AzureAD`.

2. Napravite principal usluge za uvide u korisnike pomoću Azure AD PowerShell modula.
   - U PowerShell prozor unesite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Zamenite „svoj ID zakupca“ stvarnim ID-om vašeg zakupca tamo gde želite da napravite principal usluge. Parametar naziva okruženja `AzureEnvironmentName` je opcionalan.
  
   - Unesite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ova naredba kreira principal usluge za uvide o korisnicima na izabranom zakupcu.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Dodelite dozvole principalu usluge za pristup nalogu za skladištenje

Idite na Azure portal da biste dodelili dozvole principalu usluge za nalog za skladištenje koji želite da koristite u uvidima o korisnicima.

1. Idite na [Azure portal za administraciju](https://portal.azure.com) i prijavite se u svoju organizaciju.

1. Otvorite nalog za skladištenje kojem želite da principal usluge za uvide o korisnicima ima pristup.

1. Izaberite **Kontrola pristupa (IAM)** u oknu za navigaciju i izaberite **Dodaj** > **Dodajte dodelu uloga**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snimak ekrana koji prikazuje Azure portal tokom dodavanja uloga.":::
   
1. U oknu **Dodajte dodelu uloga** postavite sledeća svojstva:
   - Uloga: *Saradnik za podatke skladišta blob objekta*
   - Dodelite pristup: *Korisnik, grupa ili principal usluge*
   - Izaberite: *Dynamics 365 AI for Customer Insights* ([principal usluge koji ste kreirali](#create-a-new-service-principal))

1.  Izaberite stavku **Sačuvaj**.

Prenos promena može trajati do 15 minuta.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Unesite ID Azure resursa ili detalje o Azure pretplati u prilogu naloga za skladištenje u uvidima o korisnicima.

Priložite Azure Data Lake nalog za skladištenje u uvide o korisnicima radi [čuvanja izlaznih podataka](manage-environments.md) ili [ga koristite kao izvor podataka](connect-dataverse-managed-lake.md). Izbor opcije Azure Data Lake omogućava vam da odaberete između pristupa zasnovanog na resursima ili pretplati.

Sledite korake u nastavku da biste pružili potrebne informacije o odabranom pristupu.

### <a name="resource-based-storage-account-connection"></a>Povezivanje naloga za skladištenje zasnovano na resursima

1. Idite na [Azure portal za administraciju](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite nalog za skladištenje.

1. Idite u **Podešavanja** > **Svojstva** u oknu za navigaciju.

1. Kopirajte vrednost ID-a resursa naloga za skladištenje.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopirajte ID resursa naloga za skladištenje.":::

1. U uvidima o korisnicima umetnite ID resursa u polje resursa prikazano na ekranu za povezivanje sa nalogom za skladištenje.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Unesite informacije o ID-u resursa naloga za skladištenje.":::   
   
1. Nastavite sa preostalim koracima u uvidima o korisnicima da biste priložili nalog za skladištenje.

### <a name="subscription-based-storage-account-connection"></a>Povezivanje naloga za skladištenje zasnovanog na pretplatama

1. Idite na [Azure portal za administraciju](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite nalog za skladištenje.

1. Idite u **Podešavanja** > **Svojstva** u oknu za navigaciju.

1. Pregledajte **Pretplata**,**Grupa resursa** i **Ime** naloga za skladištenje kako biste bili sigurni da ste izabrali prave vrednosti u uvidima o korisnicima.

1. U uvidu o korisnicima odaberite vrednosti ili odgovarajuća polja prilikom prilaganja naloga za skladištenje.
   
1. Nastavite sa preostalim koracima u uvidima o korisnicima da biste priložili nalog za skladištenje.


[!INCLUDE[footer-include](../includes/footer-banner.md)]