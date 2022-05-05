---
title: Pregled podržanih scenarija predviđanja
description: Scenariji i opcije predviđanja pokriveni su aplikacijom Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 11b0efeecf8bea893272e67d29b1c6622771110c
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643936"
---
# <a name="predictions-overview"></a>Pregled predviđanja

Dynamics 365 Customer Insights dolazi sa raznim opcijama koje koriste veštačka inteligencija i mašinsko učenje za predviđanje podataka. 

## <a name="out-of-box-models"></a>Gotovi modeli

Najlakši način da započnete sa predviđanjem podataka su unapred definisani modeli, koji se često nazivaju „gotovi modeli“. Oni samo zahtevaju određene podatke i strukturu da bi brzo stekli uvid. Trenutno su dostupni sledeći modeli: 

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

- [Trajna vrednost klijenta](predict-customer-lifetime-value.md): Predviđa potencijalni prihod klijenta tokom čitave interakcije sa preduzećem.
- [Preporuka proizvoda](predict-product-recommendation.md): Predlaže skupove prediktivnih preporuka za proizvode na osnovu ponašanja u kupovini i klijenata sa sličnim obrascima kupovine.
- [Gubitak pretplate](predict-subscription-churn.md): Predviđa da li je klijent ugrožen zbog toga što više ne koristi pretplaćene proizvode ili usluge vašeg preduzeća.
- [Gubitak transakcija](predict-transactional-churn.md): Predvidite da li klijent više neće kupovati vaše proizvode ili usluge u određenom vremenskom okviru.
- [Analiza sentimenta](sentiment-analysis.md): Analizirajte sentiment povratnih informacija klijenata i identifikujte poslovne aspekte koji se često pominju.

# <a name="business-accounts-b-to-b"></a>[Poslovni nalozi (B-to-B)](#tab/b2b)

- [Gubitak transakcija](predict-transactional-churn.md): Predvidite da li klijent više neće kupovati vaše proizvode ili usluge u određenom vremenskom okviru.

---

> [!TIP]
> Preporučujemo da redovno osvežavate modele kutija sa ažuriranim podacima kako biste se uverili da tačno obaveštavaju vaš predmet o korišćenju poslovanja. Podaci se osvežavaju ad-hoc kada sistem unosi nove ili ažurirane izvore podataka. Međutim, modeli će se u ovom slučaju samo ponovo koristiti i nastaviti da koriste postojeće podatke o obuci.
> 
> Raspored ažuriranja možete da **konfigurišete** tako što ćete podesiti raspored prekvalifikacije modela u iskustvu konfigurisanja. Model će se prekvalifikovati i ponovo oblikovati po ovom rasporedu, koji možete promeniti u bilo kom trenutku.


## <a name="azure-machine-learning-integration"></a>Integracija Azure mašinskog učenja

Ako organizacija već koristi scenarije mašinskog učenja zasnovane na eksperimentima Azure mašinskog učenja, funkcija prilagođenih modela u usluzi Customer Insights pomaže u povezivanju tačaka. Napravite tokove posla koji vam pomažu da odaberete podatke od kojih želite da generišete uvide i mapirate rezultate u svoje objedinjene profile klijenata. Za više informacija pogledajte [Prilagođeni modeli mašinskog učenja](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder predviđanje

Ponekad su skupovi podataka nepotpuni, a neke vrednosti nedostaju. Customer Insights može pomoći u predviđanju vrednosti koje nedostaju za entitet i segmente klijenta. Za više informacija, pogledajte [Dopunite svoje delimične podatke predviđanjima](predictions.md).
