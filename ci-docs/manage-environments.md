---
title: Kako da - Upravljanje okruženjima
description: Saznajte kako da upravljate postojećim okruženjima uvida klijenata kao administrator."
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833509"
---
# <a name="how-to-manage-environments"></a>Kako da: upravljanje okruženjima

Administratori kreiraju [okruženja](create-environment.md) i upravljaju njima. Oni mogu da promene neke postavke u postojećim okruženjima. Posao, tip, region, opcija skladištenja i postavke Dataverse se popravljaju nakon kreiranja okruženja. Ako želite da promenite ove postavke, uspostavite početne vrednosti okruženja ili kreirajte novo okruženje.

## <a name="edit-an-existing-environment"></a>Uređivanje postojećeg okruženja

Možete da izmenite neke detalje postojećih okruženja.

1. Izaberite birač **Okruženje** u zaglavlju aplikacije.

1. Izaberite ikonu **Uređivanje**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikona za uređivanje postavki okruženja.":::

1. U okviru **Uređivanje okruženja**, možete ažurirati podešavanja okruženja.

Za početak, pogledajte članak Kreiranje [novog okruženja](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Promena vlasnika okruženja

Nekoliko korisnika može da ima administratorske dozvole, ali samo jedan korisnik je vlasnik okruženja. Po podrazumevanoj vrednosti, administrator je taj koji u početku kreira okruženje. Kao administrator okruženja, možete da dodelite vlasništvo drugom korisniku sa administratorske dozvole.

1. Izaberite birač **Okruženje** u zaglavlju aplikacije.

1. Izaberite ikonu **Uređivanje**.

1. U okviru **Uredi okruženje** pređite na osnovni **informacioni** korak.

1. U polju **Promeni vlasnika okruženja** odaberite novog vlasnika okruženja.  

1. Izaberite rediguj **i završi**, a zatim **ažuriraj** da biste primenili promene.

## <a name="claim-ownership-of-an-environment"></a>Tražite vlasništvo nad okruženjem

Ako je korisnički nalog vlasnika izbrisan ili suspendovan, okruženje neće imati vlasnika. Svaki korisnik administratora može da preuzme vlasništvo i postane novi vlasnik. Oni mogu da nastave da poseduju životnu sredinu [ili da promene vlasništvo u drugog administratora](#change-the-owner-of-an-environment).

Da biste preuzeli vlasništvo, izaberite dugme **"Preuzmi vlasništvo** " koje se prikazuje na vrhu svake stranice u "Uvidima kupaca" kada je originalni vlasnik napustio organizaciju.

## <a name="reset-an-existing-environment-preview"></a>Uspostavljanje početnih vrednosti postojećeg okruženja (pregled)

Kao vlasnik okruženja, možete da uspostavite početne vrednosti okruženja na prazno stanje ako želite da izbrišete sve konfiguracije i uklonite unete podatke.

1. Izaberite birač **Okruženje** u zaglavlju aplikacije.

1. Izaberite okruženje koje želite da uspostavite početne vrednosti i izaberite vertikalnu elipsu (&vellip;).

1. Izaberite opciju **Resetuj**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kontrola za uspostavljanje početnih vrednosti okruženja.":::

1. Odaberite da li želite da uspostavite početne vrednosti celog okruženja, svega osim izvora podataka ili bilo čega što je konfigurisano iznad objedinjenog profila klijenta.

1. Da biste potvrdili, unesite ime okruženja i kliknite na dugme "Uspostavi početne **vrednosti"**.

## <a name="delete-an-existing-environment"></a>Brisanje postojećeg okruženja

Kao vlasnik okruženja, možete da izbrišete okruženje kojim upravljate.

1. Izaberite birač **Okruženje** u zaglavlju aplikacije.

1. Izaberite okruženje koje želite da uspostavite početne vrednosti i izaberite vertikalnu elipsu (&vellip;). 

1. Odaberite opciju **Izbriši**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kontrola za brisanje okruženja.":::

1. Da biste potvrdili brisanje, unesite naziv okruženja i izaberite **Izbriši**.

> [!IMPORTANT]
> Brisanje okruženja ne uklanja vezu sa okruženjem Dataverse. Ako planirate da ubuduće povezujete Dataverse isto okruženje sa novim okruženjem "Uvidi kupaca", morate ukloniti tu vezu Saznajte [kako da uklonite postojeću vezu sa okruženjem Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
