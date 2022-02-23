---
title: Kreiranje mera i upravljanje njima
description: Definišite mere za analizu i odraz učinka vašeg poslovanja.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f6be11bd97be71bc0c3a58eaee4d8ed45f535877
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732743"
---
# <a name="define-and-manage-measures"></a>Definišite i upravljajte merama

Mere vam pomažu da bolje razumete ponašanje klijenata i poslovne rezultate. Oni gledaju na relevantne vrednosti iz [objedinjenih profila](data-unification.md). Na primer, preduzeće želi da vidi *ukupnu potrošnju po klijentu* da biste razumeli istoriju kupovine pojedinačnog klijenta ili meru *ukupne prodaje preduzeća* da biste razumeli ukupni prihod u celom preduzeću.  

Mere se kreiraju pomoću kreatora mera, platforme za upite podataka sa različitim operaterima i jednostavnim opcijama mapiranja. Omogućava vam da filtrirate podatke, grupišete rezultate, otkrivate [putanje relacija između entiteta](relationships.md) i pregledate izlaz.

Koristite kreator mera za planiranje poslovnih aktivnosti tako što ćete potražiti podatke o klijentima i izvući uvide. Na primer, kreiranje mere *ukupna potrošnja po klijentu* i *ukupan povraćaj po klijentu* pomaže u identifikovanju grupe klijenata sa visokom potrošnjom, ali i visokim povraćajem. Možete da [kreirate segment](segments.md) da biste pokrenuli sledeće najbolje radnje. 

## <a name="build-your-own-measure-from-scratch"></a>Napravite sopstvenu meru ispočetka

Ovaj odeljak vas vodi kroz kreiranje nove mere od početka. Možete da napravite meru sa atributima podataka iz entiteta podataka koji imaju uspostavljen odnos za povezivanje sa objedinjenim entitetom profila klijenta.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

1. U uvidima o korisnicima idite na **Mere**.

1. Izaberite **Nova** i birajte **Napravite sopstvenu**.

1. Izaberite **Uređivanje naziva** i navedite **Naziv** za meru. 

1. U oblasti konfiguracije, odaberite funkciju agregacije iz padajućeg menija **Izaberi funkciju**. Agregatne funkcije uključuju: 
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
   1. Takođe možete izabrati atribut podataka iz postojeće mere izborom kartice **Mere** ili možete da pretražite naziv entiteta ili naziv mere. 
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

1. Ako u vašim podacima postoje vrednosti koje morate zameniti celim brojem, izaberite **Pravila**. Konfigurišite pravilo i obavezno odaberite samo cele brojeve kao zamenu. Na primer, zamenite *nula* sa *0*.

1. Ako postoji više putanja između entiteta podataka koji ste mapirali i entiteta *Klijent*, morate odabrati jednu od identifikovanih [putanja relacija između entiteta](relationships.md). Rezultati merenja mogu se razlikovati u zavisnosti od izabrane putanje. 
   
   1. Izaberite **Putanja odnosa** i izaberite putanju entiteta koju treba koristiti za identifikaciju mere. Ako postoji samo jedan put do entiteta *Klijent*, ova kontrola se neće prikazati.
   1. Izaberite **Gotovo** da primenite svoj izbor. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Izaberite putanju entiteta za meru.":::

1. Da biste dodali još proračuna za meru, izaberite **Novi proračun**. Entitete na istoj putanji entiteta možete koristiti samo za nove proračune. Više proračuna će se prikazati kao nove kolone u izlaznom entitetu mere.

1. Izaberite **...** na proračunu da biste **napravili duplikat**, **preimenovali** ili **uklonili** proračun iz mere.

1. U oblasti **Pregled** videćete šemu podataka izlaznog entiteta mere, uključujući filtere i dimenzije. Pregled dinamički reaguje na promene u konfiguraciji.

1. Izaberite **Pokreni** da biste izračunali rezultate za konfigurisanu meru. Izaberite **Sačuvaj i zatvori** ako želite da zadržite trenutnu konfiguraciju i pokrenete meru kasnije.

