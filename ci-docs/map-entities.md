---
title: Mapiranje entiteta i atributa za objedinjavanje podataka
description: Izaberite entitete, atribute, primarne ključeve i semantičke tipove za mapiranje podataka u objedinjeni profil klijenta.
ms.date: 10/18/2020
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bebc600e91db471c3cd50eccb5e42be309ff09c9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643173"
---
# <a name="map-entities-and-attributes"></a>Entiteti i atributi mape

**Mapa** je prva faza u procesu ujedinjenja podataka. Mapiranje se sastoji od tri faze:

- *Izbor entiteta*: Identifikujte kombinovane entitete koji vode do skupa podataka sa potpunijim informacijama o vašim klijentima.
- *Izbor atributa*: Za svaki entitet odredite kolone koje želite da kombinujete i usaglasite u fazama *podudaranje* i *spajanje*. Ove kolone se zovu *Atributi*.
- *Izbor primarnog ključa i semantičkog tipa*: Za svaki entitet identifikujte atribut koji želite da definišete kao primarni ključ za taj entitet, a za svaki atribut identifikujte semantički tip koji najbolje opisuje taj atribut.

Za više informacija o opštem toku objedinjavanja podataka, pogledajte [Ujednačavanje](data-unification.md).

## <a name="select-the-first-entities"></a>Izaberite prve entitete

1. Idite na **Podaci** > **Objedini** > **Mapiraj**.

2. Započnite fazu mapiranja odabirom **Izaberi entitete**.

3. Izaberite entitete i atribute koje želite da koristite u fazama *podudaranje* i *spajanje*. Možete da izaberete tražene atribute pojedinačno iz entiteta ili da uključite sve atribute iz entiteta izborom polja za potvrdu **Uključi sva polja** na nivou entiteta. Preporučujemo da izaberete najmanje dva entiteta koji će imati koristi od procesa objedinjavanja podataka.

   > [!div class="mx-imgBorder"]
   > ![Primer dodavanja entiteta.](media/data-manager-configure-map-add-entities-example.png "Primer dodavanja entiteta")

   U ovom primeru dodajemo entitete **eCommerceContacts** i **loyCustomers**. Odabirom ovih entiteta možete steći uvid u to koji od poslovnih korisnika na mreži su članovi programa lojalnosti.
   
   Možete pretraživati ključne reči po svim atributima i entitetima da biste izabrali potrebne atribute koje želite da mapirate.
   
     > [!div class="mx-imgBorder"]
   > ![Primer polja za pretragu.](media/data-manager-configure-map-search-fields-example.png "Primer polja za pretragu")

4. Izaberite **Primeni** da biste potvrdili svoje izbore.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Izaberite primarni ključ i semantički tip za atribute

Nakon izbora entiteta, na stranici **Mapa** se navode izabrani entiteti za pregled. Definišite primarni ključ za entitet i identifikujte semantički tip za atribut u entitetu.

- **Primarni ključ**: Izaberite jedan atribut kao primarni ključ za svaki vaš entitet. Da bi atribut bio važeći primarni ključ, ne bi trebalo da sadrži duplirane vrednosti, nedostajuće vrednosti ili prazne vrednosti. Atributi tipa podataka niska, ceo broj i GUID podržani su kao primarni ključevi i biće prikazani u polju za odabir.

- **Semantički tip atributa**: Kategorije vaših atributa, kao što su adresa e-pošte ili ime. Da biste koristili modele veštačke inteligencije za pametno predviđanje semantike, uštedite vreme i poboljšajte tačnost, podesite **Inteligentno mapiranje** na **Da**. Inteligentno mapiranje ističe preporuke o semantici zasnovane na veštačkoj inteligenciji u polju **Tip**. Ako ga podesite na **ISKLJUČENO**, videćete naše redovne preporuke za mapiranje. Možete odabrati bilo koji semantički tip sa dostupne liste opcija i zameniti predloženi izbor.

> [!div class="mx-imgBorder"]
> ![Tip atributa i semantičko predviđanje.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Tip atributa i semantičko predviđanje")

Takođe je moguće dodati prilagođeni semantički tip. Izaberite polje tipa za taj atribut i unesite svoje prilagođeno semantičko ime tipa. Tako takođe možete da promenite vrste atributa koje je sistem identifikovao.

Svi atributi za koje je semantički tip automatski identifikovan grupisani su u odeljku **Pregled mapiranih polja**. Pregledajte ove atribute i njihove semantičke tipove, jer će se koristiti za kombinovanje vaših entiteta u koraku objedinjavanja tokom ujednačavanja podataka.

Atributi koji nisu automatski mapirani u semantički tip grupisani su u odeljku **Definisanje podataka u nemapiranim poljima**. Izaberite polje semantičkog tipa za nemapirane atribute ili unesite naziv prilagođenog tipa atributa.

> [!div class="mx-imgBorder"]
> ![Primarni ključ i vrsta atributa.](media/data-manager-configure-map-add-attributes.png "Primarni ključ i vrsta atributa")

> [!NOTE]
> Jedno polje bi trebalo da se mapira u semantički tip Person.FullName da bi se ime klijenta popunilo u korisničkoj kartici. U suprotnom, kartice klijenata će se prikazivati bez imena. 

## <a name="add-and-remove-attributes-and-entities"></a>Dodavanje i uklanjanje atributa i entiteta

1. U dijalogu **Ujednačavanje** > **Mapa**, izaberite **Uredi polja**.

2. U oknu **Uredi polja**, dodajte ili uklonite atribute i entitete. Koristite pretragu ili listajte da biste pronašli i izabrali svoje atribute i entitete od interesa. Ne možete ukloniti atribut ili entitet ako se već podudaraju.

   > [!div class="mx-imgBorder"]
   > ![Dodajte ili uklonite atribute.](media/configure-data-map-edit.png "Dodajte ili uklonite atribute")

3. Izaberite **Primeni**.

## <a name="add-images-to-profiles"></a>Dodavanje slika profilima

Ako entitet sadrži URL adrese javno dostupnih slika ili logotipa profila, možete ih dodati u objedinjeni profil klijenta.

Izaberite entitet i pronađite polje koje sadrži URL do slike profila. U polje za unos **Tip** ručno unesite sledeću vrednost: 
- Za osobu: Person.ProfileImage
- Za organizaciju: Organization.LogoImage

Nastavite sa koracima objedinjavanja i uverite se da je atribut koji sadrži URL adresu slike takođe dodat u korak [Spajanje](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Podešavanje atributa za organizacije

Za organizacije (pregled), tip atributa treba da bude mapiran na „Organization.Name“
> [!div class="mx-imgBorder"]
> ![Primarni ključ i atribut tipa B-to-B.](media/configure-data-map-edit-b2b.png "Primarni ključ i atribut tipa B-to-B")

## <a name="next-step"></a>Sledeći korak

Kao deo procesa objedinjavanja podataka, idite na stranicu **Podudaranje**. Posetite članak [**Podudaranje**](match-entities.md) da biste više saznali o ovoj fazi.

> [!TIP]
> Pogledajte sledeći video: [Prvi koraci: Kreiranje jedinstvenog profila klijenta](https://youtu.be/oBfGEhucAxs).


[!INCLUDE [footer-include](includes/footer-banner.md)]