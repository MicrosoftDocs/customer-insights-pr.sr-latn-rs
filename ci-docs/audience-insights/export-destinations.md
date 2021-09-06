---
title: Izvoz podataka iz usluge Customer Insights
description: Upravljajte izvozima da biste delili podatke.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: be4d142e0f9f422cac459f603aa5dd8bb490321cfe1b2de58f4a128ae56f4ba3
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034699"
---
# <a name="exports-preview-overview"></a>Pregled izvoza (verzija za pregled)

Stranica **Izvoz** prikazuje sve konfigurisane izvoze. Izvozi dele određene podatke sa raznim aplikacijama. Mogu da uključuju profile klijenata ili entitete, šeme i detalje o mapiranju. Svaki izvoz zahteva [vezu koju je postavio administrator radi upravljanja potvrdom identiteta i pristupom](connections.md).

Idite na **Podaci** > **Izvozi** da biste videli stranicu izvoza. Sve korisničke uloge mogu pregledati konfigurisane izvoze. Koristite polje za pretragu na komandnoj traci da biste pronašli izvoze prema njihovom nazivu, nazivu veze ili tipu veze.

## <a name="set-up-a-new-export"></a>Podešavanje novog izvoza

Da biste podesili ili uredili izvoz, moraju vam biti dostupne veze. Veze zavise od vaše [korisničke uloge](permissions.md):
- Administratori imaju pristup svim vezama. Oni takođe mogu da kreiraju nove veze prilikom podešavanja izvoza.
- Saradnici mogu imati pristup određenim vezama. Oni zavise od administratora da konfigurišu i dele veze. Lista izvoza u koloni **Vaše dozvole** pokazuje saradnicima da li mogu da uređuju ili samo prikazuju izvoz. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Gledaoci mogu samo da vide postojeće izvoze, ali ne i da ih kreiraju.

### <a name="define-a-new-export"></a>Definisanje novog izvoza

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz** da biste kreirali novi izvoz.

1. U oknu **Podešavanje izvoza**, izaberite koju vezu da koristite. [Vezama](connections.md) upravljaju administratori. 

1. Navedite potrebne detalje i izaberite **Sačuvati** da biste kreirali izvoz.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Definišite novi izvoz na osnovu postojećeg izvoza

1. Idite na **Podaci** > **Izvozi**.

1. Na listi izvoza, izaberite izvoz koji želite da duplirate.

1. Izaberite **Napravi duplikat** u komandnoj traci da biste otvorili okno **Podešavanje izvoza** sa detaljima izabranog izvoza.

1. Pregledajte i prilagodite izvoz i izaberite **Sačuvaj** da biste kreirali novi izvoz.

### <a name="edit-an-export"></a>Uređivanje izvoza

1. Idite na **Podaci** > **Izvozi**.

1. Na listi izvoza, izaberite izvoz koji želite da uređujete.

1. Na komandnoj traci izaberite **Uredi**.

1. Promenite vrednosti koje želite da ažurirate i izaberite **Sačuvaj**.

## <a name="view-exports-and-export-details"></a>Prikaz izvoza i detalji o izvozu

Nakon kreiranja odredišta za izvoz, ona su navedena na stranici **Podaci** > **Izvoz**. Svi korisnici mogu videti koji se podaci dele i koji je njihov najnoviji status.

1. Idite na **Podaci** > **Izvozi**.

1. Korisnici bez dozvole za uređivanje biraju **Prikaz** umesto **Uređivanje** da videli detalje o izvozu.

1. Bočno okno prikazuje konfiguraciju izvoza. Bez dozvola za uređivanje ne možete menjati vrednosti. Izaberite **Zatvori** da biste se vratili na stranicu izvoza.

## <a name="schedule-and-run-exports"></a>Planiranje i pokretanje izvoza

Svaki izvoz koji konfigurišete ima raspored osvežavanja. Tokom osvežavanja, sistem traži nove ili ažurirane podatke koje će uključiti u izvoz. Podrazumevano se izvozi kao deo svakog [zakazanog osvežavanja sistema](system.md#schedule-tab). Možete prilagoditi raspored osvežavanja ili ga isključiti za ručno pokretanje izvoza.

Rasporedi izvoza zavise od statusa vašeg okruženja. Ako su u toku ažuriranja [zavisnih elemenata](system.md#refresh-policies) kada treba da započne planirani izvoz, sistem će prvo dovršiti ažuriranja, a zatim pokrenuti izvoz. U koloni **Osveženo** možete videti kada je izvoz poslednji put osvežen.

### <a name="schedule-exports"></a>Raspored izvoza

Možete da definišete prilagođene rasporede osvežavanja za pojedinačne izvoze ili nekoliko izvoza odjednom. Trenutno definisani raspored naveden je u koloni **Raspored** liste izvoza. Dozvola za promenu rasporeda je ista kao i za [uređivanje i definisanje izvoza](export-destinations.md#set-up-a-new-export). 

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite izvoz koji želite da zakažete.

1. Na komandnoj traci izaberite **Zakaži**.

1. U oknu **Zakazivanje izvoza**, podesite **Izvršavanje rasporeda** na **Uključeno** da biste automatski pokretali izvoz. Podesite na **Isključeno** da biste ga ručno osvežavali.

1. Da biste automatski osvežavali izvoze, odaberite vrednost **Ponavljanje** i navedite detalje za nju. Definisano vreme se odnosi na sve slučajeve ponavljanja. To je vreme kada bi izvoz trebalo da počne da se osvežava.

1. Primenite i aktivirajte promene izborom **Sačuvaj**.

Kada uređujete raspored za nekoliko izvoza, potrebno je da napravite izbor pod **Zadržite ili izmenite rasporede**:
- **Zadržite pojedinačne rasporede**: Zadržite prethodno definisani raspored za izabrane izvoze i samo ih onemogućite ili omogućite.
- **Definišite novi raspored za sve izabrane izvoze**: Izmenite postojeće rasporede izabranih izvoza.

### <a name="run-exports-on-demand"></a>Pokretanje izvoza na zahtev

Da biste izvezli podatke bez čekanja na zakazano osvežavanje, idite na stranicu **Podaci** > **Izvoz**.

- Da biste pokrenuli sve izvoze, izaberite **Pokreni sve** u komandnoj traci. Ova radnja će pokretati samo izvoze koji imaju aktivan raspored.
- Da biste pokrenuli jedan izvoz, izaberite ga na listi i izaberite **Pokreni** u komandnoj traci. Tako pokrećete izvoze bez aktivnog rasporeda. 

## <a name="remove-an-export"></a>Uklanjanje izvoza

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite izvoz koji želite da uklonite.

1. Izaberite **Ukloni** na komandnoj traci.

1. Potvrdite uklanjanje odabirom **Ukloni** na ekranu za potvrdu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
