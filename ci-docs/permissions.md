---
title: Upravljanje dozvolama korisnika
description: Saznajte više o dozvolama i ulogama korisnika.
ms.date: 02/09/2022
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
ms.openlocfilehash: 30b37645cad4e795ef20579e20e3f2bbdb2afbf6
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054903"
---
# <a name="manage-user-permissions"></a>Upravljanje dozvolama korisnika

Stranica **"Dozvole** " je mesto gde ćete podesiti uloge i dozvole za korišćenje uvida klijenata.

Morate imati administratorske dozvole da biste videli stranicu. Da biste pristupili stranici sa dozvolama, posetite stranicu "**Administrator bezbednosti** > **·** > **"**.

Postoje tri vrste uloga:

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
- Dovršavanje ***Ujedinjenje** podataka koje rezultira objedinjenim entitetom profila korisnika.
- Definišite **Relacije** i **Aktivnosti**.
- Pomoću stranice **Segmenti** kreirajte segmente.
- Kreirajte mere koristeći stranicu **Mere**.
- Upravljajte konfiguracijom i obogatite korisničke profile na stranici **Obogaćivanje** (samo za obogaćivanje prve strane).
- Upravljajte i kreirajte izvoze na osnovu veza koje se dele sa saradnicima. [Saznajte više o tome kako administratori dozvoljavaju saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Admin

- Sve dozvole su dostupne saradniku.
- Promenite podešavanja na stranici **Sistem**, uključujući radni jezik i raspored osvežavanja za vaše sistemske procese.
- Pregledajte i dodajte dozvole koristeći stranicu **Dozvole**.
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

## <a name="assign-roles-and-permissions"></a>Dodeljivanje uloga i dozvola

1. Idite na **administratorski** > **bezbednosni** > **Korisnici***.

1. Izaberite **Dodajte korisnike** da biste otvorili okno **Dodavanje/uređivanje dozvola**.

1. Koristite polje **Pretraga** za pronalaženje Azure Active Directory korisnika ili grupe čije dozvole želite da prilagodite. Izaberite **ulogu** koju želite da dodelite tom korisniku ili grupi.

1. Izaberite stavku **Sačuvaj**. Trenutno okruženje će se automatski deliti sa korisnikom ili članovima grupe čija ste dozvole promenili. Korisnici mogu pristupiti aplikaciji Customer Insights i raditi u skladu sa određenom ulogom.

## <a name="view-current-permissions"></a>Prikaz trenutnih dozvola

Posetite lokaciju **"Korisnici** > **administratora** > **bezbednosti** " da biste videli koje dodele uloga su trenutno aktivne.

- Kolona **Tip** određuje jednog korisnika, grupu ili aplikaciju. Sistem podržava pojedinačne korisnike i grupe.
- Uloge su navedene u koloni **Uloga**.
- Odaberite naslov bilo koje kolone da biste rezultate sortirali prema vrednosti te kolone.
- Koristite polje **Pretraga** na vrhu stranice da biste pronašli određene korisnike.


[!INCLUDE [footer-include](includes/footer-banner.md)]
