---
title: Kreiranje objedinjenog prikaza svojih klijenata
description: Pređite kroz proces ujedinjenja podataka sa podacima da biste kreirali jedan glavni skup podataka naloga ili profila klijenata.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304444"
---
# <a name="data-unification-overview"></a>Pregled ujednačavanja podataka

Posle[ podešavanja izvora podataka](data-sources.md), možete objediniti podatke. Ujedinjenje podataka vam omogućava da jednom omalovažite izvore podataka u jedan glavni skup podataka koji obezbeđuje objedinjeni prikaz tih podataka.

Za pojedinačne potrošače (B-to-C) gde su podaci usmereni oko pojedinaca, ujedinjenje pruža jedinstven prikaz vaših klijenata. Za poslovne naloge (od B do B) gde su podaci centrirani oko naloga, ujedinjenje pruža objedinjeni prikaz naloga. [Ujedinjenje kontakata (pregled)](data-unification-contacts.md) omogućava da se kontakti za te naloge posebno objedine i pridruže nalozima.

Podaci se mogu objediniti u jednom entitetu ili više entiteta.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

Proces ujedinjenja mapira podatke klijenata iz izvora podataka, uklanja duplikate, podudara se sa podacima u entitetima i kreira objedinjeni profil. Ujedinjenje se vrši sledećim redosledom:

1. [Izvorna polja](map-entities.md) (ranije se zvala Mapa): U koraku izvornih polja izaberite entitete i polja koja želite da uključite u proces ujedinjenja. Mapiraj polja na uobičajeni semantički tip koji opisuje svrhu polja.

1. [Duplirani zapisi](remove-duplicates.md) (prethodno deo podudaranja): U koraku dupliranih zapisa opcionalno definišite pravila za uklanjanje dupliranih zapisa kupaca iz svakog entiteta.

1. [Podudarni](match-entities.md) uslovi (prethodno nazvani Podudaranje): U koraku uslova podudaranja definišite pravila koja se podudaraju sa zapisima kupaca između entiteta. Kada se kupac nađe u dva ili više entiteta, kreira se jedan konsolidovani zapis sa svim kolonama i podacima iz svakog entiteta.

1. [Objedinjena](merge-entities.md) polja kupaca (ranije se nazivaju Objedinjavanje): U objedinjenom koraku polja kupca odredite koja izvorna polja treba uključiti, isključiti ili objediniti u objedinjeni profil kupca.  

1. [Redigujte](review-unification.md) i kreirajte objedinjeni profil.

# <a name="business-accounts-b-to-b"></a>[Poslovni nalozi (B-to-B)](#tab/b2b)

Proces ujedinjenja mapira podatke naloga iz izvora podataka, uklanja duplikate, podudara se sa podacima u entitetima i kreira objedinjeni profil. Ujedinjenje se vrši sledećim redosledom:

1. [Izvorna polja](map-entities.md) (prethodno nazvana Mapa): U koraku izvornih polja izaberite entitete i polja koja želite da uključite u proces objedinjavanja naloga. Mapiraj polja na uobičajeni semantički tip koji opisuje svrhu polja.

1. [Duplirani zapisi](remove-duplicates.md) (prethodno deo podudaranja): U koraku dupliranih zapisa opcionalno definišite pravila za uklanjanje dupliranih zapisa naloga iz svakog entiteta.

1. [Uslovi podudaranja](match-entities.md) (ranije se nazivaju Podudaranje): U koraku uslova podudaranja definišite pravila koja se podudaraju sa zapisima naloga između entiteta. Kada se nalog nađe u dva ili više entiteta, kreira se jedan konsolidovani zapis sa svim kolonama i podacima iz svakog entiteta.

1. [Objedinjena](merge-entities.md) polja kupaca (ranije se nazivaju Objedinjavanje): U objedinjenom koraku polja kupca odredite koja izvorna polja treba uključiti, isključiti ili objediniti u objedinjeni profil kupca.  

1. [Redigujte](review-unification.md) i kreirajte objedinjeni profil.

Nakon ujedinjenja naloga, opcionalno možete da ujedinite kontakte (pregled) za [te naloge i povežete objedinjene kontakte sa objedinjenim](data-unification-contacts.md) nalozima.

---

Nakon dovršavanja ujedinjenja podataka, opcionalno možete da:

- [Podesite odnosi entiteta da biste](relationships.md) kreirali sofisticirane segmente.
- [Obogatite svoje podatke](enrichment-hub.md) da biste dobili širi spektar uvida o kupcima.
- [Definišite](activities.md) aktivnosti iz nekih od unetih atributa.
- [Izgradite mere za](measures.md) bolje razumevanje ponašanja klijenata i poslovnih performansi.

[!INCLUDE [footer-include](includes/footer-banner.md)]
