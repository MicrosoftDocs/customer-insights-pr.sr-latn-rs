---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755561"
---
Nakon što unesite podatke, započnite proces ujedinjenja podataka da biste kreirali objedinjeni profil korisnika. Za više informacija pogledajte [Objedinjavanje podataka](../data-unification.md).

### <a name="select-source-fields"></a>Izbor izvornih polja

1. Nakon unosa podataka, mapirajte kontakte sa platforme eCommerce i iz podataka o lojalnosti u uobičajene tipove podataka. Idite na " **Ujedinjenje** > **podataka"**.

1. Izaberite entitete koji predstavljaju profil klijenta – **eCommerce kontakti** i **Lojalni klijenti**.

   ![objedinite izvore podataka o platform ecommerce i lojalnosti.](../media/unify-ecommerce-loyalty.png)

1. Izaberite **ID klijenta** kao primarni ključ za **eCommerce kontakte** i **ID lojalnosti** kao primarni ključ za **Lojalne klijente**.

1. Izaberite **Sledeće**. Preskočite duplirane zapise i kliknite na dugme **Dalje**.

### <a name="match-conditions"></a>Uslovi podudaranja

1. Odaberite **eCommerceContacts: eCommerce** kao primarni entitet i uključite sve zapise.

1. Odaberite **loyCustomers: LoyaltyScheme i uključite** sve zapise.

1. Dodaj pravilo:
   - Izaberite **FullName** i za eCommerceContacts i za loyCustomers.
   - Izaberite **tip (telefon, ime, adresa, ...) za** normalizaciju **·**.
   - Podesite **Nivo preciznosti**: **Osnovni** i **Vrednost**: **Visoka**.
   - Unesite **FullName, Email** za ime.

1. Dodajte drugi uslov za e-adresu:
   - Izaberite **e**-poštu i za eCommerceContacts i za loyCustomers.
   - Ostavite Normalizacija prazno.
   - Podesite **Nivo preciznosti**: **Osnovni** i **Vrednost**: **Visoka**.

   ![Objedinite pravilo podudaranja za ime i e-poštu.](../media/unify-match-rule.png)

1. Izaberite **Gotovo**.

1. Izaberite **Sledeće**.

### <a name="unify-fields"></a>Ujedini polja

1. Preimenujte **ID kontakta** **za entitet loyCustomers** **u ContactIdLOYALTY** da biste ga razlikovali od ostalih Unesed ID-a.

1. Kliknite na **dugme "** Dalje" da biste pregledali, a zatim **izaberite stavku Kreiraj profile kupaca**.
