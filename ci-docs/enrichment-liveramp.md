---
title: Obogatite profile klijenata podacima o identitetu iz programa LiveRamp (pregled)
description: Obogatite profile klijenata LiveRamp podacima.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 334440493c50448005ec90d0cfac11358d677b73
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082204"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Obogatite profile klijenata podacima o identitetu iz programa LiveRamp (pregled)

LiveRamp obezbeđuje determinističko rešavanje identiteta van mreže i konsolidaciju podataka korisnika. Lične identifikatore u podacima korisnika možete da mapirate u AbiliTec grafikon identiteta i primite AbiliTec ID-ove. Zatim možete da koristite ove lične datoteke za bolje ujedinjenje podataka klijenata.

## <a name="supported-countriesregions"></a>Podržane zemlje/regioni

Trenutno podržavamo obogaćivanje korisničkih profila samo LiveRamp podacima u SAD.

## <a name="prerequisites"></a>Preduslovi

- Aktivna LiveRamp pretplata. Da biste dobili pretplatu, obratite se timu LiveRamp naloga ili [dynamics@liveramp.com](mailto:dynamics@liveramp.com) dodatnim informacijama.

- Aktivna AbiliTec pretplata sa ID-om klijenta i tajna za pristup API-ju. Više informacija potražite u članku [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/).

- LiveRamp [vezu](connections.md)[konfiguriše](#configure-the-connection-for-liveramp) administrator.

## <a name="configure-the-connection-for-liveramp"></a>Konfigurisanje veze za LiveRamp

Morate biti administrator u programu [Customer](permissions.md#admin) Insights i imati aktivan LiveRamp ID klijenta i tajnu.

1. Izaberite **opciju** Dodaj vezu prilikom konfigurisanja obogaćivanja ili idite **na administrativne** > **veze** i izaberite **stavku** Podešavanje na LiveRamp pločici.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Okno za konfigurisanje da biste podesili vezu sa uslugom LiveRamp AbiliTec.":::

1. Unesite ime za vezu i važeći ID LiveRamp klijenta i tajnu.

1. Pregledajte i dajte saglasnost za [Privatnost podataka i usklađenost](#data-privacy-and-compliance) izborom opcije **Slažem se**.

1. Izaberite **opciju** Proveri da biste proverili valjanost konfiguracije, a zatim kliknite na dugme **Sačuvaj**.

### <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite prenos Dynamics 365 Customer Insights podataka u LiveRamp, dozvoljavate prenos podataka izvan granice usaglašenosti za, uključujući Dynamics 365 Customer Insights potencijalno osetljive podatke kao što su lični podaci. Microsoft će preneti takve podatke na vaše uputstvo, ali vi ste odgovorni za to da obezbedite da LiveRamp ispunjava sve obaveze privatnosti ili bezbednosti koje možda imate. Za više informacija pregledajte Microsoft izjavu [o privatnosti](https://go.microsoft.com/fwlink/?linkid=396732). Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.

1. Izaberite **stavku Obogati moje** podatke o **identitetu** sa LiveRamp pločice.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Pločica identiteta na stranici za pregled obogaćenja.":::

1. Pregledajte pregled, a zatim kliknite na dugme **Dalje**.

1. Izaberite vezu. Obratite se administratoru ako nije dostupan.

1. Izaberite **Sledeće**.

1. Izaberite opciju **skup podataka i** odaberite profil ili segment koji želite da obogatite podacima o identitetu iz programa LiveRamp. Entitet *kupca* obogaćuje sve profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

1. Definišite tip polja iz objedinjenih profila koja ćete koristiti za podudaranje podataka identiteta iz programa LiveRamp. Potrebno je najmanje jedno od polja **"Ime i adresa**", **"E-pošta**" **ili** "Telefon". Za veću tačnost podudaranja dodajte druga polja. Izaberite **Sledeće**.

1. Mapirajte polja na identifikacione podatke iz liveRamp-a.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opcije mapiranja podataka za LiveRamp obogaćivanje.":::

1. Izaberite **Sledeće** da biste dovršili mapiranje polja.

1. Navedite **ime** za bogaćenje i ime **entiteta izlaza**.

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

1. Kliknite **na dugme** "Pokreni" da biste započeli proces obogaćivanja ili blizu da biste se vratili na stranicu **"Obogaćivanje** ".

## <a name="view-enrichment-results"></a>Prikaži rezultate obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Broj **kupaca obogaćenih poljem obezbeđuje** dubinsku analizu pokrivenosti svakog obogaćenog polja.

## <a name="next-steps"></a>Sledeći koraci

Nadogradite na obogaćenim podacima o klijentima. Koristite AbiliTec ID-ove da biste konsolidovali profile klijenata u prikaz zasnovan na osobi.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
