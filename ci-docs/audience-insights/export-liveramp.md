---
title: LiveRamp konektor
description: Saznajte kako da izvezete podatke u LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667201"
---
# <a name="liverampreg-connector-preview"></a>LiveRamp&reg; konektor (pregled)

Aktivirajte svoje podatke u usluzi LiveRamp da biste se povezali sa preko 500 platformi u digitalnim, društvenim i TV ekosistemima. Radite sa svojim podacima u usluzi LiveRamp da biste ciljali, potisnuli i personalizovali oglasne kampanje.

## <a name="prerequisites"></a>Preduslovi

- Za upotrebu ovog konektora potrebna vam je pretplata na LiveRamp.
- Da biste dobili pretplatu, [kontaktirajte LiveRamp](https://liveramp.com/contact/) direktno. [Saznajte više o usluzi LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Povezivanje na LiveRamp

1. U uvidima o korisnicima idite na **Administrator** > **Odredišta za izvoz**.

1. Na pločici **LiveRamp** izaberite **Podesi**.

1. Dajte odredištu prepoznatljivo ime u polju **Ime za prikaz**.

1. Obezbedite **Korisničko ime** i **Lozinku** za svoj LiveRamp Secure FTP (SFTP) nalog.
Ovi akreditivi mogu biti različiti od vaših akreditiva za LiveRamp Onboarding.

1. Izaberite **Verifikuj** da testirate vezu sa uslugom LiveRamp.

1. Nakon uspešne verifikacije, dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**.

1. Izaberite **Sledeće** da podesite LiveRamp konektor.

## <a name="configure-the-connector"></a>Konfigurisanje konektora

1. U polju **Odaberite svoj identifikator ključa**, izaberite **E-pošta**, **Ime i adresa** ili **Telefon** za slanje u LiveRamp radi rešavanja identiteta.

1. Mapirajte odgovarajuće atribute vašeg objedinjenog entiteta klijenta za izabrani identifikator ključa.

1. Izaberite **Dodaj atribut** da biste mapirali dodatne atribute koje treba poslati u LiveRamp.

   > [!TIP]
   > Ako pošaljete više ključnih atributa identifikatora u LiveRamp, verovatno će dobiti višu stopu podudaranja.

1. Izaberite segmente koje želite da izvezete u LiveRamp.

1. Izaberite stavku **Sačuvaj**.

> [!div class="mx-imgBorder"]
> ![LiveRamp konektor sa mapiranjem atributa](media/export-liveramp-segments.png "LiveRamp konektor sa mapiranjem atributa")

## <a name="export-the-data"></a>Izvoz podataka

Izvoz će početi uskoro ako su ispunjeni svi preduslovi za izvoz. Izvoz će se takođe pokrenuti sa svakim [planiranim osvežavanjem](system.md#schedule-tab).
Nakon što je izvoz uspešno završen, možete se prijaviti u LiveRamp Onboarding da biste aktivirali i distribuirali svoje podatke.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Liveramp, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Liveramp ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni odredište za izvoz kako biste prestali sa korišćenjem ove funkcionalnosti.