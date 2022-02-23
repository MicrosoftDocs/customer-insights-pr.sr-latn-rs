---
title: Pregled podržanih scenarija predviđanja
description: Scenariji i opcije predviđanja pokriveni su aplikacijom Dynamics 365 Customer Insights.
ms.date: 12/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5972d5b191ded7db14e2ebe9a4a26570a8ea60ba
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 01/15/2022
ms.locfileid: "7978030"
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
- [Analiza](sentiment-analysis.md) sentimenta : Analizirajte sentiment povratnih informacija klijenata i identifikujte poslovne aspekte koji se često pominju.

# <a name="business-accounts-b-to-b"></a>[Poslovni nalozi (B-to-B)](#tab/b2b)

- [Gubitak transakcija](predict-transactional-churn.md): Predvidite da li klijent više neće kupovati vaše proizvode ili usluge u određenom vremenskom okviru.

---


## <a name="azure-machine-learning-integration"></a>Integracija Azure mašinskog učenja

Ako organizacija već koristi scenarije mašinskog učenja zasnovane na eksperimentima Azure mašinskog učenja, funkcija prilagođenih modela u usluzi Customer Insights pomaže u povezivanju tačaka. Napravite tokove posla koji vam pomažu da odaberete podatke od kojih želite da generišete uvide i mapirate rezultate u svoje objedinjene profile klijenata. Za više informacija pogledajte [Prilagođeni modeli mašinskog učenja](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder predviđanje

Ponekad su skupovi podataka nepotpuni, a neke vrednosti nedostaju. Customer Insights može pomoći u predviđanju vrednosti koje nedostaju za entitet i segmente klijenta. Za više informacija, pogledajte [Dopunite svoje delimične podatke predviđanjima](predictions.md).
