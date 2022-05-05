---
title: Odnosi između entiteta i putanja entiteta
description: Pravite i upravljajte odnosima između entiteta iz više izvora podataka.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: a7b10d985d5cba64b25595a3d7c101d6cb5c62a5
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643805"
---
# <a name="relationships-between-entities"></a>Relacije između entiteta

Relacije povezuju entitete i definišu grafikon vaših podataka kada entiteti dele zajednički identifikator, strani ključ. Ovaj strani ključ može se referencirati iz jednog entiteta na drugi. Povezani entiteti omogućavaju definiciju segmenata i mere na osnovu više izvora podataka.

Postoje tri vrste relacija: 
- Sistemske relacije koje ne mogu da se uređuju, kreira ih sistem kao deo procesa ujednačavanja podataka
- Nasleđene relacije bez mogućnosti uređivanja, koje se automatski kreiraju iz unosa izvora podataka 
- Prilagođene relacije sa mogućnošću uređivanja, koje kreiraju i konfigurišu korisnici

## <a name="non-editable-system-relationships"></a>Sistemske relacije koje ne mogu da se uređuju

Tokom ujednačavanja podataka, sistemske relacije se automatski kreiraju na osnovu inteligentnog podudaranja. Ove relacije pomažu da se povežu zapisi profila klijenata sa odgovarajućim zapisima. Sledeći dijagram ilustruje kreiranje tri sistemske relacije. Entitet klijenta se podudara sa drugim entitetima kako bi se napravio objedinjeni entitet *Klijent*.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Dijagram sa putanjama relacija za entitet klijenta sa tri relacije „1-n“.":::

- **Relacija *CustomerToContact*** je kreirana između entiteta *Klijent* i entiteta *Kontakt*. Entitet *Klijent* dobija ključno polje **Contact_contactID** da stupi u relaciju sa poljem **contactId** ključa entiteta *Kontakt*.
- **Relacija *CustomerToAccount*** je kreirana između entiteta *Klijent* i entiteta *Poslovni kontakt*. Entitet *Klijent* dobija polje ključa **Account_accountID** da stupi u relaciju sa poljem **accountID** ključa entiteta *Poslovni kontakt*.
- **Relacija *CustomerToWebAccount*** je kreirana između entiteta *Klijent* i entiteta *WebAccount*. Entitet *Klijent* dobija polje ključa **WebAccount_webaccountID** da stupi u relaciju sa poljem **webaccountID** ključa entiteta *WebAccount*.

## <a name="non-editable-inherited-relationships"></a>Nasleđene relacije koje ne mogu da se uređuju

Tokom procesa unosa podataka, sistem proverava postoje li relacije u izvorima podataka. Ako ne postoje relacije, sistem ih automatski kreira. Te relacije se takođe koriste u posledičnim procesima.

## <a name="create-a-custom-relationship"></a>Kreiranje prilagođene relacije

Relacija se sastoji od *izvornog entiteta* koji sadrži strani ključ i *ciljni entitet* na koji ukazuje strani ključ izvornog entiteta. 

1. Idite na **Podaci** > **Odnosi**.

2. Izaberite **Nova relacija**.

3. U oknu **Nova relacija**, navedite sledeće informacije:

   :::image type="content" source="media/relationship-add.png" alt-text="Novo bočno okno relacije sa praznim poljima za unos.":::

   - **Naziv relacije**: Naziv koji odražava svrhu veze. Primer: CustomerToSupportCase.
   - **Opis**: Opis relacije.
   - **Izvorni entitet**: Entitet koji se koristi kao izvor u relaciji. Primer: SupportCase.
   - **Ciljni entitet**: Entitet koji se koristi kao cilj u relaciji. Primer: Klijent.
   - **Izvorna kardinalnost**: Navedite kardinalnost izvornog entiteta. Kardinalnost opisuje broj mogućih elemenata u skupu. Uvek se odnosi na ciljnu kardinalnost. Možete birati između **Jedan** i **Više**. Podržani su samo relacije više-prema-jedan i jedan-prema-jedan.  
     - Više prema jedan: Više izvornih zapisa može se odnositi na jedan ciljni zapis. Primer: Više slučajeva podrške od jednog klijenta.
     - Jedan prema jedan: Jedan izvorni zapis odnosi se na jedan ciljni zapis. Primer: Jedan ID lojalnosti za jednog klijenta.

     > [!NOTE]
     > Relacije „Više prema više“ mogu se kreirati pomoću dve relacije „više prema jedan“ i povezujućeg entiteta, koji povezuje izvorni entitet i ciljni entitet.

   - **Ciljna kardinalnost**: Izaberite kardinalnost ciljnih zapisa entiteta. 
   - **Polje izvornog ključa**: Polje stranog ključa u izvornom entitetu. Primer: SupportCase može koristiti CaseID kao polje stranog ključa.
   - **Polje ciljnog ključa**: Polje ključa ciljnog entiteta. Primer „Klijent“ bi mogao da koristi polje ključa **CustomerID**.

