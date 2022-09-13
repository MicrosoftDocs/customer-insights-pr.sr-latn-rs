---
title: Pregled predviđanja
description: Scenariji i opcije predviđanja pokriveni su aplikacijom Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 32240c8c43751d8514d38b392f23ef4138d50ee2
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411848"
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

[!INCLUDE [footer-include](includes/footer-banner.md)]
