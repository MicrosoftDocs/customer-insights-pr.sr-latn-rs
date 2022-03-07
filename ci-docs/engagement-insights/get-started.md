---
title: Započnite rad sa mogućnošću uvida u angažovanje
description: Pregled resursa za pomoć za brzo započinjanje rada.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: c435810e712bbbf69f8f1cfb582fc0a971566de6
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225615"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Započnite rad sa Dynamics 365 Customer Insights mogućnošću uvida u angažovanje (verzija za javni pregled)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Mogućnost uvida u angažovanje omogućava vam prikupljanje i merenje ponašanja klijenata na vašoj veb-lokaciji. Integriše se sa mogućnošću uvida u angažovanje tako da možete da vidite bogatu analitiku ponašanja u realnom vremenu zajedno sa izveštajima o profilu klijenata. Veze u ovom članku pomažu vam da brzo konfigurišete i podesite okruženje.

## <a name="step-1-review-prerequisites"></a>1. korak: Pregledajte preduslove

Prvo, morate imati aktivan Microsoft Azure Active Directory (AAD) korisnički nalog. Zatim pročitajte sledeće članke pre podešavanja radnog prostora za uvide u angažovanje.

- Pregledajte i prihvatite [Uslove korišćenja usluge](terms-of-service.md) korporacije Microsoft.  
- Pročitajte članak [Upravljanje kolačićima i pristankom korisnika](user-consent-storage.md). Zatim procenite da li morate da ažurirate obaveštenje o saglasnosti korisnika. Ako ranije niste imali kolačiće koji „nisu bili ključni“, verovatno ćete morati da ažurirate smernice veb-lokacije.
- Pregledajte [rečnik](glossary.md) za brzo upoznavanje sa ključnim terminima i konceptima.

## <a name="step-2-explore-engagement-insights"></a>2. korak: Istražite uvid o angažovanju

Kada prvi put posetite uvide u angažovanje, možete da konfigurišete podešavanja, pregledate smernice i istražite mogućnosti.

1. Prijavite se na [portal sa mogućnostima uvida u angažovanje](https://home.ci.ai.dynamics.com/app/engagement-insights) koristeći svoj Microsoft AAD korisnički (školski ili poslovni) nalog.

1. Izaberite svoj region i označite polje ako želite da se prijavite za primanje ažuriranja i ponuda putem e-pošte.

1. Pregledajte **uslove korišćenja** uvida u angažovanje (verzija za pregled) i **Izjavu o privatnosti**, a zatim izaberite **Istražite demo** da biste prihvatili ova podešavanja.

1. Istražite proizvod koristeći skup uzoraka podataka.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>3. korak: Podesite radni prostor i kreirajte izveštaje

Radni prostor je mesto gde možete da prikažete aktivnost korisnika u realnom vremenu, kao i da skladištite izveštaje i upravljate njima. Dodajte kôd na svoju veb-stranicu da biste započeli sa prikupljanjem *događaja*, podataka o aktivnostima koji potiču od korisnika.

1. [Kreirajte radni prostor](create-workspace.md) i dodajte članove.

1. Dodajte kôd u svoju [veb-lokaciju](instrument-website.md) ili [aplikaciju za mobilne uređaje](developer-resources.md#capture-events-from-mobile-apps) da biste videli aktivnosti korisnika kako stižu u vaš radni prostor.

1. Prikažite [izveštaj u realnom vremenu](view-reports.md) koji prikazuje aktivne korisnike prema pregledaču, uređaju, operativnom sistemu, lokaciji i jeziku. Takođe možete da kreirate [prilagođene izveštaje](custom-reports.md) da biste kreirali sopstvene vizuelizacije.

1. Kreirajte [dimenzije](dimensions.md) za sortiranje posetilaca prema novim i povratnim korisnicima, [pokazatelje](metrics.md) radi boljeg razumevanja ponašanja korisnika i [segmente](segments.md) da identifikuje podskup posetilaca na osnovu karakteristika ili interakcija sa veb-stranicama.
    
## <a name="step-4-export-data-to-other-channels"></a>4. korak: Izvezite podatke na druge kanale

Možete da kreirate *prečišćene događaje* (virtuelni prikaz) podataka veb-analitike. Zatim filtrirajte i izvozite podatke u uslugu Azure Data Lake Storage. Izvezene podatke možete da unesete kao izvor podataka.

1. [Kreirajte prečišćene događaje](refined-events.md) za izvoz.

1. [Izvezite podatke](export-events.md) u Azure Data Lake Storage.

1. [Kreirajte vezu između uvida u ciljnu grupu i uvida u angažovanje](integrate-audience-insights-engagement-insights.md) za deljenje podataka između dve mogućnosti.

1. [Prepoznajte veb-događaje korisnika koji su prethodno potvrdili identitet](unknown-to-known.md) sa funkcijom **nepoznato u poznato**.

1. Saznajte kako da [brišete i izvozite podatke o događajima koji sadrže lične informacije](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>5. korak: Kreirajte izveštaje o toku prodaje i upravljajte njima

Izveštaj o toku prodaje prikuplja informacije o koracima koji se dešavaju tokom puta koji pređe korisnik kroz vašu veb-lokaciju ili aplikaciju za mobilne uređaje. Osim što možete da kreirate gotove izveštaje o profilima i prilagođene izveštaje, možete da kreirate i izveštaj o toku prodaje kako biste identifikovali putanje koje klijenti pređu pre nego što izvrše kupovinu. 

1. [Kreirajte izveštaj o toku](funnel-reports.md) da biste donosili informisane odluke i identifikovali oblasti za optimizaciju i poboljšanja procesa.

1. Kreirajte izveštaje o toku kanala prodaje za više kanala, nakon što ste svoju mobilnu aplikaciju opremili uvidima u angažovanje [Android SDK](get-started-android.md) ili [iOS SDK](get-started-ios.md).

1. Koristite [uvide u tokove prodaje](funnel-reports.md#funnel-insights) da biste stekli dublji uvid u ponašanje klijenata o koracima u izveštaju o toku prodaje.
 
## <a name="step-6-stay-connected"></a>6. korak: Ostanite povezani

Cenimo vaše aktivno učešće i razmatramo sve relevantne povratne informacije u razvoju budućih izdanja. Podelite povratne informacije i prijavite probleme na jednom od ovih kanala:
- [Zajednica](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Navedite povratne informacije](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Zahtev za podršku](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
