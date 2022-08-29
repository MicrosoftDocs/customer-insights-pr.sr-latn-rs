---
title: Izbor izvornih polja za ujedinjenje podataka
description: Prvi korak u procesu ujedinjenja je izbor entiteta, atributa, primarnih ključeva i semantičkih tipova za mapiranje podataka u objedinjeni profil korisnika.
recommendations: false
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304582"
---
# <a name="select-source-fields-for-data-unification"></a>Izbor izvornih polja za ujedinjenje podataka

Prvi korak u ujedinjenju je izbor entiteta i polja unutar skupova podataka koje želite da ujedinite. Izaberite entitete koji sadrže detalje vezane za kupca kao što su ime, adresa, broj telefona i e-pošta. Možete izabrati jedan ili više entiteta.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Izbor entiteta i polja

1. Idite na " **Ujedinjenje** > **podataka"**.

   Za pojedinačne kupce (B-to-C), prikazuje stranicu **za sletanje** "Ujedini" koja prikazuje " **Prvi koraci** " pri prvom koraku, polja **Izvor**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Snimak ekrana ujedinjavanja landing page-a za iskustvo prvog trčanja za pojedinačne kupce.":::

   Za poslovne naloge (od B do B), landing page **"Ujedini**" **prikazuje naloge za ujedinjavanje** **koji prikazuju prvi** korak, polja **Izvor**. Koraci **za ujedinjavanje kontakata (pregled)** su opcionalni i čekaju dovršavanje ujedinjenja naloga.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Snimak ekrana ujedinjavanja landing page-a za iskustvo prvog trčanja za poslovne naloge.":::

1. Izaberite **Prvi koraci**.

1. Na stranici **Izvorna** polja izaberite **izaberite entitete i polja**. Prikazaće **se okno "Izbor entiteta** i polja".

1. Izaberite najmanje jedan entitet.

1. Za svaki izabrani entitet identifikujte polja koja želite da koristite za podudaranje zapisa kupaca i polja koja želite da uključite u objedinjeni profil. Ova polja se zovu *Atributi*. Potrebne atribute možete da izaberete pojedinačno iz entiteta ili da uključite sve atribute iz entiteta tako što ćete potvrditi izbor u polju za potvrdu na nivou entiteta. Možete pretraživati ključne reči po svim atributima i entitetima da biste izabrali potrebne atribute koje želite da mapirate.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Snimak ekrana izabranih entiteta i atributa.":::

   U ovom primeru, dodajemo **eCommerceContacts** i **loyCustomer** entitete. Odabirom ovih entiteta možete steći uvid u to koji od poslovnih korisnika na mreži su članovi programa lojalnosti.

1. Izaberite **Primeni** da biste potvrdili svoje izbore. Prikazani su izabrani entiteti i atributi.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Izaberite primarni ključ i semantički tip za atribute

   :::image type="content" source="media/m3_select_primary.png" alt-text="Snimak ekrana izabranih entiteta sa primarnim ključem još uvek nije izabran." lightbox="media/m3_select_primary.png":::

Za svaki entitet izvršite sledeće korake.

1. Odaberite **primarni ključ**. Primarni ključ je atribut jedinstven za entitet. Da bi atribut bio važeći primarni ključ, ne bi trebalo da sadrži duplirane vrednosti, nedostajuće vrednosti ili prazne vrednosti. Atributi tipa niska, ceo broj i GUID tip podataka su podržani kao primarni ključevi.

1. Da biste koristili AI modele za predviđanje semantike što štedi vreme i poboljšava preciznost, uverite **se da je inteligentno mapiranje** u funkciji. Inteligentno mapiranje pruža semantičke preporuke zasnovane na AI u polju **Tip**.

1. Za svaki atribut odaberite semantički tip **koji** najbolje opisuje taj atribut, kao što je ime, grad ili e-adresa.

   > [!NOTE]
   > U programu B-to-C, jedno polje bi trebalo da se mapira na semantički *tip Person.FullName* da bi se popunilo ime kupca na kartici kupca. U programu B-to-B, ime naloga bi trebalo da se mapira *Organization.Name*. U suprotnom, kartice klijenata će se prikazivati bez imena.

   1. Izaberite drugu opciju da biste zamenili tip atributa koji je sistem identifikovao. Ako tip ne postoji, kreirajte prilagođeni semantički tip **tako što ćete izabrati polje Vrsta** za atribut i uneti prilagođeno ime semantičkog tipa.

   1. Izaberite entitet i polje koje sadrži URL adresu da biste dodali URL adresu javno dostupnim slikama ili logotipima profila. U polje **Vrsta** unesite sledeće:
      - Za osobu: Person.ProfileImage
      - Za organizaciju: Organization.LogoImage

1. Redigujte atribute u kojima se semantički tip automatski identifikuje. Ovi atributi su navedeni u okviru **mapiranih polja redigovanje**. Samo atributi sa istim tipom mogu da se kombinuju u koraku " **Ujedini polja kupca** ". Semantički tipovi se koriste za automatsko predlaganje uvida. Uverite se da su tipovi koje ste odabrali dosledni u svim izabranim entitetima.

1. Za atribute koji nisu automatski mapirani semantičkom tipu izaberite polje semantičkog tipa, unesite ime prilagođenog tipa atributa ili ih ostavite nenadmašne. Ovi atributi su navedeni u okviru **Definisanje podataka u nemasapisanom polju**.

1. Nakon dovršavanja koraka za svaki entitet, izaberite sačuvaj **izvorna polja**.

1. Izaberite **Sledeće**.

> [!div class="nextstepaction"]
> [Sledeći korak: Uklanjanje duplikata](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
