---
title: O prilagođenim izveštajima
description: Naučite kako da kreirate i uređujete prilagođene izveštaje.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: e8cdfc07b67b78febc1d50b3b1fd44ab94448e64
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232165"
---
# <a name="create-and-edit-custom-reports"></a>Kreiranje i uređivanje prilagođenih izveštaja

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Pored spremnih izveštaja (OOB), možete da napravite prilagođeni izveštaj sa vizuelizacijama grafikona i tabela da biste razumeli ponašanje korisnika. Ovaj članak objašnjava kako da kreirate izveštaj sa podacima koji su vam potrebni koristeći vizuelizacije tabela i grafikona. Za informacije o OOB izveštajima, pogledajte [Prikaz izveštaja](view-reports.md).

## <a name="create-a-custom-report"></a>Kreiranje prilagođenog izveštaja

1. Idite na **Analiziraj** > **Prilagođeno** za pristup listi prilagođenih izveštaja.

1. Izaberite **Novi izveštaj** da biste započeli sa kreiranjem prilagođenog izveštaja.

   :::image type="content" source="media/new-custom-report.png" alt-text="Novi prilagođeni izveštaji.":::

1. Odlučite koji tip izveštaja koji želite da napravite:

    - Izaberite **Dodaj vizuelni element** u komandnoj traci da biste kreirali podrazumevanu vizuelizaciju tabele.
    - Ili izaberite stubičasti, trakasti, linijski, prostorni, kružni, prstenasti ili vizuelizaciju tabele iz okna **Uređivač izveštaja**.

1. U odeljku **Podaci** okna **Uređivač vizuelizacije**, odaberite jednu od dostupnih opcija (na primer, prikazi stranica) iz padajućeg menija **Pokazatelji**. Takođe možete dodati **Dimenzije** (na primer, država) za prikaz na vizuelizaciji. Za više informacija pogledajte [Prikaz i kreiranje pokazatelja](metrics.md) i [Prikaz i kreiranje dimenzija](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Odaberite pokazatelj za vaš izveštaj.":::

1. Izaberite odeljak **Dizajn** u oknu **Uređivač vizuelizacije** za dodavanje **Teksta naslova** i uključite ili isključite **Pločicu**.  Tip vizuelizacije možete promeniti i izborom drugog grafikona, na primer, **kružni grafikon**.

1. Da biste promenili veličinu i položaj vizuelizacije:
   - Izaberite vizuelizaciju, a zatim prevucite jedan od uglova ili ivica da biste prilagodili njegovu veličinu.
   - Izaberite vizuelizaciju i premestite je na novi položaj. Takođe možete da koristite tastere sa strelicama za promenu položaja.
1. Da biste dodali drugu vizuelizaciju, na komandnoj traci izaberite **Dodaj vizuelni element**.
1. Nakon dodavanja vizuelizacija koje želite za izveštaj, na komandnoj traci izaberite **Sačuvaj**.

1. Navedite ime za prilagođeni izveštaj i izaberite **Sačuvaj** da ga kreirali.
 
## <a name="filter-a-custom-report"></a>Filtriranje prilagođenog izveštaja

Možete da izaberete vremenski okvir ili period u prilagođenom izveštaju da biste se fokusirali na vrednost ili vremenski period.

Da biste izabrali vremenski okvir, u gornjem desnom uglu prikaza izveštaja izaberite vrednost sa padajuće liste izveštaja. Takođe možete odabrati **Fiksni period*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Filtrirajte prema vremenu ili periodu.":::

Za većinu izveštaja izaberite **+ Dodaj uslov** da biste izabrali dimenziju ili segment za filtriranje izveštaja. Za više informacija pogledajte [Prikaz i kreiranje segmenata](segments.md).

## <a name="edit-a-custom-report"></a>Uređivanje prilagođenog izveštaja

1. Idite na **Analiziraj** > **Prilagođeno** za pristup listi prilagođenih izveštaja.

1. Na listi prilagođenih izveštaja izaberite **Još [...]** 

1. Odaberite **Uredi naziv** da biste promenili naziv izveštaja.

1. Izaberite naziv izveštaja i koristite opcije **+Dodaj vizuelni element** i **Uredi** za dodavanje, uklanjanje, premeštanje ili promenu veličine vizuelizacija.

1. Da biste promenili svojstva vizuelizacije, izaberite vizuelni element, izaberite **...**, a zatim **Izmeni vizuelni element**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Uređivanje svojstava grafikona za prilagođene izveštaje.":::

1. Kada završite uređivanje izveštaja, izaberite **Sačuvaj** da biste primenili izmene. 

## <a name="delete-a-custom-report"></a>Brisanje prilagođenog izveštaja

1. Idite na **Analiziraj** > **Prilagođeno** za pristup listi prilagođenih izveštaja.

1. Na listi prilagođenih izveštaja izaberite **...**

1. Odaberite **Izbriši** da biste uklonili izveštaj.

1. Potvrdite brisanje da biste trajno uklonili izveštaj.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
