---
title: Obogatite profile klijenata SFTP prilagođenim uvozom (pregled)
description: Opšte informacije o obogaćivanju SFTP prilagođenog uvoza.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 81ef6c62240e26cb5c9475e6306e08edc7e5eb31
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195813"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Obogatite profile klijenata SFTP prilagođenim uvozom (pregled)

Secure File Transfer Protocol (SFTP) prilagođeni uvoz vam omogućava da uvezete podatke koji ne moraju da prolaze kroz proces objedinjavanja podataka. To je fleksibilan, siguran i lak način unosa podataka. SFTP prilagođeni uvoz se može koristiti u kombinaciji sa [SFTP izvozom](export-sftp.md) koji vam omogućava izvoz podataka o profilu klijenata potrebnih za obogaćivanje. Podaci se zatim mogu obraditi i obogatiti, a SFTP prilagođeni uvoz može da se koristi za povratak obogaćenih podataka na Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Preduslovi

- Poznato je ime datoteke i lokacija (putanja) datoteke koja treba da se uveze na SFTP domaćinu.

- Dostupna *je datoteka model.json* koja navodi šemu "Uobičajeni model podataka" za uvoz podataka. Ova datoteka mora biti u istom direktorijumu kao i datoteka koju treba uvesti.

- SFTP [veza](connections.md) je [konfigurisana](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Primer šeme datoteka

Direktorijum koji sadrži datoteku za uvoz na SFTP server takođe mora sadržati *model.json* datoteku. Ova datoteka definiše šemu koja će se koristiti za uvoz podataka. Šema treba da koristi [Common Data Model](/common-data-model/) da odredi mapiranje polja. Jednostavan primer datoteke model.json izgleda ovako:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfigurisanje veze za SFTP prilagođenim uvozom

Morate biti administrator u programu [Customer](permissions.md#admin) Insights i imati korisničke akreditive, URL adresu i broj porta za SFTP lokaciju sa koje želite da uvezete podatke.

1. Izaberite **opciju Dodaj** vezu prilikom konfigurisanja obogaćenja ili idite na **administrativne** > **veze i** izaberite **stavku Podešavanje** na pločici "Prilagođeni uvoz".

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Prilagođena stranica za konfiguraciju veze uvoza.":::

1. Unesite ime za vezu.

1. Unesite važeće korisničko ime, lozinku i URL hosta za SFTP server na kojem se nalaze podaci koje treba uvesti.

1. Pregledajte i dajte saglasnost za [Privatnost podataka i usklađenost](#data-privacy-and-compliance) izborom opcije **Slažem se**.

1. Izaberite **opciju** Proveri da biste proverili valjanost konfiguracije, a zatim kliknite na dugme **Sačuvaj**.

### <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite prenos Dynamics 365 Customer Insights podataka pomoću prilagođenog uvoza, dozvoljavate prenos podataka izvan granice usaglašenosti Dynamics 365 Customer Insights za, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će preneti takve podatke na vaše uputstvo, ali vi ste odgovorni za to da obezbedite da podaci ispunjavaju sve obaveze privatnosti ili bezbednosti koje možda imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.

## <a name="configure-the-import"></a>Konfigurisanje uvoza

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.

1. Izaberite **stavku Obogati moje podatke** na **SFTP prilagođenoj pločici** za uvoz.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Pločica SFTP prilagođenog uvoza.":::

1. Pregledajte pregled, a zatim kliknite na dugme **Dalje**.

1. Izaberite vezu. Ako veza nije dostupna, obratite se administratoru.

1. Izaberite opciju **skup podataka i** odaberite profil ili segment koji želite da obogatite. Entitet *kupca* obogaćuje sve profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

1. Izaberite **Sledeće**.

1. Unesite putanju **i** ime **datoteke** datoteke sa podacima koju želite da uvezete.

1. Izaberite **Sledeće**.

1. Navedite **ime** za bogaćenje i ime **entiteta izlaza**.

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

1. Kliknite **na dugme** "Pokreni" da biste započeli proces obogaćivanja ili blizu da biste se vratili na stranicu **"Obogaćivanje** ".

## <a name="view-enrichment-results"></a>Prikaži rezultate obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
