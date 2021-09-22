---
title: Prikaz i kreiranje dimenzija
description: Kako da kreirate, uređujete i brišete aspekte.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b575c5e84197d76f53a722bac60c5af928c917f9671720ede1de38c4a7478be4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034014"
---
# <a name="view-and-create-dimensions"></a>Prikaz i kreiranje dimenzija

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Aspekt je atribut događaja koji može da opiše, filtrira ili grupiše podatke. Ako na svojoj veb-lokaciji vodite marketinšku promociju, možete da koristite aspekte za sortiranje posetilaca po novim i ponovnim korisnicima.  

Uvid u angažovanje uključuje gotove aspekte za svojstva događaja. Primeri uključuju sledeće:

- Naziv pregledača
- Ime stranice
- Model uređaja
- Operativni sistem
- Zemlja

## <a name="view-dimensions"></a>Prikaz aspekata

Aspekti se zasnivaju na postojećim svojstvima događaja. Kada koristite kôd za praćenje za uvide u angažman, sistemski aspekti se automatski kreiraju.

1. Idite na odeljak **Podaci** u levom oknu za navigaciju. 
1. Izaberite **Aspekti** da biste videli spisak svih aspekata u radnom prostoru. 
   > [!NOTE]
   > Sistemski generisani aspekti su samo za čitanje. Ne možete ih uređivati. Možete da kreirate i uređujete samo prilagođene aspekte.

## <a name="create-a-dimension"></a>Kreiranje dimenzije

Pored sistemski generisanih aspekata, administratori okruženja i radnih prostora mogu da kreiraju prilagođene aspekte. Prilagođeni aspekti se zasnivaju na podrazumevanim svojstvima osnovnih događaja ili ih mogu koristiti [prilagođena svojstva događaja](advanced-SDK-implementation.md).

1. Idite na **Podaci** > **Aspekti**.
1. Izaberite **Dodaj aspekt**.

   :::image type="content" source="media/add-dimension.png" alt-text="Dodavanje aspekta događaju.":::

1. U oknu **Kreiranje aspekta** izaberite svojstvo na kojem će se aspekt zasnivati. Lista svojstava prikazaće sva svojstva u radnom prostoru koja nisu dodeljena aspektu.
1. Unesite naziv u polje **Ime za prikaz**. Opcionalno, možete dodati opis.
1. Izaberite **Kreiraj** da biste sačuvali aspekt. Može potrajati do jednog minuta da biste počeli da koristite aspekt u [prilagođenom izveštaju](custom-reports.md) ili [segmentu](segments.md). 

## <a name="edit-a-dimension"></a>Uređivanje aspekta

Možete da promenite naziv i opis aspekta.

1. Idite na **Podaci** > **Aspekti**.
1. Izaberite aspekt koji želite da izbrišete.
1. U oknu **Uređivanje aspekta** ažurirajte aspekt.
1. Izaberite **Primeni** da biste sačuvali promene.

## <a name="delete-a-dimension"></a>Brisanje aspekta

Možete da izbrišete samo aspekte koje su kreirali korisnici, ali ne možete da uklonite sistemske aspekte.

Brisanje aspekta je trajno. Izveštaji i segmenti koji koriste izbrisani aspekt više neće funkcionisati. 

1. Idite na **Podaci** > **Aspekti**.
1. Izaberite aspekt koji želite da izbrišete.
1. U oknu **Uređivanje aspekta** izaberite **Izbriši aspekt**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Brisanje aspekta događaja.":::

1. Unesite **CONFIRM DELETE** (velikim slovima) da biste potvrdili brisanje. 
1. Izaberite **Izbriši**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
