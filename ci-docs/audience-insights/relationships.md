---
title: Odnosi između entiteta i putanja entiteta
description: Pravite i upravljajte odnosima između entiteta iz više izvora podataka.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171181"
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

1. U uvidima o korisnicima idite na **Podaci** > **Odnosi**.

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

## <a name="view-relationships"></a>Prikaz relacija

Na stranici Relacije navedene su sve relacije koje su kreirane. Svaki red predstavlja relaciju, što takođe uključuje detalje o izvornom entitetu, ciljnom entitetu i kardinalnosti. 

:::image type="content" source="media/relationships-list.png" alt-text="Lista relacija i opcija na traci sa radnjama na stranici Relacije.":::

Ova stranica nudi skup opcija za postojeće i nove relacije: 
- **Nova relacija**: [Kreiranje nove relacije](#create-a-custom-relationship).
- **Vizuelizator**: [Istražite vizuelizator odnosa](#explore-the-relationship-visualizer) da biste videli mrežni dijagram postojećih relacija i njihovu kardinalnost.
- **Filtriraj prema**: Izaberite tip relacija koji će se prikazivati na listi.
- **Pretraga relacija**: Koristite tekstualnu pretragu svojstava relacija.

### <a name="explore-the-relationship-visualizer"></a>Istražite vizuelizator relacija

Vizuelizator relacija prikazuje mrežni dijagram postojećih relacija između povezanih entiteta i njihovu kardinalnost.

Da biste prilagodili prikaz, možete da promenite položaj okvira tako što ćete ih prevući na podlogu.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Snimak ekrana mrežnog dijagrama vizuelizatora relacija sa vezama između povezanih entiteta.":::

Dostupne opcije: 
- **Izvezi kao sliku**: Snimite trenutni prikaz kao datoteku slike.
- **Promena na horizontalni/vertikalni raspored**: Promenite poravnanje entiteta i relacija.
- **Uredi**: Ažurirajte svojstva prilagođenih relacija u oknu za uređivanje i sačuvajte promene.

## <a name="manage-existing-relationships"></a>Upravljanje postojećim relacijama 

Na stranici Relacije, svaka relacija je predstavljena jednim redom. 

Izaberite relaciju i odaberite jednu od sledećih opcija: 
 
- **Uredi**: Ažurirajte svojstva prilagođenih relacija u oknu za uređivanje i sačuvajte promene.
- **Izbriši**: Izbrišite prilagođene relacije.
- **Prikaz**: Prikažite sistemski kreirane i nasleđene relacije. 

## <a name="next-step"></a>Sledeći korak

Sistemske i prilagođene relacije se koriste za [kreiranje segmenata](segments.md) na osnovu više izvora podataka koji više nisu u silosu.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