4. Izaberite **Sačuvaj** da biste kreirali prilagođenu relaciju.

## <a name="set-up-account-hierarchies"></a>Podešavanje hijerarhija naloga

Okruženja koja su konfigurisana da koriste poslovne naloge kao primarnu ciljnu grupu mogu da konfigurišu hijerarhije naloga za povezane poslovne naloge. Na primer, preduzeće koje ima zasebne poslovne jedinice. 

Organizacije kreiraju hijerarhije naloga radi boljeg upravljanja nalozima i njihovim međusobnim odnosima. Uvidi klijenata podržavaju hijerarhije naloga nadređenog deteta koje već postoje u unetim podacima klijenata. Na primer, nalozi iz usluge Dynamics 365 Sales. Ove hijerarhije mogu da se konfigurišu na **odnosi stranici**.

1. Idite na **Podaci** > **Odnosi**.
1. Izaberite karticu **Hijerarhija naloga**.
1. Izaberite **Hijerarhiju novog naloga**. 
1. U oknu **Hijerarhija naloga**, navedite naziv za hijerarhiju. Sistem kreira naziv za izlazni entitet. Možete promeniti naziv entiteta izlaznog imena.
1. Izaberite entitet koji sadrži hijerarhiju naloga. Obično se nalazi u istom entitetu koji sadrži naloge.
1. Izaberite **ID naloga** i **ID nadređenog naloga** iz izabranog entiteta 
1. Izaberite **Sačuvaj** da biste primenili podešavanja i dovršili hijerarhiju naloga.

## <a name="view-relationships"></a>Prikaz relacija

Na stranici Relacije navedene su sve relacije koje su kreirane. Svaki red predstavlja relaciju, što takođe uključuje detalje o izvornom entitetu, ciljnom entitetu i kardinalnosti. 

:::image type="content" source="media/relationships-list.png" alt-text="Lista relacija i opcija na traci sa radnjama na stranici Relacije.":::

