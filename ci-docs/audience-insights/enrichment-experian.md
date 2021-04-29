---
title: Obogaćivanje pomoću obogaćivanja treće strane Experian
description: Opšte informacije o Experian obogaćivanju treće strane.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896390"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obogatite profile klijenata demografskim podacima kompanije Experian (verzija za pregled)

Experian je globalni lider u izveštavanju o potrošačkim i poslovnim kreditima i marketinškim uslugama. Pomoću usluga obogaćivanja podataka kompanije Experian, možete da izgradite dublje razumevanje svojih klijenata obogaćivanjem profila klijenata demografskim podacima kao što su veličina domaćinstva, prihod i još mnogo toga.

## <a name="prerequisites"></a>Preduslovi

Da biste konfigurisali Experian, moraju da se ispune sledeći preduslovi:

- Imate aktivnu pretplatu na Experian. Da biste dobili pretplatu, [obratite se kompaniji Experian](https://www.experian.com/marketing-services/contact) direktno. [Saznajte više o Experian obogaćivanju podataka](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Administrator je već konfigurisao Experian vezu *ili* imate dozvole [administratora](permissions.md#administrator). Takođe su vam potrebni ID korisnika, ID stranke i broj modela za vaš nalog za bezbedni transport (ST) koji omogućava SSH i koji je Experian kreirao za vas.

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.

1. Izaberite **Obogati moje podatke** na Experian pločici.

   > [!div class="mx-imgBorder"]
   > ![Experian pločica](media/experian-tile.png "Experian pločica")
   > 

1. Izaberite [vezu](connections.md) iz padajuće liste. Ako veza nije dostupna, obratite se administratoru. Ako ste administrator, vezu možete da napravite ako izaberete **Dodaj vezu** i birate Experian iz padajućeg menija. 

1. Izaberite **Povežite se sa uslugom Experian** da potvrdite izbor veze.

1.  Izaberite **Sledeće** i odaberite **Skup podataka klijenta** koji želite da obogatite demografskim podacima usluge Experian. Možete izabrati entitet **Klijent** da biste obogatili sve vaše profile klijenata ili izaberite entitet segmenta da biste obogatili samo profile klijenata sadržane u tom segmentu.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Snimak ekrana prilikom odabira skupa podataka o klijentima.":::

1. Izaberite **Sledeće** i definišite koji tip polja iz vaših objedinjenih profila treba koristiti za traženje odgovarajućih demografskih podataka iz usluge Experian. Obavezno je barem jedno od polja **Ime i adresa**, **Telefon** ili **E-pošta**. Za veću preciznost podudaranja, mogu se dodati još dva polja. Ovaj izbor će uticati na polja za mapiranje kojima imate pristup u sledećem koraku.

    > [!TIP]
    > Više atributa ključnih identifikatora poslatih u Experian verovatno daje veću stopu podudaranja.

1. Izaberite **Sledeće** da biste započeli mapiranje polja.

1. Definišite koji tip polja iz vaših objedinjenih profila treba koristiti za traženje odgovarajućih demografskih podataka iz usluge Experian. Obavezna polja su označena.

1. Obezbedite naziv za obogaćivanje i naziv za izlazni entitet.

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

## <a name="configure-the-connection-for-experian"></a>Konfigurišite vezu za Experian 

Morate biti administrator da biste konfigurisali veze. Izaberite **Dodaj vezu** prilikom konfigurisanja obogaćivanja *ili* idite na **Administrator** > **Veze** i izaberite **Podešavanje** na pločici Experian.

1. Izaberite **Prvi koraci**.

1. Unesite naziv veze u polje **Ime za prikaz**.

1. Unesite važeći ID korisnika, ID stranke i broj modela za svoj nalog za Experian bezbedni transport.

1. Pregledajte i dajte svoj pristanak za **Privatnost podataka i usaglašenost** tako što ćete izabrati polje za potvrdu **Slažem se**

1. Izaberite **Verifikuj** da biste proverili valjanost konfiguracije.

1. Po završetku verifikacije, izaberite **Sačuvaj**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Okno za konfiguraciju veze za Experian.":::

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
