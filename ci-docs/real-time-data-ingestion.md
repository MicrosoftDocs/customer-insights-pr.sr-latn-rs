---
title: Unošenje podataka u realnom vremenu (pregled)
description: Opšte informacije o mogućnostima u realnom vremenu u uvidima klijenata.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: d6aa07dd4dfa25b3d2ce707eb6050df56fcc3079
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643126"
---
# <a name="real-time-data-ingestion-preview"></a>Unos podataka u realnom vremenu (pregled)

Funkcionalnost koja je skoro sasvim u stvarnom vremenu omogućava vam da u roku od nekoliko sekundi vidite najnovije interakcije koje su izvršili vaši klijenti sa vašim proizvodima ili uslugama.

[Zakazana osvežavanja](system.md#schedule-tab) uključuju veliki broj zapisa i nekoliko složenih operacija. Prvo se podaci uzimaju iz izvora podataka. Zatim se podaci objedinjuju, a zatim obogaćuju dodatnim informacijama. Svako pokretanje ovog postupka može trajati od nekoliko minuta do nekoliko sati.

Funkcionalnost u realnom vremenu pruža podatke koji se odmah mogu koristiti, sve dok naknadno planirano osvežavanje ne povuče ove podatke iz izvora podataka.

Ažuriranja u realnom vremenu imaju vreme isteka nakon čega više ne menjaju vrednost iz izvora podataka:

- Ažuriranja profila čuvaće se 4 sata
- Aktivnosti će se čuvati 30 dana

Te vrednosti su parametri API poziva koje možete promeniti. Oni imaju za cilj da osiguraju da vaši izvorni podaci ostanu vaš izvor istine. Ako želite da ažuriranja u realnom vremenu budu duže uključena, morate ih dodati u izvor podataka kako bi se povukla tokom sledećeg zakazanog osvežavanja.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Ažuriranje polja objedinjenog profila klijenta u realnom vremenu

Ažurirani profili će se prikazati u prikazu kartice klijenta ili bilo kojoj drugoj vizuelizaciji u roku od nekoliko sekundi.

Pošto se operacije u realnom vremenu odvijaju nakon što se desilo objedinjavanje podataka, one se primenjuju samo na objedinjene profile korisnika. Stoga promene profila u realnom vremenu neće ažurirati mere, članstvo u segmentima ili obogaćivanja.

### <a name="limitations"></a>Ograničenja

- Profili korisnika se mogu ažurirati, ali ne i kreirati ili brisati.
- Izvoz ažuriranja u realnom vremenu u spoljne sisteme, kao što je Power BI, trenutno nije moguće.

## <a name="real-time-creation-of-activities"></a>Kreiranje aktivnosti u realnom vremenu

API u realnom vremenu omogućava vam objavljivanje nove aktivnosti iz vašeg izvornog sistema (pojedinačni izvorni zapis) na objedinjenom profilu klijenta. Nova aktivnost će biti dostupna kao objedinjena aktivnost na vremenskoj osi tog objedinjenog klijenta u roku od nekoliko sekundi. Vremensku liniju možete videti u prikazu kartice klijenta ili bilo kojoj drugoj integraciji vremenske linije koju ste konfigurisali.

> [!NOTE]
>
> - Aktivnosti su nepromenljive. Ne menjaju se jednom kada ih kreirate.
> - Trenutno se segmenti i mere neće ažurirati na osnovu nove aktivnosti.
> - Aktivnosti dodate samo putem API-ja u realnom vremenu nisu deo izvoza i neće se prikazati u usluzi PowerBI.

Postoje dva načina za povezivanje sa API-jem u realnom vremenu:

- [indirektno](#connect-via-the-dynamics-365-customer-insights-connector), pomoću [Dynamics 365 Customer Insights konektora](/connectors/customerinsights/)
- [direktno](#connect-directly-to-the-real-time-api), sa kodom

Oba načina dele sledeće preduslove:

- Customer Insights okruženje
- Objedinjeni profil klijenta
- Aktivnosti se konfigurišu i pokreću
- Dozvole saradnika ili administratora za potvrdu identiteta naloga

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Povežite se putem Dynamics 365 Customer Insights konektora

API u realnom vremenu može da unosi podatke sa namenskog Power Platform konektora, po imenu [Dynamics 365 Customer Insights konektor](/connectors/customerinsights/), bez potrebe za pisanjem i primenom bilo kakvog koda.    
Konektor može da obavlja iste radnje u realnom vremenu kao i API. Potrebna vam je važeća licenca za premijum konektore. Za više informacija, pogledajte članak [Najčešća pitanja o Power Apps i Power Automate licenciranju](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps i/ili Power Automate](/connectors/)
- Azure [logičke aplikacije](/azure/connectors/apis-list)

Za detalje o kreiranju tokova, pogledajte [Power Automate dokumentaciju](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Povežite se direktno sa API-jem u realnom vremenu

Mogućnosti u realnom vremenu možete da koristite izgradnjom sopstvenog kanala i direktnim povezivanjem sa API-jem u realnom vremenu.    
Aktivnost možete objaviti u formatu vašeg izvornog sistema ili u formatu UnifiedActivity. Preuzmite format upućivanjem API poziva u /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Detalji ovog API-ja, uključujući parametre i odgovore, mogu se naći u odeljku **Podaci o entitetima** u [Referenci Customer Insights API-ja](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Za više informacija pogledajte [Radite sa Customer Insights API-jima](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Objašnjenje upotrebe u realnom vremenu pomoću telemetrije

Dobijte pregled obima zahteva za API u realnom vremenu i informacije o problemima sa kojima se sistem može susresti. Možete [pristupati telemetriji u realnom vremenu](system.md#api-usage-tab). 


[!INCLUDE [footer-include](includes/footer-banner.md)]
