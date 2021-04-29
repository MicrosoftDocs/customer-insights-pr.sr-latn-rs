---
title: Obogaćivanje uz SFTP prilagođeni uvoz
description: Opšte informacije o obogaćivanju SFTP prilagođenog uvoza.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896298"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Obogatite profile klijenata uz prilagođene podatke (verzija za pregled)

Prilagođeni uvoz protokola bezbednog prenosa datoteka (SFTP) omogućava vam uvoz podataka koji ne moraju da prolaze kroz proces objedinjavanja podataka. To je fleksibilan, siguran i lak način unosa podataka. SFTP prilagođeni uvoz se može koristiti u kombinaciji sa [SFTP izvozom](export-sftp.md) koji vam omogućava izvoz podataka o profilu klijenata potrebnih za obogaćivanje. Podaci se zatim mogu obraditi, obogatiti i SFTP prilagođeni uvoz može se koristiti za vraćanje obogaćenih podataka u mogućnost uvida o korisnicima usluge Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Preduslovi

Da biste konfigurisali SFTP prilagođeni uvoz, moraju biti ispunjeni sledeći preduslovi:

- Imate ime datoteke i lokaciju (putanju) do datoteke koju treba uvesti na SFTP host.
- Postoji datoteka *model.json* koja navodi [šemu zajedničkog modela podataka](/common-data-model/) za uvoz podataka. Ova datoteka mora biti u istom direktorijumu kao i datoteka koju treba uvesti.
- Administrator je već konfigurisao SFTP vezu *ili* imate dozvole [administratora](permissions.md#administrator). Trebaće vam korisnički akreditivi, URL adresa i broj porta za SFTP lokaciju odakle želite da uvezete podatke.


## <a name="configure-the-import"></a>Konfigurisanje uvoza

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.

1. Na **pločici za SFTP prilagođeni uvoz** izaberite **Obogati moje podatke**, a zatim izaberite **Započni**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Pločica SFTP prilagođenog uvoza.":::

1. Izaberite [vezu](connections.md) iz padajuće liste. Ako veza nije dostupna, obratite se administratoru. Ako ste administrator, vezu možete da napravite ako izaberete **Dodaj vezu** i birate **SFTP prilagođeni uvoz** iz padajućeg menija.

1. Izaberite **Povežite sa prilagođenim uvozom** da biste potvrdili izabranu vezu.

1.  Izaberite **Sledeće** i unesite **Naziv dokumenta** i **Putanju** datoteke podataka koju želite da uvezete.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Snimak ekrana prilikom unosa lokacije podataka.":::

1. Izaberite **Sledeće** i obezbedite naziv za obogaćivanje i naziv za izlazni entitet. 

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfigurisanje veze za SFTP prilagođenim uvozom 

Morate biti administrator da biste konfigurisali veze. Izaberite **Dodaj vezu** prilikom konfigurisanja obogaćivanja *ili* idite na **Administrator** > **Veze** i izaberite **Podešavanje** na pločici Custom Import.

1. Unesite naziv veze u polje **Ime za prikaz**.

1. Unesite važeće korisničko ime, lozinku i URL adresu hosta za SFTP server na kojem se nalaze podaci za uvoz.

1. Pregledajte i dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**.

1. Izaberite **Verifikuj** da biste proverili valjanost konfiguracije.

1. Kada se verifikacija završi, vezu možete sačuvati klikom na **Sačuvaj**.

> [!div class="mx-imgBorder"]
   > ![Stranica za konfiguraciju veze za Experian](media/enrichment-SFTP-connection.png "Stranica za konfiguraciju veze za Experian")


## <a name="defining-field-mappings"></a>Definisanje mapiranja polja 

Direktorijum koji sadrži datoteku za uvoz na SFTP server takođe mora sadržati *model.json* datoteku. Ova datoteka definiše šemu koja će se koristiti za uvoz podataka. Šema mora da koristi [Common Data Model](/common-data-model/) za određivanje mapiranja polja. Jednostavan primer datoteke model.json izgleda ovako:

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
