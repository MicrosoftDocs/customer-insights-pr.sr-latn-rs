---
title: Izvoz segmenata u LiveRamp (verzija za pregled)
description: Saznajte kako da konfigurišete vezu i izvezete u LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196733"
---
# <a name="export-segments-to-liverampreg-preview"></a>Izvoz segmenata u LiveRamp&reg; (verzija za pregled)

Aktivirajte svoje podatke u usluzi LiveRamp da biste se povezali sa preko 500 platformi na digitalnim, društvenim i televizijskim sistemima. Radite sa svojim podacima u usluzi LiveRamp da biste ciljali, potisnuli i personalizovali oglasne kampanje.

## <a name="prerequisites"></a>Preduslovi

- LiveRamp pretplata za korišćenje ove linije spajanja. Da biste dobili pretplatu, [kontaktirajte LiveRamp](https://liveramp.com/contact/) direktno. [Saznajte više o usluzi LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Poznata ograničenja

- LiveRamp izvoz koristi SFTP izvoz. SFTP odredišta iza zaštitnih zidova trenutno nisu podržana.
- Ako koristite SSH ključ za potvrdu identiteta, uverite se da ste [kreirali privatni](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) ključ kao PEM ili SSH.COM format. Ako koristite Putty, konvertujte privatni ključ izvozom kao Open SSH. Podržani su sledeći formati privatnih ključeva:
  - RSA u OpenSSL PEM i ssh.com formatu
  - DSA u OpenSSL PEM i ssh.com formatu
  - ECDSA 256/384/521 u OpenSSL PEM formatu
  - ED25519 i RSA u OpenSSH formatu ključa
- Vreme izvoženja zavisi od performansi vašeg sistema. Preporučujemo dva jezgra procesora i 1 GB memorije kao minimalnu konfiguraciju vašeg servera.
- Izvoz entiteta sa do 100 miliona korisničkih profila može potrajati 90 minuta kada se koristi preporučena minimalna konfiguracija sa dva jezgra procesora i 1 GB memorije.
- Stvarni broj profila (ili podataka) koje možete da izvezete u LiveRamp zavisi od vaše pretplate pomoću programa LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Podešavanje veze u usluzi LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **dodaj vezu i** odaberite **LiveRamp**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Odaberite da li želite da potvrdite identitet putem SSH ili korisničkog imena/lozinke za vezu i navedite neophodne detalje.

1. Izaberite **Verifikuj** da testirate vezu sa uslugom LiveRamp.

1. Nakon uspešne provere, pregledajte privatnost i [usaglašenost podataka i izaberite](connections.md#data-privacy-and-compliance) I **slažem se**.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka LiveRamp. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. U polju Podataka **"Povezivanje**" izaberite e-poštu **·**, **ime i adresu** ili telefon **koji ćete** poslati programu LiveRamp za rešavanje identiteta.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="LiveRamp konektor sa mapiranjem atributa.":::

1. Mapirajte odgovarajuće atribute iz vašeg entiteta *Klijent* za izabrani identifikator ključa.

1. Izaberite **Dodaj atribut** da biste mapirali više atributa za slanje u LiveRamp.

   > [!TIP]
   > Ako pošaljete više ključnih atributa identifikatora u LiveRamp, verovatno će dobiti višu stopu podudaranja.

1. Izaberite segmente koje želite da izvezete.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
