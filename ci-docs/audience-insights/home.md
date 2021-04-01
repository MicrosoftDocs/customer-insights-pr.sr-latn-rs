---
title: Stranica Početak u uvidima o korisnicima
description: Počnite da istražujete aplikaciju na stranici Početak.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597252"
---
# <a name="create-a-new-environment"></a>Napravite novo okruženje

## <a name="create-a-trial-environment"></a>Napravite probno okruženje

Možete da se upišete za probnu verziju na [stranici za upisivanje za probnu verziju](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Probne verzije ističu nakon 30 dana.

1. Izaberite opciju **Upišite se za besplatnu probnu verziju** i izaberite **Upišite se sada**.

1. Navedite poslovnu ili školsku adresu e-pošte, recite nam više o sebi i izaberite **Dalje**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dijalog za registraciju za probnu instancu":::

1. Obezbedite **Ime** za novo okruženje. 

1. Izaberite tip probne verzije.

1. Odaberite **Region** za svoje okruženje.

1. Opcionalno, za administratore Dynamics 365 organizacije: Izaberite **Napredna podešavanja** i navedite URL vaše organizacije da biste koristili funkcije predviđanja poput gubitka klijenata.

1. Izaberite **Kreiraj**. 

Nakon kreiranja okruženja, videćete **Demo** okruženje koje vam omogućava da istražite aplikaciju sa fiktivnim podacima. Uzorke podataka možete promeniti tako da odgovaraju vašoj delatnosti. Izaberite ikonu **Podešavanja** u zaglavlju i izaberite **Podešavanja demo verzije**. Pored toga, možete da promenite vizuelnu temu. 

[Prebacujete se na okruženje](#switch-environments) koje ste kreirali tokom procesa registracije da biste radili sa sopstvenim podacima.

## <a name="create-a-new-production-or-sandbox-environment"></a>Kreirajte novo proizvodno ili Sandbox okruženje

U svom okruženju izaberite birač **Okruženja** u zaglavlju aplikacije i izaberite **Novo**.

Pratite korake kao da [kreirate probno okruženje](#create-a-trial-environment). Podaci se podrazumevano čuvaju u jezeru podataka kojim upravlja Customer Insights. Dobijate dodatnu opciju prilikom izbora **Naprednih podešavanja** za čuvanje podataka u usluzi Azure Data Lake. Navedite ime i ključ naloga da biste uspostavili vezu sa uslugom Azure Data Lake. 

> [!IMPORTANT]
> Čuvanjem podataka u usluzi Azure Data Lake Storage, slažete se da će podaci biti preneti i uskladišteni na odgovarajućoj geografskoj lokaciji za taj Azure nalog za skladištenje, koja može da se razlikuje od mesta skladištenja podataka u usluzi Dynamics 365 Customer Insights. [Saznajte više u Microsoft centru za pouzdanost.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Istražite matičnu stranicu

Možete da [pristupite uvidima o korisnicima iz usluge Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) na sledećoj URL adresi: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
Stranica **Početak** prikazuje pregled segmenata, mera i podataka o obogaćivanju (ako su konfigurisani) nakon dovršavanja faza [mapiranja](map-entities.md), [podudaranja](match-entities.md) i [objedinjavanja](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Uvidi na matičnoj stranici](media/home-page-insights.png "Uvidi na matičnoj stranici")

U odeljku **Nedavni segmenti**, vidite grupe klijenata na osnovu atributa demografije, ponašanja ili transakcija koje ste definisali. [Kreiranje segmenata](segments.md) pomaže vam da grupišete bazu klijenata i bolje ciljate svoje poslovne aktivnosti.

**Najnovije mere** pokazuju pločice sa [indikatorima ključnih performansi (KPI-ovi)](measures.md) koje ste definisali. Na primer, prosečna verovatnoća da se klijent odbaci ili prosečna potrošnja na mreži po klijentu.

Odeljak **Nedavna obogaćivanja** navodi rezultate pokretanja obogaćivanja koja su nedavno završena. [Obogaćivanja](enrichment-hub.md) dodaju informacije o vašoj bazi klijenata. Na primer, razumevanjem interesa i brendova za koje imaju sklonost.

## <a name="switch-environments"></a>Zamena okruženja

Izaberite kontrolu **Okruženje** u gornjem desnom uglu stranice da biste promenili okruženje.

> [!div class="mx-imgBorder"] 
> ![Promeni okruženje](media/home-page-environment-switcher.png "Promeni okruženje")

Administratori mogu da kreiraju [više okruženja](manage-environments.md) i upravljaju njima. Održavanje više okruženja može biti korisno ako, na primer, vaša organizacija posluje na međunarodnom nivou i treba da razdvojite podatke i uvide na različite načine.

## <a name="next-step"></a>Sledeći korak

Da biste videli sopstvene uvide na početnoj stranici, prvo morate da [dodate izvore podataka](data-sources.md) i [objedinite](data-unification.md) podatke kako biste napravili korisničke profile.


[!INCLUDE[footer-include](../includes/footer-banner.md)]