---
title: Programski dodatak za karticu kupca za Dynamics 365 aplikacije (sadrži video)
description: Prikaži podatke profila klijenata iz aplikacija "Uvidi kupaca" u Dynamics 365 pomoću ovog programskog dodatka.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8508880bb3274bb491a314a043a5222d4d381073
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755653"
---
# <a name="customer-card-add-in-preview"></a>Dodatak za karticu klijenta (pregled)

Steknite pregled svojih klijenata od 360 stepeni direktno u Dynamics 365 aplikacijama. Sa instaliranim programskim dodatkom Kartica klijenta u podržanoj Dynamics 365 aplikaciji, možete odabrati da prikazujete polja profila klijenta, uvide i vremensku osu aktivnosti. Programski dodatak će preuzeti podatke iz usluge Customer Insights bez uticaja na podatke u povezanoj Dynamics 365 aplikaciji.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Preduslovi

- Programski dodatak radi samo sa Dynamics 365 aplikacijama zasnovanim na modelu, kao što su Sales ili Customer Service, verzije 9.0 i novije.
- Da bi se Vaši Dynamics 365 podaci mapirali u profile klijenata "Uvidi kupaca", preporučujemo da se oni unose [iz Dynamics 365 aplikacije pomoću Microsoft Dataverse linije spajanja](connect-power-query.md). Ako koristite drugi metod za unos Dynamics 365 kontakata (ili poslovnih kontakata), morate se uveriti `contactid` da je polje (ili `accountid`) postavljeno [kao primarni ključ za taj izvor podataka u koraku mape procesa ujedinjenja podataka](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Svi Dynamics 365 korisnici programskog dodatka "Kartica kupca" moraju biti [dodati kao korisnici u programu](permissions.md) Customer Insights da bi videli podatke.
- [Konfigurisane mogućnosti pretraživanja i filtriranja u](search-filter-index.md) uvidima klijenata su potrebne za pronalaženje podataka za rad.
- Svaka kontrola programskog dodatka oslanja se na određene podatke u uvidima klijenata. Neki podaci i kontrole dostupni su samo u određenim tipovima okruženja. Konfiguracija programskog dodatka će vas obavestiti ako kontrola nije dostupna zbog izabranog tipa okruženja. Saznajte više o [slučajevima upotrebe okruženja](work-with-business-accounts.md).
  - **Kontrola mera**: Zahteva [konfigurisane mere](measures.md) atributa tipa korisnika.
  - **Kontrola inteligencije**: Zahteva podatke generisane pomoću [predviđanja ili prilagođenih modela](predictions-overview.md).
  - **Kontrola detalja o klijentima**: sva polja iz profila dostupna su u objedinjenom profilu korisnika.
  - **Kontrola obogaćivanja**: Zahteva da se aktivna [obogaćivanja](enrichment-hub.md) primene se na profile klijenata. Programski dodatak za kartice podržava ova obogaćivanja: brendove [koje](enrichment-microsoft.md) obezbeđuje Microsoft, [interesovanja](enrichment-microsoft.md) koja obezbeđuje Microsoft i [podatke o angažovanju sistema Office](enrichment-office.md) koje obezbeđuje Microsoft.
  - **Kontrola kontakata**: zahteva definiciju semantičkog entiteta tipa kontakata.
  - **Kontrola vremenske ose**: zahteva [konfigurisane aktivnosti](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalirajte i koristite dodatak za karticu klijenta

Programski dodatak za karticu klijenta je rešenje za Customer Engagement aplikacije u sistemu Dynamics 365. Da biste instalirali rešenje, idite na AppSource i potražite **Dynamics karticu klijenta**. Izaberite [dodatak za karticu klijenta u usluzi AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) i izaberite **Preuzmi odmah**.

Možda ćete morati da se prijavite pomoću akreditiva administratora za aplikaciju Dynamics 365 da biste instalirali rešenje. Možda će biti potrebno neko vreme da se rešenje instalira u vaše okruženje.

## <a name="configure-the-customer-card-add-in"></a>Konfigurisanje dodatka klijentske kartice

1. Kao administrator, idite u odeljak **Podešavanja** u sistemu Dynamics 365 i izaberite **Rešenja**.

1. Izaberite vezu **Ime za prikaz** za rešenje **Dynamics 365 Customer Insights dodatak klijentske kartice (pregled)**.

   > [!div class="mx-imgBorder"]
   > ![Izaberite ime za prikaz.](media/select-display-name.png "Izaberite ime za prikaz.")

1. Izaberite **Prijavljivanje** i unesite akreditive za nalog administratora koji koristite za konfigurisanje usluge Customer Insights.

   > [!NOTE]
   > Proverite da li blokator iskačućih prozora pregledača ne blokira prozor za potvrdu identiteta kada izaberete dugme **Prijavljivanje**.

1. Izaberite instancu Customer Insights okruženja iz kojeg želite da preuzmete podatke.

1. Definišite mapiranje polja na zapise u Dynamics 365 aplikaciji. U zavisnosti od vaših podataka u usluzi Customer Insights, možete odabrati da mapirate sledeće opcije:
   - Da biste mapirali kontakt, odaberite polje u entitetu klijenta koje se podudara sa ID-om vašeg entiteta kontakta.
   - Da biste mapirali poslovni kontakt, odaberite polje u entitetu klijenta koje se podudara sa ID-om vašeg entiteta poslovnog kontakta.

   > [!div class="mx-imgBorder"]
   > ![Polje ID kontakta.](media/contact-id-field.png "Polje ID kontakta.")

1. Izaberite **Sačuvaj konfiguraciju** da biste sačuvali podešavanja.

1. Zatim treba da dodelite bezbednosne uloge u sistemu Dynamics 365 kako bi korisnici mogli da prilagođavaju i vide korisničku karticu. U sistemu Dynamics 365, idite na **Podešavanja** > **Bezbednost** > **Korisnici**. Izaberite korisnike da biste izmenili korisničke uloge i izaberite **Upravljaj ulogama**.

1. Dodelite ulogu **Stručnjak za prilagođavanje Customer Insights kartica** korisnicima koji će za celu organizaciju prilagođavati sadržaj prikazan na kartici.

## <a name="add-customer-card-controls-to-forms"></a>Dodajte kontrole kartice klijenta u obrasce

U zavisnosti od vašeg scenarija, možete izabrati da dodate kontrole u obrazac **Kontakt** ili obrazac **Poslovni kontakt**. Ako je vaše okruženje "Uvid u kupce" za poslovne naloge, preporučili smo dodavanje kontrola u obrazac naloga. U tom slučaju zamenite „kontakt“ u koracima ispod sa „poslovni kontakt“.

1. Da biste dodali kontrole kartice klijenta u obrazac za kontakt, idite na **Podešavanja** > **Prilagođavanja** u Dynamics 365.

1. Izaberite **Prilagodi sistem**.

1. Dođite do entiteta **Kontakt**, proširite ga, a zatim izaberite **Obrasci**.

1. Izaberite obrazac kontakta kom želite da dodate kontrole kartice klijenta.

    > [!div class="mx-imgBorder"]
    > ![Izbor obrasca Kontakta.](media/contact-active-forms.png "Izaberite obrazac Kontakt.")

1. Da biste dodali kontrolu, u uređivaču obrazaca prevucite bilo koje polje iz **Istraživača polja** tamo gde želite da se kontrola prikazuje.

1. Izaberite polje na obrascu koje ste upravo dodali, a zatim izaberite **Promeni svojstva**.

1. Idite do kartice **Kontrole** i izaberite **Dodaj kontrolu**. Izaberite neku od dostupnih prilagođenih kontrola i izaberite **Dodaj**.

1. U dijalogu **Svojstva polja**, obrišite polje za potvrdu **Prikažite oznaku na obrascu**.

1. Izaberite opciju **Veb** za kontrolu. Za kontrolu obogaćivanja izaberite tip obogaćivanja koji želite da prikažete konfigurisanjem polja **Tip obogaćivanja**. Dodajte zasebnu kontrolu obogaćivanja za svaku vrstu obogaćivanja.

1. Izaberite **Sačuvaj** i **Objavi** da biste objavili ažurirani obrazac za kontakt.

1. Idite na objavljeni obrazac kontakta. Videćete novododatu kontrolu. Možda ćete morati da se prijavite prilikom prvog korišćenja.

1. Da biste prilagodili šta želite da prikažete na prilagođenoj kontroli, izaberite dugme za uređivanje u gornjem desnom uglu.

## <a name="upgrade-customer-card-add-in"></a>Nadogradnja programskog dodatka za karticu klijenta

Programski dodatak za korisničku karticu se ne nadograđuje automatski. Da biste nadogradili na najnoviju verziju, sledite ove korake u aplikaciji Dynamics 365 sa instaliranim programskim dodatkom.

1. U Dynamics 365 aplikaciji idite na **Podešavanja** > **Prilagođavanje** i izaberite **Rešenja**.

1. U tabeli dodataka potražite **CustomerInsightsCustomerCard** i izaberite red.

1. Izaberite **Primeni nadogradnju rešenja** u traci sa radnjama.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Nadogradite rešenje u oblasti Prilagođavanje Dynamics 365 aplikacija.":::

1. Kada započnete proces nadogradnje, videćete indikator učitavanja dok se nadogradnja ne završi. Ako nema novije verzije, nadogradnja će prikazati poruku o grešci.

## <a name="troubleshooting"></a>Rešavanje problema

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Kontrole iz programskog dodatka "Kartica kupca" ne pronalaze podatke

**Problem:**

Čak i sa ispravno konfigurisanim ID poljima, kontrole ne mogu da pronađu podatke ni za kog klijenta.  

**Rešenje:**

1. Uverite se da ste konfigurisali programski dodatak kartice u skladu sa uputstvima: Konfigurisanje [programskog dodatka kartice kupca](#configure-the-customer-card-add-in)

1. Redigujte konfiguraciju ingestion podataka. Uredite izvor podataka za Dynamics 365 sistem koji sadrži ID-a kontakta. Ako je ID-a kontakta prikazan velikim sličnim znakovima u uređivaču Power Query, isprobajte sledeće korake:
    1. Uredite izvor podataka biste otvorili prozor izvor podataka u programu Power Query Editor.
    1. Izaberite kolonu ID kontakta.
    1. Na traci **zaglavlja** izaberite stavku Transformiši da biste videli dostupne radnje.
    1. Izaberite **malim s malim sličima**. Proverite valjanost ako su GUID-ove u tabeli sada malim sličima.
    1. Sačuvajte izvor podataka.
    1. Pokrenite procese unošenja podataka, ujedinjenja i nizvodno da biste propagirali promene GUID-a.

Kada sistem dovrši potpuno osvežavanje, kontrole programskog dodatka "Kartica kupca" trebalo bi da prikazuju očekivane podatke.

[!INCLUDE [footer-include](includes/footer-banner.md)]
