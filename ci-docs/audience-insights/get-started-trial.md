---
title: Kreiranje i konfigurisanje probne verzije rešenja Customer Insights
description: Koraci za dobijanje probne pretplate za Dynamics 365 Customer Insights i njegovo konfigurisanje.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f038dedd369ac9e623146b66528efa87c47a8c23769037d8709fa9b804a0b723
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035432"
---
# <a name="set-up-a-trial-environment"></a>Podešavanje probnog okruženja 

Probna verzija rešenja Dynamics 365 Customer Insights vam omogućava da pregledate ključne mogućnosti i saznate više o različitim funkcijama. Probna pretplata se briše nakon isteka. Pojedinačni korisnici kreiraju probna okruženja, pa oni postaju administratori svog probnog okruženja. Oni mogu pozvati više korisnika u svoje probno okruženje i konfigurisati različite funkcije.

## <a name="create-a-trial-environment"></a>Napravite probno okruženje

Možete da se upišete za probnu verziju na [stranici za upisivanje za probnu verziju](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Izaberite opciju **Upišite se za besplatnu probnu verziju** i izaberite **Upišite se sada**.

1. Navedite svoju poslovnu ili školsku adresu e-pošte, recite nam nešto više o sebi i izaberite **Započnite**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dijalog za registraciju za probnu instancu":::

1. Pregledajte uslove i odredbe i izaberite **Nastavi** kako biste potvrdili.

1. Obezbedite **Ime** za novo okruženje. 

1. Za **Tip** okruženja podesite **Probna verzija**.

1. U polju **Izaberite neku demo delatnost**, možete opciono izabrati skup podataka specifičnih za delatnost. Možete takođe [da promenite u demo delatnost](#use-industry-specific-demo-data-sets-in-audience-insights) kasnije i započnete sa podrazumevanim skupom podataka.

1. Odaberite **Region** za svoje okruženje.

1. Opciono, ako ste administrator Dynamics 365 organizacije: izaberite **Napredna podešavanja** i navedite URL vaše organizacije za korišćenje funkcija predviđanja kao što je predviđanje gubitka klijenata. 

1. Izaberite **Kreiraj**. 

Potrebno je nekoliko trenutaka za dovršetak konfigurisanja okruženja. Po završetku, bićete preusmereni na demonstraciono okruženje ili demo delatnost koju ste izabrali u prethodnom koraku. Sada možete da istražite aplikaciju sa demonstracionim podacima koji su samo za čitanje. Da biste dodali svoje podatke u okruženje, pogledajte [Kreiranje demonstracionih podataka specifičnih za scenario u svom okruženju](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Snimak ekrana novokreiranog probnog okruženja.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Koristite skupove demonstracionih podataka specifičnih za delatnost u uvidima o ciljnoj grupi

Povezivanje stvarnih izvora podataka jedan je od presudnih koraka u korišćenju moći rešenja Customer Insights. Da biste isprobali funkcije bez mešanja u vlastite podatke, opciono možete koristiti demonstracione podatke specifične za delatnost. Dostupno je nekoliko demonstracionih skupova podataka za sledeće delatnosti: 

-   Automobilska
-   Bankarstvo
-   Roba široke potrošnje
-   Vlada
-   Zdravstvo
-   Ugostiteljstvo
-   Osiguranje
-   Proizvodnja
-   Profesionalne usluge
-   Maloprodaja

### <a name="see-industry-specific-demo-data-in-trials"></a>Pogledajte demonstracione podatke specifične za određenu delatnost

Za verziju rešenja Customer Insights koja je samo za čitanje, prilagođenu određenoj delatnosti ili scenariju, započnite rad u demonstracionom okruženju. 
 
1.  U uvidima u ciljnu grupu, odaberite **Demonstraciono** okruženje u biraču okruženja.

2.  Na opciji **Početak**, odaberite opciju sa padajućeg menija Izaberite demonstracionu delatnost.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Odaberite delatnost za probno okruženje.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Kreirajte demonstracione podatke specifične za scenario u svom okruženju

Kao administrator, izaberite birač okruženja u zaglavlju aplikacije da biste kreirali novo okruženje. U novom okruženju možete konfigurisati sopstvene izvore podataka i konfigurisati aplikaciju prema svojim zahtevima. 

1.  U uvidima o korisnicima idite na **Podaci** > **Izvori podataka**.

2.  Da biste uvezli sopstvene izvore podataka, idite na [vodič za unos podataka](data-sources.md).     
   Ako više volite da radite sa primerima podataka koji vam omogućavaju da isprobate unos podataka, možete unositi demonstracione podatke za delatnost u svoje okruženje. Odaberite opciju **Uvezi iz sistema Datahub** i pratite dolenavedene korake.

3.  Izaberite karticu delatnosti koja odgovara vašem scenariju. 

4.  Pregledajte i opciono ažurirajte predloženi naziv izvora podataka. 

5.  Izaberite **Dalje** da biste uneli probne podatke. 

Sada možete da koristite unete podatke za prilagođavanje rešenja Customer Insights u vaš scenario. Da biste videli okruženje specifično za unete demonstracione podatke, odaberite opciju **Demonstracija za <Industry>** u biraču okruženja.

## <a name="limitations-in-trials"></a>Ograničenja u probnim verzijama

- Probne verzije su podrazumevano aktivne 30 dana. Međutim, možete ih produžiti nakon 23. dana kada se prijavite u probnu verziju.
- Ne možete koristiti sopstveni Azure Data Lake Storage nalog da biste skladištili izlazne podatke tokom probnog perioda. Međutim, možete unositi podatke iz Data Lake Storage naloga.
- Možete da uskladištite do 3 GB podataka u Dataverse okruženje koje se automatski obezbeđuje kada započnete probnu verziju rešenja Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Kopiranje podataka iz probne verzije u plaćenu pretplatu

Uopšteno, preporučujemo da počnete iznova sa sopstvenim podacima prilikom nadogradnje na plaćenu verziju rešenja Customer Insights. 

Opciono, možete kopirati svoje podatke iz probnog okruženja ako kupite Customer Insights. Morate biti administrator probne verzije rešenja Customer Insights i globalni administrator vašeg Microsoft 365 zakupca ili Dynamics 365 administrator u vašoj organizaciji da biste migrirali podešavanja iz probnog okruženja u plaćeno okruženje. 

Nakon što se prvi put prijavite na svoju plaćenu instancu rešenja Customer Insights od vas će biti zatraženo da kreirate novo okruženje. U ovom procesu možete izabrati da kopirate konfiguraciju iz postojećeg okruženja i da migrirate većinu podešavanja. Ako imate gorenavedene dozvole, probno okruženje će se prikazati na ovoj listi. Još informacija potražite u članku [Kopiranje konfiguracije okruženja](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Sledeći koraci

Pregledajte sledeće članke koji će vam pomoći da započnete sa konfigurisanjem rešenja Customer Insights. 

- [Dodajte još korisnika i dodelite dozvole](permissions.md).
- [Unesite svoje izvore podataka](data-sources.md) i provucite ih kroz [proces objedinjavanja podataka](data-unification.md) kako biste dobili [objedinjene profile klijenata](customer-profiles.md).
- [Obogatite objedinjene profile klijenata](enrichment-hub.md) ili [pokrenite modele predviđanja](predictions-overview.md).
- Kreirajte [segmente](segments.md) da biste grupisali klijente i [mere](measures.md) pregledajte KPI pokazatelje.
- Podesite [veze](connections.md) i [izvoze](export-destinations.md) za obradu podskupova podataka u drugim aplikacijama.