---
title: Koristi saglasnost kupca
description: Ispoštuj željene opcije saglasnosti klijenata u uvidima klijenata uvozom podataka o pristanku.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99fe24cb47a8c20f629182d9a1c6adfd36a1eaf7
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188065"
---
# <a name="use-customer-consent"></a>Koristi saglasnost kupca

Propisi o zaštiti podataka i privatnosti pružaju pojedincima pravo da regulišu način na koji organizacija koristi svoje lične podatke. Primeri takvih propisa su Opšta uredba o zaštiti podataka u Evropskoj uniji ili Kalifornijski zakon o privatnosti potrošača u SJEDINJENIM Državama. Ovi propisi omogućavaju osobama da se opredele da svoje lične podatke prikupljaju, obrađuju ili dele sa trećim licima.  

Kupci mogu odabrati da povuku ili uskrate svoj pristanak za određene oblike kontakta. Oni takođe mogu zahtevati da ih odbijete iz prikupljanja, skladištenja, korišćenja ili prodaje njihovih ličnih podataka. Važno je da vaša organizacija ispoštuje saglasnost svih klijenata i željene opcije privatnosti.  

Dynamics 365 Customer Insights pomaže vam da ispoštujete zahteve klijenata uvozom i skladištenjem njihovih željenih opcija kao dela objedinjenih profila klijenata.

Ako se podaci o pristanku skladište odvojeno od profila klijenata, dodajte [podatke o saglasnosti kao novi izvor podataka](#import-and-unify-consent-data). Program izvor podataka koji sadrži podatke o saglasnosti dodaje se procesu ujedinjenja podataka. Uspešno ujedinjenje podataka o pristanku i profila klijenata zatim dovodi do objedinjenih profila klijenata koji sadrže informacije o pristanku. Za profile klijenata koji već sadrže informacije o pristanku idite direktno u odeljak sa podacima [o korišćenju saglasnosti](#use-consent-data).

## <a name="prerequisites"></a>Preduslovi

Sledeće informacije moraju biti dostupne u izvornim podacima da biste ujedinili podatke o pristanku sa drugim profilima klijenata:

- Alternativni ključ da mapirate informacije o saglasnosti na korisničke profile u uvidima klijenata. Na primer, e-adresa ili broj telefona.
- Vrednost saglasnosti za određivanje statusa saglasnosti kupca.

Razmislite o dodavanju sledećih *opcionalnih* informacija:

- Primarni ključ za ažuriranje statusa pristanka ako kupac zatraži promenu.
- Tip pristanka, ako postoji više načina za obradu informacija o klijentima.
- Datum pristanka ili bilo koji drugi tip podataka relevantan za vaše scenarije pristanka.

Primer tabele jednostavne baze podataka saglasnosti sa više opcija pristanka:

|ID pristanka (primarni ključ)   |Email (Alternativni ključ)  |Opcija pristanka  |Vrednost pristanka  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Bilten       |  Netačno       |
|2    |  holly@contoso.com       |  Ispravke proizvoda       |  Tačno       |
|3    |  frank@contoso.com       |  Bilten       | Tačno        |
|4    |  frank@contoso.com       |  Ispravke proizvoda       |  Netačno       |

## <a name="import-and-unify-consent-data"></a>Uvoz i ujedinjenje podataka o pristanku

Uvezite podatke o saglasnosti na isti način na koji unosite druge izvore podataka u korisničke uvide. Više informacija o podržanim izvorima podataka i načinu njihovog uvoza potražite u [pregledu izvora podataka](data-sources.md).

Više informacija o ujedinjenju izvora podataka potražite u pregledu [pregleda ujedinjenja podataka](data-unification.md).

## <a name="use-consent-data"></a>Korišćenje podataka o pristanku

Kada podaci o saglasnosti budu deo objedinjenih profila klijenata, možete ih koristiti u okviru stavke "Uvidi kupaca". Na primer, kreirajte segment sa pravilom da biste se uverili da poštujete željene postavke privatnosti i zaštite podataka klijenata. Pravila koja podržavaju željene opcije pristanka koriste se za isključivanje korisnika iz segmenta zasnovanog na atributima profila. Dodajte pravilo segmentu koji isključuje profile klijenata koji nisu dali saglasnost za kontakt.

Govoreći o gorenavedenom uzorku tabele, segment može da sadrži ovo pravilo:`Consent option=Newsletter & Consent value=True`. Ova konfiguracija rezultira segmentom koji poštuje željene opcije kontakta za slanje biltena.

Više informacija o izradi segmenata potražite u članku [Kreiranje segmenata](segment-builder.md).

Kada kreirate segment, možete da koristite jednu od mnogih opcija [izvoza da](export-destinations.md) biste koristili segment u drugim aplikacijama.

## <a name="ensure-updated-consent-status"></a>Uverite se da je ažuriran status pristanka

Važno je da status pristanka za kupce bude ažuriran. Planirano osvežavanje u uvidima klijenata uvek uvozi najnovije stanje izvora podataka. Ove informacije se zatim obrađuju putem ujedinjenja podataka i rezultiraju ažuriranim profilima klijenata. Ovi ažurirani profili se zatim koriste za osvežavanje segmenata da bi se uverili da radite sa najautetnijim informacijama.

Drugim rečima, uverite se da izvorni podaci koji se uvoze u uvid kupca uvek imaju najnovije informacije.

Više informacija potražite u članku Ručno [osvežavanje segmenata ili](segments.md#refresh-segments) konfigurisanje [planiranog osvežavanja](system.md#schedule-tab).

[!INCLUDE [footer-include](includes/footer-banner.md)]
