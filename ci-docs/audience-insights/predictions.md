---
title: Dopunite delimične podatke koristeći predviđanja
description: Koristite predviđanja za popunjavanje nepotpunih podataka o klijentima.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268289"
---
# <a name="complete-your-partial-data-with-predictions"></a>Popunite svoje delimične podatke predviđanjima

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Predviđanja vam omogućavaju da lako kreirate predviđene vrednosti koje mogu poboljšati razumevanje vašeg klijenta. Na stranici **Obaveštavanje** > **Predviđanja** možete odabrati **Moja predviđanja** da biste videli predviđanja koja ste konfigurisali u drugim delovima uvida o korisnicima i dodatno ih prilagodili.

> [!NOTE]
> Ovu funkciju ne možete da koristite ako okruženje koristi Azure Data Lake Gen 2 prostor za skladištenje.
>
> Funkcija predviđanja koristi automatizovano sredstvo za ocenjivanje podataka i pravljenje predviđanja na osnovu tih podataka i zbog toga ima mogućnost da se koristi kao metod profilisanja, jer je taj pojam definisan Opštom uredbom o zaštiti podataka („GDPR“). Klijentovo korišćenje ove funkcije za obradu podataka može da bude podložno GDPR-u ili drugim zakonima ili propisima. Odgovorni ste za to da koristite Dynamics 365 Customer Insights, uključujući predviđanja, u skladu sa svim važećim zakonima i propisima, uključujući zakone koji se odnose na privatnost, lične podatke, biometrijske podatke, zaštitu podataka i poverljivost komunikacija.

## <a name="prerequisites"></a>Preduslovi

Pre nego što organizacija bude mogla da koristi funkciju predviđanja, sledeći preduslovi moraju da budu ispunjeni:

1. Vaša organizacija ima instancu [postavljenu u usluzi Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) i u istoj je organizaciji kao i Customer Insights.

2. Vaše okruženje je vezano za vašu Common Data Service instancu.

Ako [kreirate prvo okruženje](manage-environments.md), konfigurišite ga u dijalogu **Kreiranje okruženja** i izaberite stavku **Napredno**. Ako ste već kreirali okruženje, idite na njegova podešavanja i izaberite **Napredno**. U svakom slučaju, u odeljku **Koristite predviđanja** unesite URL Common Data Service instance na koji želite da prikačite svoje okruženje.

## <a name="create-a-prediction-in-the-customer-entity"></a>Kreiranje predviđanja u usluzi Customer entity

1. U uvidima o korisnicima idite na **Podaci** > **Entiteti**.

2. Izaberite entitet **Klijent**.

3. U entitetu **Klijent: CustomerInsights** izaberite stavku na kartici **Polja**.

4. Pronađite ime atributa za koje želite da predvidite vrednosti, a zatim izaberite ikonu **Pregled** u koloni **Rezime**.
   > [!div class="mx-imgBorder"]
   > ![Ikona „Pregled“](media/intelligence-overviewicon.png "Ikona „Pregled“")

5. Ako postoji visoka stopa nedostajućih vrednosti za atribut, izaberite **Predvidi nedostajuće vrednosti** da biste nastavili sa predviđanjem.
   > [!div class="mx-imgBorder"]
   > ![Prikaz statusa pregleda sa prikazanim dugmetom za vrednosti koje nedostaju](media/intelligence-overviewpredictmissingvalues.png "Prikaz statusa pregleda sa prikazanim dugmetom za vrednosti koje nedostaju")

6. Navedite **Ime za prikaz** i **Naziv izlaznog entiteta** za rezultate predviđanja.

7. Unapred popunjena lista opcija će pokazati gde možete da mapirate vrednosti u predviđenoj kategoriji. U ovom slučaju, samo opcije kategorije će biti 0 ili 1 dok se mapiraju u tačno/netačno ili binarnu prirodu predviđanja. U koloni „Kategorija“, vrednosti polja koje biste želeli da se klasifikuju kao „0“ u konačnom predviđanju mapirajte na „0“, a stavke koje biste želeli da se klasifikuju kao „1“ u konačnom predviđanju mapirajte na vrednost „1“.
   > [!div class="mx-imgBorder"]
   > ![Primer koji prikazuje mapirane vrednosti polja u kategorije](media/intelligence-categorymapping.png "Primer koji prikazuje mapirane vrednosti polja u kategorije")

8. Izaberite **Gotovo** i predviđanje će biti obrađeno. Obrada će potrajati izvesno vreme, u zavisnosti od veličine i složenosti podataka. Rezultati će biti dostupni u novom entitetu na osnovu **Naziva izlaznog entiteta** predviđanja koje ste kreirali.

## <a name="create-a-prediction-while-creating-a-segment"></a>Kreiranje predviđanja tokom kreiranja segmenta

Predviđanje nedostajućih vrednosti za određeni atribut izbora je moguće i prilikom kreiranja segmenta. Posebno, kada brzo kreirate segment zasnovan na objedinjenom entitetu Klijent ili entitetu Customer_Measure.

U okviru ovog toka biraćete određeni atribut na kojem će zasnovati segment, kao što je zadovoljstvo klijenta ili iznos nabavke. Nakon kreiranja segmenta, sistem će predložiti metod za predviđanje svih nedostajućih vrednosti za ovaj atribut.

1. U uvidima o klijentima idite na **Segmenti** i izaberite pločicu **Profili**.

