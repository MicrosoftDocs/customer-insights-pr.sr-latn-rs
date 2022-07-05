---
title: 'Kako da: Kreiranje nove sredine'
description: Koraci za kreiranje okruženja u Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 62969527ceed906ff06fb9be90b972496323ce0a
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052763"
---
# <a name="how-to-create-a-new-environment"></a>Kako da: Kreiranje nove sredine

Nakon [kupovine licence za pretplatu Dynamics 365 Customer Insights](paid-license.md), globalni administrator zakupca Microsoft 365 dobija e-poruku koja ih poziva da kreiraju okruženje. Idite na [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) da biste započeli. U ovom scenariju, možete da idete direktno na [Korak 1: Obezbedite osnovne informacije](#step-1-provide-basic-information).

Nakon kreiranja prvog okruženja, globalni administrator zakupca može da doda Microsoft 365 korisnicima [da formiraju svoju organizaciju kao administratori](permissions.md). Ako se krećete napred, ovi administratori mogu da upravljaju korisnicima i okruženjima. Ukoliko vaša organizacija kupi više licenci za korisničke uvide, obratite [se našem timu za](https://go.microsoft.com/fwlink/?linkid=2079641) podršku da biste povećali broj raspoloživih okruženja. Za više informacija o kapacitetu i kapacitetu dodatka pregledajte Dynamics [365 vodič za licenciranje](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Ako želite da isprobate uslugu, pogledajte [Konfigurisanje probnog okruženja](trial-signup.md).

## <a name="prerequisites"></a>Preduslovi

Potrebne su vam [administratorske dozvole u](permissions.md) fascikli "Uvidi klijenata" da biste kreirali ili upravljali okruženjima.

## <a name="start-the-environment-creation-process"></a>Započnite proces kreiranja okruženja

1. Otvorite birač okruženja i izaberite **+ Novo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Izaberite birač okruženja.":::

1. Pratite vođeno iskustvo navedeno u sledećim odeljcima da biste obezbedili sve potrebne informacije za novo okruženje. Ako ste ranije konfigurisali okruženje, možete i da kopirate [konfiguraciju](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>1. korak: Pružanje osnovnih informacija

U koraku **Osnovne informacije**, odaberite da li želite da kreirate okruženje od nule ili da [kopirate podatke iz drugog okruženja](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dijalog za kreiranje novog Customer Insights okruženja.":::

Navedite sledeće detalje:

- **Naziv**: Unesite naziv ovog okruženja. Ovo polje je već popunjeno ako ste kopirali postojeće okruženje, ali možete ga promeniti.
- **Odaberite svoje poslovanje**: Odaberite primarnu ciljnu grupu za novo okruženje. Možete da radite sa pojedinačnim potrošačima (B-to-C) ili [poslovnim kontaktima](work-with-business-accounts.md) (B-to-B). Ako vaša organizacija uglavnom posluje sa pojedincima, kao što su prodavac ili kafić, odaberite pojedinačne potrošače. U slučaju da su korisnici kompanije, kao što su proizvođač automobila ili preduzeće za papir, odaberite poslovne naloge.
- **Tip**: izaberite da li želite da kreirate proizvodno ili Sandbox okruženje. Sandbox okruženja ne dozvoljavaju zakazano osvežavanje podataka i namenjena su za predimplementaciju i testiranje. Sandbox okruženja koriste istu primarnu ciljnu grupu kao i trenutno izabrano proizvodno okruženje.
- **Region**: Region u kojem je usluga primenjena i hostovana. Da [biste koristili sopstveni Azure Data Lake Storage nalog](own-data-lake-storage.md) ili se [povezali sa postojećom Microsoft Dataverse organizacijom](customer-insights-dataverse.md), okruženje "Uvidi kupaca" mora biti u istom regionu.

## <a name="step-2-configure-data-storage"></a>2. korak: Konfigurišite skladište podataka

U koraku **skladištenja podataka** odaberite gde želite da uskladištite podatke "Uvidi kupaca".

Postoje dve opcije koje možete odabrati:

- **Skladište uvida kupaca**: Skladištem podataka upravlja tim uvida kupaca. To je podrazumevana opcija i ukoliko ne postoje određeni zahtevi za skladištenje podataka u sopstvenom nalogu za skladištenje, preporučujemo da koristite ovu opciju.
- **Azure Data Lake Storage**: Navedite sopstveni nalog Azure Data Lake Storage za skladištenje podataka tako da imate potpunu kontrolu gde su podaci uskladišteni. Više informacija potražite u članku [Korišćenje sopstvenog naloga Azure Data Lake Storage](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Odaberite željenu opciju za skladištenje podataka.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>3. korak: Povezivanje sa sistemom Microsoft Dataverse

Korak **Microsoft Dataverse** vam omogućava da povežete Customer Insights sa vašim Dataverse okruženjem. Delite podatke sa Dataverse njima da biste ih koristili sa poslovnim aplikacijama Dataverse zasnovanim na sistemu, kao što je Dynamics 365 Marketing ili aplikacije sa modelima u programu Power Apps.


Ostavite ovo polje prazno ako nemate svoje okruženje i Dataverse mi ćemo vam ga kreirati.

Više informacija potražite u članku Rad [sa podacima o uvidima klijenata u .Microsoft Dataverse](customer-insights-dataverse.md)

:::image type="content" source="media/dataverse-provisioning.png" alt-text="deljenje podataka Microsoft Dataverse sa automatski omogućenim za neto nova okruženja.":::

### <a name="step-4-finalize-the-settings"></a>4. korak: Dovršavanje podešavanja

U **koraku** "Redigovanje" pregledajte sve navedene postavke. Kada sve izgleda završeno, izaberite **Kreiraj** da biste konfigurisali okruženje.

Neke od postavki možete promeniti kasnije. Više informacija potražite u članku [Upravljanje okruženjem](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Rad sa novim okruženjem

Pregledajte sledeće članke koji će vam pomoći da započnete sa konfigurisanjem usluge Customer Insights:

- [Dodajte još korisnika i dodelite dozvole](permissions.md).
- [Unesite svoje izvore podataka](data-sources.md) i provucite ih kroz [proces objedinjavanja podataka](data-unification.md) kako biste dobili [objedinjene profile klijenata](customer-profiles.md).
- [Obogatite objedinjene profile klijenata](enrichment-hub.md) ili [pokrenite modele predviđanja](predictions-overview.md).
- [Kreirajte segmente](segments.md) da biste grupisali klijente i [mere](measures.md) za pregled KPI pokazatelja.
- [Podesite veze](connections.md) i [izvoze](export-destinations.md) za obradu podskupova podataka u drugim aplikacijama.

## <a name="copy-the-environment-configuration"></a>Kopiranje konfiguracije okruženja

Kao administrator, možete odabrati da kopirate konfiguraciju iz postojećeg okruženja kada kreirate novu.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Snimak ekrana opcija podešavanja u podešavanjima okruženja.":::

Videćete listu svih dostupnih okruženja u vašoj organizaciji, odakle možete kopirati podatke.

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

## <a name="set-up-a-copied-environment"></a>Podešavanje kopirane sredine

Kada kopirate konfiguraciju okruženja, morate da prođete kroz neke dodatne korake da biste potvrdili akreditive:

- Profili klijenata. Prvo potvrdite verodostojnost i unesite izvore podataka i pokrenite ujedinjenje podataka da biste ponovo napravili identitete klijenata.
- Akreditivi izvora podataka. Morate da obezbedite akreditive za svaku izvor podataka biste ručno potvrdili verodostojnost i osvežili izvore podataka.
- Izvori podataka iz fascikle "Uobičajeni model podataka" i Dataverse. Te izvore podataka morate da kreirate ručno sa istim imenom kao u izvornom okruženju.
- Tajne veze koje se koriste za izvoz i obogaćivanje. Morate ponovo da uspostavite vezu i da ponovo aktivirate obogaćivanje i izvoz.

Videćete poruku potvrde kada se kreira kopirano okruženje. Izaberite **Idite na izvore podataka** da biste videli listu izvora podataka.

Svi izvori podataka će pokazati status **Potrebni su akreditivi**. Uredite izvore podataka i unesite akreditive da biste ih osvežili.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista izvora podataka koji su kopirani i kojima je potrebna potvrda identiteta.":::

Nakon osvežavanja izvora podataka, idite na **Podaci** > **Objedini**. Ovde ćete pronaći podešavanja iz izvornog okruženja. Uredite ih po potrebi ili izaberite **Pokreni** da biste pokrenuli proces objedinjavanja podataka i kreirali objedinjeni entitet klijenta.

Kada objedinjavanje podataka bude dovršeno, idite na **Mere** i **Segmenti** da osvežite i njih.

Pre nego što ponovo aktivirate izvoz i obogaćivanje, **idite na lokaciju "Administrativne** > **veze**" da biste ponovo uvideli veze u novom okruženju.

[!INCLUDE [footer-include](includes/footer-banner.md)]
