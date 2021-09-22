---
title: Upravljanje radnim prostorima i okruženjima
description: Kako da kreirate, preimenujete i brišete radne prostore i okruženja.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 07/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: bf310b1a50ba7baac5d11d5f22ff42003fbba516efd7d165c00b59adc958da2e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034059"
---
# <a name="manage-environments-and-workspaces"></a>Upravljajte okruženjima i radnim prostorima

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Pregled

Radni prostor je prostor za skladištenje i upravljanje događajima i izveštajima. Tu možete u realnom vremenu prikazivati aktivnosti korisnika. Kada kreirate radni prostor, izaberite vrstu podataka koju želite da pošaljete u radni prostor. Trenutno su podržani veb-podaci i aplikacije za mobilne uređaje.

Okruženje je prostor u kojem upravljate svojim radnim prostorima i vezama. Način na koji koristite okruženja zavisi od vaše organizacije i slučaja upotrebe. Na primer, možete da kreirate:

-   Jedno okruženje.
-   Zasebna okruženja za testiranje i proizvodnju.
-   Zasebna okruženja za određene timove ili odeljenja u vašoj organizaciji koja sadrže relevantne događaje za svaku ciljnu grupu.
-   Zasebna okruženja za različite globalne ogranke vaše kompanije.
-   Veze sa Customer Insights mogućnošću uvida u ciljnu grupu.

## <a name="choose-an-environment-and-create-a-workspace"></a>Odabir okruženja i kreiranje radnog prostora 

Svaki radni prostor mora biti u okruženju. Možete da izaberete prethodno postojeće okruženje ili da napravite novo kada kreirate radni prostor. Tada možete odabrati da dodate članove radnog prostora i započnete sa prikupljanjem podataka.

**Da biste kreirali prvi radni prostor**

1. U uvidima u angažovanje, izaberite **Novo** iz promene radnog prostora. 

   :::image type="content" source="media/New-workspace.png" alt-text="Birač radnog prostora Customer Insights stranice.":::

1. Odaberite okruženje sa liste ili izaberite **Kreiraj novo okruženje**.

1. Unesite naziv u **Naziv radnog prostora**. 

1. Izaberite tip okruženja koje želite da kreirate, u zavisnosti od toga da li želite da merite šta se dešava na veb-lokaciji ili u aplikaciji za mobilne uređaje. 

1. Možete da dodajete članove i dodeljujete nivo njihovih dozvola sa liste **Uloga**. Zatim izaberite **Završi** da biste kreirali radni prostor ili **Sledeće** da biste instalirali kôd. 

1. Instalirajte isečak koda da biste počeli da primate podatke, a zatim izaberite **Gotovo**. 

## <a name="manage-a-workspace"></a>Upravljanje radnim prostorom

Možete istovremeno održavati više radnih prostora u okruženju. Vaša [uloga](user-roles.md) određuje kako možete raditi u njima. 

 - Morate biti administrator okruženja ili administrator radnog prostora da biste upravljali radnim prostorom.
 - Kao administrator radnog prostora, možete preimenovati postojeće radne prostore ili ih izbrisati. 

### <a name="edit-a-workspace-name"></a>Uređivanje naziva radnog prostora

1. Idite na **Administrator** > **Radni prostor** i izaberite **Podešavanja**.

1. U polju **Naziv radnog prostora** unesite novi naziv.

1. Izaberite **Sačuvaj** da primenite promene.

### <a name="delete-a-workspace"></a>Brisanje radnog prostora

Brisanje radnog prostora trajno će ukloniti sav njegov sadržaj, podatke, podešavanja i dozvole. To nije moguće opozvati.

1. Idite na **Administrator** > **Radni prostor** i izaberite **Podešavanja**.

1. Izaberite **Brisanje radnog prostora**. 

1. U dijalogu **Brisanje radnog prostora** unesite **POTVRDI BRISANJE**. 

1. Izaberite **Izbriši** da biste trajno izbrisali radni prostor.

