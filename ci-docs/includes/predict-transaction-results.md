---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611134"
---
- **Performanse modela** obuke: Ocene A, B ili C ukazuju na performanse predviđanje-a i mogu vam pomoći da donesete odluku o korišćenju rezultata uskladištenih u izlaznom entitetu.

  Klase se određuju na osnovu sledećih pravila:
  - **A.** Kada je model tačno predvideo najmanje 50% ukupnih predviđanja i kada je procenat tačnih predviđanja za klijente koji su izgubljeni veći od osnovne stope za najmanje 10%.
  - **B.** Kada je model tačno predvideo najmanje 50% ukupnih predviđanja i kada je procenat tačnih predviđanja za klijente koji su izgubljeni veći od osnovne stope za najviše 10%.
  - **C** kada je model tačno predvideo manje od 50% od ukupnih predviđanja, ili kada je procenat tačnih predviđanja za kupce koji su se kretali manji od osnovne linije.
  - **Osnovna** linija uzima predviđanje vremenski unos za model (na primer, godinu dana) i kreira različite razlomke vremena tako što ga deli sa 2 dok ne dostigne mesec dana ili manje. Koristi ove delove za stvaranje poslovnog pravila za klijente koji nisu kupili ništa u ovom vremenskom okviru. Ovi klijenti se smatraju izgubljenim. Pravilo poslovanja zasnovano na vremenu sa najvećom sposobnošću da se predvidi ko će verovatno da churn bude izabran kao osnovni model.

- **Verovatnoća gubitka (broj klijenata)**: Grupe klijenata na osnovu predviđenog rizika od gubitka. Opcionalno, [kreirajte segmente kupaca](../prediction-based-segment.md) sa visokim rizikom. Takvi segmenti vam pomažu da razumete gde treba da bude prekid članstva u segmentu.

- **Najuticajniji faktori**: Mnogo je faktora koji se uzimaju u obzir pri kreiranju predviđanja. Svaki od faktora ima svoj značaj izračunat za agregirana predviđanja koja model kreira. Koristite ove faktore da biste proverili valjanost predviđanje rezultata. Ili koristite ove informacije kasnije da biste kreirali [segmente koji](../prediction-based-segment.md) bi mogli da utiču na rizik za kupce.