---
title: Omogućavanje unapred definisanih izveštaja o profilima
description: Kako da kreirate unapred definisane izveštaje o profilima grupisane prema polu, starosti i okrugu ili regionu porekla.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033969"
---
# <a name="out-of-box-profile-reports"></a>Unapred definisani izveštaji o profilima

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Izveštaj je zbirka vizuelizacije podataka koja vam pomaže da razumete kako se korisnici ponašaju. Povezivanjem sa Customer Insights uvidima u ciljnu grupu, uvidi u angažovanje mogu da prikažu izveštaj sa informacijama o objedinjenim profilima klijenata. Ovaj izveštaj obuhvata broj profila koje imate, grupisane prema polu, starosti i geografskoj lokaciji.

## <a name="prerequisites"></a>Preduslovi

Okruženje uvida u ciljnu grupu mora da skladišti podatke u Azure Data Lake Storage nalogu koji je korisnički upravljan.

Ako koristite probnu verziju mogućnosti uvida u ciljnu grupu ili okruženje u jezeru podataka kojem upravlja Customer Insights, [obratite nam se](https://go.microsoft.com/fwlink/?linkid=2145734) za pomoć.  


## <a name="enable-the-customer-profile-report"></a>Omogućavanje izveštaja o profilu klijenta

Administrator okruženja da [kreira vezu sa uvidima u ciljnu grupu](configure-connections.md).

Nakon navođenja detalja o vezi, administrator može odobriti pristup drugim ljudima u organizaciji da vide izveštaj. Administrator okruženja koji podešava vezu automatski ima pristup izveštaju. 

Po završetku veze, funkcija **Profili** će biti dostupna u levom oknu za navigaciju. 

- Idi na **Otkrivanje** > **Profili** da biste videli izveštaj.

Izveštaj **Profili** sadrži vizualizacije o polu, starosti i geografskoj lokaciji povezanih profila klijenata.

:::image type="content" source="media/customer-profiles.png" alt-text="Izveštaj o profilu klijenta.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]