---
title: Prepoznajte veb-događaje od posetilaca kojima je prethodno potvrđen identitet iz nepoznatih u poznate
description: Funkcija Nepoznato u poznato vam omogućava da povežete događaje na veb-lokaciji sa posetiocima koji su prethodno izvršili potvrdu identiteta.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036800"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Prepoznajte veb-događaje od posetilaca kojima je prethodno potvrđen identitet

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Funkcija **nepoznato u poznato** u mogućnosti uvida u angažovanje omogućava povezivanje događaja na veb-lokaciji sa posetiocima koji su prethodno izvršili potvrdu identiteta. Ako je funkcija onemogućena, posetioci koji su potvrdili identitet tokom ranije posete, a zatim otišli, neće biti identifikovani ako pri povratku opet ne izvrše potvrdu identiteta. 

Na primer, osoba je prošle nedelje posetila veb-lokaciju, prijavila se na svoj korisnički nalog na njoj i pregledala katalog proizvoda. Osoba se sledeće nedelje vraća da pregleda još proizvoda bez prijavljivanja na svoj nalog. Vlasnik veb-lokacije koji koristi funkciju **Nepoznato u poznato** bi znao da se ista osoba vratila i šta je radila na veb-lokaciji. Ovo omogućava preciznije izveštavanje i analizu aktivnosti veb-stranice.

## <a name="enable-unknown-to-known"></a>Omogućavanje funkcije „nepoznato u poznato“

Za omogućavanje ove funkcije morate da budete [administrator radnog prostora](user-roles.md). 

1. U uvidima u angažovanje, idite na **Administrator** > **Radni prostor**. 
2. Izaberite karticu **Podešavanja**.
3. U odeljku **Nepoznato u poznato**, podesite prekidač na **Omogućeno**.

![Omogućavanje funkcije „nepoznato u poznato“](media/U2Ktoggle.png "Omogućavanje funkcije „nepoznato u poznato“")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Dodavanje JavaScript koda u fragment za praćenje vaše lokacije

Veb-lokacija može zabeležiti **authId korisnika** sa sledećim JavaScript uzorkom koristeći [veb SDK uvida u angažovanje](advanced-SDK-implementation.md). Kako bi funkcija **nepoznato u poznato** radila, morate da zabeležite authId *i* omogućite userMapping:True u vašem JavaScript fragmentu kao u donjem primeru.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
