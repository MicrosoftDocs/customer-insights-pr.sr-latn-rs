---
title: Kreiranje okruženja u usluzi Customer Insights
description: Koraci za kreiranje okruženja sa licenciranom pretplatom za Dynamics 365 Customer Insights.
ms.date: 04/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0efda9d2997bcfd069b6d2445b69d159d7d3e59b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643101"
---
# <a name="create-an-environment-in-customer-insights"></a>Kreiranje okruženja u uvidima klijenata

Ovaj članak objašnjava kako da kreirate novo okruženje nakon što je vaša organizacija kupila Dynamics 365 Customer Insights pretplatu. 

Organizacije mogu da kreiraju više okruženja za svaku licencu "Uvid u kupce". Ako vaša organizacija kupi više licenci, [kontaktirajte naš tim za podršku](https://go.microsoft.com/fwlink/?linkid=2079641) da bi povećali broj dostupnih okruženja. Za više informacija o kapacitetu i kapacitetu dodatka pregledajte Dynamics [365 vodič za licenciranje](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Ako želite da isprobate uslugu, pogledajte [Konfigurisanje probnog okruženja](trial-signup.md).

## <a name="create-a-new-environment"></a>Kreirajte novo okruženje

Nakon kupovine licence za pretplatu za Customer Insights, globalni administrator zakupca Microsoft 365 dobija e-poruku koja ih poziva da kreiraju okruženje. Idite na [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) da biste započeli. 

Vođeno iskustvo vam pomaže kroz korake prikupljanja svih potrebnih informacija za novo okruženje. Potrebne su vam [administratorske dozvole u](permissions.md) fascikli "Uvidi klijenata" da biste kreirali ili upravljali okruženjima.

1. Otvorite birač okruženja i izaberite **+ Novo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Izaberite birač okruženja.":::

1. Pratite vođeno iskustvo opisano u sledećim odeljcima.

### <a name="step-1-provide-environment-information"></a>1. korak: Pružite informacije o okruženju

U koraku **Osnovne informacije**, odaberite da li želite da kreirate okruženje od nule ili da [kopirate podatke iz drugog okruženja](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dijalog za kreiranje novog Customer Insights okruženja.":::

Navedite sledeće detalje:
   - **Naziv**: Unesite naziv ovog okruženja. Ovo polje je već popunjeno ako ste kopirali postojeće okruženje, ali možete ga promeniti.
   - **Odaberite svoje poslovanje**: Odaberite primarnu ciljnu grupu za novo okruženje. Možete da radite sa pojedinačnim potrošačima (B-to-C) ili [poslovnim kontaktima](work-with-business-accounts.md) (B-to-B).
   - **Tip**: izaberite da li želite da kreirate proizvodno ili Sandbox okruženje. Sandbox okruženja ne dozvoljavaju zakazano osvežavanje podataka i namenjena su za predimplementaciju i testiranje. Sandbox okruženja koriste istu primarnu ciljnu grupu kao i trenutno izabrano proizvodno okruženje.
   - **Region**: Region u kojem je usluga primenjena i hostovana.

### <a name="step-2-configure-data-storage"></a>2. korak: Konfigurišite skladište podataka

U koraku **skladištenja podataka** odaberite gde želite da uskladištite podatke "Uvidi kupaca".

Imaćete dve mogućnosti: **Customer Insights skladište** (Azure jezero podataka kojim upravlja Customer Insights tim) i **Azure Data Lake Storage** (vaš sopstveni Azure Data Lake Storage). Podrazumevano je odabrana opcija Customer Insights skladišta.

:::image type="content" source="media/data-storage-environment.png" alt-text="Odaberite podatke Azure Data Lake Storage za skladištenje podataka.":::

Čuvanjem podataka u usluzi Azure Data Lake Storage, slažete se da će se podaci prenositi i skladištiti na odgovarajućoj geografskoj lokaciji za taj Azure nalog za skladištenje. Ova lokacija se može razlikovati od mesta na kome se čuvaju podaci iz usluge Dynamics 365 Customer Insights. Saznajte više u [Microsoft centru za pouzdanost](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights trenutno podržava sledeće:
> - Uneti entiteti iz Power BI tokova podataka koji se čuvaju u Microsoft Dataverse upravljanoj usluzi Data Lake.  
> - Azure Data Lake Storage nalozi iz istog Azure regiona koji ste izabrali prilikom kreiranja okruženja.
> - Azure Data Lake Storage naloge koji su Gen2 i imaju *omogućen hijerarhijski prostor za* ime. Azure Data Lake Gen1 nalozi za skladištenje nisu podržani.

Za opciju Azure Data Lake Storage, možete odabrati između opcije zasnovane na resursima i opcije zasnovane na pretplati za potvrdu identiteta. Više informacija potražite u članku [Povezivanje sa Azure Data Lake Storage nalogom koristeći Azure principal usluge](connect-service-principal.md). Imenovani kontejner `customerinsights` mora da postoji na nalogu za skladištenje.

Kada su sistemski procesi poput unosa podataka, završeni, sistem kreira odgovarajuće fascikle na nalogu za skladištenje koji ste naveli. Datoteke sa podacima i *model.json* datoteke se kreiraju i dodaju u fascikle na osnovu naziva procesa.

Ako kreirate više okruženja usluge Customer Insights i odaberete da sačuvate izlazne entitete iz tih okruženja na svoj nalog za skladištenje, Customer Insights kreira zasebne fascikle za svako okruženje sa `ci_environmentID` u kontejneru.

### <a name="step-3-connect-to-microsoft-dataverse"></a>3. korak: Povezivanje sa sistemom Microsoft Dataverse
   
Korak **Microsoft Dataverse** vam omogućava da povežete Customer Insights sa vašim Dataverse okruženjem.

Obezbedite sopstveno Microsoft Dataverse okruženje za deljenje podataka (profila i uvida) sa poslovnim aplikacijama zasnovanim Dataverse na sistemu, kao što je Dynamics 365 Marketing ili aplikacije sa modelima u programu Power Apps. Ostavite ovo polje prazno ako nemate svoje okruženje, a Dataverse mi ćemo vam ga obezbediti.

Povezivanje sa okruženjem Dataverse vam takođe omogućava da unosite [podatke iz lokalni podataka pomoću Power Platform priliva podataka i mrežnih prolaza](data-sources.md#add-data-from-on-premises-data-sources). Takođe možete da [koristite modele za predviđanje tako što ćete](predictions-overview.md?tabs=b2c#out-of-box-models) se povezati sa okruženjem Dataverse.

> [!IMPORTANT]
> 1. Uvidi klijenata i Dataverse moraju da budu u istom regionu da bi omogućili deljenje podataka.
> 1. Morate imati ulogu globalnog administratora u okruženju Dataverse. Proverite da [Dataverse li je ovo okruženje](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) povezano sa određenim bezbednosnim grupama i uverite se da ste dodati tim bezbednosnim grupama.
> 1. Postojeće okruženje "Uvidi kupaca" već nije povezano sa tim okruženjem Dataverse. Saznajte kako [da uklonite postojeću vezu sa okruženjem Dataverse](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="deljenje podataka sa Microsoft Dataverse automatski omogućenim za nove neto instance.":::

Više informacija o omogućavanju deljenja podataka sa sopstvenim Microsoft Dataverse potražite u članku Azure Data Lake Storage Povezivanje [sa Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

Customer Insights ne podržava sledeće scenarije deljenja podataka:
- Ako omogućite deljenje podataka sa uslugom Dataverse, nećete moći da [kreirate predviđene ili vrednosti koje nedostaju u entitetu](predictions.md).

### <a name="step-4-finalize-the-settings"></a>4. korak: Dovršavanje podešavanja

U koraku **Pregled**, prođite kroz sva navedena podešavanja. Kada sve izgleda završeno, izaberite **Kreiraj** da biste konfigurisali okruženje. 

Većinu podešavanja možete promeniti i kasnije. Više informacija potražite u članku [Upravljanje okruženjem](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Rad sa novim okruženjem

Pregledajte sledeće članke koji će vam pomoći da započnete sa konfigurisanjem usluge Customer Insights: 

- [Dodajte još korisnika i dodelite dozvole](permissions.md).
- [Unesite svoje izvore podataka](data-sources.md) i provucite ih kroz [proces objedinjavanja podataka](data-unification.md) kako biste dobili [objedinjene profile klijenata](customer-profiles.md).
- [Obogatite objedinjene profile klijenata](enrichment-hub.md) ili [pokrenite modele predviđanja](predictions-overview.md).
- [Kreirajte segmente](segments.md) da biste grupisali klijente i [mere](measures.md) za pregled KPI pokazatelja.
- [Podesite veze](connections.md) i [izvoze](export-destinations.md) za obradu podskupova podataka u drugim aplikacijama.
