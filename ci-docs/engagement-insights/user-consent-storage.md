---
title: Upravljanje kolačićima i saglasnošću korisnika za čuvanje korisničkih podataka
description: Razumite kako se kolačići i saglasnost korisnika koriste za identifikaciju posetilaca veb-stranice.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036755"
---
# <a name="manage-cookies-and-user-consent"></a>Upravljajte kolačićima i pristankom korisnika

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights mogućnost uvida u angažovanje koristi kolačiće i lokalno skladište (`localStorage`) za identifikovanje posetilaca veb-stranice.

Kolačići su male datoteke u kojima se čuvaju komadići informacija o interakciji korisnika sa veb-lokacijom. Čuvaju se u veb-pregledačima. Kada korisnici posete veb-lokaciju za koju su vaši korisnici sačuvali kolačiće, pregledač šalje te informacije serveru, koji vraća informacije koje su jedinstvene za korisnika. Ovo je tehnologija koja omogućava, na primer, korpu za kupovinu na mreži da čuva izabrane artikle čak i ako korisnik napusti veb-lokaciju.

## <a name="user-consent"></a>Pristanak korisnika

[Opšta uredba o zaštiti podataka (GDPR)](/dynamics365/get-started/gdpr/) je uredba Evropske unije (EU) koja nalaže kako organizacije treba da postupaju sa privatnošću i bezbednošću svojih korisnika. Kolačići često čuvaju ili prikupljaju „lične podatke“, kao što je identifikator prisustva na mreži, koji je pokriven GDPR-om. Ako vaše preduzeće zapošljava i/ili prodaje subjektima podataka iz EU, GDPR utiče na vas. [Saznajte više o tome kako vam Microsoft može pomoći da se pridržavate GDPR-a](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Da biste omogućili SDK-u za uvide u angažovanje da čuva kolačića ili druge osetljive podatke, morate da navedete da li su vaši korisnici dali pristanak. Do toga dolazi inicijalizacije SDK-a.

Ako naznačite da ne postoji saglasnost korisnika, SDK neće čuvati nikakve podatke i neće slati događaje koji se mogu koristiti za praćenje ponašanja korisnika. Svi prethodno sačuvani podaci biće izbrisani iz pregledača.

Ako nije navedena vrednost saglasnosti korisnika, SDK će pretpostaviti da je korisnik dao saglasnost. To znači da će se, ako vi (kao naš klijent) ne navedete vrednost za saglasnost korisnika u SDK-u, podaci prikupljati. Međutim, ako navedete da vrednost za saglasnost korisnika mora da bude „tačno“, podaci se neće prikupljati ako korisnik odbije ili ne pruži izričitu saglasnost.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Čuvanje podataka o posetiocima u mogućnosti uvida u angažovanje

### <a name="cookies"></a>Kolačići

- _msei
    - Skladišti anonimni ID korisnika. Ovaj kolačić je postavljen na domenu klijenta i ističe za 365 dana.

### <a name="local-storage"></a>Lokalno skladište

Mogućnost uvida u angažovanje takođe koristi lokalno skladište (`localStorage`) za praćenje neosetljivih podataka. Ovi podaci se u potpunosti skladište u samom pregledaču, bez saobraćaja koji se šalje na vaše servere ili sa njih.

- *EISession.Id* 
    - Skladišti informacije o tekućoj sesiji korisnika, kao što je ID sesije, kada je započela i kada ističe.
- *EISession.Previous*
    - Skladišti URL adresu prethodno posećene stranice u trenutnoj sesiji.
    
Ključevi u lokalnom skladištu ne ističu automatski. SDK će ih resetovati tokom sledeće sesije.

## <a name="deleting-cookies"></a>Brisanje kolačića

Vaši klijenti mogu u bilo kom trenutku ručno da izbrišu kolačiće i ključeve lokalnog skladišta kroz podešavanja svog pregledača.


[!INCLUDE[footer-include](../includes/footer-banner.md)]