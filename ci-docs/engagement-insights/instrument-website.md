---
title: Dodavanje koda na veb-lokaciju
description: Kako da dodate isečak koda za beleženje događaja na vašoj veb-lokaciji.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035111"
---
# <a name="install-the-code-snippet-on-a-website"></a>Instalirajte isečak koda na veb-lokaciju

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ovaj članak opisuje kako administrator instalira isečak koda na veb-lokaciju. Događaje u vašem radnom prostoru počećete da vidite ubrzo nakon dodavanja skripte veb-lokaciji. Za više informacija pogledajte [Upravljanje radnim prostorima i okruženjima](manage-environments-workspaces.md). Da biste zabeležili događaje u aplikacijama za mobilne uređaje, pogledajte [Pregled resursa za programere](developer-resources.md).


### <a name="prerequisites"></a>Preduslovi

* Morate imati dozvole administratora za radni prostor za skladištenje podataka.
* Vaša veb-lokacija ili projekat moraju biti hostovani na mreži radi slanja podataka o aktivnostima. Server neće prihvatiti podatke poslate iz lokalne datoteke.


## <a name="add-code-to-your-website"></a>Dodavanje koda na veb-lokaciju
1.  Idite na **Administrator** > **Radni prostor**, a zatim izaberite **Uputstvo za instalaciju**.
1. Izaberite **Kopiraj kod** za kopiranje isečka koda. Podrazumevano je ključ za unos vašeg radnog prostora ugrađen u isečak koda.
:::image type="content" source="media/copy-code.png" alt-text="Snimak ekrana stranice sa isečkom koda.":::
3. Dodajte kopirani isečak koda na svoju veb-lokaciju, blizu <head> oznake i pre bilo koje druge skripte ili CSS oznaka.
4.  Objavite ažuriranu veb-lokaciju i sačekajte nekoliko minuta da biste pribeležili dolazni veb-saobraćaj.
5.  Da biste videli svoje podatke, izaberite radni prostor iz opcije za promenu radnog prostora u oknu za navigaciju. Zatim izaberite jedan od izveštaja u odeljku **Otkrivanje**.

## <a name="configuration-options"></a>Opcije konfiguracije

U isečku koda možete da promenite sledeće opcije konfiguracije:

- **ingestionKey**: ključ za unos koji se koristi za slanje događaja vašem radnom prostoru. Možete promeniti ključ za unos da biste slali događaje u drugi radni prostor. Ključ za unos je jedinstven za svaki radni prostor. 
- **autoCapture**: navodi da li se beleže prikazi stranice i interakcije sa veb-lokacijom. Ima dve mogućnosti:
    - **prikaz**: postavite na *tačno* da biste zabeležili prikaze stranice. Prikazi stranice beleže se kao [događaji](glossary.md#event) *Prikaza*, tip [osnovnog događaja](glossary.md#base-event).
    - **klik**: postavite na *tačno* da biste zabeležili interakcije posetilaca na veb-lokaciji. Interakcije se beleže kao [događaji](glossary.md#event) *Radnje*, tip [osnovnog događaja](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
