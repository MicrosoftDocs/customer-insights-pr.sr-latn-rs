---
title: Odnosi između entiteta i putanja entiteta
description: Pravite i upravljajte odnosima između entiteta iz više izvora podataka.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406822"
---
# <a name="relationships-between-entities"></a>Relacije između entiteta

Relacije vam pomažu da povežete entitete i generišete grafikon vaših podataka kada entiteti dele zajednički identifikator (strani ključ) koji se može referencirati iz jednog entiteta u drugi. Povezani entiteti vam omogućavaju da definišete segmente i mere na osnovu više izvora podataka.

Postoje dva tipa relacija. Sistemske relacije koje se ne mogu uređivati, koje se kreiraju automatski, i prilagođene relacije, koje kreiraju i konfigurišu korisnici.

Tokom procesa podudaranja i spajanja, sistemske relacije se kreiraju se iza scene na osnovu inteligentnog podudaranja. Ove relacije pomažu da se povežu evidencije profila klijenata sa podacima drugih entiteta. Sledeći dijagram ilustruje kreiranje tri sistemske relacije kada se entitet klijenta podudari sa dodatnim entitetima kako bi se proizveo konačni entitet Profil klijenta.

> [!div class="mx-imgBorder"]
> ![Kreiranje relacije](media/relationships-entities-merge.png "Kreiranje relacije")

- **Relacija *CustomerToContact*** je kreirana između entiteta Klijent i kontaktnog entiteta. Entitet Klijent dobija ključno polje **Contact_contactId** da stupi u relaciju sa poljem ključa entiteta Kontakt **contactId**.
- **Relacija _CustomerToContact_** je kreirana između entiteta Klijent i entiteta Poslovni kontakt. Entitet Klijent dobija polje ključa **Account_accountId** da stupi u relaciju sa poljem ključa entiteta Poslovni kontakt **accountId**.
- **Relacija _CustomerToWebAccount_** je kreirana između entiteta Klijent i entiteta WebAccount. Entitet Klijent dobija polje ključa **WebAccount_webaccountId** da stupi u relaciju sa poljem ključa entiteta WebAccount **webaccountId**.

## <a name="create-a-relationship"></a>Kreiranje odnosa

Definišite prilagođene relacije na stranici **Relacije**. Svaka relacija se sastoji od izvornog entiteta (entiteta koji drži strani ključ) i ciljnog entiteta (entiteta na koji ukazuje na strani ključ izvornog entiteta).

1. U uvidima o korisnicima idite na **Podaci** > **Odnosi**.

2. Izaberite **Nova relacija**.

3. U oknu **Nova relacija**, navedite sledeće informacije:

   > [!div class="mx-imgBorder"]
   > ![Unesite detalje relacije](media/relationships-add.png "Unesite detalje relacije")

   - **Naziv relacije**: Ime koje odražava svrhu relacije (na primer, **AccountWebLogs**).
   - **Opis**: Opis relacije.
   - **Izvorni entitet**: Izaberite entitet koji se koristi kao izvor u relaciji (na primer, WebLog).
   - **Kardinalnost**: Izaberite kardinalnost izvornih zapisa entiteta. Na primer, „mnogo“ znači da je više Weblog zapisa u relaciji sa jednim entitetom WebAccount.
   - **Izvorno polje ključa**: Ovo predstavlja polje stranog ključa u izvornom entitetu. Na primer, WebLog ima polje stranog ključa **accountId**.
   - **Ciljni entitet**: Izaberite entitet koji se koristi kao cilj u relaciji (na primer, WebAccount).
   - **Ciljna kardinalnost**: Izaberite kardinalnost ciljnih zapisa entiteta. Na primer, „jedan“ znači da je više Weblog zapisa u relaciji sa jednim entitetom WebAccount.
   - **Ciljno polje ključa**: Ovo polje predstavlja polje ključa ciljnog entiteta. Na primer, WebAccount ima polje ključa **accountId**.

> [!NOTE]
> Podržani su samo relacije više-prema-jedan i jedan-prema-jedan. Relacije više-prema-više mogu da se kreiraju pomoću dve relacije više-prema-jedan i jednog entiteta veze (entiteta koji se koristi za povezivanje izvornog entiteta i ciljnog entiteta).

## <a name="delete-a-relationship"></a>Brisanje relacije

1. U uvidima o korisnicima idite na **Podaci** > **Odnosi**.

2. Izaberite polja za potvrdu za relacije koje želite da izbrišete.

3. Izaberite **Izbriši** na vrhu tabele **Relacije**.

4. Potvrdite brisanje.

## <a name="next-step"></a>Sledeći korak

Sistemske i prilagođene relacije se koriste za kreiranje segmenata na osnovu više izvora podataka koji se više ne biraju. Za više informacija, pogledajte članak [Segmenti](segments.md).
