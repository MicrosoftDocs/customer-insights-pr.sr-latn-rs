---
title: Upravljanje okruženjima
description: Saznajte kako da upravljate postojećim okruženjima uvida klijenata kao administrator."
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 8b4a88bdb75c6e638a76c39d18647681ad4556d7
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304306"
---
# <a name="manage-environments"></a>Upravljanje okruženjima

Administratori kreiraju [okruženja](create-environment.md) i upravljaju njima. Oni mogu da promene neke postavke u postojećim okruženjima. Posao, tip, region, opcija skladištenja i postavke Dataverse se popravljaju nakon kreiranja okruženja. Ako želite da promenite ove postavke, uspostavite [početne vrednosti okruženja](#reset-an-existing-environment-preview)[ili kreirajte novo okruženje](create-environment.md).

## <a name="edit-an-existing-environment"></a>Uređivanje postojećeg okruženja

Uredite detalje postojećeg okruženja kao što je ime ili postavljanje podrazumevanog okruženja.

1. Izaberite birač **Okruženje** u zaglavlju aplikacije.

1. Izaberite ikonu **Uređivanje**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikona za uređivanje postavki okruženja.":::

1. U oknu **"Uređivanje** okruženja" ažurirajte postavke okruženja.

1. Izaberite rediguj **i završi**, a zatim **ažuriraj** da biste primenili promene.

## <a name="change-the-owner-of-an-environment"></a>Promena vlasnika okruženja

Nekoliko korisnika može da ima administratorske dozvole, ali samo jedan korisnik je vlasnik okruženja. Po podrazumevanoj vrednosti, administrator je taj koji u početku kreira okruženje. Kao administrator okruženja, možete da dodelite vlasništvo drugom korisniku sa administratorske dozvole.

1. Izaberite birač **Okruženje** u zaglavlju aplikacije.

1. Izaberite ikonu **Uređivanje**.

1. U oknu **"Uređivanje** okruženja" pređite na **osnovni korak sa informacijama**.

1. U polju **Promeni vlasnika okruženja** odaberite novog vlasnika okruženja.  

1. Izaberite rediguj **i završi**, a zatim **ažuriraj** da biste primenili promene.

## <a name="claim-ownership-of-an-environment"></a>Tražite vlasništvo nad okruženjem

Ako je korisnički nalog vlasnika izbrisan ili suspendovan, okruženje neće imati vlasnika. Svaki korisnik administratora može da preuzme vlasništvo i postane novi vlasnik. Administrator vlasnika može da nastavi da poseduje okruženje ili da [promeni vlasništvo u drugog administratora](#change-the-owner-of-an-environment).

Da biste preuzeli vlasništvo, izaberite dugme **"Preuzmi vlasništvo** " koje se prikazuje na vrhu svake stranice u "Uvidima kupaca" kada je originalni vlasnik napustio organizaciju.

## <a name="reset-an-existing-environment-preview"></a>Uspostavljanje početnih vrednosti postojećeg okruženja (pregled)

Kao vlasnik okruženja, vratite okruženje na prazno stanje ako želite da izbrišete sve konfiguracije i uklonite unete podatke.

1. Izaberite birač **Okruženje** u zaglavlju aplikacije.

1. Izaberite okruženje koje želite da uspostavite početne vrednosti i izaberite vertikalnu elipsu (&vellip;).

1. Odaberite uspostavljanje **početnih vrednosti (pregled)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kontrola za uspostavljanje početnih vrednosti okruženja.":::

1. Odaberite da li želite da uspostavite početne vrednosti celog okruženja, svega osim izvora podataka ili bilo čega što je konfigurisano iznad objedinjenog profila klijenta.

1. Da biste potvrdili, unesite ime okruženja i kliknite na dugme "Uspostavi početne **vrednosti"**.

## <a name="delete-an-existing-environment"></a>Brisanje postojećeg okruženja

Kao vlasnik okruženja, možete da ga izbrišete.

> [!IMPORTANT]
> Brisanje okruženja ne uklanja vezu sa okruženjem Dataverse. Ako planirate da ubuduće povezujete Dataverse isto okruženje sa novim okruženjem "Uvidi kupaca", morate ukloniti [tu vezu sa okruženjem Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Izaberite birač **Okruženje** u zaglavlju aplikacije.

1. Izaberite okruženje koje želite da izbrišete i izaberite vertikalnu elipsu (&vellip;). 

1. Odaberite stavku **Izbriši**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kontrola za brisanje okruženja.":::

1. Da biste potvrdili brisanje, unesite naziv okruženja i izaberite **Izbriši**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
