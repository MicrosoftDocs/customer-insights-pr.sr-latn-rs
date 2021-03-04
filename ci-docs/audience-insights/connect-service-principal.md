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
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267739"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="bfe5a-103">Povežite se sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge za uvide u ciljnu grupu</span><span class="sxs-lookup"><span data-stu-id="bfe5a-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="bfe5a-104">Automatizovani alati koji koriste Azure usluge uvek bi trebalo da imaju ograničene dozvole.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="bfe5a-105">Umesto da se aplikacije prijavljuju kao potpuno privilegovani korisnik, Azure nudi principale usluga.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="bfe5a-106">Čitajte dalje da biste saznali kako da povežete uvide u korisnike sa Azure Data Lake Storage Gen2 nalogom koji koristi Azure principal usluge umesto ključeva naloga za skladištenje.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="bfe5a-107">Principal usluge možete koristiti za sigurno [dodavanje ili uređivanje Common Data Model fascikle kao izvora podataka](connect-common-data-model.md) ili [kreirajte novo ili ažurirajte postojeće okruženje](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="bfe5a-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="bfe5a-108">Azure Data Lake Gen2 nalog za skladištenje koji namerava da koristi principala usluge mora da ima [omogućenu funkciju hijerarhijskog prostora imena (HNS)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="bfe5a-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="bfe5a-109">Potrebne su vam administratorske dozvole za Azure pretplatu da biste kreirali principal usluge.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="bfe5a-110">Napravite principal Azure usluge za uvide u korisnike</span><span class="sxs-lookup"><span data-stu-id="bfe5a-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="bfe5a-111">Pre nego što napravite nov principal usluge za uvide u korisnike, proverite da li već postoji u vašoj organizaciji.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="bfe5a-112">Potražite postojeći principal usluge</span><span class="sxs-lookup"><span data-stu-id="bfe5a-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="bfe5a-113">Idite na [Azure portal za administraciju](https://portal.azure.com) i prijavite se u svoju organizaciju.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="bfe5a-114">Izaberite **Azure Active Directory** iz Azure usluga.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="bfe5a-115">U odeljku **Upravljanje**, izaberite **Poslovne aplikacije**.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="bfe5a-116">Potražite ID direktne aplikacije uvida u korisnike `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ili ime `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="bfe5a-117">Ako pronađete odgovarajući zapis, to znači da postoji principal usluge za uvide u korisnike.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="bfe5a-118">Ne morate da ga ponovo kreirate.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snimak ekrana koji prikazuje postojeći principal usluge.":::
   
6. <span data-ttu-id="bfe5a-120">Ako se ne prikažu rezultati, kreirajte nov principal usluge.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="bfe5a-121">Kreiraj nov principal usluge</span><span class="sxs-lookup"><span data-stu-id="bfe5a-121">Create a new service principal</span></span>

1. <span data-ttu-id="bfe5a-122">Instalirajte najnoviju verziju **Azure Active Directory PowerShell za Graph**.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="bfe5a-123">Za više informacija pogledajte [Instalirajte Azure Active Directory PowerShell za Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="bfe5a-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="bfe5a-124">Na računaru izaberite Windows taster na tastaturi i potražite **Windows PowerShell** i **Pokreni kao administrator**.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="bfe5a-125">U PowerShell prozoru koji se otvori unesite `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="bfe5a-126">Napravite principal usluge za uvide u korisnike pomoću Azure AD PowerShell modula.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="bfe5a-127">U PowerShell prozor unesite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="bfe5a-128">Zamenite „svoj ID zakupca“ stvarnim ID-om vašeg zakupca tamo gde želite da napravite principal usluge.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="bfe5a-129">Parametar naziva okruženja `AzureEnvironmentName` je opcionalan.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="bfe5a-130">Unesite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="bfe5a-131">Ova naredba kreira principal usluge za uvide o korisnicima na izabranom zakupcu.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="bfe5a-132">Dodelite dozvole principalu usluge za pristup nalogu za skladištenje</span><span class="sxs-lookup"><span data-stu-id="bfe5a-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="bfe5a-133">Idite na Azure portal da biste dodelili dozvole principalu usluge za nalog za skladištenje koji želite da koristite u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="bfe5a-134">Idite na [Azure portal za administraciju](https://portal.azure.com) i prijavite se u svoju organizaciju.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="bfe5a-135">Otvorite nalog za skladištenje kojem želite da principal usluge za uvide o korisnicima ima pristup.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="bfe5a-136">Izaberite **Kontrola pristupa (IAM)** u oknu za navigaciju i izaberite **Dodaj** > **Dodajte dodelu uloga**.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snimak ekrana koji prikazuje Azure portal tokom dodavanja uloga.":::
   
1. <span data-ttu-id="bfe5a-138">U oknu **Dodajte dodelu uloga** postavite sledeća svojstva:</span><span class="sxs-lookup"><span data-stu-id="bfe5a-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="bfe5a-139">Uloga: *Saradnik za podatke skladišta blob objekta*</span><span class="sxs-lookup"><span data-stu-id="bfe5a-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="bfe5a-140">Dodelite pristup: *Korisnik, grupa ili principal usluge*</span><span class="sxs-lookup"><span data-stu-id="bfe5a-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="bfe5a-141">Izaberite: *Dynamics 365 AI for Customer Insights* ([principal usluge koji ste kreirali](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="bfe5a-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="bfe5a-142">Izaberite stavku **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-142">Select **Save**.</span></span>

<span data-ttu-id="bfe5a-143">Prenos promena može trajati do 15 minuta.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="bfe5a-144">Unesite ID Azure resursa ili detalje o Azure pretplati u prilogu naloga za skladištenje u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="bfe5a-145">Priložite Azure Data Lake nalog za skladištenje u uvide o korisnicima radi [čuvanja izlaznih podataka](manage-environments.md) ili [ga koristite kao izvor podataka](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="bfe5a-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="bfe5a-146">Izbor opcije Azure Data Lake omogućava vam da odaberete između pristupa zasnovanog na resursima ili pretplati.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="bfe5a-147">Sledite korake u nastavku da biste pružili potrebne informacije o odabranom pristupu.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="bfe5a-148">Povezivanje naloga za skladištenje zasnovano na resursima</span><span class="sxs-lookup"><span data-stu-id="bfe5a-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="bfe5a-149">Idite na [Azure portal za administraciju](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite nalog za skladištenje.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="bfe5a-150">Idite u **Podešavanja** > **Svojstva** u oknu za navigaciju.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="bfe5a-151">Kopirajte vrednost ID-a resursa naloga za skladištenje.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopirajte ID resursa naloga za skladištenje.":::

1. <span data-ttu-id="bfe5a-153">U uvidima o korisnicima umetnite ID resursa u polje resursa prikazano na ekranu za povezivanje sa nalogom za skladištenje.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Unesite informacije o ID-u resursa naloga za skladištenje.":::   
   
1. <span data-ttu-id="bfe5a-155">Nastavite sa preostalim koracima u uvidima o korisnicima da biste priložili nalog za skladištenje.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="bfe5a-156">Povezivanje naloga za skladištenje zasnovanog na pretplatama</span><span class="sxs-lookup"><span data-stu-id="bfe5a-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="bfe5a-157">Idite na [Azure portal za administraciju](https://portal.azure.com), prijavite se na svoju pretplatu i otvorite nalog za skladištenje.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="bfe5a-158">Idite u **Podešavanja** > **Svojstva** u oknu za navigaciju.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="bfe5a-159">Pregledajte **Pretplata**,**Grupa resursa** i **Ime** naloga za skladištenje kako biste bili sigurni da ste izabrali prave vrednosti u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="bfe5a-160">U uvidu o korisnicima odaberite vrednosti ili odgovarajuća polja prilikom prilaganja naloga za skladištenje.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="bfe5a-161">Nastavite sa preostalim koracima u uvidima o korisnicima da biste priložili nalog za skladištenje.</span><span class="sxs-lookup"><span data-stu-id="bfe5a-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]