---
title: Kreiranje i konfigurisanje plaćene licence rešenja Customer Insights
description: Koraci za dobijanje licencirane pretplate za Dynamics 365 Customer Insights i njegovo konfigurisanje.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034469"
---
# <a name="get-started-with-a-paid-subscription"></a>Prvi koraci uz plaćenu pretplatu

Ovaj članak objašnjava kako da kreirate novo okruženje nakon što je vaša organizacija kupila Dynamics 365 Customer Insights pretplatu. Ako želite da kupite rešenje Customer Insights, naše opcije za kontakt su navedene na [Dynamics 365 Customer Insights veb-lokaciji](https://dynamics.microsoft.com/ai/customer-insights/). 

Ako želite da isprobate uslugu i funkcije, pogledajte [Konfigurisanje probnog okruženja](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Kreirajte okruženje u postojećoj organizaciji

Nakon što kupite pretplatničku licencu za Customer Insights, globalni administrator Microsoft 365 zakupca prima poruku e-pošte koja ga poziva da kreira okruženje. Idite na [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) da biste započeli. 

Customer Insights nije licenciran po korisniku, pa se neće prikazivati u području Licence. Ako tražite licencu u Microsoft 365 centru administracije, idite na **Vaši proizvodi**. 

> [!NOTE]
> Organizacije mogu da kreiraju *dva* okruženja za svaku Customer Insights licencu. Ako vaša organizacija više puta kupi licencu, [kontaktirajte naš tim za podršku](https://go.microsoft.com/fwlink/?linkid=2079641) da biste povećali broj dostupnih okruženja. Za više informacija o kapacitetu i dodatnom kapacitetu preuzmite [Dynamics 365 vodič za licenciranje](https://go.microsoft.com/fwlink/?LinkId=866544).

Da biste kreirali okruženja:

1. U dijalogu **Kreiranje okruženja**, izaberite **Novo okruženje**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dijalog za kreiranje novog Customer Insights okruženja.":::

   Preporučujemo da započnete sa konfigurisanjem okruženja od početka. Međutim, ako ste administrator ili član probnog okruženja, mogli biste [da kopirate podatke iz drugog okruženja](manage-environments.md#copy-the-environment-configuration), izborom opcije **Kopiraj iz postojećeg okruženja**. Videćete listu svih dostupnih okruženja u vašoj organizaciji, odakle možete kopirati podatke.

1. Navedite sledeće detalje:
   - **Naziv**: Unesite naziv ovog okruženja. Ovo polje je već popunjeno ako ste kopirali postojeće okruženje, ali možete ga promeniti.
   - **Region**: Region u kojem je usluga primenjena i hostovana.
   - **Tip**: izaberite da li želite da kreirate proizvodno ili Sandbox okruženje. Sandbox okruženja ne dozvoljavaju zakazano osvežavanje podataka i namenjena su za predimplementaciju i testiranje.
   
1. Po želji možete odabrati **Napredna podešavanja**:

   - **Sačuvaj sve podatke u**: Određuje gde želite da sačuvate izlazne podatke generisane u usluzi Customer Insights. Imaćete dve mogućnosti: **Customer Insights skladište** (Azure Data Lake kojim upravlja Customer Insights tim) i **Azure Data Lake Storage** (vaš sopstveni Azure Data Lake Storage). Podrazumevano je odabrana opcija Customer Insights skladišta.

     > [!NOTE]
     > Čuvanjem podataka u usluzi Azure Data Lake Storage, slažete se da će podaci biti preneti i uskladišteni na odgovarajućoj geografskoj lokaciji za taj Azure nalog za skladištenje, koja može da se razlikuje od mesta skladištenja podataka u usluzi Dynamics 365 Customer Insights. [Saznajte više u Microsoft centru za pouzdanost.](https://www.microsoft.com/trust-center)
     >
     > Trenutno se uneti entiteti iz Power BI tokova podataka uvek čuvaju u Microsoft Dataverse upravljanoj usluzi Data Lake. 
     > 
     > Podržavamo samo Azure Data Lake Storage naloge iz istog Azure regiona koji ste izabrali prilikom kreiranja okruženja. 
     > 
     > Podržavamo samo Azure Data Lake Storage naloge koji imaju omogućen hijerarhijski prostor imena.


   - Za opciju Azure Data Lake Storage, možete odabrati između opcije zasnovane na resursima i opcije zasnovane na pretplati za potvrdu identiteta. Za više informacija pogledajte [Povezivanje uvida o korisnicima sa Azure Data Lake Storage Gen2 nalogom pomoću principala Azure usluge](connect-service-principal.md). Naziv **kontejnera** se ne može promeniti i biće `customerinsights`.
   
   - Ako želite da koristite [gotove modele](predictions-overview.md#out-of-box-models), konfigurišite deljenje podataka sa uslugom Microsoft Dataverse ili omogućite unos podataka iz lokalnih izvora podataka, navedite URL adresu Microsoft Dataverse okruženja u okviru opcije **Konfigurišite deljenje podataka sa uslugom Microsoft Dataverse i omogućite dodatne mogućnosti**. Izaberite **Omogući deljenje podataka** da biste delili Customer Insights izlazne podatke pomoću usluge Microsoft Dataverse Managed Data Lake.

     > [!NOTE]
     > - Deljenje podataka pomoću usluge Microsoft Dataverse Managed Data Lake trenutno nije podržano kada sve podatke čuvate u sopstvenom Azure Data Lake Storage.
     > - [Predviđanje vrednosti koje nedostaju u entitetu](predictions.md) trenutno nije podržano kada omogućite deljenje podataka sa uslugom Microsoft Dataverse Managed Data Lake.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Opcije konfiguracije za omogućavanje deljenja podataka sa platformom Microsoft Dataverse.":::

   Kada sistem obradi potpuni unos podataka, sistem kreira odgovarajuće fascikle na nalogu za skladištenje koji ste naveli. Datoteke sa podacima i model.json datoteke se kreiraju i dodaju u fascikle na osnovu naziva procesa.

   Ako kreirate više okruženja za Customer Insights i odlučite da sačuvate izlazne entitete iz tih okruženja na svom nalogu za skladištenje, kreiraće se zasebne fascikle za svako okruženje sa ci_<environmentid> u kontejneru.

1. Izaberite **Kreiraj** da biste konfigurisali okruženje. 

## <a name="configure-an-environment"></a>Konfigurisanje okruženja

Pregledajte sledeće članke koji će vam pomoći da započnete sa konfigurisanjem rešenja Customer Insights. 

- [Dodajte još korisnika i dodelite dozvole](permissions.md).
- [Unesite svoje izvore podataka](data-sources.md) i provucite ih kroz [proces objedinjavanja podataka](data-unification.md) kako biste dobili [objedinjene profile klijenata](customer-profiles.md).
- [Obogatite objedinjene profile klijenata](enrichment-hub.md) ili [pokrenite modele predviđanja](predictions-overview.md).
- Kreirajte [segmente](segments.md) da biste grupisali klijente i [mere](measures.md) pregledajte KPI pokazatelje.
- Podesite [veze](connections.md) i [izvoze](export-destinations.md) za obradu podskupova podataka u drugim aplikacijama.
