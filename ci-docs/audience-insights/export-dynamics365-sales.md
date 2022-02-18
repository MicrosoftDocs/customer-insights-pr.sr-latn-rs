---
title: Izvezite Customer Insights podatke u Dynamics 365 Sales
description: Saznajte kako da konfigurišete vezu i izvezete u Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d8a35424f4271b350b8d84e72a01deb6d69652a0
ms.sourcegitcommit: 08a5dfcc4f9d293c8e7ac4fef604bc52985b1b78
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/04/2022
ms.locfileid: "8090940"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Korišćenje segmenata u usluzi Dynamics 365 Sales (verzija za pregled)



Koristite podatke o klijentima da biste kreirali marketinške spiskove, pratili tokove posla i slali promocije sa uslugom Dynamics 365 Sales.

## <a name="known-limitations"></a>Poznata ograničenja

- Izvoz u Dynamics 365 Prodaju je ograničen na 100.000 članova po segmentu.
- Izvoz segmenta u Dynamics 365 Prodaja može trajati do 3 sata. 

## <a name="prerequisite-for-connection"></a>Preduslov za vezu

1. Zapisi kontakata moraju biti prisutni u usluzi Dynamics 365 Sales da biste mogli da izvezete segment iz usluge Customer Insights u Sales. Pročitajte više o tome kako se unose kontakti u [Dynamics 365 Sales pomoću usluge Microsoft Dataverse](connect-power-query.md).

   > [!NOTE]
   > Izvoz segmenata iz uvida o korisnicima u Sales neće kreirati nove zapise kontakata u instancama usluge Sales. Evidencija kontakata iz usluge Sales mora se uneti u uvid o korisnicima i koristiti kao izvor podataka. Takođe ih treba uključiti u jedinstveni entitet klijenta da bi se ID-ovi klijenata mapirali u ID-ove kontakata da bi segmenti mogli da se izvezu.

## <a name="set-up-the-connection-to-sales"></a>Podešavanje veze sa uslugom Sales

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu** i birajte **Dynamics 365 Sales** da biste konfigurisali vezu.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Ako ništa ne preduzmete, podrazumevani će biti Administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Unesite URL organizacije za Sales u polje **Adresa servera**.

1. U odeljku **Administratorski nalog na serveru**, izaberite **Prijavite se** i izaberite Dynamics 365 Sales nalog.

1. Mapirajte polje korisničkog ID-a sa Dynamics 365 ID-om kontakta.

1. Izaberite **Sačuvaj** da biste kreirali vezu. 

## <a name="configure-an-export"></a>Konfigurisanje izvoza

Ovaj izvoz možete da konfigurišete ako imate pristup vezi ove vrste. Za više informacija pogledajte [Dozvole potrebne za konfigurisanje izvoza](export-destinations.md#set-up-a-new-export).

1. Idite na **Podaci** > **Izvozi**.

1. Da biste kreirali novi izvoz, izaberite **Dodaj odredište**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka Dynamics 365 Sales. Ako ne vidite naziv ovog odeljka, ne postoje veze ovog tipa koje su vam dostupne.

1. Izaberite jedan ili više segmenata.

1. Izaberite stavku **Sačuvaj**

Čuvanje izvoza ne pokreće izvoz odmah.

Izvoz se pokreće sa svakim [zakazanim osvežavanjem](system.md#schedule-tab). Takođe možete da [izvezete podatke na zahtev](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
