---
title: Obogaćivanje pomoću obogaćivanja treće strane Experian
description: Opšte informacije o Experian obogaćivanju treće strane.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269577"
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

1.  Izaberite **Dodaj podatke** i izaberite **Skup podataka o klijentima** koji želite da obogatite demografskim podacima kompanije Experian. Možete izabrati entitet **Klijent** da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.

1. Izaberite svoje ključne identifikatore iz polja **Ime i adresa**, **E-adresa** ili **Telefon** koje ćete poslati kompaniji Experian radi rešavanja identiteta.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]