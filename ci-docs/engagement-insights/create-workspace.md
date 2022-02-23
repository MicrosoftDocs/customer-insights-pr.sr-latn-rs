---
title: Kreirajte novi radni prostor
description: Svrha radnog prostora i kako da kreirate novi.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f8922703af506974c8b5b24086b61f05a83609d
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673510"
---
# <a name="create-a-new-workspace-and-add-members"></a>Kreiranje novog radnog prostora i dodavanje članova

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Radni prostor je način na koji možete prikazati aktivnost korisnika u realnom vremenu da biste bolje razumeli svoju ciljnu grupu. Tu skladištite događaje i izveštaje i upravljate njima.

Kada kreirate radni prostor, izaberite vrstu podataka na koju želite da se fokusirate. U bilo kom trenutku u postojeći radni prostor možete dodati druge korisnike ili članove. 

## <a name="create-a-new-workspace"></a>Kreirajte novi radni prostor

Proces kreiranja radnog prostora uključuje konfigurisanje *okruženja* da biste organizovali svoj radni prostor. Okruženje je prostor koji može da sadrži jedan radni prostor ili više njih. Okruženje možete da koristite za upravljanje radnim prostorom i vezama sa korisnici uvida.

1. Izaberite **+Novo** iz prekidača radnog prostora.

   :::image type="content" source="media/new-workspace.png" alt-text="Stranica Uvidi kupaca sa pozivom u oknu za navigaciju i opisom.":::

1. U oknu **Radni prostor**, unesite **Naziv radnog prostora**.

   :::image type="content" source="media/workspace-name.png" alt-text="Unesite naziv radnog prostora.":::

1. Odaberite tip platforme (veb ili mobilni) koji želite da izmerite.

1. Izaberite **Prikaži napredna podešavanja** da biste omogućili ili onemogućili ova opciona podešavanja:

   - Prebacite **Nepoznato u poznato** na „omogućeno“ za povezivanje veb-događaja sa korisnicima koji su prethodno izvršili potvrdu identiteta. Za više informacija pogledajte [Prepoznavanje veb-događaja posetilaca koji su prethodno izvršili potvrdu identiteta](unknown-to-known.md)
   - Prebacite **Filtriraj saobraćaj robota** na „omogućeno“ za uklanjanje veb-saobraćaja robota za ovaj radni prostor. 

1. Izaberite **Dovrši** kada završite. 

1. Instalirajte isečak koda da biste počeli da primate podatke, a zatim izaberite **Završi** za kreiranje radnog prostora. Za više informacija, pogledajte [Pregled resursa za programere](developer-resources.md).

> [!NOTE]
> Sada možete dodati članove i dodeliti im nivo dozvola sa liste **Uloga**. Za više informacija pogledajte [Uloge i dozvole](user-roles.md). 

Za više informacija pogledajte [Upravljanje okruženjima i radnim prostorima](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
