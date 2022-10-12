---
title: Povežite se sa podacima u Microsoft Dataverse upravljanom jezeru podataka
description: Uvoz podataka iz Microsoft Dataverse upravljanog jezera podataka.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609813"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Povežite se sa podacima u Microsoft Dataverse upravljanom jezeru podataka

Microsoft Dataverse korisnici mogu brzo da se povežu sa analitičkim entitetima u upravljanom Microsoft Dataverse jezeru. Samo jedan izvor podataka okruženja može istovremeno da koristi isto Dataverse nadgledano jezero.

> [!NOTE]
> Morate biti administrator organizacije da biste Dataverse nastavili i pregledali listu entiteta dostupnih u kontrolisanom jezeru.

## <a name="prerequisites"></a>Preduslovi

- Podaci uskladišteni u mrežnim uslugama, kao što je Azure Data Lake Storage, mogu se skladištiti na lokaciji različitoj od one na kojoj se podaci obrađuju ili skladište u usluzi Dynamics 365 Customer Insights.Uvozom ili povezivanjem sa podacima uskladištenim u uslugama na mreži slažete se da se podaci mogu prenositi i skladištiti sa programom Dynamics 365 Customer Insights. [Saznajte više u Microsoft centru za pouzdanost](https://www.microsoft.com/trust-center).

- Vidljivi Dataverse su samo entiteti [sa omogućenim](/power-platform/admin/enable-change-tracking-control-data-synchronization) praćenjem promena. Ovi entiteti se mogu izvesti u jezero sa podacima Dataverse kojim se upravlja i koristiti u uvidima kupaca. Tabele bez okvira Dataverse podrazumevano imaju omogućeno praćenje promena. Potrebno je da uključite praćenje promena za prilagođene tabele. Da biste proverili da Dataverse li je tabela omogućena za praćenje promena, idite na tabele [Power Apps](https://make.powerapps.com) > **podataka** > **·**. Pronađite tabelu koja vas interesuje i izaberite je. Idite na **opcije** > **"Više opcija postavki"** i pregledajte postavku **praćenja** promena.

## <a name="connect-to-a-dataverse-managed-lake"></a>Povežite se sa Dataverse upravljanim jezerom

1. Idite na **Podaci** > **Izvori podataka**.

1. Izaberite **Dodaj izvor podataka**.

1. Izaberite stavku **Microsoft Dataverse**.

1. Unesite **ime** za izvor podataka i opcionalni **opis**.

1. Navedite **Adresu servera** za Dataverse organizaciju i izaberite **Prijavite se**.

1. Izaberite tabele koje želite da unestite kao entitete u uvid kupca sa dostupne liste.

   > [!NOTE]
   > Ako su neke tabele već izabrane, mogu ih koristiti druge Dynamics 365 aplikacije (poput Dynamics 365 Sales Insights ili Customer Service Insights). Ne možete promeniti izbor. Ove tabele će biti dostupne kao entiteti kada se kreira izvor podataka.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dijalog koji prikazuje listu entiteta u Dataverse okruženju.":::

1. Sačuvajte svoj izbor da biste započeli sinhronizaciju izabranih tabela iz usluge Dataverse. Novododatu vezu ćete pronaći na stranici **Izvori podataka**. Biće stavljeno u red za osvežavanje i prikazaće broj entiteta kao 0 dok se sve izabrane tabele ne sinhronizuju.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Učitavanje podataka može potrajati. Nakon uspešnog osvežavanja, uneti podaci se mogu redigovanje sa stranice [**"Entiteti**](entities.md) ".

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Uredite izvor podataka za Dataverse upravljano jezero

Izbor entiteta uređujete tek nakon što kreirate izvor podataka. Na primer, ako su dodati dodatni entiteti u uslugu Dataverse, a želite i da ih uvozite.
Da biste se povezali sa drugim Dataverse jezerom podataka, [kreirajte novi izvor podataka](#connect-to-a-dataverse-managed-lake).

1. Idite na **Podaci** > **Izvori podataka**.

1. Pored izvor podataka želite da ažurirate, izaberite stavku **Uredi**.

1. Izaberite dodatne entitete sa dostupne liste entiteta.

1. Kliknite **na dugme** "Sačuvaj" da biste primenili promene i vratili se na **stranicu "Izvori podataka** ".

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Uobičajeni razlozi za greške u brisanju ili oštećene podatke

Sledeće provere se vrše na unetim podacima kako bi se otkrili oštećeni zapisi:

- Vrednost polja se ne podudara sa tipom podataka njegove kolone.
- Polja sadrže znakove zbog kojih se kolone ne podudaraju sa očekivanom šemom. Na primer: nepravilno oblikovani navodnici, neupareni navodnici ili znakovi novog reda.
- Ako postoje kolone datuma/datuma/datuma/datuma, njihov format mora biti naveden u modelu ako ne sledi standardni ISO format.

### <a name="schema-or-data-type-mismatch"></a>Nepodudaranje šeme ili tipa podataka

Ako podaci nisu u skladu sa šemom, zapisi su klasifikovani kao oštećeni. Ispravite izvorne podatke ili šemu i ponovo ih unesite.

### <a name="datetime-fields-in-the-wrong-format"></a>Polja datuma u pogrešnom formatu

Polja datuma u entitetu nisu u ISO ili en-US formatima. Podrazumevani format datuma u uvidima klijenata je en-US format. Sva polja datuma u entitetu treba da budu u istom formatu. Uvidi klijenata podržavaju druge formate navedene beleške ili osobine koje se izlaћu na nivou izvora ili entiteta u modelu ili manifestu.json. Na primer:

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  U manifestu.json, format datuma može biti naveden na nivou entiteta ili na nivou atributa. Na nivou entiteta koristite "osobine eksponata" u entitetu u *.manifest.cdm.json da biste definisali format vremena prenosa podataka. Na nivou atributa koristite "primenjene osobine" u atributu u imenu entiteta.cdm.json.

**Manifest.json na nivou entiteta**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entitet.json na nivou atributa**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
