---
title: Kreiranje i izmena izabranih događaja
description: Kako da kreirate i izmenite izabrane događaje.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034791"
---
# <a name="create-and-modify-refined-events"></a>Kreiranje i izmena izabranih događaja

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Događaj je podatak koji predstavlja ponašanje korisnika, poput aktivnosti na veb-lokaciji.

- *Osnovni* događaj beleži kada korisnik prikaže stranicu (događaj prikaza) ili stupi u interakciju sa sadržajem (događaj radnje).
- *Prečišćeni* događaj je virtuelni prikaz osnovnog događaja. Prečišćene događaje definišete uklanjanjem i dodavanjem svojstava ili filtriranjem događaja na osnovu vrednosti svojstava.

Koristite prečišćene događaje da biste smanjili opseg osnovnog događaja da [izvozi](export-events.md) ili uklanja svojstva koja nisu potrebna za izlaganje.

## <a name="create-refined-events"></a>Napravite istančane događaje

Postoje tri načina za kreiranje prečišćenog događaja iz osnovnog događaja. 

1. Idite na **Podaci**> **Događaji** i odaberite jednu od sledećih opcija:
    - Izaberite **Novi događaji**, a zatim izaberite **Kreiraj prečišćene događaje**.
    - Izaberite osnovni događaj da biste otvorili detaljan prikaz, pa sa gornjeg menija izaberite **Kreiraj prečišćene događaje**.
    - Izaberite **Još [...]** da biste otvorili meni sa prečicama za osnovni događaj. Zatim izaberite **Kreiraj prečišćene događaje**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Opcije za kreiranje prečišćenih događaja.":::

1. U dijalogu **Kreiranje prečišćenih događaja** unesite sledeće podatke:

- Izaberite događaj sa padajuće liste **Osnovni događaji** ako kreirate novi događaj.
- Unesite naziv u polje **Ime za prikaz prečišćenih događaja**.
- Opciono, ažurirajte predloženo **Stvarno ime** ne koristeći razmake.

3. Izaberite **Kreiraj** da biste primenili svoja podešavanja.

1. U detaljnom prikazu vašeg prečišćenog događaja izaberite **Dodavanje i uklanjanje svojstava** da biste otvoriti okno **Izmena svojstva**. 

1. Koristite polja za potvrdu da biste izabrali svojstva koja želite da prikažete i ona koja želite da sakrijete. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Uredite svojstva za prečišćene događaje.":::

1. Izaberite **Potvrdi** da biste primenili izbor.

1. Izaberite **Sačuvaj** da biste sačuvali konfiguraciju.

## <a name="edit-refined-events"></a>Uređivanje prečišćenih događaja

Možete da promenite naziv i svojstva prečišćenog događaja.

### <a name="edit-event-name"></a>Uređivanje naziva događaja

1. Idite na **Podaci** > **Događaji**. 
1. Izaberite **Još [...]** za događaj i izaberite **Uredi naziv**.
1. Ažurirajte naziv događaja i izaberite **Preimenuj**.

### <a name="edit-selected-properties"></a>Uređivanje izabranih svojstava

1. Idite na **Podaci** > **Događaji** i izaberite prečišćene događaje da biste otvorili detaljan prikaz.
1. Izaberite **Dodavanje i uklanjanje svojstava**. 
1. Uredite izbor polja za potvrdu.
1. Izaberite **Potvrdi**, a zatim **Sačuvaj** da biste primenili promene.

Za informacije o izvozu događaja, pogledajte [Izvoz događaja](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
