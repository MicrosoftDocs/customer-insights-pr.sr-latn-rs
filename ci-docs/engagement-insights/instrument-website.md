---
title: Dodavanje koda na veb-lokaciju
description: Kako da dodate isečak koda za beleženje Dynamics 365 Customer Insights događaja na vašoj veb-lokaciji.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558910"
---
# <a name="install-the-web-sdk-on-a-website"></a>Instalirajte veb SDK na veb-lokaciji

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ovaj članak opisuje kako administrator instalira veb paket alata za razvoj softvera (SDK) na veb-lokaciju. Događaje u svom radnom prostoru ćete početi da vidite ubrzo nakon opremanja veb-lokacije. Za više informacija pogledajte [Upravljanje radnim prostorima i okruženjima](manage-environments-workspaces.md). Da biste zabeležili događaje u aplikacijama za mobilne uređaje, pogledajte [Pregled resursa za programere](developer-resources.md).


### <a name="prerequisites"></a>Preduslovi

* Morate imati dozvole administratora za radni prostor za skladištenje podataka.
* Vaša veb-lokacija ili projekat moraju biti hostovani na mreži radi slanja podataka o aktivnostima. Server neće prihvatiti podatke poslate iz lokalne datoteke.


## <a name="add-web-sdk-to-your-website"></a>Dodavanje veb SDK paketa na veb-lokaciju

Idite na **Administrator** > **Radni prostor**, a zatim izaberite **Uputstvo za instalaciju**. Postoje dve opcije za instaliranje veb SDK paketa. Prvi je da koristite vezu za preuzimanje, a drugi je da instalirate paket menadžera paketa čvorova (NPM).

### <a name="option-1-using-the-download-link"></a>1. opcija: Korišćenje veze za preuzimanje

1. Izaberite **Kopiraj kod** za kopiranje isečka koda. Podrazumevano je ključ za unos vašeg radnog prostora ugrađen u isečak koda.
  :::image type="content" source="media/copy-code.png" alt-text="Snimak ekrana stranice sa isečkom koda.":::

1. Dodajte kopirani kôd na svoju veb-lokaciju, u blizini <head> oznake i pre bilo koje druge skripte ili CSS oznaka.
1. Objavite ažuriranu veb-lokaciju i sačekajte nekoliko minuta da biste pribeležili dolazni veb-saobraćaj.
1. Da biste videli svoje podatke, izaberite radni prostor iz opcije za promenu radnog prostora u oknu za navigaciju. Zatim izaberite jedan od izveštaja u odeljku **Otkrivanje**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>2. opcija: Korišćenje NPM paketa (preporučuje se za veb-aplikacije zasnovane na JavaScript-u)

1. Idite na našu [NPM veb-stranicu](https://www.npmjs.com/package/engagementinsights-web) i pratite uputstva za instaliranje i konfigurisanje veb SDK NPM paketa.
1. Objavite ažuriranu veb-lokaciju i sačekajte nekoliko minuta da biste pribeležili dolazni veb-saobraćaj.
1. Da biste videli svoje podatke, izaberite radni prostor iz opcije za promenu radnog prostora u oknu za navigaciju. Zatim izaberite jedan od izveštaja u odeljku **Otkrivanje**.

## <a name="configuration-options"></a>Opcije konfiguracije

U isečku koda možete da promenite sledeće opcije konfiguracije:

- **ingestionKey**: ključ za unos koji se koristi za slanje događaja vašem radnom prostoru. Možete promeniti ključ za unos da biste slali događaje u drugi radni prostor. Ključ za unos je jedinstven za svaki radni prostor.
- **autoCapture**: navodi da li se beleže prikazi stranice i interakcije sa veb-lokacijom. Ima dve mogućnosti:
    - **prikaz**: postavite na *tačno* da biste zabeležili prikaze stranice. Prikazi stranice beleže se kao [događaji](glossary.md#event) *Prikaza*, tip [osnovnog događaja](glossary.md#base-event).
    - **klik**: postavite na *tačno* da biste zabeležili interakcije posetilaca na veb-lokaciji. Interakcije se beleže kao [događaji](glossary.md#event) *Radnje*, tip [osnovnog događaja](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
