---
title: LiveRamp obogaćivanje podataka identiteta
description: Obogatite profile klijenata LiveRamp podacima.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0727818f6df565d9a031966a68d521ae7167e484
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643191"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Obogatite profile klijenata podacima o identitetu iz programa LiveRamp (Pregled) 

LiveRamp obezbeđuje determinističko rešavanje identiteta van mreže i konsolidaciju podataka korisnika. Lične identifikatore u podacima korisnika možete da mapirate u AbiliTec grafikon identiteta i primite AbiliTec ID-ove. Zatim možete da koristite ove lične datoteke za bolje ujedinjenje podataka klijenata. 

## <a name="prerequisites"></a>Preduslovi 

Da biste konfigurisali bogaćenje, moraju biti ispunjeni sledeći preduslovi: 

- Imate aktivnu LiveRamp pretplatu. Da biste dobili pretplatu, obratite se timu LiveRamp naloga ili [dynamics@liveramp.com](mailto:dynamics@liveramp.com) dodatnim informacijama.   

- Aktivna AbiliTec pretplata sa ID-om klijenta i tajna za pristup API-ju. Više informacija potražite u članku [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Podržane zemlje/regioni 

Trenutno podržavamo obogaćivanje korisničkih profila samo LiveRamp podacima u SAD. 

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja 

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**. 

1. Izaberite **stavku Obogati moje podatke** na pločici **identiteta**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Pločica identiteta na stranici za pregled obogaćenja.":::

1. Izaberite [vezu](connections.md) sa padajuće liste. Ako veza nije dostupna, obratite se administratoru. Ako ste administrator, možete da kreirate vezu tako što ćete izabrati stavku "Dodaj **vezu"**. Odaberite **LiveRamp** sa padajuće liste. 

1. Kliknite **na dugme** Dalje i odaberite **opciju skup podataka želite** da obogatite podacima o identitetu iz usluge LiveRamp. Možete izabrati entitet *kupca* da biste obogatili sve profile kupaca ili *izabrati entitet segmenta* da biste obogatili samo profile kupaca koji se nalaze u tom segmentu. 

1. Kliknite **na** dugme "Dalje" i definišite koji tip polja iz objedinjenih profila treba da se koristi za pronalaženje podataka identiteta koji se podudaraju iz programa LiveRamp. Potrebno je najmanje jedno od polja **"Ime i adresa** **·**", "Telefon" **ili "** E-pošta". 

   > [!TIP]
   > Što više ključnih identifikatora i polja mapirate, veća je verovatnoća veće stope podudaranja 

1. Mapirajte polja iz objedinjenog *entiteta* kupca koja će se koristiti za podudaranje sa AbiliTec ID grafikonom usluge LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opcije mapiranja podataka za LiveRamp obogaćivanje.":::

1. Izaberite **Sledeće** da biste dovršili mapiranje polja. 

1. Navedite **ime** za bogaćenje i izlazni **entitet**. 

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora. 

## <a name="configure-the-connection-for-liveramp"></a>Konfigurisanje veze za LiveRamp 

Potrebno je da budete administrator da biste konfigurisali [veze](connections.md). Izaberite opciju **Dodaj vezu prilikom konfigurisanja bogaćenja ili idite** na **AdminConnections** > **i izaberite** **stavku Podešavanje na** LiveRamp **pločici.** 

:::image type="content" source="media/liveramp-connection.png" alt-text="Okno za konfigurisanje da biste podesili vezu sa uslugom LiveRamp AbiliTec.":::

1. Za **ime za prikaz** unesite ime veze. 

1. Obezbedite važeći ID LiveRamp klijenta i tajnu. 

1. Pregledajte i dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**. 

1. Izaberite **Verifikuj** da biste proverili valjanost konfiguracije. 

1. Da biste dovršili vezu, kliknite na dugme **Sačuvaj**. 

## <a name="enrichment-results"></a>Rezultati obogaćivanja 

Da biste započeli proces obogaćivanja, izaberite pokreni sa komandne trake. Takođe možete dozvoliti sistemu da automatski pokrene obogaćivanje kao deo ašednog [osvežavanja](system.md#schedule-tab). Vreme obrade zavisi od veličine podataka vaših klijenata. 

Nakon završetka procesa obogaćivanja, možete pregledati novoobogaćene podatke profila klijenata u okviru **"Mojih obogaćivanja"**. Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila. 

Detaljnom prikazu svakog obogaćenog profila možete pristupiti tako što ćete izabrati stavkuView **obogaćeni** podaci. 

## <a name="next-steps"></a>Sledeći koraci

Nadogradite na obogaćenim podacima o klijentima. Koristite AbiliTec ID-ove da biste konsolidovali profile klijenata u prikaz zasnovan na osobi. 
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost 

Kada omogućite prenos Dynamics 365 Customer Insights podataka u LiveRamp, dozvoljavate prenos podataka izvan granice usaglašenosti za, uključujući Dynamics 365 Customer Insights potencijalno osetljive podatke kao što su lični podaci. Microsoft će preneti takve podatke na vaše uputstvo, ali vi ste odgovorni za to da obezbedite da LiveRamp ispunjava sve obaveze privatnosti ili bezbednosti koje možda imate. Za više informacija pregledajte Microsoft izjavu [o privatnosti](https://go.microsoft.com/fwlink/?linkid=396732). Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti. 


[!INCLUDE [footer-include](includes/footer-banner.md)]
