---
title: Veze sa ostalim uslugama iz usluge Customer Insights.
description: Podelite podatke sa drugim uslugama.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e78e18b75ee9797b5fc76486615992e301e4c650
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977754"
---
# <a name="connections-preview-overview"></a>Pregled veza (verzija za pregled)

Veze su ključ za omogućavanje deljenja podataka u uslugu Customer Insights i iz nje. Svaka veza uspostavlja deljenje podataka sa određenom uslugom. Veze su temelj da [konfigurišete obogaćivanja trećih strana](enrichment-hub.md) i [konfigurisanje izvoza](export-destinations.md). Ista veza se može koristiti više puta. Na primer, jedna veza sa uslugom Dynamics 365 Marketing funkcioniše za više izvoza, a jedna Leadspace veza može se koristiti za nekoliko obogaćivanja.

Idite na **Administrator** > **Veze** da biste kreirali i prikazali veze.

Na kartici **Veze** prikazuju se sve aktivne veze. Lista prikazuje red za svaku vezu. 

Preuzmite brzi pregled, opis i saznajte šta možete učiniti sa svakom opcijom proširivosti na kartici **Otkrivanje**.

### <a name="exports"></a>Izvozi

Samo administratori mogu da konfigurišu nove veze, ali mogu da daju pristup saradnicima da koriste postojeće veze. Administratori kontrolišu kuda podaci mogu da idu, saradnici definišu korisne podatke i učestalost u skladu sa svojim potrebama. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Obogaćivanja

Samo administratori mogu da konfigurišu nove veze, ali kreirane veze su uvek dostupne i administratorima i saradnicima. Administratori upravljaju akreditivima i daju saglasnost za prenos podataka. Veze tada mogu da koriste administratori i saradnici za obogaćivanja.

## <a name="add-a-new-connection"></a>Dodavanje nove veze

Da biste dodali veze, morate da imate [administratorske dozvole](permissions.md). Ako se povežete sa drugim Microsoft uslugama, pretpostavljamo da su obe usluge u istoj organizaciji.

1. Idite na **Administrator** > **Veze (pregled)**.

1. Idite na karticu **Veze**.

1. Izaberite **Dodaj vezu** da biste kreirali novu vezu. Odaberite iz padajućeg menija koju vrstu veze želite da kreirate.

1. U oknu **Podešavanje veze**, navedite potrebne detalje. 
   1. **Ime za prikaz** i vrsta veze opisuju vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj ove veze.
   1. Tačna polja zavise od usluge na koju se povezujete. Više o detaljima određenog tipa veze možete saznati u članku o ciljnoj usluzi.
   1. Ako [koristite sopstveni Key Vault](use-azure-key-vault.md) za čuvanje tajni, aktivirajte **Koristi Key Vault** i izaberite tajnu sa liste.

1. Da biste kreirali vezu, izaberite **Sačuvaj**.

Takođe možete da izaberete **Podešavanje** na pločici na kartici **Otkrivanje**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Dozvolite saradnicima da koriste vezu za izvoz

Kada podešavate ili uređujete vezu za izvoz, vi birate koji korisnici smeju da koriste ovu određenu vezu za definisanje [izvoza](export-destinations.md). Podrazumevano je veza dostupna korisnicima sa administratorskom ulogom. Ovo podešavanje možete promeniti u delu **Izaberite ko može da koristi ovu vezu** i dozvolite korisnicima sa ulogom saradnika da koriste ovu vezu.

- Saradnici neće moći da vide ili izmene vezu. Videće samo ime za prikaz i tip veze prilikom kreiranja izvoza.
- Deljenjem veze omogućavate saradnicima da je koriste. Saradnici će videti zajedničke veze kada uspostave izvoz. Oni mogu upravljati svakim izvozom koji koristi ovu specifičnu vezu.
- Možete da promenite ovo podešavanje, a da zadržite izvoz koji su već definisali saradnici.

## <a name="edit-a-connection"></a>Uređivanje veze

1. Idite na **Administrator** > **Veze (pregled)**.

1. Idite na karticu **Veze**.

1. Izaberite vertikalne tri tačke za vezu koju želite da uredite.

1. Izaberite **Uredi**.

1. Promenite vrednosti koje želite da ažurirate i izaberite **Sačuvaj**.

## <a name="remove-a-connection"></a>Uklanjanje veze

Ako se veza koju uklanjate koristi za obogaćivanje ili izvoz, prvo ih morate odvojiti ili ukloniti. Dijalog za uklanjanje vodiće vas do relevantnih obogaćivanja ili izvoza. 

Odvojena obogaćivanja i izvozi postaju neaktivni. Ponovo ih aktivirate dodavanjem druge veze sa njima na stranici [Obogaćivanja](enrichment-hub.md) ili [Izvozi](export-destinations.md).

1. Idite na **Administrator** > **Veze (pregled)**.

1. Idite na karticu **Veze**.

1. Izaberite vertikalne tri tačke za vezu koju želite da uklonite.

1. Izaberite **Ukloni** iz padajućeg menija. Prikazuje se dijalog za potvrdu.

   1. Ako postoje obogaćivanja ili izvozi koji koriste ovu vezu, izaberite dugme da biste videli šta koristi vezu.
      - **Izvozi:** Možete da uklonite ili prekinete izvoz kako biste mogli da uklonite vezu. Da bi prekinuli izvoz, administratori mogu da koriste radnju **Prekini vezu**. Ova radnja je dostupna za pojedinačne i višestruko izabrane izvoze. Prekidom veze zadržavate konfiguraciju izvoza, ali ona se neće pokrenuti dok joj se ne doda druga veza.
      - **Obogaćivanja:** Možete da uklonite ili deaktivirate obogaćivanja kako biste mogli da uklonite vezu. 
   1. Kada veza nema više zavisnosti, vratite se na **Administrator** > **Veze** i pokušajte ponovo da uklonite vezu.

1. Da biste potvrdili brisanje, izaberite **Ukloni**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Uspostavljanje veza sa tajnama kojima upravlja vaš Key Vault

Nekim vezama su potrebne tajne, poput API ključeva ili lozinki. Neke veze podržavaju tajne sačuvane u vašem Key Vaultu. Saznajte više o podržanim vezama i načinu podešavanja [sopstvenog Key Vaulta za uvide u ciljnu grupu](use-azure-key-vault.md).
