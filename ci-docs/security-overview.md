---
title: Konfigurisanje bezbednosnih postavki
description: Saznajte više o bezbednosnim postavkama u Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246079"
---
# <a name="configure-security-settings"></a>Konfigurisanje bezbednosnih postavki

Upravljajte API ključevima, pristupite podacima klijenata i podesite Azure privatnu vezu.

## <a name="manage-api-keys"></a>Upravljanje API ključevima

Prikažite ključeve i upravljajte njima da biste koristili [API-je korisničkih uvida](apis.md) sa podacima u vašem okruženju.

1. Idite na **opciju** > **"Bezbednost** sistema" i izaberite **karticu "API-je**".

1. Ako API pristup okruženju nije podešen, izaberite opciju **Omogući**. Ili, da biste blokirali API pristup okruženju, izaberite Onemogući **i** potvrdi.

1. Upravljajte primarnim i sekundarnim API ključevima:

   1. Izaberite simbol "Prikaži" da biste prikaželi primarni ili sekundarni **API** ključ.

   1. Izaberite simbol Kopiraj da biste kopirali primarni ili sekundarni **API** ključ.

   1. Da biste kreirali nove primarne ili sekundarne API ključeve, izaberite **opciju Ponovo generiši** primarni **ili ponovo generiši sekundarne**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Bezbedan pristup podacima klijenata pomoću okvira za zaključavanje klijenta (pregled)

Customer Insights koristi mogućnost zaključavanja Power Platform kupca. Customer Lockbox obezbeđuje interfejs za redigovanje i odobravanje (ili odbacivanje) zahteva za pristup podacima. Do ovih zahteva dolazi kada je potreban pristup podacima o podacima korisnika da bi se rešio predmet podrške. Da biste koristili ovu funkciju, "Uvidi kupaca" moraju da imaju postojeću vezu sa Microsoft Dataverse okruženjem u vašem zakupu.

Više informacija o okviru za zaključavanje kupca potražite u rezimeu [okvira](/power-platform/admin/about-lockbox#summary) za Power Platform zaključavanje kupca. Članak takođe opisuje tok posla i potrebno [podešavanje](/power-platform/admin/about-lockbox#workflow) da bi se [omogućilo zaključavanje](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) kupca.

> [!IMPORTANT]
> Globalni administratori za ili Power Platform administratori Power Platform mogu da odobre zahteve za zaključavanje klijenta izdate za uvid u kupce.

## <a name="set-up-an-azure-private-link"></a>Podešavanje Azure privatne veze

[Azure privatna veza omogućava](/azure/private-link/private-link-overview) korisnicima da se povežu sa vašim nalogom Azure Data Lake Storage preko privatnog krajnja tačka u virtuelnoj mreži. Za podatke u nalogu za skladištenje, koji nije izložen javnom Internetu, privatna veza omogućava povezivanje sa tom ograničenom mrežom.

> [!IMPORTANT]
> Minimalni zahtev za uloga za podešavanje veze privatne veze:
>
> - Uvidi klijenata: administrator
> - Ugrađena uloga Azure: Nalog [za skladištenje saradnik](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Dozvole za prilagođenu Azure ulogu: [Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. U fascikli "Uvidi klijenata" idite na opciju **"Administrator bezbednosti** > **·**" i izaberite karticu **"Privatne veze**".

1. Izaberite **dodaj privatnu vezu**.

   Okno **"Dodavanje privatne** veze" navodi naloge za skladištenje od stanara koje imate dozvole da vidite.

1. Izaberite nalog pretplate, grupe resursa i skladišta.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Izaberite **Sačuvaj**.

1. Idite na svoj Data Lake Storage nalog i otvorite vezu predstavljenu na ekranu.

1. Odobrite privatnu vezu.


[!INCLUDE [footer-include](includes/footer-banner.md)]
