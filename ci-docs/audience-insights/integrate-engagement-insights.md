---
title: Integrisanje veb-podataka iz uvida o angažovanju sa uvidima o korisnicima
description: Donesite veb-informacije o kupcima iz uvida o angažovanju sa uvidima o korisnicima.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mukeshpo
manager: shellyha
ms.openlocfilehash: ba1cf6c7e85b8fe90baf34018f1309095573adf1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267693"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integrisanje veb-podataka iz uvida o angažovanju sa uvidima o korisnicima

Klijenti često svakodnevno obavljaju transakcije na mreži koristeći veb-stranice. Sposobnost uvida u angažman u usluzi Dynamics 365 Customer Insights je zgodno rešenje za integrisanje veb-podataka kao izvora. Pored podataka o transakcijama, demografskim podacima ili ponašanju, aktivnosti na vebu možemo videti i u objedinjenim profilima klijenata. Ovaj profil možemo koristiti za sticanje dodatnih uvida poput segmenata, mera ili predviđanja za aktivaciju korisnika.

Ovaj članak opisuje korake za unošenje podataka o veb-aktivnostima vaših klijenata iz uvida u angažovanja u vaše postojeće okruženje za uvide o korisnicima.

U ovom primeru, pretpostavljamo da okruženje sadrži objedinjene profile klijenata. Profili su objedinjeni sa izvorima iz anketa, maloprodaje i sistema za prodaju ulaznica. Takođe prikazuje povezane aktivnosti klijenata. 

Sada želimo da znamo da li klijent posećuje naše veb-proizvode i razume njihove aktivnosti. Aktivnosti uključuju, na primer, posećene veb-lokacije ili pregledane stranice proizvoda putem veze primljene u e-poruci.

## <a name="prerequisites"></a>Preduslovi

Da bi se integrisali podaci iz uvida u angažovanje, potrebno je ispuniti nekoliko preduslova: 

