---
title: Bezbednosne postavke u uvidima klijenata
description: Saznajte više o bezbednosnim postavkama u Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947432"
---
# <a name="security-settings-in-customer-insights"></a>Bezbednosne postavke u uvidima klijenata

Bezbednosna **stranica** navodi opcije za konfigurisanje korisničkih dozvola i funkcija koje pomažu da se učini Dynamics 365 Customer Insights bezbednijim. Samo administratori mogu da pristupe ovoj stranici.

Idite na administrator **bezbednost** > **da biste** konfigurisali postavke.

Stranica **"** Bezbednost" sadrži sledeće kartice:

- [Korisnici](#users-tab)
- [API-ji](#apis-tab)
- [Privatne veze](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Bezbedan pristup podacima klijenata pomoću okvira za zaključavanje klijenta (pregled)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Kartica "Korisnici"

Pristup uvidima klijenata ograničen je na korisnike u vašoj organizaciji koje je administrator dodao aplikaciji. Kartica **"Korisnici** " vam omogućava da upravljate korisničkim pristupom i njihovim dozvolama. Više informacija potražite u članku [Korisničke dozvole](permissions.md).

## <a name="apis-tab"></a>Kartica "APIS"

Prikažite ključeve i upravljajte njima da biste koristili [API-je korisničkih uvida](apis.md) sa podacima vašeg okruženja.

Nove primarne i sekundarne ključeve možete kreirati tako što ćete izabrati **stavku Regeneriši primarnu** ili **regeneriši sekundarnu**. 

Da biste blokirali API pristup okruženju, izaberite **Onemogući**. Ako su API-je onemogućeni, možete izabrati opciju Omogući **da** ponovo odobri pristup.

## <a name="private-links-tab"></a>Kartica "Privatne veze"

[Azure privatna veza omogućava](/azure/private-link/private-link-overview) korisnicima da se povežu sa vašim nalogom Azure Data Lake Storage preko privatnog krajnja tačka u virtuelnoj mreži. Za podatke u nalogu za skladištenje, koji nije izložen javnom Internetu, privatna veza omogućava povezivanje sa tom ograničenom mrežom.

> [!IMPORTANT]
> Minimalni zahtev za uloga za podešavanje veze privatne veze:
>
> - Uvidi klijenata: administrator
> - Ugrađena uloga Azure: Nalog [za skladištenje saradnik](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Dozvole za prilagođenu Azure ulogu: [Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Podešavanje privatne veze u uvidima klijenata je proces u dva koraka. Prvo započinjete kreiranje privatne veze iz administratorskog obezbeđenja **Privatne** > **veze** > **u uvidima** klijenata. Okno **"Dodavanje privatne** veze" navodi naloge za skladištenje od stanara koje imate dozvole da vidite. Izaberite nalog za skladištenje i obezbedite saglasnost za kreiranje privatne veze.

Zatim je potrebno da odobrite privatnu vezu na strani naloga za skladištenje podataka Lejk. Otvorite vezu predstavljenu na ekranu da biste odobrili novu privatnu vezu.

## <a name="key-vault-tab"></a>Kartica "Trezor ključa"

Kartica **"Ključni trezor** " vam omogućava da povežete sopstveni [Azure ključni trezor sa](/azure/key-vault/general/basic-concepts) okolinom i upravljate njima.
Namensko bezbednosno skladište može da se koristi za postavljanje i korišćenje tajni u granicama usklađenosti organizacije. Uvidi klijenata mogu da koriste tajne u Azure ključ trezoru za [podešavanje veza sa sistemima](connections.md) nezavisnih proizvođača.

Za više informacija pogledajte članak [Dovedite sopstveni Azure Key Vault](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Bezbedan pristup podacima klijenata pomoću okvira za zaključavanje klijenta (pregled)

Customer Insights koristi mogućnost zaključavanja Power Platform kupca. Customer Lockbox obezbeđuje interfejs za redigovanje i odobravanje (ili odbacivanje) zahteva za pristup podacima. Do ovih zahteva dolazi kada je potreban pristup podacima o podacima korisnika da bi se rešio predmet podrške. Da biste koristili ovu funkciju, "Uvidi kupaca" moraju da imaju postojeću vezu sa Microsoft Dataverse okruženjem u vašem zakupu.

Više informacija o okviru za zaključavanje kupca potražite u rezimeu [okvira](/power-platform/admin/about-lockbox#summary) za Power Platform zaključavanje kupca. Članak takođe opisuje tok posla i potrebno [podešavanje](/power-platform/admin/about-lockbox#workflow) da bi se [omogućilo zaključavanje](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) kupca.

> [!IMPORTANT]
> Globalni administratori za ili Power Platform administratori Power Platform mogu da odobre zahteve za zaključavanje klijenta izdate za uvid u kupce.

[!INCLUDE [footer-include](includes/footer-banner.md)]
