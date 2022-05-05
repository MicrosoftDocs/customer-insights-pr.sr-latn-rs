---
title: Bezbednosne postavke u Dynamics 365 Customer Insights
description: Saznajte više o bezbednosnim postavkama u Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653812"
---
# <a name="security-overview-page"></a>Stranica za pregled bezbednosti

Bezbednosna **stranica** navodi opcije za konfigurisanje korisničkih dozvola i funkcija koje pomažu da se učini Dynamics 365 Customer Insights bezbednijim. Samo administratori mogu da pristupe ovoj stranici. 

Idite na **adminSecurity** > **da** biste konfigurisali postavke.

Stranica **"** Bezbednost" sadrži sledeće kartice:
- [Korisnici](#users-tab)
- [API-ji](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Kartica "Korisnici"

Pristup uvidima klijenata ograničen je na korisnike u vašoj organizaciji koje je administrator dodao aplikaciji. Kartica **"Korisnici** " vam omogućava da upravljate korisničkim pristupom i njihovim dozvolama. Više informacija potražite u članku [Korisničke dozvole](permissions.md).

## <a name="apis-tab"></a>Kartica "APIS"

Prikažite ključeve i upravljajte njima da biste koristili [API-je korisničkih uvida](apis.md) sa podacima vašeg okruženja.

Nove primarne i sekundarne ključeve možete kreirati tako što ćete izabrati **stavku Regeneriši primarnu** ili **regeneriši sekundarnu**. 

Da biste blokirali API pristup okruženju, izaberite **Onemogući**. Ako su API-je onemogućeni, možete izabrati opciju Omogući **da** ponovo odobri pristup.

## <a name="key-vault-tab"></a>Kartica "Trezor ključa"

Kartica **"Ključni trezor** " vam omogućava da povežete sopstveni [Azure ključni trezor sa](/azure/key-vault/general/basic-concepts) okolinom i upravljate njima.
Namensko bezbednosno skladište može da se koristi za postavljanje i korišćenje tajni u granicama usklađenosti organizacije. Uvidi klijenata mogu da koriste tajne u Azure ključ trezoru za [podešavanje veza sa sistemima](connections.md) nezavisnih proizvođača.

Za više informacija pogledajte članak [Dovedite sopstveni Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
