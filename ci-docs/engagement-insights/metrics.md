---
title: Prikaz i kreiranje metrike
description: Kako da kreirate, uređujete i brišete metriku.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7e8c96f38af74f25080a40fd92e73f05c71320a8
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229833"
---
# <a name="view-and-create-metrics"></a>Prikaz i kreiranje metrike

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Metrika pomaže u razumevanju ponašanja vaših posetilaca. Oni objedinjavaju svojstva događaja i mere statistiku i performanse vaših veb-svojstava.  

Pretpostavimo da na svojoj veb-lokaciji vodite marketinšku promociju. Pomoću metrike možete da pratite broj jedinstvenih posetilaca ili korisnika koji su došli na vašu veb-lokaciju tokom promocije. Analiza metrike pomaže vam da bolje razumete ciljnu grupu svoje veb-lokacije. Kombinovanje metrike sa [aspektima](dimensions.md) u [prilagođenom izveštaju](custom-reports.md) omogućava vam da merite ponašanje kako biste razumeli svoje korisnike. Na primer, možete da razdvojite posetioce u nove i povratne kategorije kako biste identifikovali razlike u interesovanjima i namerama između grupa.

## <a name="view-metrics"></a>Prikaz metrike

Uvidi u angažovanje uključuju najčešće korišćene agregacije svojstava događaja kao sistemske metrike: 

- Posetioci
- Posete
- Prikazi stranica
- Klikovi

Ove sistemske metrike se zasnivaju na postojećim svojstvima događaja u osnovnim događajima.

1. Idite na odeljak **Podaci** u levom oknu za navigaciju. 
1. Izaberite karticu **Metrika** da biste videli listu sve metrike u radnom prostoru. 
   > [!NOTE]
   > Sistemski generisana metrika je samo za čitanje. Ne možete ih uređivati niti brisati. Možete da kreirate i uređujete samo prilagođenu metriku.

## <a name="create-a-metric"></a>Kreiranje metrike

Administratori okruženja i radnog prostora mogu da kreiraju metriku. Svojstva događaja moraju biti poslata u radni prostor pre nego što kreirate metriku. Možete da kreirate metriku na osnovu svojstava događaja koja se šalju osnovnim događajima ili da za to koristite veb SDK da [šaljete prilagođena svojstva događaja](advanced-SDK-implementation.md).

1. Idite na **Podaci** > **Metrika**.
1. Izaberite **Nova metrika** da biste otvorili **Biblioteku resursa** i dijalog **Nova metrika bez naslova**.

   :::image type="content" source="media/new-metric.png" alt-text="Dodajte metriku događaju.":::

1. U dijalogu **Nova metrika bez naslova**, izaberite padajuću listu **Format** i izaberite **Ceo broj** ili **Dvostruki** tip podataka. Celobrojna vrednost je ceo broj. Za Double možete izabrati jedno i tri decimalna mesta.

   :::image type="content" source="media/create-new-metric.png" alt-text="Kreirajte novu metriku.":::
   
5. U oknu **Biblioteka resursa** pronađite svojstvo događaja na kojem ćete zasnovati metriku.
6. Izaberite **znak plus (+)** pored svojstva da biste ga koristili u formuli. Možete kreirati formulu zasnovanu na jednom svojstvu. 
7. Odaberite jednu od sledećih agregatnih funkcija. 

   - Zbir: aritmetički zbir svih vrednosti 
   - Prosek: srednja prosečna vrednost svih vrednosti
   - Brojanje: ukupan broj vrednosti
   - Broj jedinstvenih vrednosti: ukupan broj jedinstvenih vrednosti

   Kada definišete metriku, videćete pregled aktivnosti metrike za poslednji sat.

1. Izaberite stavku **Sačuvaj**. 
1. Unesite naziv za metriku i izaberite **Sačuvaj**.

Može da potraje i minut pre nego što budete mogli da upotrebite metriku za [kreiranje prilagođenih izveštaja](custom-reports.md).

## <a name="edit-a-metric"></a>Uređivanje metrike

Možete da menjate samo prilagođene pokazatelje.

1. Idite na **Podaci** > **Metrika**.
1. Izaberite metriku na listi.
1. Promena definicije metrike
1. Izaberite stavku **Sačuvaj**.

## <a name="change-the-name-of-a-metric"></a>Promena naziva metrike

Možete samo da promenite naziv prilagođenih pokazatelja.

1. Idite na **Podaci** > **Metrika**.
1. Izaberite **Još [...]** za metriku i odaberite **Uredi naziv**.
1. Promenite naziv. 
1. Izaberite **Preimenuj**.

## <a name="delete-a-metric"></a>Brisanje metrike

Možete da brišete samo prilagođene pokazatelje.

1. Idite na **Podaci** > **Metrika**.
1. Izaberite **Još [...]** za metriku i odaberite **Izbriši**.

   :::image type="content" source="media/delete-metric.png" alt-text="Izbrišite metriku za događaj.":::

1. Izaberite **Izbriši** da biste potvrdili brisanje.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
