---
title: Obogaćivanje uz SFTP prilagođeni uvoz
description: Opšte informacije o obogaćivanju SFTP prilagođenog uvoza.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269623"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Obogatite profile klijenata uz prilagođene podatke (verzija za pregled)

Secure File Transfer Protocol (SFTP) prilagođeni uvoz vam omogućava da uvezete podatke koji ne moraju da prolaze kroz proces objedinjavanja podataka. To je fleksibilan, siguran i lak način unosa podataka. SFTP prilagođeni uvoz se može koristiti u kombinaciji sa [SFTP izvozom](export-sftp.md) koji vam omogućava izvoz podataka o profilu klijenata potrebnih za obogaćivanje. Podaci se zatim mogu obraditi, obogatiti i SFTP prilagođeni uvoz može se koristiti za vraćanje obogaćenih podataka u mogućnost uvida o korisnicima usluge Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Preduslovi

Da biste konfigurisali SFTP prilagođeni uvoz, moraju biti ispunjeni sledeći preduslovi:

- Imate korisničke akreditive (korisničko ime i lozinku) za SFTP lokaciju odakle će se podaci uvoziti.
- Imate URL i broj porta (obično 22) za STFP host.
- Imate ime datoteke i lokaciju datoteke koju treba uvesti na SFTP host.
- Postoji *model.json* datoteka koja navodi šemu za podatke koji se uvoze. Ova datoteka mora biti u istom direktorijumu kao i datoteka koju treba uvesti.
- Imate [administratorsku](permissions.md#administrator) dozvolu.

## <a name="configuration"></a>Konfigurisanje

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.

1. Na **pločici SFTP prilagođenog uvoza**, izaberite **Obogati moje podatke**.

   > [!div class="mx-imgBorder"]
   > ![Pločica SFTP prilagođenog uvoza](media/SFTP_Custom_Import_tile.png "Pločica SFTP prilagođenog uvoza")

1. Izaberite **Započnite** i navedite akreditive i adresu za SFTP server. Na primer, sftp://mysftpserver.com:22.

1. Unesite ime datoteke koja sadrži podatke i putanju do datoteke na SFTP serveru ako nije u osnovnoj fascikli.

1. Potvrdite sve unose izborom opcije **Povežite se sa prilagođenim uvozom**.

   > [!div class="mx-imgBorder"]
   > ![Potpaleta konfiguracije SFTP prilagođenog uvoza](media/SFTP_Custom_Import_Configuration_flyout.png "Potpaleta konfiguracije SFTP prilagođenog uvoza")

## <a name="defining-field-mappings"></a>Definisanje mapiranja polja 

Direktorijum koji sadrži datoteku za uvoz na SFTP server takođe mora sadržati *model.json* datoteku. Ova datoteka definiše šemu koja će se koristiti za uvoz podataka. Šema mora da koristi [Common Data Model](https://docs.microsoft.com/common-data-model/) za određivanje mapiranja polja. Jednostavan primer datoteke model.json izgleda ovako:

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
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
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

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake. Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab). Vreme obrade zavisiće od veličine podataka koji se uvoze i veze sa SFTP serverom.

Po završetku procesa obogaćivanja, možete pregledati svoje novouvezene prilagođene podatke obogaćivanja pod **Moja obogaćenja**. Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.

## <a name="next-steps"></a>Sledeći koraci

Nadogradite na obogaćenim podacima o klijentima. Kreirajte [segmente](segments.md), [mere](measures.md) i [izvezite podatke](export-destinations.md) da biste klijentima pružili personalizovana iskustva.




[!INCLUDE[footer-include](../includes/footer-banner.md)]