---
title: Kreiranje mera i upravljanje njima
description: Definišite mere za analizu i odraz učinka vašeg poslovanja.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269945"
---
# <a name="define-and-manage-measures"></a>Definišite i upravljajte merama

Mere vam pomažu da bolje razumete ponašanje klijenata i poslovne performanse preuzimanjem relevantnih vrednosti iz [objedinjenih profila](data-unification.md). Na primer, preduzeće želi da vidi *ukupnu potrošnju po klijentu* da bi razumelo istoriju kupovine pojedinačnog klijenta. Ili meri *ukupnu prodaju preduzeća* da bi razumelo prihod na zbirnom nivou u celom preduzeću.  

Mere se kreiraju pomoću kreatora mera, platforme za upite podataka sa različitim operaterima i jednostavnim opcijama mapiranja. Omogućava vam da filtrirate podatke, grupišete rezultate, otkrivate [putanje relacija između entiteta](relationships.md) i pregledate izlaz.

Koristite kreator mera za planiranje poslovnih aktivnosti tako što ćete potražiti podatke o klijentima i izvući uvide. Na primer, kreiranje mere *ukupna potrošnja po klijentu* i *ukupan povraćaj po klijentu* pomaže u identifikovanju grupe klijenata sa visokom potrošnjom, ali i visokim povraćajem. Možete da [kreirate segment](segments.md) da biste pokrenuli sledeće najbolje radnje. 

## <a name="create-a-measure"></a>Kreiranje mere

Ovaj odeljak vas vodi kroz kreiranje nove mere od početka. Možete da izradite meru sa atributima podataka od entiteta podataka koji imaju uspostavljenu relaciju za povezivanje sa entitetom Klijent. 

1. U uvidima o korisnicima idite na **Mere**.

1. Izaberite **Novo**.

1. Izaberite **Uređivanje naziva** i navedite **Naziv** za meru. 
   > [!NOTE]
   > Ako vaša nova konfiguracija mere ima samo dva polja, za primer, CustomerID i jedan proračun, izlaz će biti dodat kao nova kolona sistemski generisanom entitetu pod nazivom Customer_Measure. I moći ćete da vidite vrednost mere u objedinjenom profilu klijenta. Druge mere će generisati sopstvene entitete.

1. U oblasti konfiguracije, odaberite agregatnu funkciju iz padajućeg menija **Izaberite funkciju**. Agregatne funkcije uključuju: 
   - **Sum**
   - **Prosek**
   - **Brojanje**
   - **Broj jedinstvenih**
   - **Maksimalna**
   - **Min**
   - **Prvi**: uzima prvu vrednost zapisa podataka
   - **Poslednji**: uzima poslednju vrednost koja je dodata u zapis podataka

   :::image type="content" source="media/measure-operators.png" alt-text="Operatori za proračun mera.":::

1. Izaberite **Dodaj atribut** da biste izabrali podatke koji su vam potrebni za kreiranje ove mere.
   
   1. Izaberite karticu **Atributi**. 
   1. Entitet podataka: Izaberite entitet koji uključuje atribut koji želite da merite. 
   1. Atribut podataka: Izaberite atribut koji želite da koristite u agregatnoj funkciji za izračunavanje mere. Istovremeno možete da izaberete samo jedan atribut.
   1. Takođe možete izabrati atribut podataka iz postojeće mere izborom kartice **Mere**. Ili možete da pretražite naziv entiteta ili naziv mere. 
   1. Izaberite **Dodaj** da biste meri dodali izabrani atribut.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Izaberite atribut koji ćete koristiti u proračunima.":::

1. Da biste izgradili složenije mere, možete dodati više atributa ili koristiti matematičke operatore na svojoj funkciji mere.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Kreirajte složenu meru pomoću matematičkih operatora.":::

