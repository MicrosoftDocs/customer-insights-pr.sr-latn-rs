---
title: Upravljanje dozvolama korisnika
description: Saznajte više o dozvolama i ulogama korisnika.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760390"
---
# <a name="user-permissions"></a>Korisničke dozvole

Na stranici **Dozvole** ćete postaviti uloge i dozvole za korišćenje uvida o korisnicima.

Morate imati administratorske dozvole da biste videli stranicu. Da biste pristupili stranici sa dozvolama u uvidima o korisnicima, idite na odeljak **Administrator** > **Dozvole**.

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
- Popunite odeljke *Objedinjavanje podataka* (**Mapiranje**, **Podudaranje** i **Objedinjavanje**) koji rezultiraju jedinstvenim entitetom profila klijenta.
- Definišite **Relacije** i **Aktivnosti**.
- Pomoću stranice **Segmenti** kreirajte segmente.
- Kreirajte mere koristeći stranicu **Mere**.
- Upravljajte konfiguracijom i obogatite korisničke profile na stranici **Obogaćivanje** (samo za obogaćivanje prve strane).
- Upravljajte i kreirajte izvoze na osnovu veza koje se dele sa saradnicima. [Saznajte više o tome kako administratori dozvoljavaju saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="administrator"></a>Administrator

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

## <a name="assign-roles-and-permissions"></a>Dodeljivanje uloga i dozvola

1. U uvidima o korisnicima idite na **Administrator** > **Dozvole**.

1. Izaberite **Dodajte korisnike** da biste otvorili okno **Dodavanje/uređivanje dozvola**.

1. Koristite polje **Pretraga** za pronalaženje Azure Active Directory korisnika ili grupe čije dozvole želite da prilagodite. Izaberite **ulogu** koju želite da dodelite tom korisniku ili grupi.

1. Izaberite stavku **Sačuvaj**. Trenutno okruženje će se automatski deliti sa korisnikom ili članovima grupe čija ste dozvole promenili. Korisnici mogu pristupiti aplikaciji Customer Insights i raditi u skladu sa određenom ulogom.

## <a name="view-current-permissions"></a>Prikaz trenutnih dozvola

U uvidima o korisnicima idite na **Administrator** > **Dozvole** da biste videli koje su dodele uloga trenutno aktivne.

- Kolona **Tip** određuje jednog korisnika, grupu ili aplikaciju. Sistem podržava pojedinačne korisnike i grupe.
- Uloge su navedene u koloni **Uloga**.
- Odaberite naslov bilo koje kolone da biste rezultate sortirali prema vrednosti te kolone.
- Koristite polje **Pretraga** na vrhu stranice da biste pronašli određene korisnike.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