Ova stranica nudi skup opcija za postojeće i nove relacije: 
- **Nova relacija**: [Kreiranje nove relacije](#create-a-custom-relationship).
- **Vizuelizator**: [Istražite vizuelizator odnosa](#explore-the-relationship-visualizer) da biste videli mrežni dijagram postojećih relacija i njihovu kardinalnost.
- **Filtriraj prema**: Izaberite tip relacija koji će se prikazivati na listi.
- **Pretraga relacija**: Koristite tekstualnu pretragu svojstava relacija.

### <a name="explore-the-relationship-visualizer"></a>Istražite vizuelizator relacija

Vizuelizator relacija prikazuje mrežni dijagram postojećih relacija između povezanih entiteta i njihovu kardinalnost. Takođe vizuelizuje putanju relacija.

Da biste prilagodili prikaz, možete da promenite položaj okvira tako što ćete ih prevući na podlogu.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Snimak ekrana mrežnog dijagrama vizuelizatora relacija sa vezama između povezanih entiteta.":::

Dostupne opcije: 
- **Izvezi kao sliku**: Snimite trenutni prikaz kao datoteku slike.
- **Promena na horizontalni/vertikalni raspored**: Promenite poravnanje entiteta i relacija.
- **Uredi**: Ažurirajte svojstva prilagođenih relacija u oknu za uređivanje i sačuvajte promene.

## <a name="relationship-paths"></a>Putanje relacija

Putanja relacija opisuje entitete koji su povezani sa relacijama između izvornog entiteta i ciljnog entiteta. Koristi se pri kreiranju segmenta ili mere koja uključuje druge entitete osim entiteta objedinjenog profila i postoji više opcija za dosezanje entiteta objedinjenog profila. 

Putanja relacija obaveštava sistem preko koje relacije da pristupi objedinjenom entitetu profila. Različite putanje relacija mogu postići različite rezultate.

Na primer, entitet *eCommerce_eCommercePurchases* ima sledeće relacije na objedinjenom profilu entiteta *Klijent*:

- eCommerce_eCommercePurchases > Klijent
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Klijent
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Klijent 

Putanja relacija određuje koje entitete možete koristiti pri kreiranju pravila za mere ili segmente. Odabir opcije sa najdužom putanjom relacija verovatno će postići manje rezultata, jer zapisi koji se podudaraju moraju da budu deo svih entiteta. U ovom primeru, klijent mora da kupi robu putem e-trgovine (eCommerce_eCommercePurchases), na prodajnom mestu (POS_posPurchases) i da učestvuje u našem programu lojalnosti (loyaltyScheme_loyCustomers). Kada birate prvu opciju, verovatno ćete dobiti više rezultata jer klijenti moraju postojati samo u jednom dodatnom entitetu.

### <a name="direct-relationship"></a>Direktna relacija

Relacija je klasifikovana kao **direktna relacija** kada se izvorni entitet odnosi na ciljni entitet sa samo jednom relacijom.

Na primer, ako se entitet aktivnosti pod nazivom *eCommerce_eCommercePurchases* povezuje sa ciljnim entitetom *eCommerce_eCommerceContacts* samo kroz *ContactId*, to je direktna relacija.

:::image type="content" source="media/direct_Relationship.png" alt-text="Izvorni entitet se direktno povezuje sa ciljnim entitetom.":::

#### <a name="multi-path-relationship"></a>Relacija kroz više putanja

**Relacija kroz više putanja** je posebna vrsta direktne relacije koja povezuje izvorni entitet sa više ciljnih entiteta.

Na primer, ako se entitet aktivnosti pod nazivom *eCommerce_eCommercePurchases* odnosi se na dva ciljna entiteta, oba *eCommerce_eCommerceContacts* i *loyaltyScheme_loyCustomers*, to je relacija sa više putanja.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Izvorni entitet se povezuje direktno sa više ciljnih entiteta putem odnosa više skokova.":::

### <a name="indirect-relationship"></a>Indirektna relacija

Relacija je klasifikovana kao **indirektna relacija** kada se izvorni entitet odnosi na jedan ili više dodatnih entiteta pre nego što se odnosi na ciljni entitet.

#### <a name="multi-hop-relationship"></a>Relacija kroz više skokova

*Relacija kroz više skokova* je *indirektna relacija* koja vam omogućava da povežete izvorni entitet sa ciljnim entitetom preko jednog ili više drugih posredničkih entiteta.

Na primer, ako se entitet aktivnosti pod nazivom *eCommerce_eCommercePurchasesWest* povezuje sa posredničkim entitetom pod nazivom *eCommerce_eCommercePurchasesEast*, a zatim se povezuje sa ciljnim entitetom pod nazivom *eCommerce_eCommerceContacts*, to je relacija sa više skokova.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Izvorni entitet se povezuje direktno sa ciljnim entitetom sa posrednim entitetom.":::

### <a name="multi-hop-multi-path-relationship"></a>Više skokova, relacija sa više putanja

Relacije sa više skokova i više putanja se mogu koristiti zajedno za kreiranje **relacija sa više skokova, više putanja**. Ova posebna vrsta kombinuje funkcije **relacija sa više skokova** i **više putanja**. Omogućava vam povezivanje sa više ciljnih entiteta dok koristite posredničke entitete.

Na primer, ako se entitet aktivnosti pod nazivom *eCommerce_eCommercePurchasesWest* povezuje sa posredničkim entitetom pod nazivom *eCommerce_eCommercePurchasesEast*, a zatim se povezuje sa dva ciljna entiteta, oba pod nazivom *eCommerce_eCommerceContacts* i *loyaltyScheme_loyCustomers*, to je relacija sa više skokova, više putanja.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Izvorni entitet se povezuje direktno sa jednim ciljnim entitetom i povezuje se sa drugim ciljnim entitetom preko posrednog entiteta.":::

## <a name="manage-existing-relationships"></a>Upravljanje postojećim relacijama 

Na stranici Relacije, svaka relacija je predstavljena jednim redom. 

Izaberite relaciju i odaberite jednu od sledećih opcija: 
 
- **Uredi**: Ažurirajte svojstva prilagođenih relacija u oknu za uređivanje i sačuvajte promene.
- **Izbriši**: Izbrišite prilagođene relacije.
- **Prikaz**: Prikažite sistemski kreirane i nasleđene relacije. 

## <a name="next-step"></a>Sledeći korak

Sistemske i prilagođene relacije se koriste za [kreiranje segmenata](segments.md) i [mera](measures.md) na osnovu više izvora podataka koji više nisu izolovani.

[!INCLUDE [footer-include](includes/footer-banner.md)]