1. Da biste dodali filtere, izaberite **Filter** u oblasti konfiguracije. 
  
   1. U odeljku **Dodaj atribut** okna **Filteri**, izaberite atribut koji želite da koristite za kreiranje filtera.
   1. Postavite operatore filtera da definišu filter za svaki izabrani atribut.
   1. Izaberite **Primeni** da biste meri dodali filtere.

1. Da biste dodali dimenzije, izaberite **Dimenzija** u oblasti konfiguracije. Dimenzije će se prikazati kao kolone u izlaznom entitetu mere.
   1. Izaberite **Uređivanje dimenzija** da biste dodavali atribute podataka po kojima želite da grupišete vrednosti mere. Na primer, grad ili pol. Podrazumevano, dimenzija *CustomerID* se bira za kreiranje *mera na nivou klijenta*. Možete da uklonite podrazumevanu dimenziju ako želite da kreirate *mere na nivou preduzeća*.
   1. Izaberite **Gotovo** da biste meri dodali dimenzije.

1. Ako postoji više putanja između entiteta podataka koji ste mapirali i entiteta klijenta, morate odabrati jednu od identifikovanih [putanja relacija između entiteta](relationships.md). Rezultati merenja mogu se razlikovati u zavisnosti od izabrane putanje.
   1. Izaberite **Željene opcije podataka** i odaberite putanju entiteta koju treba koristiti za identifikaciju vaše mere.
   1. Izaberite **Gotovo** da primenite svoj izbor. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Izaberite putanju entiteta za meru.":::

1. Da biste dodali još proračuna za meru, izaberite **Novi proračun**. Entitete na istoj putanji entiteta možete koristiti samo za nove proračune. Više proračuna će se prikazati kao nove kolone u izlaznom entitetu mere.

1. Izaberite **...** na proračunu da biste **napravili duplikat**, **preimenovali** ili **uklonili** proračun iz mere.

1. U oblasti **Pregled** videćete šemu podataka izlaznog entiteta mere, uključujući filtere i dimenzije. Pregled dinamički reaguje na promene u konfiguraciji.

1. Izaberite **Pokreni** da biste izračunali rezultate za konfigurisanu meru. Izaberite **Sačuvaj i zatvori** ako želite da zadržite trenutnu konfiguraciju i pokrenete meru kasnije.

1. Idite na **Mere** da biste na listi videli novokreiranu meru.

## <a name="manage-your-measures"></a>Upravljanje merama

Kada [kreirate meru](#create-a-measure), videćete listu mera na stranici **Mere**.

Pronaći ćete informacije o tipu mere, autoru, datumu nastanka, statusu i stanju. Kada izaberete meru sa liste, možete da pregledate izlaz i preuzmete .CSV datoteku.

Da biste istovremeno osvežili sve mere, izaberite **Osvežite sve** bez izbora određene mere.

> [!div class="mx-imgBorder"]
> ![Radnje za upravljanje jedinstvenim merama](media/measure-actions.png "Radnje za upravljanje jedinstvenim merama")

Izaberite meru sa liste za sledeće opcije:

- Izaberite naziv mere da biste videli njene detalje.
- **Uredite** konfiguraciju mere.
- **Osvežite** meru na osnovu najnovijih podataka.
- **Preimenujte** meru.
- **Izbrišite** meru.
- **Aktivirajte** ili **Deaktivirajte**. Neaktivne mere se neće osvežavati tokom [zakazanog osvežavanja](system.md#schedule-tab).

> [!TIP]
> Postoji [šest vrsta statusa](system.md#status-types) za zadatke/procese. Uz to, većina procesa [zavisi od drugih procesa na nižem toku](system.md#refresh-policies). Možete izabrati status procesa da biste videli detalje o toku celog posla. Nakon izbora opcije **Vidi detalje** za jedan od zadataka posla pronaći ćete dodatne informacije: vreme obrade, datum poslednje obrade i sve greške i upozorenja povezana sa zadatkom.

## <a name="next-step"></a>Sledeći korak

Možete koristiti postojeće mere za kreiranje [segmenta klijenata](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]