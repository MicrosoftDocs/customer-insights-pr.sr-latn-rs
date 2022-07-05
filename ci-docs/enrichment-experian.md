---
title: Obogatite profile klijenata demografskim podacima iz usluge Experian (verzija za pregled)
description: Opšte informacije o Experian nezavisnom obogaćivanju.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: a30e98b06ed07590ab95cae1d8db8023e49ff7f9
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053038"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obogatite profile klijenata demografskim podacima iz usluge Experian (verzija za pregled)

Experian je globalni lider u izveštavanju o potrošačkim i poslovnim kreditima i marketinškim uslugama. Koristeći Experian usluge obogaćivanja podataka, možete da razvijete dublje razumevanje svojih klijenata obogaćujući svoje profile klijenata demografskim podacima kao što su veličina domaćinstva, prihod i još mnogo toga.

## <a name="supported-countriesregions"></a>Podržane zemlje/regioni

Trenutno podržavamo obogaćivanje profila kupaca samo u Sjedinjenim Državama.

## <a name="prerequisites"></a>Preduslovi

- Aktivna pretplata Experian. Da biste nabavili pretplatu, [kontaktirajte Experian](https://www.experian.com/marketing-services/contact) direktno. [Saznajte više o Experian obogaćivanju podataka](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Vezu Experian [je](connections.md) [konfigurisao](#configure-the-connection-for-experian) administrator.

- Experian Korisnički ID, ID stranke i broj modela za vaš nalog bezbednog transporta (ST) omogućen za SSH koji je Experian kreiran za vas.

## <a name="configure-the-connection-for-experian"></a>Konfigurisanje veze za Experian

Morate biti administrator u " [Uvidima](permissions.md#admin) klijenata" i imati Experian ID korisnika, ID stranke i broj modela.

1. Izaberite **opciju** Dodaj vezu prilikom konfigurisanja obogaćivanja ili idite **na administrativne** > **veze** i izaberite **stavku Podešavanje** na Experian pločici.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Okno za konfiguraciju Experian veze.":::

1. Unesite ime za vezu i važeći ID korisnika, ID stranke i broj modela za vaš nalog bezbednog Experian transporta.

1. Pregledajte i dajte saglasnost za [Privatnost podataka i usklađenost](#data-privacy-and-compliance) izborom opcije **Slažem se**.

1. Izaberite **opciju** Proveri da biste proverili valjanost konfiguracije, a zatim kliknite na dugme **Sačuvaj**.

### <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite Dynamics 365 Customer Insights za prenos podataka u Experian, dozvoljavate prenos podataka izvan granice usklađenosti za Dynamics 365 Customer Insights, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će prenositi takve podatke po vašem uputstvu, ali vi ste odgovorni za to da Experian ispunjava sve obaveze privatnosti ili bezbednosti koje imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Vaš Dynamics 365 Customer Insights administrator može u svakom trenutku da ukloni ovo obogaćivanje kako biste prestali sa korišćenjem ove funkcionalnosti.

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.

1. Izaberite **obogati moje podatke** o **demografiji** sa Experian pločice.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian pločica na stranici za pregled obogaćivanja.":::

1. Pregledajte pregled, a zatim kliknite na dugme **Dalje**.

1. Izaberite vezu. Obratite se administratoru ako nije dostupan.

1. Izaberite **Sledeće**.

1. Izaberite opciju **skup podataka i** odaberite profil ili segment koji želite da obogatite demografskim podacima iz Experian programa. Entitet *kupca* obogaćuje sve profile kupaca, dok segment obogaćuje samo profile kupaca sadržane u tom segmentu.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Snimak ekrana prilikom odabira skupa podataka o klijentima.":::

1. Definišite tip polja iz objedinjenih profila koja ćete koristiti za podudaranje demografskih podataka iz Experian programa. Obavezno je barem jedno od polja **Ime i adresa**, **Telefon** ili **E-pošta**. Za veću tačnost podudaranja dodajte druga polja. Izaberite **Sledeće**.

1. Mapirajte polja na demografske podatke od Experian.

1. Izaberite **Sledeće** da biste dovršili mapiranje polja.

1. Navedite **ime** za bogaćenje i ime **entiteta izlaza**.

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

1. Kliknite **na dugme** "Pokreni" da biste započeli proces obogaćivanja ili blizu da biste se vratili na stranicu **"Obogaćivanje** ".

## <a name="view-enrichment-results"></a>Prikaži rezultate obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Broj **kupaca obogaćenih poljem obezbeđuje** dubinsku analizu pokrivenosti svakog obogaćenog polja.

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]