---
title: Stranica Početak u uvidima o korisnicima
description: Počnite da istražujete aplikaciju na stranici Početak.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406806"
---
# <a name="create-a-new-environment"></a>Napravite novo okruženje

## <a name="create-a-trial-environment"></a>Napravite probno okruženje

Možete da se upišete za probnu verziju na [stranici za upisivanje za probnu verziju](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Probne verzije ističu nakon 30 dana.

1. Izaberite opciju **Upišite se za besplatnu probnu verziju** i izaberite **Upišite se sada**.

1. Navedite poslovnu ili školsku adresu e-pošte, recite nam više o sebi i izaberite **Dalje**.

1. Obezbedite **Ime** za novo okruženje. 

1. Izaberite tip probne verzije.

1. Odaberite **Region** za svoje okruženje.

1. Opcionalno, za administratore Dynamics 365 organizacije: Izaberite **Napredna podešavanja** i navedite URL vaše organizacije da biste koristili funkcije predviđanja poput gubitka klijenata.

1. Izaberite **Kreiraj**. 

Nakon kreiranja okruženja, videćete **Demo** okruženje koje vam omogućava da istražite aplikaciju sa fiktivnim podacima. Uzorke podataka možete promeniti tako da odgovaraju vašoj delatnosti. Izaberite ikonu **Podešavanja** u zaglavlju i izaberite **Podešavanja demo verzije**. Pored toga, možete da promenite vizuelnu temu. 

[Prebacujete se na okruženje](#change-between-environments) koje ste kreirali tokom procesa registracije da biste radili sa sopstvenim podacima.

## <a name="create-a-new-production-or-sandbox-environment"></a>Kreirajte novo proizvodno ili Sandbox okruženje

U svom okruženju odaberite ikonu **Podešavanja** u zaglavlju i izaberite **Novo okruženje**.

Pratite korake kao da [kreirate probno okruženje](#create-a-trial-environment). Dobijate dodatnu opciju prilikom izbora **Naprednih podešavanja** za čuvanje podataka u usluzi Azure Data Lake. Navedite ime i ključ naloga da biste uspostavili vezu sa uslugom Azure Data Lake. Podaci se podrazumevano čuvaju u jezeru podataka kojim upravlja Customer Insights.

> [!IMPORTANT]
> Čuvanjem podataka u usluzi Azure Data Lake Storage, slažete se da će podaci biti preneti i uskladišteni na odgovarajućoj geografskoj lokaciji za taj Azure nalog za skladištenje, koja može da se razlikuje od mesta skladištenja podataka u usluzi Dynamics 365 Customer Insights. [Saznajte više u Microsoft centru za pouzdanost.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Istražite matičnu stranicu

Možete [da pristupite Customer Insights okruženju](https://home.ci.ai.dynamics.com/) na sledećem URL-u:[https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
Stranica **Početak** prikazuje pregled baze klijenata i ključne pokazatelje za praćenje stanja vašeg poslovanja.

> [!div class="mx-imgBorder"] 
> ![Uvidi na matičnoj stranici](media/home-page-insights.png "Uvidi na matičnoj stranici")

U odeljku **Nedavni segmenti**, vidite grupe klijenata na osnovu atributa demografije, ponašanja ili transakcija koje ste definisali. [Pravljenje segmenata](segments.md) vam pomaže da bolje ciljate poslovne aktivnosti.

**Nedavne mere** prikazuju pločice sa [merama](measures.md). Mere su indikatori ključnih performansi (KPI-ovi) koje ste definisali. Na primer, prosečna verovatnoća gubitka klijenta ili prosečna potrošnja na mreži po klijentu.

Odeljak **Nedavna obogaćivanja** navodi rezultate pokretanja obogaćivanja koja su nedavno završena. Obogaćivanja dodaju informacije o vašoj bazi klijenata. Na primer, razumevanjem interesa i brendova za koje imaju sklonost. Ove informacije možete da otključate pomoću mogućnosti [obogaćivanja](enrichment-microsoft-graph.md), nakon završetka faza [mapa](map-entities.md), [podudaranje](match-entities.md) i [spajanje](merge-entities.md).

## <a name="change-between-environments"></a>Promena između okruženja

Kada podesite i konfigurišete [izvore podataka](data-sources.md), možete da pređete iz demo okruženja u živo okruženje. Korišćenje proizvodnog okruženja omogućava vam rad sa sopstvenim podacima o klijentima. Izaberite kontrolu **Okruženje** u gornjem desnom uglu stranice da biste promenili okruženje.

> [!div class="mx-imgBorder"] 
> ![Promeni okruženje](media/home-page-environment-switcher.png "Promeni okruženje")

Administratori mogu da kreiraju [više okruženja](manage-environments.md) i upravljaju njima. Održavanje više okruženja može biti korisno ako, na primer, vaša organizacija posluje na međunarodnom nivou i treba da razdvojite podatke i uvide na različite načine.

## <a name="next-step"></a>Sledeći korak

Da biste videli sopstvene uvide na početnoj stranici, prvo morate da [dodate izvore podataka](data-sources.md) i [objedinite](data-unification.md) podatke kako biste napravili korisničke profile.
