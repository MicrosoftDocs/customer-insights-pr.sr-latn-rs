---
title: Dodela dozvola korisnika
description: Saznajte više o dozvolama i ulogama korisnika.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245436"
---
# <a name="assign-user-permissions"></a>Dodela dozvola korisnika

Pristup uvidima korisnika je ograničen na korisnike u vašoj organizaciji koje administrator dodaje aplikaciji. Administrator može da dodaje, uređuje ili uklanja korisnike. Korisnik može biti jedan korisnik, grupa ili aplikacija. Postoje tri tipa uloga koje korisnik može da ima:

## <a name="viewer"></a>Gledalac

- Istražite uvide i segmente unutar stranica **Početak** i **Segmenti**.
- Pretražite i filtrirajte korisničke profile pomoću stranice **Klijenti**. Polja moraju da budu ona koja je moguće pretraživati.
- Prikaz i istraživanje stranice **Obogaćivanje**.
- Istražite i izvozite entitete pomoću stranice **Entiteti**.
- Pregledajte status sistemskih procesa koristeći stranicu **Sistem**.
- Pogledajte izvoz na stranici **Izvozi**.
- Instalirajte i koristite **Power BI Customer Insights** kontrolnu tablu.

## <a name="contributor"></a>Saradnik

- Sve dozvole su dostupne gledaocu.
- Učitajte i transformišite podatke koristeći stranicu **Izvori podataka**.
- Kompletno **ujedinjenje podataka** koje rezultira objedinjenim entitetom profila korisnika.
- Definišite **Relacije** i **Aktivnosti**.
- Pomoću stranice **Segmenti** kreirajte segmente.
- Kreirajte mere koristeći stranicu **Mere**.
- Upravljajte konfiguracijom i obogatite korisničke profile na stranici **Obogaćivanje** (samo za obogaćivanje prve strane).
- Upravljajte i kreirajte izvoz na osnovu [veza koje se dele sa saradnicima](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Admin

- Sve dozvole su dostupne saradniku.
- Promenite postavke na **stranici** "Sistem", uključujući radni jezik, osvežite rasporede sistemskih procesa i izvezite dijagnostičke evidencije.
- Promenite postavke na **stranici** "Bezbednost", uključujući korisnike, API ključeve, privatne veze i trezor ključa.
- Podesite definicije pretraživanja i filtriranja za stranicu Klijenti pomoću stranice **Indeks pretrage i filtriranja** (dostupno preko stranice **Klijenti**).
- Upravljajte vezama i dozvolite im druge korisničke uloge na stranici **Veze**.
- Upravljajte konfiguracijom i obogatite korisničke profile na stranici **Obogaćivanje** (za sva obogaćivanja).
- Upravljajte i kreirajte izvoz na stranici **Izvozi**.
- Instalirajte i koristite **Dodatak kartice Klijent**.
- Dodajte i koristite **Power Apps konektor**.
- Omogućavanje upotrebe [Customer Insights API-ja](apis.md).
- [Dodelite vlasništvo nad okruženjem](manage-environments.md#change-the-owner-of-an-environment) drugom administratoru.

## <a name="admin-owner"></a>Administrator (vlasnik)

- Sve dozvole dostupne administratoru.
- [Uspostavite početne vrednosti i](manage-environments.md#reset-an-existing-environment-preview) izbrišite okruženje.

## <a name="add-users"></a>Dodaj korisnike

1. Idite na karticu **"Administrator** > **bezbednosti**" i izaberite **karticu** "Korisnici".

1. Izaberite **Dodajte korisnike** da biste otvorili okno **Dodavanje/uređivanje dozvola**.

1. Koristite polje **"** Pretraži" da biste pronašli Azure Active Directory korisnika ili grupu koju želite da dodate. Izaberite **ulogu** koju želite da dodelite tom korisniku ili grupi.

1. Izaberite **Sačuvaj**. Trenutno okruženje se automatski deli sa korisnikom ili članovima grupe. Korisnici mogu pristupiti aplikaciji Customer Insights i raditi u skladu sa određenom ulogom.

## <a name="view-current-permissions"></a>Prikaz trenutnih dozvola

Idite na **karticu "** > **Administrator** bezbednosti" i izaberite **karticu** "Korisnici" da biste prikazali listu aktivnih korisnika i njihove dodele uloga. Listu korisnika možete da sortirate po bilo kojoj koloni ili da koristite polje za pretragu da biste pronašli određenog korisnika.

## <a name="manage-current-users"></a>Upravljanje trenutnim korisnicima

Idite na karticu **"Administrator** > **bezbednosti**" i izaberite **karticu** "Korisnici". Listu korisnika možete da sortirate po bilo kojoj koloni ili da koristite polje za pretragu da biste pronašli korisnika kojim želite da upravljate.

Izaberite korisnika da biste prikazali dostupne radnje.

- **Uredite** da biste uredili ulogu korisnika u "Uvidima kupaca". Kliknite na **dugme Sačuvaj** da biste potvrdili promenu.
- **Uklonite** da biste uklonili korisnika da nema pristup uvidima klijenata. Izaberite **Izbriši** da biste potvrdili brisanje.

[!INCLUDE [footer-include](includes/footer-banner.md)]
