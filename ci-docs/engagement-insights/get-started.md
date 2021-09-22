---
title: Započnite rad sa mogućnošću uvida u angažovanje
description: Pregled resursa za pomoć za brzo započinjanje rada.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405375"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Započnite rad sa Dynamics 365 Customer Insights mogućnošću uvida u angažovanje (verzija za javni pregled)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Mogućnost uvida u angažovanje omogućava vam prikupljanje i merenje ponašanja klijenata na vašoj veb-lokaciji. Integriše se sa mogućnošću uvida u angažovanje tako da možete da vidite bogatu analitiku ponašanja u realnom vremenu zajedno sa izveštajima o profilu klijenata. Veze u ovom članku pomažu vam da brzo konfigurišete i podesite okruženje.

## <a name="step-1-review-prerequisites"></a>1. korak: Pregledajte preduslove

Prvo, morate imati aktivan Microsoft Azure Active Directory korisnički nalog. Zatim pročitajte sledeće članke pre podešavanja radnog prostora za uvide u angažovanje.

- Pregledajte i prihvatite [Uslove korišćenja usluge](terms-of-service.md) korporacije Microsoft.  
- Pročitajte članak [Upravljanje kolačićima i pristankom korisnika](user-consent-storage.md). Nakon pregleda ovog članka, procenite da li treba da ažurirate obaveštenje o pristanku korisnika. Ako ranije niste imali kolačiće koji „nisu bili ključni“, verovatno ćete morati da ažurirate smernice veb-lokacije.
- Pregledajte [rečnik](glossary.md) za brzo upoznavanje sa ključnim terminima i konceptima.

## <a name="step-2-explore-engagement-insights"></a>2. korak: Istražite uvid o angažovanju

Kada prvi put posetite uvide o angažovanju, možete da konfigurišete podešavanja, pregledate smernice i istražite proizvod.

1. Prijavite se na [portal za mogućnosti uvida u angažovanje](https://pi.dynamics.com) pomoću svog Microsoft Azure Active Directory korisničkog naloga. (To može biti školski ili poslovni nalog.)

1. Izaberite region i pomoću polja za potvrdu označite da li želite da se uključite da primate ažuriranja i ponude putem e-pošte.

1. Pregledajte **Uslove korišćenja usluge uvida o angažovanju (verzija za pregled)** i **Izjavu o privatnosti**, a zatim izaberite **Istražite demo verziju** da biste ih prihvatili.

1. Istražite proizvod koristeći skup uzoraka podataka.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>3. korak: Podesite radni prostor i dodajte kôd na svoju veb-lokaciju

Radni prostor je mesto gde možete da prikazujete aktivnosti korisnika u realnom vremenu, kao i da skladištite izveštaje i upravljate njima. Dodajte kôd na svoju veb-stranicu da biste započeli sa prikupljanjem *događaja*, podataka o aktivnostima koji potiču od korisnika.

1. [Kreirajte radni prostor](create-workspace.md) i dodajte članove.

1. [Dodajte kôd u svoju veb-lokaciju](instrument-website.md) ili [aplikaciju za mobilne uređaje](developer-resources.md#capture-events-from-mobile-apps) da biste videli aktivnosti korisnika kako stižu u vaš radni prostor.

1. Prikažite [izveštaj u realnom vremenu](view-reports.md) koji prikazuje aktivne korisnike prema pregledaču, uređaju, operativnom sistemu, lokaciji i jeziku. Takođe možete da kreirate [prilagođene izveštaje](custom-reports.md) da biste kreirali sopstvene vizuelizacije.
    
## <a name="step-4-export-data-to-other-channels"></a>4. korak: Izvezite podatke na druge kanale

Možete da kreirate *prečišćene događaje* (virtuelni prikaz) podataka veb-analitike. Zatim filtrirajte i izvozite podatke u uslugu Azure Data Lake Storage. Izvezene podatke možete da unesete kao izvor podataka. Za više informacija, pogledajte [Napravite vezu između uvida u ciljnu grupu i uvida u angažovanje](integrate-audience-insights-engagement-insights.md).

1. [Kreirajte prečišćene događaje](refined-events.md) za izvoz.

1. [Izvezite podatke](export-events.md) u Data Lake Storage.

1. Saznajte kako da [brišete i izvozite podatke o događajima koji sadrže lične informacije](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>5. korak: Ostanite povezani

Cenimo vaše aktivno učešće i planiramo da uzmemo u obzir sve relevantne povratne informacije u razvoju budućih izdanja. Podelite povratne informacije i prijavite probleme na jednom od ovih kanala:
- [Zajednica](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Navedite povratne informacije](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Zahtev za podršku](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
