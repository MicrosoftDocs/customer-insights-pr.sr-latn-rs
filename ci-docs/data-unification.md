---
title: Kreiranje objedinjenog prikaza svojih klijenata
description: Pređite kroz proces ujedinjenja podataka sa podacima da biste kreirali jedan skup podataka objedinjenih profila klijenata.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: bb8da6f4b9f92f2b265ff9807e04638edae4f814
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755751"
---
# <a name="data-unification-overview"></a>Pregled ujednačavanja podataka

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Posle[ podešavanja izvora podataka](data-sources.md), možete objediniti podatke. Ujedinjenje podataka vam omogućava da jednom omalovažite izvore podataka u jedan glavni skup podataka koji obezbeđuje objedinjeni prikaz tih podataka. Za pojedinačne potrošače (B-to-C) gde su podaci usmereni oko pojedinaca, ujedinjenje pruža jedinstven prikaz vaših klijenata. Za poslovne naloge (od B do B) gde su podaci centrirani oko naloga, ujedinjenje pruža objedinjeni prikaz naloga.

Podaci se mogu objediniti u jednom entitetu ili više entiteta. Ujedinjenje se vrši sledećim redosledom:

1. [Izvorna polja](map-entities.md) (ranije se zvala Mapa): U koraku izvornih polja izaberite entitete i polja koja želite da uključite u proces ujedinjenja. Mapiraj polja na uobičajeni semantički tip koji opisuje svrhu polja.

1. [Duplirani zapisi](remove-duplicates.md) (prethodno deo podudaranja): U koraku dupliranih zapisa opcionalno definišite pravila za uklanjanje dupliranih zapisa kupaca iz svakog entiteta.

1. [Podudarni](match-entities.md) uslovi (prethodno nazvani Podudaranje): U koraku uslova podudaranja definišite pravila koja se podudaraju sa zapisima kupaca između entiteta. Kada se kupac nađe u dva ili više entiteta, kreira se jedan konsolidovani zapis sa svim kolonama i podacima iz svakog entiteta.

1. [Objedinjena](merge-entities.md) polja kupaca (ranije se nazivaju Objedinjavanje): U objedinjenom koraku polja kupca odredite koja izvorna polja treba uključiti, isključiti ili objediniti u objedinjeni profil kupca.  

1. [Redigujte](review-unification.md) i kreirajte objedinjeni profil.

Nakon dovršavanja ujedinjenja podataka, opcionalno možete da:

- [Podesite odnosi entiteta da biste](relationships.md) kreirali sofisticirane segmente.
- [Obogatite svoje podatke](enrichment-hub.md) da biste dobili širi spektar uvida o kupcima.
- [Definišite](activities.md) aktivnosti iz nekih od unetih atributa.
- [Izgradite mere za](measures.md) bolje razumevanje ponašanja klijenata i poslovnih performansi.

[!INCLUDE [footer-include](includes/footer-banner.md)]