2. Odaberite **Polje** za kreiranje segmenta i izaberite **Operator**, a zatim izaberite stavku **Pregled**.

3. Navedite **Ime** i **Ime za prikaz** za segment.

4. Izaberite stavku **Sačuvaj**.

5. Ako segment koji ste upravo kreirali nema potpune podatke u izvornom polju, možete da izaberete da predvidite vrednosti koje nedostaju.
   > [!div class="mx-imgBorder"]
   > ![Dugme predviđanja](media/segments-predictoption.png "Dugme predviđanja")

6. Navedite **Ime za prikaz** i **Naziv izlaznog entiteta** za rezultate predviđanja.

7. Izaberite **Gotovo**. Predviđanje će se uskoro generisati u novom entitetu sa imenom koje ste naveli za **Ime izlaznog entiteta**.

## <a name="view-a-prediction"></a>Prikaz predviđanja

1. U uvidima o korisnicima idite na **Obaveštavanje** > **Predviđanja** > **Moja predviđanja**.

2. Izaberite predviđanje koje želite da pregledate.

3. Izaberite tri tačke u koloni **Radnje** i izaberite stavku **Prikaz**.

4. Videćete broj tačaka podataka u prikazu predviđanja.
   > [!div class="mx-imgBorder"]
   > ![Stranica predviđanja](media/intelligence-predictionsviewpage.png "Stranica predviđanja")

   - **Predviđene vrednosti** prikazuju mapiranje koje ste kreirali tokom faze mapiranja vrednosti polja u kategoriju. Ovo su vrednosti u vašem skupu podataka koje su mapirane u određenu kategoriju.
   -**Najuticajniji faktori** su faktori u vašem skupu podataka koji najverovatnije najviše utiču na poverenje predviđanja vaše vrednosti polja koja se mapiraju u određenu kategoriju.
   - **Performanse** ukazuju na način na koji se prognoze obavljaju. Izaberite vezu da biste saznali više.
   - **Pregled** prikazuje uzorke izlaznih grupa podataka iz predviđanja i verovatnoću, ili naše poverenje, predviđene vrednosti, gde je 0 neizvesno, a 1 je sigurno.

## <a name="update-a-prediction"></a>Ažuriranje predviđanja

1. U uvidima o korisnicima idite na **Obaveštavanje** > **Predviđanja** > **Moja predviđanja**.

2. Izaberite predviđanje koje želite da ažurirate i izaberite ikonu **Ažuriraj**.

3. Predviđanje će biti zakazano za obradu. Vreme kad je poslednji put ažurirano možete da vidite u koloni **Ažurirano** na stranici **Predviđanja**.

## <a name="edit-a-prediction"></a>Uređivanje predviđanja

Kada kreirate predviđanje, možete da prilagodite model u programu AI Builder da biste povećali efikasnost vašeg modela.  

1. U uvidima o korisnicima idite na **Obaveštavanje** > **Predviđanja** > **Moja predviđanja**.

2. Izaberite predviđanje koje želite da uredite.

3. Izaberite tri tačke u koloni **Radnje** i izaberite stavku **Prikaz**.

4. Izaberite **Prilagodite u usluzi AI Builder**.

5. Ažurirajte model u programu AI Builder. [Saznajte više o upravljanju modelima u programu AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).

Sledeće pokretanje predviđanja koristiće ažurirani model koji ste kreirali.

> [!NOTE]
> Novi modeli napravljeni u AI Builder-u neće se prikazivati u uvidima o korisnicima, osim ako model nije napravljen na osnovu gorenavedenih iskustava.

## <a name="remove-a-prediction"></a>Uklanjanje predviđanja

1. U uvidima o korisnicima idite na **Obaveštavanje** > **Predviđanja** > **Moja predviđanja**.

2. Izaberite predviđanje koje želite da izbrišete.

3. Izaberite tri tačke u koloni **Radnje** i izaberite stavku **Izbriši**.

4. Potvrdite brisanje.

## <a name="troubleshooting"></a>Rešavanje problema

Ako ne možete da dovršite prilaganje Common Data Service procesa zbog greške, možete pokušati da dovršite postupak ručno. Postoje dva poznata problema koja se mogu pojaviti u procesu prilaganja:

- Rešenje Dodatak za karticu klijenta nije instalirano.
    1. Dovršite uputstva za [instaliranje i konfigurisanje rešenja](customer-card-add-in.md).

- Dozvole za aplikacije nisu dodeljene.
    1. Idite na [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Izaberite **Okruženja**.
    1. Izaberite tri tačke pored okruženja kojem želite da dodate dozvolu i izaberite **Podešavanja**.
    1. Proširite odeljak **Korisnici + dozvole** i izaberite **Korisnici**.
    1. Izaberite **+ Novo** i izaberite **Korisnik**.
    1. Izaberite opciju **Korisnik aplikacije** ako nije već izabrana i unesite sledeće informacije:
        - **Korisničko ime:** cihelp@microsoft.com
        - **ID aplikacije** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Ime:** Klijent
        - **Prezime:** Uvidi
        - **Primarna e-adresa:** cihelp@microsoft.com
    1. Izaberite stavku **Sačuvaj i zatvori**.
    1. Izaberite korisnika kojeg ste upravo kreirali.
    1. Izaberite **Upravljaj ulogama** u gornjoj traci menija.
    1. Izaberite **Sistemski administrator**, a zatim izaberite **U redu**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]