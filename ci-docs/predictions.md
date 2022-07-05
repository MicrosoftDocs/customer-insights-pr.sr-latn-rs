---
title: Popunite svoje delimične podatke predviđanjima
description: Koristite predviđanja za popunjavanje nepotpunih podataka o klijentima.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-predictions
- ci-custom-models
- customerInsights
ms.openlocfilehash: 7e93670007db27d13b84d7516f56830988da083e
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082519"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Dovršavanje delimičnih podataka predviđanjima (neodobreno)

> [!IMPORTANT]
> Ova funkcija će biti zastarela **od** **5. novembra 2021. godine**. Trenutne implementacije će nastaviti da funkcionišu dok se funkcija ne ukloni, ali nećete moći da kreirate nove integracije koristeći dolenavedena uputstva.

Predviđanja vam omogućavaju da lako kreirate predviđene vrednosti koje mogu poboljšati razumevanje vašeg klijenta. Na stranici **Obaveštavanje** > **Predviđanja** možete da izaberete **Moja predviđanja** da biste videli predviđanja koja ste konfigurisali u drugim delovima aplikacije Customer Insights, a i da omogućite njihovo dalje prilagođavanje.

> [!NOTE]
> Ovu funkciju ne možete da koristite ako okruženje koristi Azure Data Lake Gen 2 prostor za skladištenje.
>
> Funkcija predviđanja koristi automatizovano sredstvo za ocenjivanje podataka i pravljenje predviđanja na osnovu tih podataka i zbog toga ima mogućnost da se koristi kao metod profilisanja, jer je taj pojam definisan Opštom uredbom o zaštiti podataka („GDPR“). Klijentovo korišćenje ove funkcije za obradu podataka može da bude podložno GDPR-u ili drugim zakonima ili propisima. Odgovorni ste za to da koristite Dynamics 365 Customer Insights, uključujući predviđanja, u skladu sa svim važećim zakonima i propisima, uključujući zakone koji se odnose na privatnost, lične podatke, biometrijske podatke, zaštitu podataka i poverljivost komunikacija.

## <a name="prerequisites"></a>Preduslovi

Pre nego što organizacija bude mogla da koristi funkciju predviđanja, sledeći preduslovi moraju da budu ispunjeni:

