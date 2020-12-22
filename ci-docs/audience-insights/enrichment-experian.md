---
title: Obogaćivanje pomoću obogaćivanja treće strane Experian
description: Opšte informacije o Experian obogaćivanju treće strane.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668830"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obogatite profile klijenata demografskim podacima kompanije Experian (verzija za pregled)

Experian je globalni lider u izveštavanju o potrošačkim i poslovnim kreditima i marketinškim uslugama. Pomoću usluga obogaćivanja podataka kompanije Experian, možete da izgradite dublje razumevanje svojih klijenata obogaćivanjem profila klijenata demografskim podacima kao što su veličina domaćinstva, prihod i još mnogo toga.

## <a name="prerequisites"></a>Preduslovi

Da biste konfigurisali Experian, moraju da se ispune sledeći preduslovi:

- Imate aktivnu pretplatu na Experian. Da biste dobili pretplatu, [obratite se kompaniji Experian](https://www.experian.com/marketing-services/contact) direktno. [Saznajte više o Experian obogaćivanju podataka](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Imate ID korisnika, ID stranke i broj modela za SSH omogućeni Secure Transport (ST) nalog koji je Experian kreirao za vas.
- Imate [administratorske](permissions.md#administrator) dozvole u uvidima o korisnicima.

## <a name="configuration"></a>Konfigurisanje

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.

1. Izaberite **Obogati moje podatke** na Experian pločici.

   > [!div class="mx-imgBorder"]
   > ![Experian pločica](media/experian-tile.png "Experian pločica")

1. Izaberite **Započnite** i unesite ID korisnika, ID stranke i broj modela za vaš Experian Secure Transport nalog. Pregledajte i dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**. Potvrdite sve unose izborom **Primeni**.

## <a name="map-your-fields"></a>Mapiranje polja

1. Izaberite **Dodaj podatke** i izaberite ključne identifikatore iz opcija **Ime i adresa**, **E-pošta** ili **Telefon** koje ćete poslati kompaniji Experian radi rešavanja identiteta.

   > [!TIP]
   > Više atributa ključnih identifikatora poslatih u Experian verovatno daje veću stopu podudaranja.

1. Izaberite **Sledeće** i mapirajte odgovarajuće atribute iz vašeg objedinjenog entiteta klijenta za izabrana polja ključnog identifikatora.

1. Izaberite **Dodaj atribut** da biste mapirali sve dodatne atribute koje biste želeli da pošaljete kompaniji Experian.

1.  Izaberite **Sačuvaj** da biste dovršili mapiranje polja.

   > [!div class="mx-imgBorder"]
   > ![Mapiranje polja za Experian](media/experian-field-mapping.png "Mapiranje polja za Experian")

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake. Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab). Vreme obrade zavisiće od veličine vaših podataka o klijentima i procesa obogaćivanja koje je za vaš nalog podesio Experian.

Nakon završetka procesa obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod opcijom **Moja obogaćivanja**. Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.

## <a name="next-steps"></a>Sledeći koraci

Nadogradite na obogaćenim podacima o klijentima. Kreirajte [segmente](segments.md), [mere](measures.md), pa čak i [izvezite podatke](export-destinations.md) da biste pružili personalizovana iskustva svojim klijentima.

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite da Dynamics 365 Customer Insights prenosi podatke u Experian, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Experian ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.