1. Idite na **Mere** da biste na listi videli novokreiranu meru.

# <a name="business-accounts-b-to-b"></a>[Poslovni nalozi (B-to-B)](#tab/b2b)

1. U uvidima o korisnicima idite na **Mere**.

1. Izaberite **Nova** i birajte **Napravite sopstvenu**.

1. Izaberite **Uređivanje naziva** i navedite **Naziv** za meru. 

1. U oblasti konfiguracije, odaberite funkciju agregacije iz padajućeg menija **Izaberi funkciju**. Agregatne funkcije uključuju: 
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
   1. Takođe možete izabrati atribut podataka iz postojeće mere izborom kartice **Mere** ili možete da pretražite naziv entiteta ili naziv mere. 
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

1. Ako u vašim podacima postoje vrednosti koje morate zameniti celim brojem, izaberite **Pravila**. Konfigurišite pravilo i obavezno odaberite samo cele brojeve kao zamenu. Na primer, zamenite *nula* sa *0*.

1. Možete koristiti prekidač **Sabiranje dodatnih poslovnih kontakata** ako [koristite naloge sa hijerarhijom](relationships.md#set-up-account-hierarchies).
   - Ako je podešeno na **Isključeno**, mera se izračunava za svaki poslovni kontakt. Svaki poslovni kontakt ima svoj rezultat.
   - Ako je podešeno na **Uključeno**, izaberite **Uredi** da biste odabrali hijerarhiju poslovnih kontakata prema unetim hijerarhijama. Mera će dati samo jedan rezultat jer je objedinjena sa podnalozima.

1. Ako postoji više putanja između entiteta podataka koji ste mapirali i entiteta *Klijent*, morate odabrati jednu od identifikovanih [putanja relacija između entiteta](relationships.md). Rezultati merenja mogu se razlikovati u zavisnosti od izabrane putanje. 
   
   1. Izaberite **Putanja odnosa** i izaberite putanju entiteta koju treba koristiti za identifikaciju mere. Ako postoji samo jedan put do entiteta *Klijent*, ova kontrola se neće prikazati.
   1. Izaberite **Gotovo** da primenite svoj izbor. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Izaberite putanju entiteta za meru.":::

1. Izaberite **...** na proračunu da biste **napravili duplikat**, **preimenovali** ili **uklonili** proračun iz mere.

1. U oblasti **Pregled** videćete šemu podataka izlaznog entiteta mere, uključujući filtere i dimenzije. Pregled dinamički reaguje na promene u konfiguraciji.

1. Izaberite **Pokreni** da biste izračunali rezultate za konfigurisanu meru. Izaberite **Sačuvaj i zatvori** ako želite da zadržite trenutnu konfiguraciju i pokrenete meru kasnije.

1. Idite na **Mere** da biste na listi videli novokreiranu meru.

---

## <a name="use-a-template-to-build-a-measure"></a>Korišćenje predloška za izgradnju mere

Da biste ih kreirali, možete koristiti unapred definisane predloške najčešće korišćenih mera. Detaljni opisi predložaka i vođeno iskustvo pomažu vam u efikasnom kreiranju mera. Predlošci se nadovezuju na mapirane podatke iz entiteta *Objedinjena aktivnost*. Uverite se da ste konfigurisali [aktivnosti klijenata](activities.md) pre nego što kreirate meru iz predloška.

# <a name="individual-consumers-b-to-c"></a>[Pojedinačni potrošači (B-to-C)](#tab/b2c)

Da biste ih kreirali, možete koristiti unapred definisane predloške najčešće korišćenih mera. Detaljni opisi predložaka i vođeno iskustvo pomažu vam u efikasnom kreiranju mera. Predlošci se nadovezuju na mapirane podatke iz entiteta *Objedinjena aktivnost*. Uverite se da ste konfigurisali [aktivnosti klijenata](activities.md) pre nego što kreirate meru iz predloška.

Dostupni predlošci mera: 
- Prosečna vrednost transakcije (ATV)
- Ukupna vrednost transakcije
- Prosečan dnevni prihod
- Prosečan godišnji prihod
- Broj transakcija
- Osvojeni poeni lojalnosti
- Iskorišćeni poeni lojalnosti
- Bilans poena iz programa lojalnosti
- Vremenski opseg aktivnosti klijenta
- Trajanje članstva u programu lojalnosti
- Vreme od poslednje kupovine

Sledeći postupak opisuje korake za izgradnju nove mere pomoću predloška.

1. U uvidima o korisnicima idite na **Mere**.

1. Izaberite **Nova** i birajte **Odaberi predložak**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Snimak ekrana padajućeg menija prilikom kreiranja nove mere sa isticanjem na predlošku.":::

1. Pronađite predložak koji odgovara vašim potrebama i izaberite **Odaberi predložak**.

1. Pregledajte potrebne podatke i izaberite **Započnite** ako su svi podaci na svom mestu.

1. U oknu **Uređivanje naziva** postavite naziv mere i izlazni entitet. 

1. Izaberite **Gotovo**.

1. U odeljku **Podešavanje vremenskog perioda** definišite vremenski okvir podataka koji će se koristiti. Odaberite da li želite da nova mera pokriva čitav skup podataka izborom **Sve vreme**, ili ako želite da se mera fokusira na **Određeni vremenski period**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Snimak ekrana koji prikazuje odeljak vremenskog perioda prilikom konfigurisanja mere iz predloška.":::

1. U sledećem odeljku, izaberite **Dodaj podatke** da biste izabrali aktivnosti i mapirali odgovarajuće podatke iz svog entiteta *Objedinjena aktivnost*.

    1. Korak 1 od 2: Ispod **Tipa aktivnosti** odaberite tip entiteta koji želite da koristite. Za **Aktivnosti**, izaberite entitete koje želite da mapirate.
    1. Korak 2 od 2: Izaberite atribut iz entiteta *Objedinjena aktivnost* za komponentu koja je obavezna za formulu. Na primer, za „Prosečna vrednost transakcije“, to je atribut koji predstavlja vrednost transakcije. Za **Vremensku oznaku aktivnosti**, odaberite atribut iz entiteta objedinjene aktivnosti koji predstavlja datum i vreme aktivnosti.
   
1. Kada mapiranje podataka bude uspešno, možete videti da status ima vrednost **Kompletno** i naziv mapiranih aktivnosti i atributa.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Snimak ekrana dovršene konfiguracije predloška mere.":::

1. Sada možete odabrati **Pokreni** da biste izračunali rezultate mere. Da biste je kasnije precizirali, izaberite **Sačuvaj radnu verziju**.

# <a name="business-accounts-b-to-b"></a>[Poslovni nalozi (B-to-B)](#tab/b2b)

Ova funkcija je dostupna samo za mere kreirane u okruženjima čiji su pojedinačni klijenti primarna ciljna grupa.

---

## <a name="manage-your-measures"></a>Upravljanje merama

Spisak mera možete pronaći na stranici **Mere**.

Pronaći ćete informacije o tipu mere, autoru, datumu nastanka, statusu i stanju. Kada na listi izaberete meru, možete da pregledate izlaz i preuzmete CSV datoteku.

Da biste istovremeno osvežili sve mere, izaberite **Osvežite sve** bez izbora određene mere.

> [!div class="mx-imgBorder"]
> ![Radnje za upravljanje jedinstvenim merama.](media/measure-actions.png "Radnje za upravljanje jedinstvenim merama.")

Izaberite meru sa liste za sledeće opcije:

- Izaberite naziv mere da biste videli njene detalje.
- **Uredite** konfiguraciju mere.
- **Osvežite** meru na osnovu najnovijih podataka.
- **Preimenujte** meru.
- **Izbrišite** meru.
- **Aktivirajte** ili **Deaktivirajte**. Neaktivne mere se neće osvežavati tokom [zakazanog osvežavanja](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Sledeći korak

Možete koristiti postojeće mere da biste kreirali [segment klijenata](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