### <a name="manage-workspace-members"></a>Upravljanje članovima radnog prostora

1. Idite na **Administrator** > **Radni prostor** i izaberite **Članovi**.

1. Izaberite **Dodaj članove** da biste dali pristup i [dodelili uloge](user-roles.md). Trenutno, dostupno je samo **Administrator radnog prostora**.

1. Ako konfiguriše [vezu sa uvidima u ciljnu grupu](configure-connections.md),možete da izaberete **Dozvoli pristup podacima o profilu** kako biste dozvolili članu da vidi izveštaje na osnovu [profila korisnika](profile-reports.md).

1. Izaberite **Dodaj članove** da biste ih dodali u svoj radni prostor.

## <a name="manage-an-environment"></a>Upravljanje okruženjem

Kao administrator okruženja, okruženju možete pristupiti iz levog okna za navigaciju. Možete da konfigurišete podešavanja okruženja, druge administratore okruženja, radne prostore i [veze do uvida u ciljnu grupu](configure-connections.md). Izaberite kartice da biste se kretali između različitih oblasti u centru administracije.

:::image type="content" source="media/New-environment.png" alt-text="Centar administracije okruženja.":::

### <a name="create-an-environment"></a>Kreiranje okruženja

1. U biraču radnog prostora, izaberite **+Novo**.

1. U vođenom iskustvu, otvorite padajući meni **Okruženje** i izaberite **Kreiraj novo okruženje**. 

1. Navedite **Naziv okruženja**.

   :::image type="content" source="media/create-environment.png" alt-text="Zakoračite u vođeno iskustvo da biste naveli detalje o okruženju.":::

1. Odaberite **Region** i izaberite **Dalje**. 

1. Navedite naziv radnog prostora i odaberite tip radnog prostora koji želite da kreirate. 

1.  Opciono dodajte članove i kopirajte fragment koda da biste dovršili proces kreiranja.

### <a name="rename-an-environment"></a>Preimenujte okruženje

1. Idite na **Administrator** > **Okruženje** i izaberite **Podešavanja**.

1. Ažurirajte **Naziv okruženja** i izaberite **Sačuvaj** da biste primenili izmene.

### <a name="manage-environment-members"></a>Upravljanje članovima okruženja

1. Idite na **Administrator** > **Okruženje** i izaberite **Članovi**.

1. Izaberite **Dodaj članove** da biste ažurirali članove i [dodelili uloge](user-roles.md). Trenutno, dostupno je samo **Administrator okruženja**.

1. Ako konfiguriše [vezu sa uvidima u ciljnu grupu](configure-connections.md),možete da izaberete **Dozvoli pristup podacima o profilu** kako biste dozvolili članu da vidi izveštaje na osnovu [profila korisnika](profile-reports.md).

1. Izaberite **Dodaj članove** da biste ih dodali u svoje okruženje.

### <a name="delete-an-environment"></a>Brisanje okruženja

Administratori okruženja mogu brisati okruženja. Pre nego što izbrišete okruženje, morate ukloniti sve radne prostore u okviru njega.

1. Idite na **Administrator** > **Okruženje** i izaberite **Podešavanja**.

1. Izaberite **Brisanje okruženja**. 

1. U dijalogu **Brisanje radnog prostora** unesite **POTVRDI BRISANJE**. 

1. Izaberite **Izbriši** kako biste trajno izbrisali okruženje.

## <a name="manage-connections"></a>Upravljanje vezama

Uspostavljanje veza sa uvidima u ciljnu grupu omogućava vam da vidite izveštaje u uvidima o angažovanju na osnovu objedinjenih profila klijenata. 

Za više informacija pogledajte [konfigurisanje veza](configure-connections.md).

## <a name="manage-personal-data"></a>Upravljanje ličnim podacima

Da biste zaštitili lične podatke klijenta, možete izbrisati ili izvesti podatke koji mogu identifikovati krajnjeg korisnika.

Za više informacija, pogledajte [Brisanje i izvoz podataka o događajima koji sadrže lične informacije](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
