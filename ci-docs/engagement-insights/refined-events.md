---
title: Napravite i izmenite događaje
description: Kako da kreirate i menjate događaje.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 935dc4cd41218842e8406b747daef47de04e337a
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606262"
---
# <a name="create-and-modify-events"></a>Napravite i izmenite događaje

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Događaj je podatak koji predstavlja ponašanje korisnika, poput aktivnosti na veb-lokaciji.

- *Osnovni* događaj beleži kada korisnik prikaže stranicu (događaj prikaza) ili stupi u interakciju sa sadržajem (događaj radnje).
- *Prečišćeni* događaj je virtuelni prikaz osnovnog događaja. Prečišćene događaje definišete uklanjanjem i dodavanjem svojstava ili filtriranjem događaja na osnovu vrednosti svojstava.

## <a name="prerequisites"></a>Preduslovi

Da biste preuzeli događaje, podaci veb-lokacije moraju prvo biti povezani sa uvidima u angažovanje pomoću isečka koda. Za više informacija pogledajte [Instaliranje SDK-a za veb na veb-lokaciji](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Prvo povežite podatke.":::

## <a name="create-refined-events"></a>Kreiranje preciziranih događaja

Koristite prečišćene događaje da biste smanjili opseg osnovnog događaja da [izvozi](export-events.md) ili uklanja svojstva koja nisu potrebna za izlaganje.

> [!NOTE]
> Kada jednom dodate SDK za veb na svoju veb-lokaciju, možete prikazati svoje osnovne događaje i kreirati precizirane događaje. 

Da biste prikazali osnovne događaje:

1. Idite na odeljak **Podaci** u levom oknu za navigaciju.

1. Izaberite **Događaji** da biste videli listu svih događaja u radnom prostoru.

    :::image type="content" source="media/data-events.png" alt-text="Prikažite događaje.":::

Da biste kreirali preciziran događaj iz osnovnog događaja: 

1. Idite na **Podaci** > **Događaji** i izaberite **+ Novi događaji** pri vrhu ekrana.

1. U dijalogu **Novi događaji**, izaberite **Kreiraj prefinjene događaje**, a zatim izaberite **Sledeće**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Čarobnjak za nove događaje.":::
     
1. U dijalogu **Novi događaji**, unesite sledeće podatke:

   - Izaberite događaj sa padajuće liste **Osnovni događaji**.
   - Unesite naziv u polje **Ime za prikaz prečišćenih događaja**.
   - Opciono, ažurirajte predloženo **Stvarno ime** ne koristeći razmake.

1. Izaberite **Kreiraj** da biste primenili svoja podešavanja.

Precizirani događaj se sada pojavljuje na vašoj listi **Događaji**.

### <a name="edit-event-name"></a>Uređivanje naziva događaja

Možete promeniti naziv i svojstva osnovnog ili preciziranog događaja.

1. Idite na **Podaci** > **Događaji**. 

1. Izaberite **Još [...]** za događaj i izaberite **Uredi naziv**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Opcije za kreiranje prečišćenih događaja.":::

3. Ažurirajte naziv događaja i izaberite **Preimenuj**.

### <a name="view-the-details-of-a-refined-event"></a>Prikažite detalje preciziranog događaja:

1. Na listi **Događaj**, izaberite osnovni ili precizirani događaj. 

1. Izaberite **Dodaj i ukloni svojstva** pri vrhu ekrana da biste otvorili okno **Uređivanje svojstava**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Dodavanje i uklanjanje svojstava.":::

1. Koristite polja za potvrdu da biste izabrali svojstva koja želite da prikažete i ona koja želite da sakrijete. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Uredite svojstva za prečišćene događaje.":::

1. Izaberite **Potvrdi** da biste primenili svoj izbor, a zatim izaberite **Sačuvaj**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Uredite izabrana svojstva za precizirani događaj

1. Idite na **Podaci** > **Događaji** i izaberite prečišćene događaje da biste otvorili detaljan prikaz.
1. Izaberite **Dodavanje i uklanjanje svojstava**. 
1. Uredite izbor polja za potvrdu.
1. Izaberite **Potvrdi**, a zatim **Sačuvaj** da biste primenili promene.

Za informacije o izvozu događaja, pogledajte [Izvoz događaja](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
