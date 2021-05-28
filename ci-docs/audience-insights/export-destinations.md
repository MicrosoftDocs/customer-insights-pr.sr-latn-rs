---
title: Izvoz podataka iz usluge Customer Insights
description: Upravljajte izvozima da biste delili podatke.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016653"
---
# <a name="exports-preview-overview"></a>Pregled izvoza (verzija za pregled)

Stranica **Izvoz** prikazuje sve konfigurisane izvoze. Izvozi dele određene podatke sa raznim aplikacijama. Mogu da uključuju profile klijenata ili entitete, šeme i detalje o mapiranju. Svaki izvoz zahteva [vezu koju je postavio administrator radi upravljanja potvrdom identiteta i pristupom](connections.md).

Idite na **Podaci** > **Izvozi** da biste videli stranicu izvoza. Sve korisničke uloge imaju pristup za prikaz konfigurisanih izvoza. Koristite polje za pretragu na komandnoj traci da biste pronalazili izvoze prema njihovom nazivu, nazivu veze ili tipu veze.

## <a name="set-up-a-new-export"></a>Podešavanje novog izvoza

Da biste podesili ili uredili izvoz, moraju vam biti dostupne veze. Veze zavise od vaše [korisničke uloge](permissions.md):
- Administratori imaju pristup svim vezama. Oni takođe mogu da kreiraju nove veze prilikom podešavanja izvoza.
- Saradnici mogu imati pristup određenim vezama. Oni zavise od administratora da konfigurišu i dele veze. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Gledaoci mogu samo da vide postojeće izvoze, ali ne i da ih kreiraju.

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz** da biste kreirali novo odredište za izvoz.

1. U oknu **Podešavanje izvoza**, izaberite koju vezu da koristite. [Vezama](connections.md) upravljaju administratori. 

1. Navedite potrebne detalje i izaberite **Sačuvati** da biste kreirali izvoz.

### <a name="edit-an-export"></a>Uređivanje izvoza

1. Izaberite vertikalne tri tačke za odredište za izvoz koje želite da uređujete.

1. U padajućem meniju izaberite **Uredi**.

1. Promenite vrednosti koje želite da ažurirate i izaberite **Sačuvaj**.

## <a name="view-exports-and-export-details"></a>Prikaz izvoza i detalji o izvozu

Nakon kreiranja odredišta za izvoz, ona su navedena na stranici **Podaci** > **Izvoz**. Svi korisnici mogu videti koji se podaci dele i koji je njihov najnoviji status.

1. Idite na **Podaci** > **Izvozi**.

1. Korisnici bez dozvole za uređivanje biraju **Prikaži** umesto **Uredi** da bi videli detalje o izvozu.

1. Ovo bočno okno prikazuje podešavanje ovog izvoza. Bez dozvola za uređivanje ne možete menjati vrednosti. Izaberite **Zatvori** da biste se vratili na stranicu izvoza.

## <a name="run-exports-on-demand"></a>Pokretanje izvoza na zahtev

Nakon konfigurisanja, izvoz će se pokrenuti sa svakim [zakazanim osvežavanjem](system.md#schedule-tab) sve dok ima funkcionalnu vezu.

Da biste izvezli podatke bez čekanja na zakazano osvežavanje, idite na stranicu **Podaci** > **Izvoz**. Na raspolaganju su vam dve opcije:

- Da biste pokrenuli sve izvoze, izaberite **Pokreni sve** u komandnoj traci. 
- Da biste pokrenuli pojedinačni izvoz, izaberite tri tačke (...) na stavci liste, a zatim odaberite **Pokreni**.

## <a name="remove-an-export"></a>Uklanjanje izvoza

1. Idite na **Podaci** > **Izvozi**.

1. Odaberite vertikalne tri tačke za izvoz koji želite da uklonite.

1. Izaberite **Ukloni** iz padajućeg menija.

1. Potvrdite uklanjanje odabirom **Ukloni** na ekranu za potvrdu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
