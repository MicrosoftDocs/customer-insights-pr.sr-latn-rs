---
title: Pregled predviđanja
description: Scenariji i opcije predviđanja pokriveni su aplikacijom Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610207"
---
# <a name="predictions-overview"></a>Pregled predviđanja

Dynamics 365 Customer Insights dolazi sa raznim opcijama koje koriste veštačka inteligencija i mašinsko učenje za predviđanje podataka.

## <a name="out-of-box-models"></a>Gotovi modeli

Najlakši način da započnete sa predviđanjem podataka su unapred definisani modeli, koji se često nazivaju „gotovi modeli“. Oni samo zahtevaju određene podatke i strukturu da bi brzo stekli uvid. Dostupni su sledeći modeli:

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

- [Trajna vrednost klijenta](predict-customer-lifetime-value.md): Predviđa potencijalni prihod klijenta tokom čitave interakcije sa preduzećem.
- [Preporuka proizvoda](predict-product-recommendation.md): Predlaže skupove prediktivnih preporuka za proizvode na osnovu ponašanja u kupovini i klijenata sa sličnim obrascima kupovine.
- [Gubitak pretplate](predict-subscription-churn.md): Predviđa da li je klijent ugrožen zbog toga što više ne koristi pretplaćene proizvode ili usluge vašeg preduzeća.
- [Transactional churn](predict-transactional-churn.md): Predviđa da li pojedinačni kupac više neće kupovati vaše proizvode ili usluge u određenom vremenski okvir.
- [Analiza sentimenta](sentiment-analysis.md): Analizira sentiment povratnih informacija klijenata i identifikuje poslovne aspekte koji se često pominju.

# <a name="business-accounts-b-to-b"></a>[Poslovni nalozi (B-to-B)](#tab/b2b)

- [Transactional churn](predict-transactional-churn.md): Predviđa da li nalog kupca više neće kupovati vaše proizvode ili usluge u određenom vremenski okvir.

---

> [!TIP]
> Preporučujemo da redovno osvežavate modele kutija sa ažuriranim podacima kako biste se uverili da tačno obaveštavaju vaš predmet o korišćenju poslovanja. Podaci se osvežavaju ad-hoc kada sistem unosi nove ili ažurirane izvore podataka. Međutim, modeli će se u ovom slučaju samo ponovo koristiti i nastaviti da koriste postojeće podatke o obuci.
>
> Konfigurišite **raspored ažuriranja** postavljanjem rasporeda prekvalifikacije modela tokom konfiguracije. Model će se prekvalifikovati i ponovo oblikovati po ovom rasporedu, koji možete promeniti u bilo kom trenutku.

## <a name="azure-machine-learning-integration"></a>Integracija Azure mašinskog učenja

Ako organizacija već koristi scenarije mašinskog učenja zasnovane na eksperimentima Azure mašinskog učenja, funkcija prilagođenih modela u usluzi Customer Insights pomaže u povezivanju tačaka. Napravite tokove posla koji vam pomažu da odaberete podatke od kojih želite da generišete uvide i mapirate rezultate u svoje objedinjene profile klijenata. Za više informacija pogledajte [Prilagođeni modeli mašinskog učenja](custom-models.md).

## <a name="manage-existing-predictions"></a>Upravljanje postojećim predviđanjima

Idite na stranicu **"Predviđanja** > **obaveštajnih podataka** ". Na kartici **Moja predviđanja** pogledajte predviđanja koja ste kreirali, njihov tip predviđanje, ime izlaznog entiteta, status, poslednji put kada je predviđanje uređen i poslednji put kada su podaci osveženi. Listu predviđanja možete da sortirate po bilo kojoj koloni.

Izaberite predviđanje biste prikazali dostupne radnje.

:::image type="content" source="media/predictions.png" alt-text="Moja stranica sa predviđanjima.":::

- **Uredite** predviđanje biste promenili njegova svojstva.
- [**Osvežite**](#refresh-a-prediction) predviđanje biste uključili najnovije podatke.
- **Pogledajte** predviđanje detalje.
- [**Izveštaj o upotrebljivosti ulaznih**](#view-the-input-data-usability-report) podataka da biste prikazali greške, upozorenja i preporuke.
- **Izbrišite** predviđanje.

### <a name="refresh-a-prediction"></a>Osvežavanje predviđanja

Predviđanja se mogu osvežiti automatskim rasporedom ili osvežiti ručno na zahtev. Da biste ručno osvežili sva predviđanja, izaberite stavku Osveži **sve**. Da biste ručno osvežili predviđanje, izaberite ga i izaberite **Osveži**. Da biste [zakazali automatsko osvežavanje](schedule-refresh.md), idite **na administrativni** > **plan** > **sistema**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Pogledajte izveštaj o upotrebljivosti ulaznih podataka

Izveštaj o upotrebljivosti ulaznih podataka pruža konsolidovani prikaz grešaka i upozorenja koja mogu proizvesti vaša gotova predviđanja. Takođe daje preporuke kako poboljšati performanse modela.

Izveštaj je dostupan nakon što model završi svoj proces obuke. Kreiran je za svaki model posebno, bez obzira na to da li je uspešno završio obuku ili ne.

Na kartici **Moja predviđanja** izaberite karticu Predviđanje i odaberite izveštaj o **upotrebljivosti podataka unosa**. Ili iz prikaza predviđanje detalje izaberite izveštaj o upotrebljivosti **ulaznih podataka**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Primer izveštaja o upotrebljivosti ulaznih podataka koji prikazuje tabelu sa greškama, upozorenjima i preporukama.":::

Izveštaj obuhvata:

- **Ime:** Opisno ime greške, upozorenja ili preporuke.
- **Korak:** Model faza, voz ili rezultat, informacije se odnose na njih.
- **Stanje:** Ozbiljnost informacija (greška, upozorenje, preporuka).
- **Ime kolone:** Kolona u entitetu koju treba izmeniti da bi se poboljšale performanse modela.
- **Ime entiteta:** Ime entiteta koje treba izmeniti da bi se poboljšale performanse modela.
- **Detalji:** Detalji o grešci, upozorenju ili preporuci.

[!INCLUDE [footer-include](includes/footer-banner.md)]
