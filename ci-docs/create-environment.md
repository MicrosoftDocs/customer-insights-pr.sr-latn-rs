---
title: Kreirajte novo okruženje
description: Koraci za kreiranje okruženja u Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304261"
---
# <a name="create-a-new-environment"></a>Kreirajte novo okruženje

Nakon [kupovine licence za pretplatu Dynamics 365 Customer Insights](paid-license.md), globalni administrator zakupca Microsoft 365 dobija e-poruku koja ih poziva da kreiraju okruženje. Idite na [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) da biste započeli. U ovom scenariju, počnite sa [Korakom 1: Obezbedite osnovne informacije](#step-1-provide-basic-information).

Nakon kreiranja prvog okruženja, globalni administrator zakupca može Microsoft 365 da doda [korisnike iz svoje organizacije kao administratore](permissions.md). Ovi administratori zatim mogu da upravljaju korisnicima i okruženjima. Ukoliko vaša organizacija kupi više licenci za korisničke uvide, obratite [se našem timu za](https://go.microsoft.com/fwlink/?linkid=2079641) podršku da biste povećali broj raspoloživih okruženja. Za više informacija o kapacitetu i kapacitetu dodatka pregledajte Dynamics [365 vodič za licenciranje](https://go.microsoft.com/fwlink/?LinkId=866544). Kada budete imali mogućnost da kreirate dodatna okruženja, idite na početni [proces kreiranja okruženja](#start-the-environment-creation-process).

> [!TIP]
> Ako želite da isprobate uslugu, pogledajte [Konfigurisanje probnog okruženja](trial-signup.md).

## <a name="prerequisites"></a>Preduslovi

[Administratorske dozvole u](permissions.md) uvidima klijenata

## <a name="start-the-environment-creation-process"></a>Započnite proces kreiranja okruženja

1. Otvorite birač okruženja i izaberite **+ Novo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Izaberite birač okruženja.":::

1. Pratite vođeno iskustvo navedeno u sledećim odeljcima da biste obezbedili sve potrebne informacije za novo okruženje.

## <a name="step-1-provide-basic-information"></a>1. korak: Pružanje osnovnih informacija

1. Odaberite da li želite da kreirate okruženje od početka ili da kopirate podatke iz drugog okruženja. [Kopiranje podataka iz drugog okruženja zahteva](#copy-the-environment-configuration) dodatne korake.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dijalog za kreiranje novog Customer Insights okruženja.":::

1. Navedite sledeće detalje:

   - **Naziv**: Ime za ovo okruženje. Ovo polje je već popunjeno ako ste kopirali postojeće okruženje, ali možete ga promeniti.
   - **Odaberite svoje poslovanje**: primarni korisnici za novu sredinu: pojedinačni potrošači (B-na-C) ili poslovni [nalozi](work-with-business-accounts.md) (od B do B). Ako vaša organizacija uglavnom posluje sa pojedincima, kao što su prodavac ili kafić, odaberite pojedinačne potrošače. Ako su korisnici preduzeća, kao što su proizvođač automobila ili preduzeće za papir, odaberite poslovne naloge.
   - **Tip**: Vrsta okruženja: proizvodnja ili peščana kutija. Sandbox okruženja ne dozvoljavaju zakazano osvežavanje podataka i namenjena su za predimplementaciju i testiranje. Sandbox okruženja koriste istu primarnu ciljnu grupu kao i trenutno izabrano proizvodno okruženje.
   - **Region**: Region u koji je usluga raspoređena i hostovana. Da [biste koristili sopstveni Azure Data Lake Storage nalog](own-data-lake-storage.md) ili se [povezali sa postojećom Microsoft Dataverse organizacijom](customer-insights-dataverse.md), okruženje "Uvidi kupaca" mora biti u istom regionu.

1. Izaberite **Sledeće**.

## <a name="step-2-configure-data-storage"></a>2. korak: Konfigurišite skladište podataka

1. Odaberite gde želite da uskladištite podatke o uvidima kupaca:

   - **Skladište uvida klijenata**: automatski se upravlja skladištem podataka. To je podrazumevana opcija i ukoliko ne postoje određeni zahtevi za skladištenje podataka u sopstvenom nalogu za skladištenje, preporučujemo da koristite ovu opciju.
   - **Azure Data Lake Storage**: Sopstveni nalog za Azure Data Lake Storage skladištenje podataka tako da imate potpunu kontrolu gde su podaci uskladišteni. Sledite korake u korišćenju [sopstvenog Azure Data Lake Storage naloga](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Odaberite željenu opciju za skladištenje podataka.":::

1. Izaberite **Sledeće**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>3. korak: Povezivanje sa sistemom Microsoft Dataverse

Ako imate okruženje Dataverse, povežite korisničke uvide. Delite podatke sa Dataverse njima da biste ih koristili sa poslovnim aplikacijama Dataverse zasnovanim na sistemu, kao što je Dynamics 365 Marketing ili aplikacije sa modelima u programu Power Apps.

1. Sledite korake u radu [sa podacima "Uvid klijenta" u programu Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="deljenje podataka Microsoft Dataverse sa automatski omogućenim za neto nova okruženja.":::

1. Izaberite **Sledeće**.

## <a name="step-4-finalize-the-settings"></a>4. korak: Dovršavanje podešavanja

Pregledajte navedene postavke. Kada sve izgleda završeno, izaberite **Kreiraj** da biste konfigurisali okruženje.

Da biste kasnije promenili neke od postavki, pogledajte članak [Upravljanje okruženjima](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Rad sa novim okruženjem

Pregledajte sledeće članke koji će vam pomoći da započnete sa konfigurisanjem usluge Customer Insights:

- [Dodajte još korisnika i dodelite dozvole](permissions.md).
- [Unesite svoje izvore podataka](data-sources.md) i provucite ih kroz [proces objedinjavanja podataka](data-unification.md) kako biste dobili [objedinjene profile klijenata](customer-profiles.md).
- [Obogatite objedinjene profile klijenata](enrichment-hub.md) ili [pokrenite modele predviđanja](predictions-overview.md).
- [Kreirajte segmente](segments.md) da biste grupisali klijente i [mere](measures.md) za pregled KPI pokazatelja.
- [Podesite veze](connections.md) i [izvoze](export-destinations.md) za obradu podskupova podataka u drugim aplikacijama.

## <a name="copy-the-environment-configuration"></a>Kopiranje konfiguracije okruženja

Ako ste kao administrator odabrali da kopirate konfiguraciju iz postojećeg okruženja, izaberite sa liste svih dostupnih okruženja u vašoj organizaciji.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Snimak ekrana opcija podešavanja u podešavanjima okruženja.":::

Kopiraju se sledeća podešavanja konfiguracije:

- Izvori podataka uvezeni putem Power Query
- Konfiguracija ujedinjenja podataka
- Segmenti
- Mere
- Relacije
- Aktivnosti
- Indeks pretrage i filtriranja
- Izvozi
- Raspored osvežavanja
- Obogaćivanja
- Predviđanje modeli
- Dodela uloga

### <a name="set-up-a-copied-environment"></a>Podešavanje kopirane sredine

Kada kopirate konfiguraciju okruženja, poruka potvrde se prikazuje kada se kreira kopirano okruženje. Izvršite sledeće korake da biste potvrdili akreditive.

1. Izaberite **Idite na izvore podataka** da biste videli listu izvora podataka. Svi izvori podataka prikazuju status **"Potrebni akreditivi** ".

   :::image type="content" source="media/data-sources-copied.png" alt-text="Lista izvora podataka koji su kopirani i kojima je potrebna potvrda identiteta.":::

1. Uredite izvore podataka i unesite akreditive da biste ih osvežili. Izvori podataka iz fascikle "Uobičajeni model podataka" Dataverse i moraju biti kreirani ručno sa istim imenom kao u izvornom okruženju.

1. Nakon osvežavanja izvora podataka, idite na **Podaci** > **Objedini**. Ovde ćete pronaći podešavanja iz izvornog okruženja. Uredite ih po potrebi ili izaberite **Ujedinite** > **objedinite profile i zavisnosti klijenata** da biste započeli proces ujedinjenja podataka i kreirali objedinjeni entitet klijenta.

   > [!TIP]
   > Za naloge i kontakte izaberite **opciju Ujedini naloge** > **Ujedini profile i zavisnosti**.

1. Kada se ujedinjenje podataka dovrši, idite na mere i **segmente** da **biste** ih osvežili.

1. Idite **na administrativne** > **veze** da biste ponovo ukažuli na veze u novom okruženju.

1. Idite na **obogaćenje** > **podataka** i **izvoz** > **podataka da** biste ih ponovo aktivirali.

[!INCLUDE [footer-include](includes/footer-banner.md)]
