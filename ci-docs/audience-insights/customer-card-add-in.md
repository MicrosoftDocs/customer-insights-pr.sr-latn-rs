---
title: Programski dodatak za karticu klijenta za Dynamics 365 aplikacije
description: Prikažite podatke iz uvida u ciljnu grupu u Dynamics 365 aplikacijama sa ovim programskim dodatkom.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6a7137730ab8cc43bc93daf647d9d55d02d96cd8
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692222"
---
# <a name="customer-card-add-in-preview"></a>Dodatak za karticu klijenta (pregled)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Steknite pregled svojih klijenata od 360 stepeni direktno u Dynamics 365 aplikacijama. Kada je programski dodatak za klijentsku karticu instaliran u podržanoj Dynamics 365 aplikaciji, možete odabrati da prikazujete demografske podatke, uvide i vremenske ose aktivnosti. Programski dodatak će preuzeti podatke iz usluge Customer Insights bez uticaja na podatke u povezanoj Dynamics 365 aplikaciji. 

## <a name="prerequisites"></a>Preduslovi

- Programski dodatak radi samo sa Dynamics 365 aplikacijama zasnovanim na modelu, kao što su Sales ili Customer Service, verzije 9.0 i novije.
- Da bi se vaši Dynamics 365 podaci mapirali u korisničke profile uvida u ciljnu grupu, oni treba da budu [uneti iz Dynamics 365 aplikacije pomoću Microsoft Dataverse konektora](connect-power-query.md).
- Svi Dynamics 365 korisnici programskog dodatka za kartice klijenta moraju biti [dodati kao korisnici](permissions.md) u uvidima u ciljnu grupu da biste videli podatke.
- [Konfigurisane mogućnosti pretrage i filtriranja](search-filter-index.md) u uvidima u ciljnu grupu su potrebne da bi pronalaženje podataka funkcionisalo.
- Svaka kontrola programskog dodatka oslanja se na određene podatke u uvidima u ciljnu grupu:
  - Kontrola mere: Zahteva [konfigurisane mere](measures.md).
  - Kontrola obaveštavanja: Zahteva podatke generisane korišćenjem [predviđanja](predictions.md) ili [prilagođenih modela](custom-models.md).
  - Demografska kontrola: Demografska polja (kao što su starost ili pol) dostupna su u objedinjenom profilu klijenta.
  - Kontrola obogaćivanja: Zahteva da se aktivna [obogaćivanja](enrichment-hub.md) primene se na profile klijenata.
  - Kontrola vremenske linije: Zahteva[ konfigurisane aktivnosti](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalirajte i koristite dodatak za karticu klijenta

Programski dodatak za karticu klijenta je rešenje za Customer Engagement aplikacije u sistemu Dynamics 365. Da biste instalirali rešenje, idite na AppSource i potražite **Dynamics karticu klijenta**. Izaberite [dodatak za karticu klijenta u usluzi AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i izaberite **Preuzmi odmah**.

Možda ćete morati da se prijavite pomoću akreditiva administratora za aplikaciju Dynamics 365 da biste instalirali rešenje.

Možda će biti potrebno neko vreme da se rešenje instalira u vaše okruženje.

## <a name="configure-the-customer-card-add-in"></a>Konfigurisanje dodatka klijentske kartice

1. Kao administrator, idite u odeljak **Podešavanja** u sistemu Dynamics 365 i izaberite **Rešenja**.

1. Izaberite vezu **Ime za prikaz** za rešenje **Dynamics 365 Customer Insights dodatak klijentske kartice (pregled)**.

   > [!div class="mx-imgBorder"]
   > ![Izaberite ime za prikaz.](media/select-display-name.png "Izaberite ime za prikaz")

1. Izaberite **Prijavljivanje** i unesite akreditive za nalog administratora koji koristite za konfigurisanje usluge Customer Insights.

   > [!NOTE]
   > Proverite da li blokator iskačućih prozora pregledača ne blokira prozor za potvrdu identiteta kada izaberete dugme **Prijavljivanje**.

1. Izaberite instancu Customer Insights okruženja iz kojeg želite da preuzmete podatke.

1. Definišite mapiranje polja na zapise u Dynamics 365 aplikaciji. U zavisnosti od vaših podataka u usluzi Customer Insights, možete odabrati da mapirate sledeće opcije:
   - Da biste mapirali kontakt, odaberite polje u entitetu klijenta koje se podudara sa ID-om vašeg entiteta kontakta.
   - Da biste mapirali poslovni kontakt, odaberite polje u entitetu klijenta koje se podudara sa ID-om vašeg entiteta poslovnog kontakta.

   > [!div class="mx-imgBorder"]
   > ![Polje ID kontakta.](media/contact-id-field.png "Polje ID kontakta")

1. Izaberite **Sačuvaj konfiguraciju** da biste sačuvali podešavanja.

1. Zatim treba da dodelite bezbednosne uloge u sistemu Dynamics 365 kako bi korisnici mogli da prilagođavaju i vide korisničku karticu. U sistemu Dynamics 365, idite na **Podešavanja** > **Bezbednost** > **Korisnici**. Izaberite korisnike da biste izmenili korisničke uloge i izaberite **Upravljaj ulogama**.

1. Dodelite ulogu **Stručnjak za prilagođavanje Customer Insights kartica** korisnicima koji će za celu organizaciju prilagođavati sadržaj prikazan na kartici.

## <a name="add-customer-card-controls-to-forms"></a>Dodajte kontrole kartice klijenta u obrasce
  
1. Da biste dodali kontrole kartice klijenta u obrazac za kontakt, idite na **Podešavanja** > **Prilagođavanja** u Dynamics 365.

1. Izaberite **Prilagodi sistem**.

1. Dođite do entiteta **Kontakt**, proširite ga, a zatim izaberite **Obrasci**.

1. Izaberite obrazac kontakta na koji želite da dodate kontrole kartice klijenta.

    > [!div class="mx-imgBorder"]
    > ![Izbor obrasca Kontakta.](media/contact-active-forms.png "Izbor obrasca Kontakta")

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

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Nadogradite rešenje u oblasti Prilagođavanje Dynamics 365 aplikacija.":::

1. Kada započnete proces nadogradnje, videćete indikator učitavanja dok se nadogradnja ne završi. Ako nema novije verzije, nadogradnja će prikazati poruku o grešci.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