- Integrišite SDK za uvid u angažovanje sa svojom veb-lokacijom. Za više informacija, pogledajte [Započnite rad sa paketom za razvoj softvera na vebu](../engagement-insights/instrument-website.md).
- Izvoz veb-događaja iz uvida o angažovanju zahteva pristup nalogu za skladištenje ADLS Gen 2 koji će se koristiti za unos podataka o veb-događajima u uvidima o korisnicima. Za više informacija, pogledajte članak [Izvoz događaja](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Konfigurisanje preciziranih događaja u uvidima o angažovanju

Kada administrator opremi veb-lokaciju SDK-om za uvide u angažovanje, *osnovni događaji* se prikupljaju kada korisnik pregleda veb-stranicu ili klikne negde. Osnovni događaji obično sadrže brojne detalje. U zavisnosti od slučaja upotrebe, potreban vam je podskup podataka samo u osnovnom događaju. Uvidi o angažovanju omogućavaju vam da kreirate *precizirane događaje* koji sadrže samo svojstva osnovnog događaja koji ste izabrali.     

Za više informacija, pogledajte [Kreiranje i izmena preciziranih događaja](../engagement-insights/refined-events.md).

Razmatranja prilikom kreiranja preciziranih događaja: 

- Navedite smisleno ime za precizirani događaj. Koristi se kao naziv aktivnosti u uvidima o korisnicima.
- Izaberite barem sledeća svojstva da biste kreirali aktivnost u uvidima o korisnicima: 
    - Signal.Action.Name – označava detalje aktivnosti
    - Signal.User.Id – koristi se za mapiranje sa ID-om klijenta
    - Signal.View.Uri – koristi se kao veb-adresa kao osnova za segmente ili mere
    - Signal.Export.Id – da se koristi kao primarni ključ za događaje <!-- system generated, do we need to list?-->
    - Signal.Timestamp – za određivanje datuma i vremena aktivnosti

Izaberite filtere da biste se usredsredili na događaje i stranice koji su važni za vaš slučaj upotrebe. U ovom primeru ćemo koristiti naziv radnje „Promocija e-poštom“.

## <a name="export-the-refined-web-events"></a>Izvezite precizirane veb-događaje 

Nakon definisanja preciziranog događaja, morate konfigurisati izvoz podataka događaja u Azure Data Lake Storage, koji se može postaviti kao izvor podataka za unos u uvide o korisnicima. Izvozi se dešavaju neprestano dok događaji proističu iz veb-svojstva.

Za više informacija, pogledajte članak [Izvoz događaja](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Unos podataka o događaju u uvide o korisnicima

Sada kada ste definisali precizirani događaj i konfigurisali njegov izvoz, prelazimo na unošenje podataka u uvide o korisnicima. Treba da kreirate novi izvor podataka zasnovan na Common Data Model fascikli. Unesite detalje za nalog skladišta u koji izvozite događaje. U datoteci *default.cdm.json* izaberite precizirani događaj koji ćete uneti i kreirajte entitet u uvidima o korisnicima.

Za više informacija, pogledajte [Povezivanje sa Common Data Model fasciklom pomoću Azure Data Lake naloga](connect-common-data-model.md)


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Povežite precizirane podatke o događajima kao aktivnost profila klijenta

Kada dovršite unosa entiteta, možete da konfigurišete aktivnost za profil klijenta.

Za više informacija pogledajte [aktivnosti klijenta](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Stranica aktivnosti sa proširenim oknom Uređivanje aktivnosti i popunjavanjem polja.":::

Konfigurišite novu aktivnost sa sledećim mapiranjem: 

- **Primarni ključ:** Signal.Export.Id, jedinstveni ID koji je dostupan za svaki zapis događaja u uvidima o angažovanju. Ovo svojstvo se automatski generiše.

- **Vremenska oznaka:** Signal.Timestamp u svojstvu događaja.

- **Događaj:** Signal.Name, naziv događaja koji želite da pratite.

- **Veb-adresa:** Signal.View.Uri koji se odnosi na URI stranice koja je kreirala događaj.

- **Detalji:** Signal.Action.Name da predstavlja informacije koje treba povezati sa događajem. Izabrano svojstvo u ovom slučaju označava da je događaj namenjen promociji putem e-pošte.

- **Tip aktivnosti:** U ovom primeru biramo postojeći tip aktivnosti WebLog. Ovaj izbor je korisna opcija filtera za pokretanje modela predviđanja ili kreiranje segmenata na osnovu ove vrste aktivnosti.

- **Uspostavljanje relacije:** Ovo važno podešavanje veže aktivnost za postojeće profile klijenata. **Signal.User.Id** je identifikator konfigurisan u SDK-u koji se prikuplja i koji se odnosi na korisnički ID u drugim izvorima podataka koji su konfigurisani u uvidima o klijentima. U ovom primeru konfigurišemo relaciju između Signal.User.Id i RetailCustomers:CustomerRetailId, što je primarni ključ koji je definisan u koraku mape u procesu objedinjavanja podataka.


Nakon obrade aktivnosti, možete pregledati evidenciju klijenata i otvoriti karticu klijenta da biste na vremenskoj osi videli aktivnosti iz uvida u angažovanje. 

> [!TIP]
> Da biste pronašli ID klijenta koji ima aktivnost uvida u angažovanje, idite u odeljak **Entiteti** i pregledajte podatke za entitet UnifiedActivity. ActivityTypeDisplay = WebLog sadrži aktivnost uvida u angažovanje konfigurisanu u primeru iznad. Kopirajte ID klijenta za jedan od tih zapisa i za taj ID na stranici **Klijenti**.

## <a name="next-steps"></a>Sledeći koraci

Sada možete da kreirate [segmente](segments.md), [mere](measures.md) i [predviđanja](predictions.md) kako biste uspostavili smislenu vezu sa svojim klijentima.


[!INCLUDE[footer-include](../includes/footer-banner.md)]