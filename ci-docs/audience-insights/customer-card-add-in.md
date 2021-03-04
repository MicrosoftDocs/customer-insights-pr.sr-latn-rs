---
title: Instalirajte i konfigurišite Dodatak za karticu klijenta
description: Instalirajte i konfigurišite dodatak za karticu klijenta za Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268061"
---
# <a name="customer-card-add-in-preview"></a>Dodatak za karticu klijenta (pregled)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Steknite pregled svojih klijenata od 360 stepeni direktno u Dynamics 365 aplikacijama. Prikažite demografske podatke, uvide i vremenske rokove aktivnosti pomoću dodatka kartice klijenta.

## <a name="prerequisites"></a>Preduslovi

- Aplikacija Dynamics 365 (kao što je Čvorište za prodaju ili čvorište korisničke službe), verzije 9.0 i novije sa omogućenim objedinjenim interfejsom.
- Profili klijenata [uneti iz aplikacije Dynamics 365 pomoću usluge Common Data Service](connect-power-query.md).
- Korisnici Dodatka za karticu klijenta moraju biti [dodati kao korisnici](permissions.md) u uvidima o korisnicima.
- [Konfigurisane mogućnosti pretraživanja i filtriranja](search-filter-index.md).
- Demografska kontrola: Demografska polja (kao što su starost ili pol) dostupna su u objedinjenom profilu klijenta.
- Kontrola obogaćivanja: Zahteva da se aktivna [obogaćivanja](enrichment-hub.md) primene se na profile klijenata.
- Kontrola obaveštavanja: Zahteva podatke generisane pomoću Azure mašinskog učenja ([predviđanja](predictions.md) ili [prilagođeni modeli](custom-models.md))
- Kontrola mere: Zahteva [konfigurisane mere](measures.md).
- Kontrola vremenske linije: Zahteva[ konfigurisane aktivnosti](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalirajte i koristite dodatak za karticu klijenta

Programski dodatak za karticu klijenta je rešenje za Customer Engagement aplikacije u sistemu Dynamics 365. Da biste instalirali rešenje, idite na AppSource i potražite **Dynamics karticu klijenta**. Izaberite [dodatak za karticu klijenta u usluzi AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i izaberite **Preuzmi odmah**.

Možda ćete morati da se prijavite pomoću akreditiva administratora za aplikaciju Dynamics 365 da biste instalirali rešenje.

Možda će biti potrebno neko vreme da se rešenje instalira u vaše okruženje.

## <a name="configure-the-customer-card-add-in"></a>Konfigurisanje dodatka klijentske kartice

1. Kao administrator, idite u odeljak **Podešavanja** u sistemu Dynamics 365 i izaberite **Rešenja**.

1. Izaberite vezu **Ime za prikaz** za rešenje **Dynamics 365 Customer Insights dodatak klijentske kartice (pregled)**.

   > [!div class="mx-imgBorder"]
   > ![Izaberite ime za prikaz](media/select-display-name.png "Izaberite ime za prikaz")

1. Izaberite **Prijavljivanje** i unesite akreditive za nalog administratora koji koristite za konfigurisanje usluge Customer Insights.

   > [!NOTE]
   > Proverite da li blokator iskačućih prozora pregledača ne blokira prozor za potvrdu identiteta kada izaberete dugme **Prijavljivanje**.

1. Izaberite okruženje iz kojeg želite da preuzmete podatke.

1. Definišite koje se mapiranje polja snima u aplikaciji Dynamics 365.
   - Da biste mapirali kontakt, odaberite polje u entitetu klijenta koje se podudara sa ID-om vašeg entiteta kontakta.
   - Da biste mapirali poslovni kontakt, odaberite polje u entitetu klijenta koje se podudara sa ID-om vašeg entiteta poslovnog kontakta.

   > [!div class="mx-imgBorder"]
   > ![Polje ID kontakta](media/contact-id-field.png "Polje ID kontakta")

1. Izaberite **Sačuvaj konfiguraciju** da biste sačuvali podešavanja.

1. Zatim treba da dodelite bezbednosne uloge u sistemu Dynamics 365 kako bi korisnici mogli da prilagođavaju i vide korisničku karticu. U sistemu Dynamics 365, idite na **Podešavanja** > **Bezbednost** > **Korisnici**. Izaberite korisnike da biste izmenili korisničke uloge i izaberite **Upravljaj ulogama**.

1. Dodelite ulogu **Stručnjak za prilagođavanje Customer Insights kartica** korisnicima koji će za celu organizaciju prilagođavati sadržaj prikazan na kartici.

## <a name="add-customer-card-controls-to-forms"></a>Dodajte kontrole kartice klijenta u obrasce
  
1. Da biste dodali kontrole kartice klijenta u obrazac za kontakt, idite na **Podešavanja** > **Prilagođavanja** u Dynamics 365.

1. Izaberite **Prilagodi sistem**.

1. Dođite do entiteta **Kontakt**, proširite ga, a zatim izaberite **Obrasci**.

1. Izaberite obrazac kontakta na koji želite da dodate kontrole kartice klijenta.

    > [!div class="mx-imgBorder"]
    > ![Izbor obrasca Kontakta](media/contact-active-forms.png "Izbor obrasca Kontakta")

1. Da biste dodali kontrolu, u uređivaču obrazaca prevucite bilo koje polje iz **Istraživača polja** tamo gde želite da se kontrola prikazuje.

1. Izaberite polje na obrascu koje ste upravo dodali, a zatim izaberite **Promeni svojstva**.

1. Idite do kartice **Kontrole** i izaberite **Dodaj kontrolu**. Izaberite neku od dostupnih prilagođenih kontrola i izaberite **Dodaj**.

1. U dijalogu **Svojstva polja**, obrišite polje za potvrdu **Prikažite oznaku na obrascu**.

1. Izaberite opciju **Veb** za kontrolu. Za kontrolu obogaćivanja izaberite tip obogaćivanja koji želite da prikažete konfigurisanjem polja **Tip obogaćivanja**. Dodajte zasebnu kontrolu obogaćivanja za svaku vrstu obogaćivanja.

1. Izaberite **Sačuvaj** i **Objavi** da biste objavili ažurirani obrazac za kontakt.

1. Idite na objavljeni obrazac kontakta. Videćete novododatu kontrolu. Možda ćete morati da se prijavite prilikom prvog korišćenja.

1. Da biste prilagodili šta želite da prikažete na prilagođenoj kontroli, izaberite dugme za uređivanje u gornjem desnom uglu.

## <a name="upgrade-customer-card-add-in"></a>Nadogradnja programskog dodatka za karticu klijenta
Programski dodatak za korisničku karticu se ne nadograđuje automatski. Da biste nadogradili na najnoviju verziju, sledite ovaj postupak u Dynamics 365 aplikaciji u kojoj je instaliran programski dodatak.

1. U Dynamics 365 aplikaciji idite na **Podešavanja** > **Prilagođavanje** i izaberite **Rešenja**.

1. U tabeli dodataka potražite **CustomerInsightsCustomerCard** i izaberite red.

1. Izaberite **Primeni nadogradnju rešenja** u traci sa radnjama.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Nadogradite rešenje u oblasti Prilagođavanje Dynamics 365 aplikacija":::

1. Kada započnete proces nadogradnje, videćete indikator učitavanja dok se nadogradnja ne završi. Ako nema novije verzije, nadogradnja će prikazati poruku o grešci.


[!INCLUDE[footer-include](../includes/footer-banner.md)]