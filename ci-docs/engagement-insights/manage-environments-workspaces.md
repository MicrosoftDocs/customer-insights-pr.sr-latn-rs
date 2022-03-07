---
title: Upravljanje radnim prostorima i okruženjima
description: Kako da kreirate, preimenujete i brišete radne prostore i okruženja.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ded9e98f06109b7cdc27f449455b7f58d633722f
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350654"
---
# <a name="manage-environments-and-workspaces"></a>Upravljajte okruženjima i radnim prostorima

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Pregled

Ova tema govori o tome kako upravljati radnim prostorima i okruženjima nakon što su već kreirani. 

- *Radni prostor* je prostor za skladištenje i upravljanje događajima i izveštajima. Tu možete u realnom vremenu prikazivati aktivnosti korisnika. Kada kreirate radni prostor, izaberite vrstu podataka koju želite da pošaljete u radni prostor. Trenutno su podržani veb-podaci i aplikacije za mobilne uređaje. Više informacija potražite u članku [Kreiranje novog radnog prostora i dodavanje članova](create-workspace.md).

- *Okruženje* je prostor u kojem upravljate svojim radnim prostorima i vezama. Više informacija potražite u članku [Kreiranje novog okruženja](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Upravljanje postojećim radnim prostorom

Možete istovremeno održavati više radnih prostora u okruženju. Vaša [uloga](user-roles.md) određuje kako možete raditi u njima. 

 - Morate biti administrator okruženja ili administrator radnog prostora da biste upravljali radnim prostorom.
 - Kao administrator radnog prostora, možete preimenovati postojeće radne prostore ili ih izbrisati. 

:::image type="content" source="media/workspace-edit.png" alt-text="Centar administratora radnog prostora.":::

### <a name="edit-a-workspace-name"></a>Uređivanje naziva radnog prostora

1. Idite na **Administrator** > **Radni prostor** i izaberite **Podešavanja**.

1. U polju **Naziv radnog prostora** unesite novi naziv.

1. Izaberite **Sačuvaj** da primenite promene.

### <a name="delete-a-workspace"></a>Brisanje radnog prostora

Brisanje radnog prostora trajno uklanja sav njegov sadržaj, podatke, postavke i dozvole. To nije moguće opozvati.

1. Idite na **Administrator** > **Radni prostor** i izaberite **Podešavanja**.

1. Izaberite **Brisanje radnog prostora**. 

1. U dijalogu **Brisanje radnog prostora** unesite **POTVRDI BRISANJE** velikim slovima. 

1. Izaberite **Izbriši** da biste trajno izbrisali radni prostor.

### <a name="manage-workspace-members"></a>Upravljanje članovima radnog prostora

1. Idite na **Administrator** > **Radni prostor** i izaberite **Članovi**.

1. Izaberite **Dodaj članove** da biste dali pristup i [dodelili uloge](user-roles.md). Trenutno, dostupno je samo **Administrator radnog prostora**.

1. Izaberite **Dodaj članove** da biste ih dodali u svoj radni prostor.

## <a name="manage-an-existing-environment"></a>Upravljajte postojećim okruženjem

Kao administrator okruženja, okruženju možete pristupiti iz levog okna za navigaciju. Možete da konfigurišete podešavanja okruženja, druge administratore okruženja i radne prostore. Izaberite kartice da biste se kretali između različitih oblasti u centru administracije.

:::image type="content" source="media/environment-edit.png" alt-text="Centar administracije okruženja.":::

### <a name="edit-an-environment-name"></a>Uređivanje imena okruženja

1. Idite na **Administrator** > **Okruženje** i izaberite **Podešavanja**.

1. Ažurirajte **Naziv okruženja** i izaberite **Sačuvaj** da biste primenili izmene.

### <a name="delete-an-environment"></a>Brisanje okruženja

Administratori okruženja mogu brisati okruženja. Pre nego što izbrišete okruženje, morate ukloniti sve radne prostore u okviru njega.

1. Idite na **Administrator** > **Okruženje** i izaberite **Podešavanja**.

1. Izaberite **Brisanje okruženja**. 

1. U dijalogu **Brisanje radnog prostora** unesite **POTVRDI BRISANJE** velikim slovima. 

1. Izaberite **Izbriši** kako biste trajno izbrisali okruženje.

### <a name="manage-environment-members"></a>Upravljanje članovima okruženja

1. Idite na **Administrator** > **Okruženje** i izaberite **Članovi**.

1. Izaberite **Dodaj članove** da biste ažurirali članove i [dodelili uloge](user-roles.md). Trenutno, dostupno je samo **Administrator okruženja**.

1. Izaberite **Dodaj članove** da biste ih dodali u svoje okruženje.

## <a name="manage-connections"></a>Upravljanje vezama

Uspostavljanje veza sa uvidima u ciljnu grupu omogućava vam da vidite izveštaje u uvidima o angažovanju na osnovu objedinjenih profila klijenata. 

Za više informacija, pogledajte [Napravite vezu između uvida u ciljnu grupu i uvida u angažovanje](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Upravljanje ličnim podacima

Da biste zaštitili lične podatke klijenta, možete izbrisati ili izvesti podatke koji mogu identifikovati krajnjeg korisnika.

Za više informacija, pogledajte [Brisanje i izvoz podataka o događajima koji sadrže lične informacije](../dsr-rights-requests.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
