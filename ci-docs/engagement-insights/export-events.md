---
title: Izvoz prečišćenih događaja
description: Kako da izvezete prečišćene događaje i osnovne događaje.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032402"
---
# <a name="export-events"></a>Izvoz događaja

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Događaj predstavlja ponašanje korisnika. On beleži kada korisnik prikaže stranicu (događaj prikaza) ili stupi u interakciju sa sadržajem (događaj radnje). Kada možete da odlučite koja svojstva podataka želite da prikažete u izveštaju, ovaj virtuelni prikaz podataka naziva se *prečišćenim događajem*. 

- Događaje i prečišćene događaje možete da izvezete u spoljnu memoriju. 
- Izvozi su tok za prosleđivanje podataka. Ne možete da dopunite tok. 
- Izvozi imaju fiksne šeme. Ako događaju dodate prilagođena svojstva, ona neće biti uključena. Moraćete da kreirate novi izvoz.

## <a name="prerequisites"></a>Preduslovi

Pre podešavanja izvoza treba da imate pristup i aktivnu pretplatu na Azure portal. Informacije o nalogu za skladištenje biće vam potrebne tokom procesa izvoza. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Kreiranje Azure Data Lake Storage Gen 2 naloga

1. Prijavite se na Azure portal i [kreirajte novi nalog za skladištenje](/azure/storage/common/storage-account-create). 

1. Obavezno omogućite **Hijerarhijski prostor za ime** na kartici **Napredno**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Omogućite hijerarhijski prostor za ime na kartici Napredno.":::

1. Nakon što primene, idite na novokreirani nalog za skladištenje. U oknu za navigaciju izaberite **Podešavanja** > **Pristupni ključevi**. 

1. Kopirajte **Naziv naloga** i **Ključ** da biste ih koristili prilikom kreiranja novog izvoza.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Ključevi za pristup u nalogu za skladištenje.":::

## <a name="export-events"></a>Izvoz događaja

Postoje dva načina izvoza događaja: 
- Idite na **Podaci** > **Izvozi** i izaberite **Novi izvoz**.
- Idite na **Podaci** > **Događaji**, izaberite **Još [...]** pored događaja koji želite da izvezete i izaberite **Izvoz** iz padajućeg menija. 

Navodiće vas kroz korake za kreiranje izvoza:

1. Navedite **Naziv za izvoz**.

1. U padajućoj listi **Izbor događaja**, odaberite osnovne događaje i precizirane događaje koje ćete uključiti u izvoz. 

1. U okviru **Strukture datoteke**, izaberite kadencu za kreiranje novih datoteka u odredišnom skladištu. Događaji se izvoze kontinuirano kako dolaze.

1. Izaberite format za izvoz. Možete birati između **Common Data Model**, **CSV** i **JSON** formata. Da biste koristili izvoz sa drugim Dynamics 365 aplikacijama, preporučujemo da korišćenje Common Data Model formata.

1. U koraku **Odabir odredišta**, navedite Azure Data Lake Storage Gen 2. lokacije.
    1. **Naziv ADLS Gen 2 naloga** je naziv naloga za skladištenje u kojem želite da sačuvate izvoz. 
    1. **Putanja do direktorijuma** definiše gde izvoz treba biti uskladišten u sistemu datoteka i strukturi direktorijuma naloga za skladištenje.
    1. **Deljeni ključ** je dostupan sa Azure portala za nalog za skladištenje.

1. Pregledajte i potvrdite izabrane opcije.

## <a name="view-and-manage-exports"></a>Prikaz izvoza i upravljanje njima

Kada konfigurišete izvoz, idite na **Podaci** > **Izvozi** kako biste ga prikazali. Izaberite **Još [...]** za bilo koji postojeći izvoz da biste ga uredili ili izbrisali.


[!INCLUDE[footer-include](../includes/footer-banner.md)]