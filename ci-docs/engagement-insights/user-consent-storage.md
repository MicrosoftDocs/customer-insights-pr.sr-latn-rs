---
title: Upravljanje kolačićima i pristankom korisnika za skladištenje korisničkih podataka u sistemu Dynamics 365 Customer Insights
description: Razumite kako se kolačići i saglasnost korisnika koriste za identifikaciju posetilaca veb-stranice.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229002"
---
# <a name="manage-cookies-and-user-consent"></a>Upravljajte kolačićima i pristankom korisnika

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights mogućnost uvida u angažovanje koristi kolačiće i (`localStorage`) ključeve za identifikaciju posetilaca veb-lokacije.

Kolačići su male datoteke u kojima se čuvaju komadići informacija o interakciji korisnika sa veb-lokacijom. Čuvaju se u veb-pregledačima. Kada korisnici posete veb-lokaciju za koju su vaši korisnici sačuvali kolačiće, pregledač šalje te informacije serveru, koji vraća informacije koje su jedinstvene za korisnika. Ovo je tehnologija koja omogućava, na primer, korpu za kupovinu na mreži da čuva izabrane artikle čak i ako korisnik napusti veb-lokaciju.

## <a name="user-consent"></a>Pristanak korisnika

[Opšta uredba o zaštiti podataka (GDPR)](/dynamics365/get-started/gdpr/) je uredba Evropske unije (EU) koja nalaže kako organizacije treba da postupaju sa privatnošću i bezbednošću svojih korisnika. Kolačići često čuvaju ili prikupljaju „lične podatke“, kao što je identifikator prisustva na mreži, koji je pokriven GDPR-om. Ako vaše preduzeće zapošljava i/ili prodaje subjektima podataka iz EU, GDPR utiče na vas. [Saznajte više o tome kako vam Microsoft može pomoći da se pridržavate GDPR-a](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Da biste omogućili SDK-u za uvide u angažovanje da čuva kolačića ili druge osetljive podatke, morate da navedete da li su vaši korisnici dali pristanak. To se dešava prilikom inicijalizacije SDK postavljanjem polja `userConsent` u konfiguraciji.

Ako naznačite da ne postoji saglasnost korisnika, SDK neće čuvati nikakve podatke i neće slati događaje koji se mogu koristiti za praćenje ponašanja korisnika. Svi prethodno sačuvani podaci biće izbrisani iz pregledača.

Ako nije navedena vrednost saglasnosti korisnika, SDK će pretpostaviti da je korisnik dao saglasnost. To znači da će se, ako vi (kao naš klijent) ne navedete vrednost za saglasnost korisnika u SDK-u, podaci prikupljati. Međutim, ako navedete da vrednost za saglasnost korisnika mora da bude „tačno“, podaci se neće prikupljati ako korisnik odbije ili ne pruži izričitu saglasnost.

Ispod je fragment koda za pokretanje veb SDK-a sa pristankom korisnika:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Čuvanje podataka o posetiocima u mogućnosti uvida u angažovanje

### <a name="cookies"></a>Kolačići

- _msei
    - Skladišti anonimni ID korisnika. Ovaj kolačić je postavljen na domenu klijenta i ističe za 365 dana.

### <a name="local-storage"></a>Lokalno skladište

Mogućnost uvida u angažovanje takođe koristi (`localStorage`) ključeve za praćenje neosetljivih podataka. Ovi podaci se u potpunosti skladište u samom pregledaču, bez saobraćaja koji se šalje na vaše servere ili sa njih.

- *EISession.Id*
    - Skladišti informacije o tekućoj sesiji korisnika, kao što je ID sesije, kada je započela i kada ističe.
- *EISession.Previous*
    - Skladišti URL adresu prethodno posećene stranice u trenutnoj sesiji.

Ključevi u lokalnoj memoriji ne ističu automatski i uspostaviće početne vrednosti se tokom sledeće sesije SDK-a.

## <a name="deleting-cookies"></a>Brisanje kolačića

Vaši klijenti mogu u bilo kom trenutku ručno da izbrišu kolačiće i ključeve lokalnog skladišta kroz podešavanja svog pregledača.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
