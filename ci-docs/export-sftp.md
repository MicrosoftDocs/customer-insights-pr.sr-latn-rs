---
title: Izvoz podataka u SFTP domaćine (pregled) (sadrži video)
description: Saznajte kako da konfigurišete vezu i izvezete na SFTP lokaciju.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207246"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Izvoz podataka u SFTP domaćine (pregled)

Koristite podatke o klijentima u nezavisnim aplikacijama tako što ćete ih izvesti na lokaciju protokola za bezbedni prenos datoteka (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Preduslovi

- Dostupnost SFTP hosta i odgovarajućih akreditiva.

## <a name="known-limitations"></a>Poznata ograničenja

- SFTP odredišta iza zaštitnih zidova trenutno nisu podržana.
- Vreme izvoženja zavisi od performansi vašeg sistema. Preporučujemo dva jezgra procesora i 1 GB memorije kao minimalnu konfiguraciju vašeg servera.
- Do 100 miliona profila klijenata, što može da potraje 90 minuta kada se koristi preporučena minimalna konfiguracija dva CPU jezgra i 1 Gb memorije.
- Ako koristite SSH ključ za potvrdu identiteta, uverite se da ste [kreirali privatni](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) ključ kao PEM ili SSH.COM format. Ako koristite Putty, konvertujte privatni ključ izvozom kao Open SSH. Podržani su sledeći formati privatnih ključeva:
  - RSA u OpenSSL PEM i ssh.com formatu
  - DSA u OpenSSL PEM i ssh.com formatu
  - ECDSA 256/384/521 u OpenSSL PEM formatu
  - ED25519 i RSA u OpenSSH formatu ključa

## <a name="set-up-connection-to-sftp"></a>Podešavanje veze sa SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Idite na **Administrator** > **Veze**.

1. Izaberite **Dodaj vezu i** odaberite **SFTP**.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Odaberite ko može da koristi ovu vezu. Podrazumevano su to samo administratori. Za više informacija, pogledajte [Dozvolite saradnicima da koriste vezu za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Odaberite da li želite da potvrdite identitet putem SSH ili korisničkog imena/lozinke za vezu i navedite neophodne detalje. Ako koristite SSH ključ za potvrdu identiteta, uverite se da ste [kreirali privatni](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) ključ kao PEM ili SSH.COM format. Ako koristite Putty, konvertujte privatni ključ izvozom kao Open SSH. Podržani su sledeći formati privatnih ključeva:
   - RSA u OpenSSL PEM i ssh.com formatu
   - DSA u OpenSSL PEM i ssh.com formatu
   - ECDSA 256/384/521 u OpenSSL PEM formatu
   - ED25519 i RSA u OpenSSH formatu ključa

1. Izaberite **Verifikuj** da testirate vezu.

1. Pregledajte privatnost [i usaglašenost podataka i](connections.md#data-privacy-and-compliance) izaberite I **slažem se**.

1. Izaberite **Sačuvaj** da biste kreirali vezu.

## <a name="configure-an-export"></a>Konfigurisanje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Idite na **Podaci** > **Izvozi**.

1. Izaberite **Dodaj izvoz**.

1. U polju **Veza za izvoz**, odaberite vezu iz odeljka SFTP. Ako veza nije dostupna, obratite se administratoru.

1. Unesite ime za izvoz.

1. Odaberite da li želite da izvezete podatke **spakovano** ili **raspakovano** i **separator polja** za izvezene datoteke.

1. Izaberite entitete, npr.

   > [!NOTE]
   > Svaki izabrani entitet će biti podeljen na najviše pet izlaznih datoteka kada se izveze.

1. Izaberite **Sačuvaj**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Izvoz entiteta koji sadrže veliku količinu podataka može dovesti do više CSV datoteka u istoj fascikli za svaki izvoz. Deljenje izvoza se dešava iz razloga performansi da bi se umanjilo vreme potrebno za dovršavanje izvoza.

[!INCLUDE [footer-include](includes/footer-banner.md)]
