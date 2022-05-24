---
title: Kreiranje okruženja i upravljanje njima
description: Saznajte kako se registrujete za uslugu i kako da upravljate okruženjima.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 599cbaf4e19c3a7331e92bfc54c701fefe6c69b3
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741058"
---
# <a name="manage-environments"></a>Upravljanje okruženjima

## <a name="switch-environments"></a>Zamena okruženja

Izaberite kontrolu **Okruženje** u gornjem desnom uglu stranice da biste promenili okruženje.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Snimak ekrana kontrole za promenu okruženja.":::

Administratori mogu da [kreiraju](create-environment.md) okruženja i upravljaju njima.

## <a name="edit-an-existing-environment"></a>Uređivanje postojećeg okruženja

Možete da izmenite neke detalje postojećih okruženja.

1.  Izaberite birač **Okruženje** u zaglavlju aplikacije.

2.  Izaberite ikonu **Uređivanje**.

3. U okviru **Uređivanje okruženja**, možete ažurirati podešavanja okruženja.

Više informacija o podešavanjima okruženja potražite u članku [Kreiranje novog okruženja](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Povezivanje sa sistemom Microsoft Dataverse
   
Korak **Microsoft Dataverse** vam omogućava da povežete Customer Insights sa vašim Dataverse okruženjem. 

Obezbedite sopstveno Microsoft Dataverse okruženje za deljenje podataka (profila i uvida) sa poslovnim aplikacijama zasnovanim Dataverse na sistemu, kao što je Dynamics 365 Marketing ili aplikacije sa modelima u programu Power Apps.

Da biste koristili [gotove modele predviđanja](predictions-overview.md#out-of-box-models), konfigurišite deljenje podataka sa uslugom Dataverse. Ili možete omogućiti unos podataka iz lokalnih izvora podataka,obezbeđujući URL adresu Microsoft Dataverse okruženja kojim upravlja vaša organizacija.

Omogućavanje deljenja podataka potvrđujući Microsoft Dataverse izbor u polju za potvrdu za deljenje podataka pokrenuće jednom potpuno osvežavanje izvora podataka i svih drugih procesa.

> [!IMPORTANT]
> 1. Uvidi klijenata i Dataverse moraju da budu u istom regionu da bi omogućili deljenje podataka.
> 1. Morate imati ulogu globalnog administratora u okruženju Dataverse. Proverite da [Dataverse li je ovo okruženje](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) povezano sa određenim bezbednosnim grupama i uverite se da ste dodati tim bezbednosnim grupama.
> 1. Postojeće okruženje "Uvidi kupaca" već nije povezano sa tim okruženjem Dataverse. Saznajte kako [da uklonite postojeću vezu sa okruženjem Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Opcije konfiguracije za omogućavanje deljenja podataka sa platformom Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Omogući deljenje podataka Dataverse sa sopstvenim Azure Data Lake Storage (Pregled)

Ako je vaše okruženje konfigurisano da koristi sopstveno za skladištenje podataka Azure Data Lake Storage "Uvid u korisnike", omogućavanje deljenja podataka sa potrebno je Microsoft Dataverse dodatnom konfiguracijom.

1. Kreirajte dve bezbednosne grupe na Azure pretplati - **jednu čitalac bezbednosnu** **grupu i saradnik bezbednosnu** grupu i podesite Microsoft Dataverse uslugu kao vlasnika za obe bezbednosne grupe.
2. Upravljajte listom kontrole pristupa (ACL) na kontejneru CustomerInsights u nalogu za skladištenje putem ovih bezbednosnih grupa. Dodajte uslugu Microsoft Dataverse i sve Dataverse poslovne aplikacije zasnovane na sistemu Dynamics 365 Marketing **u čitalac** grupu sa **dozvolama samo** za čitanje. Dodajte *samo* aplikaciju "Uvidi klijenata **" u saradnik grupu** da biste dodelili dozvole **za** čitanje i pisanje profila i uvida.
   
#### <a name="prerequisites"></a>Preduslovi

Da biste izvršili PowerShell skripte, potrebno je da uvezete sledeća tri modula. 

1. Instalirajte najnoviju verziju [Azure Active Directory programa PowerShell za Graph](/powershell/azure/active-directory/install-adv2).
   1. Na računaru izaberite taster Windows na tastaturi i potražite **Windows PowerShell** i izaberite **Pokreni kao administrator**.
   1. U PowerShell prozoru koji se otvori unesite `Install-Module AzureAD`.
2. Uvezi tri modula.
    1. U prozoru PowerShell unesite `Install-Module -Name Az.Accounts` i sledite korake. 
    1. Ponovite za `Install-Module -Name Az.Resources` i `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Koraci konfiguracije

1. Preuzmite dve PowerShell skripte koje treba da pokrenete sa [GitHub repoa našeg inženjera](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Potrebne su vam *administratorske dozvole* zakupca da biste pokrenuli ovu PowerShell skriptu. 
       - Ova PowerShell skripta kreira dve bezbednosne grupe na Azure pretplati. Jedan za čitalac grupu i drugi za saradnik grupu i učiniće Microsoft Dataverse uslugu kao vlasnik obe ove bezbednosne grupe.
       - Izvršite ovu PowerShell skriptu u programu Windows PowerShell tako što ćete obezbediti ID Azure pretplate koji sadrži vaš Azure Data Lake Storage. Otvorite PowerShell skriptu u uređivaču da biste pregledali dodatne informacije i primenjenu logiku.
       - Sačuvajte vrednosti ID-a obe bezbednosne grupe koje generiše ova skripta jer ćemo ih koristiti u skripti `ByolSetup.ps1`.
       
        > [!NOTE]
        > Kreiranje bezbednosne grupe može biti onemogućeno vašem stanaru. U tom slučaju, biće potrebno ručno podešavanje i administrator će Azure AD morati da omogući kreiranje [bezbednosnih grupa](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Potrebne su vam *dozvole vlasnika podataka za skladištenje* na nalogu/kontejneru za skladištenje da biste pokrenuli ovu skriptu ili će ova skripta kreirati jednu za vas. Dodeljivanje uloge može biti uklonjeno ručno nakon uspešnog pokretanja skripte.
        - Ova PowerShell skripta dodaje potrebnu kontrolu pristupa zasnovanu na tolima (RBAC) za Microsoft Dataverse uslugu i sve poslovne Dataverse aplikacije zasnovane na tome. Takođe ažurira Listu kontrole pristupa (ACL) na kontejneru CustomerInsights za bezbednosne grupe kreirane pomoću skripte `CreateSecurityGroups.ps1`. Grupa saradnik će imati rwx *dozvolu* i grupa čitalaca će imati samo *r-x* dozvolu.
        - Izvršite ovu PowerShell skriptu u programu Windows PowerShell tako što ćete obezbediti ID Azure Data Lake Storage Azure pretplate koji sadrži vaše ime naloga za skladištenje, ime grupe resursa i ID čitalac i saradnik bezbednosne grupe. Otvorite PowerShell skriptu u uređivaču da biste pregledali dodatne informacije i primenjenu logiku.
        - Kopirajte izlaznu nisku nakon uspešnog pokretanja skripte. Izlazna niska izgleda ovako: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Unesite izlaznu nisku kopiranu odozgo u **polje identifikatora** dozvola koraka konfiguracije okruženja za Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opcije konfiguracije da biste omogućili deljenje podataka iz sopstvenih sa Azure Data Lake Storage programom Microsoft Dataverse.":::

Customer Insights ne podržava sledeće scenarije deljenja podataka:
- Ako omogućite deljenje podataka sa uslugom Dataverse, nećete moći da [kreirate predviđene ili vrednosti koje nedostaju u entitetu](predictions.md).
- Ako omogućite deljenje podataka pomoću Dataverse, nećete moći da prikažete opcionalne PowerBI ugrađene izveštaje u okruženju "Uvidi kupaca".

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Uklanjanje postojeće veze sa okruženjem Dataverse

Kada se povezujete sa okruženjem Dataverse, poruka o grešci **Ova CDS organizacija je već priložena drugoj instanci uvida klijenata** znači Dataverse da se okruženje već koristi u okruženju "Uvidi kupaca". Postojeću vezu možete da uklonite kao globalni administrator u okruženju Dataverse. Može da potraje nekoliko sati da se promene nasele.

1. Idite na [Power Apps](https://make.powerapps.com).
1. Izaberite okruženje od birača okruženja.
1. Idi na **rešenja**
1. Deinstalirajte ili izbrišite rešenje pod imenom **Dynamics 365 Customer Insights "Programski dodatak kartice kupca " (pregled)**.

ILI 

1. Otvorite svoju Dataverse okolinu.
1. Idite na rešenja **za više opcija** > **za postavke**.
1. Deinstalirajte **CustomerInsightsCustomerCard** rešenje.

## <a name="copy-the-environment-configuration"></a>Kopiranje konfiguracije okruženja

Kao administrator, možete odabrati da kopirate konfiguraciju iz postojećeg okruženja kada kreirate novu. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Snimak ekrana opcija podešavanja u podešavanjima okruženja.":::

Videćete listu svih dostupnih okruženja u vašoj organizaciji, odakle možete kopirati podatke.

Kopiraju se sledeća podešavanja konfiguracije:

- Uneseni/uvezeni izvori podataka
- Konfiguracija ujedinjenja podataka
- Segmenti
- Mere
- Relacije
- Aktivnosti
- Indeks pretrage i filtriranja
- Odredišta za izvoz
- Planirano osvežavanje
- Obogaćivanja
- Upravljanje modelima
- Dodela uloga

## <a name="set-up-a-copied-environment"></a>Podešavanje kopirane sredine

Kada kopirate konfiguraciju okruženja, sledeći podaci se *ne* kopiraju:

- Profili klijenata.
- Akreditivi izvora podataka. Moraćete da dostavite akreditive za svaki izvor podataka i ručno osvežite izvore podataka.
- Izvori podataka iz Common Data Model fascikle i Dataverse upravljanog jezera podataka. Te izvore podataka ćete morati da kreirate ručno, s istim nazivom kao u izvornom okruženju.
- Tajne veze koje se koriste za izvoz i obogaćivanje. Morate ponovo da uspostavite vezu i da ponovo aktivirate obogaćivanje i izvoz. 

Kada kopirate okruženje, videćete poruku potvrde da je kreirano novo okruženje. Izaberite **Idite na izvore podataka** da biste videli listu izvora podataka.

Svi izvori podataka će pokazati status **Potrebni su akreditivi**. Uredite izvore podataka i unesite akreditive da biste ih osvežili.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista izvora podataka koji su kopirani i kojima je potrebna potvrda identiteta.":::

Nakon osvežavanja izvora podataka, idite na **Podaci** > **Objedini**. Ovde ćete pronaći podešavanja iz izvornog okruženja. Uredite ih po potrebi ili izaberite **Pokreni** da biste pokrenuli proces objedinjavanja podataka i kreirali objedinjeni entitet klijenta.

Kada objedinjavanje podataka bude dovršeno, idite na **Mere** i **Segmenti** da osvežite i njih.

Pre nego što ponovo aktivirate izvoz i obogaćivanje, **idite na lokaciju "Administrativne** > **veze**" da biste ponovo uvideli veze u novom okruženju.

## <a name="change-the-owner-of-an-environment"></a>Promena vlasnika okruženja

Dok nekoliko korisnika može da ima administratorske dozvole u programu Customer Insights, samo jedan korisnik je vlasnik okruženja. Po podrazumevanoj vrednosti, administrator je taj koji u početku kreira okruženje. Kao administrator okruženja, možete da dodelite vlasništvo drugom korisniku sa administratorske dozvole.

1. Izaberite birač **Okruženje** u zaglavlju aplikacije.

1. Izaberite ikonu **Uređivanje**.

1. U okviru **Uredi okruženje** pređite na osnovni **informacioni** korak.

1. U polju **Promeni vlasnika okruženja** odaberite novog vlasnika okruženja.  

1. Izaberite rediguj **i završi**, a zatim **ažuriraj** da biste primenili promene. 

## <a name="claim-ownership-of-an-environment"></a>Tražite vlasništvo nad okruženjem

Ako vlasnik okruženja napusti organizaciju ili je njihov korisnički nalog izbrisan, okruženje neće imati vlasnika. Korisnik sa administratorske dozvole može da preuzme vlasništvo i postane novi vlasnik. Oni mogu da nastave da poseduju životnu sredinu [ili da promene vlasništvo u drugog administratora](#change-the-owner-of-an-environment). 

Da biste preuzeli vlasništvo, izaberite dugme **"Preuzmi vlasništvo** " koje se prikazuje na vrhu svake stranice u "Uvidima kupaca" kada je originalni vlasnik napustio organizaciju.

## <a name="reset-an-existing-environment"></a>Uspostavljanje početnih vrednosti postojećeg okruženja

Kao vlasnik okruženja, možete da uspostavite početne vrednosti okruženja na prazno stanje ako želite da izbrišete sve konfiguracije i uklonite unete podatke.

1.  Izaberite birač **Okruženje** u zaglavlju aplikacije. 

2.  Izaberite okruženje koje želite da resetujete i izaberite tri tačke (**...**). 

3. Izaberite opciju **Resetuj**. 

4.  Da biste potvrdili brisanje, unesite ime okruženja i izaberite **Resetuj**.

## <a name="delete-an-existing-environment"></a>Brisanje postojećeg okruženja

Kao vlasnik okruženja, možete da izbrišete okruženje kojim upravljate.

1.  Izaberite birač **Okruženje** u zaglavlju aplikacije.

2.  Izaberite okruženje koje želite da resetujete i izaberite tri tačke (**...**). 

3. Odaberite opciju **Izbriši**. 

4.  Da biste potvrdili brisanje, unesite naziv okruženja i izaberite **Izbriši**.

> [!NOTE]
> Brisanje okruženja ne uklanja povezivanje sa okruženjem Dataverse. Saznajte kako [da uklonite postojeću vezu sa okruženjem Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE [footer-include](includes/footer-banner.md)]