1. Vaša organizacija ima instancu [konfigurisanu u usluzi Microsoft Dataverse](/ai-builder/build-model#prerequisites) i nalazi se u istoj organizaciji kao i Customer Insights.

2. Vaše Customer Insights okruženje je priloženo uz vašu Dataverse instancu.

Više informacija potražite u članku [Kreiranje novog okruženja](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Kreiranje predviđanja u usluzi Customer entity

1. Idite na **entitete** > **podataka**.

2. Izaberite entitet **Klijent**.

3. U entitetu **Klijent: CustomerInsights** izaberite stavku na kartici **Polja**.

4. Pronađite ime atributa za koje želite da predvidite vrednosti, a zatim izaberite ikonu **Pregled** u koloni **Rezime**.
   > [!div class="mx-imgBorder"]
   > ![Ikona „Pregled“.](media/intelligence-overviewicon.png "Ikona „Pregled“")

5. Ako postoji visoka stopa nedostajućih vrednosti za atribut, izaberite **Predvidi nedostajuće vrednosti** da biste nastavili sa predviđanjem.
   > [!div class="mx-imgBorder"]
   > ![Prikaz statusa pregleda sa prikazanim dugmetom za vrednosti koje nedostaju.](media/intelligence-overviewpredictmissingvalues.png "Prikaz statusa pregleda sa prikazanim dugmetom za vrednosti koje nedostaju")

6. Navedite **Ime za prikaz** i **Naziv izlaznog entiteta** za rezultate predviđanja.

7. Unapred popunjena lista opcija će pokazati gde možete da mapirate vrednosti u predviđenoj kategoriji. U ovom slučaju, samo opcije kategorije će biti 0 ili 1 dok se mapiraju u tačno/netačno ili binarnu prirodu predviđanja. U koloni „Kategorija“, vrednosti polja koje biste želeli da se klasifikuju kao „0“ u konačnom predviđanju mapirajte na „0“, a stavke koje biste želeli da se klasifikuju kao „1“ u konačnom predviđanju mapirajte na vrednost „1“.
   > [!div class="mx-imgBorder"]
   > ![Primer koji prikazuje mapirane vrednosti polja u kategorije.](media/intelligence-categorymapping.png "Primer koji prikazuje mapirane vrednosti polja u kategorije")

8. Izaberite **Gotovo** i predviđanje će biti obrađeno. Obrada će potrajati izvesno vreme, u zavisnosti od veličine i složenosti podataka. Rezultati će biti dostupni u novom entitetu na osnovu **Naziva izlaznog entiteta** predviđanja koje ste kreirali.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Kreiranje predviđanja tokom kreiranja segmenta

Predviđanje nedostajućih vrednosti za određeni atribut izbora je moguće i prilikom kreiranja segmenta. Posebno, kada brzo kreirate segment zasnovan na objedinjenom entitetu Klijent ili entitetu Customer_Measure.

U okviru ovog toka biraćete određeni atribut na kojem će zasnovati segment, kao što je zadovoljstvo klijenta ili iznos nabavke. Nakon kreiranja segmenta, sistem će predložiti metod za predviđanje svih nedostajućih vrednosti za ovaj atribut.

1. Idite na **stavku "Segmenti** " i izaberite **pločicu** "Profili".

2. Odaberite **Polje** za kreiranje segmenta i izaberite **Operator**, a zatim izaberite stavku **Pregled**.

3. Navedite **Ime** i **Ime za prikaz** za segment.

4. Izaberite stavku **Sačuvaj**.

5. Ako segment koji ste upravo kreirali nema potpune podatke u izvornom polju, možete da izaberete da predvidite vrednosti koje nedostaju.
   > [!div class="mx-imgBorder"]
   > ![Dugme „Predviđanje“.](media/segments-predictoption.png "Dugme predviđanja")

6. Navedite **Ime za prikaz** i **Naziv izlaznog entiteta** za rezultate predviđanja.

7. Izaberite **Gotovo**. Predviđanje će se uskoro generisati u novom entitetu sa imenom koje ste naveli za **Ime izlaznog entiteta**.

## <a name="view-a-prediction"></a>Prikaz predviđanja

1. Idite na **obaveštajna** > **predviđanja** > **Moja predviđanja**.

2. Izaberite predviđanje koje želite da pregledate.

3. Izaberite vertikalnu elipsu () u koloni Radnje&vellip;**i izaberite** stavku **Prikaz**.

4. Videćete broj tačaka podataka u prikazu predviđanja.
   > [!div class="mx-imgBorder"]
   > ![Stranica predviđanja.](media/intelligence-predictionsviewpage.png "Stranica predviđanja")

   - **Predviđene vrednosti** prikazuju mapiranje koje ste kreirali tokom faze mapiranja vrednosti polja u kategoriju. Ovo su vrednosti u vašem skupu podataka koje su mapirane u određenu kategoriju.
   -**Najuticajniji faktori** su faktori u vašem skupu podataka koji najverovatnije najviše utiču na poverenje predviđanja vaše vrednosti polja koja se mapiraju u određenu kategoriju.
   - **Performanse** ukazuju na način na koji se prognoze obavljaju. Izaberite vezu da biste saznali više.
   - **Pregled** prikazuje uzorke izlaznih grupa podataka iz predviđanja i verovatnoću, ili naše poverenje, predviđene vrednosti, gde je 0 neizvesno, a 1 je sigurno.

## <a name="update-a-prediction"></a>Ažuriranje predviđanja

1. Idite na **obaveštajna** > **predviđanja** > **Moja predviđanja**.

2. Izaberite predviđanje koje želite da ažurirate i izaberite ikonu **Ažuriraj**.

3. Predviđanje će biti zakazano za obradu. Vreme kad je poslednji put ažurirano možete da vidite u koloni **Ažurirano** na stranici **Predviđanja**.

## <a name="edit-a-prediction"></a>Uređivanje predviđanja

Nakon što kreirate predviđanje, možete da prilagodite model tako da AI Builder poveća efektivnost vašeg modela.  

1. Idite na **obaveštajna** > **predviđanja** > **Moja predviđanja**.

2. Izaberite predviđanje koje želite da uredite.

3. Izaberite vertikalnu elipsu () u koloni Radnje&vellip;**i izaberite** stavku **Prikaz**.

4. Izaberite **prilagodi u programu AI Builder**.

5. Ažurirajte svoj model u programu AI Builder. [Saznajte više o upravljanju modelima u programu AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

Sledeće pokretanje predviđanja koristiće ažurirani model koji ste kreirali.

> [!NOTE]
> Novi modeli kreirani AI Builder u programu neće biti prikazani u "Uvidima kupaca" osim ako model nije kreiran iz gore navedenih iskustava.

## <a name="remove-a-prediction"></a>Uklanjanje predviđanja

1. Idite na **obaveštajna** > **predviđanja** > **Moja predviđanja**.

2. Izaberite predviđanje koje želite da izbrišete.

3. Izaberite vertikalnu elipsu () u koloni Radnje i izaberite&vellip; stavku **Izbriši**.**·**

4. Potvrdite brisanje.

## <a name="troubleshooting"></a>Rešavanje problema

Ako ne možete da dovršite prilaganje Dataverse procesa zbog greške, možete pokušati da dovršite postupak ručno. Postoje dva poznata problema koja se mogu pojaviti u procesu prilaganja:

- Rešenje Dodatak za karticu klijenta nije instalirano.
    1. Dovršite uputstva za [instaliranje i konfigurisanje rešenja](customer-card-add-in.md).

- Dozvole za aplikacije nisu dodeljene.
    1. Idite na [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Izaberite **Okruženja**.
    1. Izaberite vertikalnu elipsu () pored okruženja&vellip; kojem želite da dodate dozvolu i izaberite **postavke**.
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


[!INCLUDE [footer-include](includes/footer-banner.md)]