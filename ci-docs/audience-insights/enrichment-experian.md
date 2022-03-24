---
title: Obogaćivanje putem nezavisnog obogaćivanja Experian
description: Opšte informacije o Experian nezavisnom obogaćivanju.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: efa26fa82a950063e074a4ab930ed95383c55334
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376709"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obogatite profile klijenata demografskim podacima iz usluge Experian (verzija za pregled)

Experian je globalni lider u izveštavanju o potrošačkim i poslovnim kreditima i marketinškim uslugama. Koristeći Experian usluge obogaćivanja podataka, možete da razvijete dublje razumevanje svojih klijenata obogaćujući svoje profile klijenata demografskim podacima kao što su veličina domaćinstva, prihod i još mnogo toga.

## <a name="prerequisites"></a>Preduslovi

Da biste konfigurisali Experian, morate ispuniti sledeće preduslove:

- Imate aktivnu pretplatu na Experian. Da biste nabavili pretplatu, [kontaktirajte Experian](https://www.experian.com/marketing-services/contact) direktno. [Saznajte više o Experian obogaćivanju podataka](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Administrator je već konfigurisao vezu sa uslugom Experian *ili* imate dozvole [administratora](permissions.md#admin). Takođe su vam potrebni ID korisnika, ID stranke i broj modela za vaš SSH omogućeni nalog za bezbedni transport (ST)koji je usluga Experian kreirala za vas.

## <a name="supported-countriesregions"></a>Podržane zemlje/regioni

Trenutno podržavamo obogaćivanje profila kupaca samo u Sjedinjenim Državama.

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.

1. Izaberite **Obogati moje podatke** na pločici Experian.

   > [!div class="mx-imgBorder"]
   > ![Experian pločica.](media/experian-tile.png "Experian tile")
   > 

1. Izaberite [vezu](connections.md) sa padajuće liste. Ako veza nije dostupna, obratite se administratoru. Ako ste administrator, vezu možete da napravite ako izaberete **Dodaj vezu** i birate Experian sa padajuće liste. 

1. Izaberite **Poveži se za uslugom Experian** da biste potvrdili izbor veze.

1.  Izaberite **Sledeće** i birajte **Skup podataka o klijentu** koji želite da obogatite demografskim podacima iz usluge Experian. Možete izabrati entitet **Klijent** da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Snimak ekrana prilikom odabira skupa podataka o klijentima.":::

1. Izaberite **Sledeće** i definišite koji tip polja iz vaših objedinjenih profila treba da koristite za traženje odgovarajućih demografskih podataka iz usluge Experian. Obavezno je barem jedno od polja **Ime i adresa**, **Telefon** ili **E-pošta**. Za veću preciznost podudaranja, mogu se dodati još dva polja. Ovaj izbor će uticati na polja za mapiranje kojima imate pristup u sledećem koraku.

    > [!TIP]
    > Više atributa identifikatora ključa poslatih usluzi Experian povećavaju verovatnoću postizanja više stope podudaranja.

1. Izaberite **Sledeće** da biste započeli mapiranje polja.

1. Definišite koja polja iz vaših objedinjenih profila treba da koristite za traženje odgovarajućih demografskih podataka iz usluge Experian. Obavezna polja su označena.

1. Obezbedite naziv za obogaćivanje i naziv za izlazni entitet.

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

## <a name="configure-the-connection-for-experian"></a>Konfigurisanje veze za Experian 

Morate biti administrator da biste konfigurisali veze. Izaberite **Dodaj vezu** kada konfigurišete obogaćivanje *ili* idite na **Administrator** > **Veze** i izaberite **Podesiti** na pločici Experian.

1. Izaberite **Prvi koraci**.

1. Unesite naziv veze u polje **Ime za prikaz**.

1. Unesite važeći ID korisnika, ID stranke i broj modela za svoj nalog za Experian bezbedan transport.

1. Pregledajte i dajte saglasnost za **Privatnost podataka i usklađenost** izborom opcije **Slažem se**.

1. Izaberite **Verifikuj** da biste proverili valjanost konfiguracije.

1. Po završetku verifikacije, izaberite **Sačuvaj**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Okno za konfiguraciju Experian veze.":::

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Da biste započeli proces obogaćivanja, izaberite **Pokreni** sa komandne trake. Takođe možete pustiti da sistem automatski pokreće obogaćivanje kao deo [planiranog osvežavanja](system.md#schedule-tab). Vreme obrade zavisiće od veličine vaših podataka o klijentu i procesa obogaćivanja koje je za vaš nalog podesio Experian.

Nakon završetka procesa obogaćivanja, podatke o novoobogaćenim profilima klijenata možete pregledati pod opcijom **Moja obogaćivanja**. Osim toga, pronaći ćete vreme poslednjeg ažuriranja i broj obogaćenih profila.

Detaljnom prikazu svakog obogaćenog profila možete pristupiti ako izaberete **Prikaži obogaćene podatke**.

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite Dynamics 365 Customer Insights za prenos podataka u Experian, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Experian ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
