---
title: Kreiranje okruženja u usluzi Customer Insights
description: Koraci za kreiranje okruženja sa licenciranom pretplatom za Dynamics 365 Customer Insights.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 95afd1fedb98a451e4978ee66be2ea98ad7a4a76
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645724"
---
# <a name="create-an-environment-in-audience-insights"></a>Kreiranje okruženja u uvidima u ciljnu grupu

Ovaj članak objašnjava kako da kreirate novo okruženje nakon što je vaša organizacija kupila Dynamics 365 Customer Insights pretplatu. 

Organizacije mogu da kreiraju *dva* okruženja za svaku Customer Insights licencu. Ako vaša organizacija kupi više licenci, [kontaktirajte naš tim za podršku](https://go.microsoft.com/fwlink/?linkid=2079641) da bi povećali broj dostupnih okruženja. Za više informacija o kapacitetu i dodatnom kapacitetu preuzmite [Dynamics 365 vodič za licenciranje](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Ako želite da isprobate uslugu, pogledajte [Konfigurisanje probnog okruženja](../trial-signup.md).

## <a name="create-a-new-environment"></a>Kreirajte novo okruženje

Nakon što kupite pretplatničku licencu za Customer Insights, globalni administrator Microsoft 365 zakupca prima poruku e-pošte koja ga poziva da kreira okruženje. Idite na [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) da biste započeli. 

Vođeno iskustvo vam pomaže kroz korake prikupljanja svih potrebnih informacija za novo okruženje. Potrebne su vam [dozvole administratora](permissions.md) u uvidima u ciljnu grupu da biste kreirali ili upravljali okruženjima.

1. U uvidima u ciljnu grupu, otvorite birač okruženja i izaberite **+ Novo**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Izaberite birač okruženja.":::

1. Pratite vođeno iskustvo opisano u sledećim odeljcima.

### <a name="step-1-provide-environment-information"></a>1. korak: Pružite informacije o okruženju

U koraku **Osnovne informacije**, odaberite da li želite da kreirate okruženje od nule ili da [kopirate podatke iz drugog okruženja](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dijalog za kreiranje novog Customer Insights okruženja.":::

Navedite sledeće detalje:
   - **Naziv**: Unesite naziv ovog okruženja. Ovo polje je već popunjeno ako ste kopirali postojeće okruženje, ali možete ga promeniti.
   - **Odaberite svoje poslovanje**: Odaberite primarnu ciljnu grupu za novo okruženje. Možete raditi sa individualnim klijentima (B2C) ili [poslovnim nalozima ](work-with-business-accounts.md) (B2B).
   - **Tip**: izaberite da li želite da kreirate proizvodno ili Sandbox okruženje. Sandbox okruženja ne dozvoljavaju zakazano osvežavanje podataka i namenjena su za predimplementaciju i testiranje. Sandbox okruženja koriste istu primarnu ciljnu grupu kao i trenutno izabrano proizvodno okruženje.
   - **Region**: Region u kojem je usluga primenjena i hostovana.

### <a name="step-2-configure-data-storage"></a>2. korak: Konfigurišite skladište podataka

U koraku **Skladištenje podataka**, izaberite gde ćete skladištiti podatke iz uvida u ciljnu grupu.

Imaćete dve mogućnosti: **Customer Insights skladište** (Azure Data Lake kojim upravlja Customer Insights tim) i **Azure Data Lake Storage** (vaš sopstveni Azure Data Lake Storage). Podrazumevano je odabrana opcija Customer Insights skladišta.

:::image type="content" source="media/data-storage-environment.png" alt-text="Izaberite Azure Data Lake Storage za skladištenje podataka iz uvida u ciljnu grupu.":::

Čuvanjem podataka u usluzi Azure Data Lake Storage, slažete se da će se podaci prenositi i skladištiti na odgovarajućoj geografskoj lokaciji za taj Azure nalog za skladištenje. Ova lokacija se može razlikovati od mesta na kome se čuvaju podaci iz usluge Dynamics 365 Customer Insights. Saznajte više u [Microsoft centru za pouzdanost](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights trenutno podržava sledeće:
> - Uneti entiteti iz Power BI tokova podataka koji se čuvaju u Microsoft Dataverse upravljanoj usluzi Data Lake.  
> - Azure Data Lake Storage nalozi iz istog Azure regiona koji ste izabrali prilikom kreiranja okruženja.
> - Azure Data Lake Storage nalozi koji imaju omogućen *hijerarhijski prostor za ime*.

Za opciju Azure Data Lake Storage, možete odabrati između opcije zasnovane na resursima i opcije zasnovane na pretplati za potvrdu identiteta. Za više informacija pogledajte [Povezivanje uvida o korisnicima sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge](connect-service-principal.md). Naziv za **Kontejner** će biti `customerinsights` i ne možete ga promeniti.

Kada su sistemski procesi poput unosa podataka, završeni, sistem kreira odgovarajuće fascikle na nalogu za skladištenje koji ste naveli. Datoteke sa podacima i *model.json* datoteke se kreiraju i dodaju u fascikle na osnovu naziva procesa.

Ako kreirate više okruženja usluge Customer Insights i odaberete da sačuvate izlazne entitete iz tih okruženja na svoj nalog za skladištenje, Customer Insights kreira zasebne fascikle za svako okruženje sa `ci_environmentID` u kontejneru.

### <a name="step-3-connect-to-microsoft-dataverse"></a>3. korak: Povezivanje sa sistemom Microsoft Dataverse
   
Korak **Microsoft Dataverse** vam omogućava da povežete Customer Insights sa vašim Dataverse okruženjem.

Da biste koristili [gotove modele predviđanja](predictions-overview.md#out-of-box-models), konfigurišite deljenje podataka sa uslugom Dataverse. Ili možete omogućiti unos podataka iz lokalnih izvora podataka,obezbeđujući URL adresu Microsoft Dataverse okruženja kojim upravlja vaša organizacija. Izaberite **Omogući deljenje podataka** da biste delili Customer Insights izlazne podatke pomoću usluge Dataverse Managed Data Lake.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Opcije konfiguracije za omogućavanje deljenja podataka sa platformom Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights ne podržava sledeće scenarije deljenja podataka:
> - Ako sve podatke sačuvate u sopstvenoj usluzi Azure Data Lake Storage, nećete moći da omogućite deljenje podataka sa Microsoft Dataverse upravljanoj usluzi Data Lake.
> - Ako omogućite deljenje podataka sa Microsoft Dataverse upravljanoj usluzi Data Lake nećete moći da [kreirate predviđene ili vrednosti koje nedostaju u entitetu](predictions.md).

### <a name="step-4-finalize-the-settings"></a>4. korak: Dovršavanje podešavanja

U koraku **Pregled**, prođite kroz sva navedena podešavanja. Kada sve izgleda završeno, izaberite **Kreiraj** da biste konfigurisali okruženje. 

Većinu podešavanja možete promeniti i kasnije. Više informacija potražite u članku [Upravljanje okruženjem](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Rad sa novim okruženjem

Pregledajte sledeće članke koji će vam pomoći da započnete sa konfigurisanjem rešenja Customer Insights. 

- [Dodajte još korisnika i dodelite dozvole](permissions.md).
- [Unesite svoje izvore podataka](data-sources.md) i provucite ih kroz [proces objedinjavanja podataka](data-unification.md) kako biste dobili [objedinjene profile klijenata](customer-profiles.md).
- [Obogatite objedinjene profile klijenata](enrichment-hub.md) ili [pokrenite modele predviđanja](predictions-overview.md).
- [Kreirajte segmente](segments.md) da biste grupisali klijente i [mere](measures.md) pregleda KPI pokazatelja.
- [Podesite veze](connections.md) i [izvoze](export-destinations.md) za obradu podskupova podataka u drugim aplikacijama.
