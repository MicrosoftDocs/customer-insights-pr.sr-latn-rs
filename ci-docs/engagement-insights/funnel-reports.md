---
title: Izveštaji o tokovima prodaje
description: Kako da pomoću izveštaja o tokovima prodaje razumete kako ciljna grupa donosi odluke.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/17/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 901e7ec50037d66c7c5ceb635d1c6cda6cfff83b
ms.sourcegitcommit: 3bafa27adae113948636b30c7462e0af060c7131
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/17/2021
ms.locfileid: "7498659"
---
# <a name="create-and-manage-funnel-reports"></a>Kreiranje izveštaja o toku prodaje i upravljanje njima

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Izveštaj o toku prodaje prikuplja informacije o koracima koji se dešavaju tokom puta koji pređe korisnik kroz vašu veb-lokaciju ili aplikaciju za mobilne uređaje. Pomaže vam da razumete kako ciljna grupa napreduje kroz proces i identifikuje tačke odustajanja. Na primer, možete da koristite izveštaj o toku prodaje kako biste identifikovali puteve i dodirne tačke klijenata pre nego što obave kupovinu. Izveštaj o toku prodaje pruža podatke za donošenje informisanih odluka i identifikovanje područja za optimizaciju i poboljšanja procesa.

## <a name="create-a-funnel-report"></a>Kreiranje izveštaja o toku prodaje

Da biste kreirali izveštaj o toku prodaje, navedite korake koje želite da uključite i aktivnost za svaki korak. Aktivnost je [događaj](glossary.md) koji predstavlja ponašanje korisnika. Izveštaj o toku prodaje prikazuje broj korisnika koji su završili svaki definisani korak. 

1. Idite na **Tokovi prodaje** i izaberite **+Novi tok prodaje** da biste započeli izveštaj o toku prodaje.

1. U opciji **Uređivač tokova prodaje**, pod **Koraci** izaberite **+Dodaj korak.** 

1. Unesite naziv u **Naslov koraka**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Novi izveštaj o toku prodaje.":::

1. Izaberite **Aktivnost**. Aktivnost beleži kada korisnik prikaže stranicu (aktivnost **Prikaza**) ili stupi u interakciju sa sadržajem (aktivnost **Radnje**).

1. Koristite **Kriterijume koraka** da biste odredili aspekt aktivnosti. [Aspekti](dimensions.md) su atributi koji mogu da opisuju, filtriraju ili grupišu podatke.

1. Opcionalno, možete da konfigurišete korake toka prodaje za više uslova. Izaberite **Dodaj uslov** da biste naveli više dimenzija u koraku. Dodatni kriterijumi moraju koristiti isti tip aktivnosti. Možete da odaberete da li je više uslova povezano operatorom AND ili OR.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Uređivač toka prodaje koji prikazuje konfiguraciju koraka sa koracima sa više uslova.":::

1. Izaberite **Dodaj korak** dok ne izvršite sve korake koje želite u izveštaju.

1. Izaberite **Sačuvaj**, imenujte izveštaj i ponovo **Sačuvaj**. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Primer: izveštaj o toku prodaje za kompaniju Fourth Coffee

Sledeći scenario prikazuje jedan od načina korišćenja izveštaja o toku prodaje. Analitičarka kompanije Fourth Coffee želi da razume uticaj nedavne promocije na stope pretplate. Ona kreira izveštaj o toku prodaje da bi identifikovala aktivnost klijenata. Počinje kada klijenti dođu na početnu stranicu kompanije dok ne iskoriste promotivni kôd pretplate. Analitičarka kreira izveštaj o toku prodaje u sledećim koracima:

1. korak: klijenti koji dođu na početnu stranicu   
2. korak: klijenti koji izvrše kupovinu   
3. korak: klijenti koji koriste promotivni kôd ostvaruju popust na pretplatu   
4. korak: registracija na pretplatu   

:::image type="content" source="media/funnel-report-example.png" alt-text="primer izveštaja o toku prodaje.":::
  
Ovaj tok prodaje vam omogućava da vidite broj korisnika koji su iskoristili promotivni kôd nakon jednokratne kupovine za registraciju za program pretplate.

### <a name="configure-advanced-settings"></a>Konfigurisanje naprednih podešavanja 

Izveštaji o toku prodaje omogućavaju vam da definišete ograničenje vremena potrebno za dovršavanje toka prodaje. Na primer, možete da podesite vreme za završetak toka prodaje na četiri dana. Ovo podešavanje broji samo uspešne registracije za pretplatu koje su se dogodile u roku od četiri dana nakon što je korisnik posetio početnu stranicu.

1. Idite na **Tokovi prodaje** da biste otvorili **Biblioteku tokova prodaje**.

1. Izaberite naziv da biste otvorili izveštaj. 

1. U oknu **Uređivač toka prodaje** izaberite **Napredna podešavanja**. 

1. Podesite „Ograniči vreme završetka toka prodaje“ na **Uključeno**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Uređivač toka prodaje prikazuje napredna podešavanja i opcije za ograničavanje vremena za završetak toka prodaje.":::

1. Odaberite vreme kada je tok prodaje morao biti završen u padajućoj listi **Postavite ograničenje na**.

1. Izaberite **Sačuvaj** da primenite promene.


## <a name="cross-channel-funnel-reports"></a>Izveštaji o toku prodaje za više kanala 

Uvidi u angažovanje takođe mogu da prikupljaju podatke o ponašanju klijenata u vašoj aplikaciji za mobilne uređaje. Kada opremite aplikaciju za mobilne uređaje platformom [Android SDK](get-started-android.md) ili [iOS SDK](get-started-ios.md) za uvide u angažovanje, možete da kreirate izveštaje o toku prodaje za više kanala. 

### <a name="create-a-cross-channel-funnel-report"></a>Kreiranje izveštaja o toku prodaje za više kanala 

1. Sledite korake da [kreirate izveštaj o toku prodaje](#create-a-funnel-report).    

1. Da biste pratili kako vaši klijenti komuniciraju sa vašim brendom na vašoj veb-lokaciji i u aplikaciji za mobilne uređaje ili na više veb-lokacija, koristite prebacivač radnog prostora da biste kreirali korake toka prodaje sa podacima iz drugih radnih prostora. U **Uređivaču toka prodaje**, u odeljku **Koraci** izaberite iz kog radnog prostora treba da potiču podaci za vaš korak toka prodaje.

## <a name="manage-funnel-reports"></a>Upravljanje izveštajima o tokovima prodaje

Možete da pregledate izveštaje o tokovima prodaje da biste analizirali podatke, pratili učinak i prikupljali uvide.

> [!NOTE]
> - Izveštaji o tokovima prodaje uvida u angažovanje trenutno podržavaju scenarije u kojima su svi korisnici u toku prodaje anonimni ili je svim korisnicima potvrđen identitet. 
> - Istorijski podaci u izveštajima o tokovima prodaje dostupni su za poslednjih 30 dana.

### <a name="view-funnel-reports"></a>Prikaz izveštaja o tokovima prodaje

1. Idite na **Tokovi prodaje** da biste otvorili **Biblioteku tokova prodaje**.
1. Izaberite naziv da biste otvorili izveštaj.    

### <a name="see-the-data-collected-for-a-report"></a>Pogledajte podatke prikupljene za izveštaj   

Da biste videli informacije o fazi

- Ukažite na korak u izveštaju.

:::image type="content" source="media/funnel-step-data.png" alt-text="podaci o toku prodaje.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Promena vremenskog perioda izveštaj o toku prodaje

1. Idite na **Tokovi prodaje** da biste otvorili **Biblioteku tokova prodaje**.

1. Izaberite naziv da biste otvorili izveštaj.

1. Otvorite **Vremenski period** i izaberite novi vremenski period sa liste ili **Fiksni opseg datuma** da biste odredili opseg datuma.

## <a name="edit-or-delete-funnel-reports"></a>Izmena ili brisanje izveštaja o tokovima prodaje

Možete da promenite naziv izveštaja o toku prodaje, da ga izbrišete ili da izmenite korake u izveštaju.

### <a name="rename-or-delete-a-funnel-report"></a>Preimenovanje ili brisanje izveštaja o toku prodaje

1. Idite na **Tokovi prodaje** da biste otvorili **Biblioteku tokova prodaje**. 

1. Izaberite **Još** pored izveštaja koji želite da promenite i odaberete **Uredi naziv** ili **Izbriši**.

### <a name="edit-a-funnel-step"></a>Uređivanje koraka toka prodaje  

1. Idite na **Tokovi prodaje** da biste otvorili **Biblioteku tokova prodaje**. 

1. Izaberite naziv da biste otvorili izveštaj.

1. Izaberite korak koji želite da uredite.

1. Izaberite **Uredi**.

1. U **Uređivaču toka prodaje**, ažurirajte informacije koje želite da promenite.  

1. Izaberite stavku **Sačuvaj**.

### <a name="reorder-a-funnel-step"></a>Preuređivanje koraka toka prodaje

1. Idite na **Tokovi prodaje** da biste otvorili **Biblioteku tokova prodaje**. 

1. Izaberite naziv da biste otvorili izveštaj.

1. Izaberite korak koji želite da preuredite.

1. Izaberite **Premesti**, a zatim **Nagore**, **Nadole**, **Na vrh** ili **Na dno**, kako biste pomerili korak.

### <a name="delete-a-funnel-step"></a>Brisanje koraka toka prodaje

1. Idite na **Tokovi prodaje** da biste otvorili **Biblioteku tokova prodaje**. 

1. Izaberite naziv da biste otvorili izveštaj.

1. Izaberite korak koji želite da uklonite i izaberite **Izbriši**.

## <a name="funnel-insights"></a>Uvidi u tokove prodaje 

Uvidi u angažovanje sada nude uvide u tokove prodaje za klijente. Koristite uvide u tokove prodaje da biste stekli dublji uvid u ponašanje klijenata o koracima u izveštaju o toku prodaje. Kada kreirate i sačuvate novi izveštaj o toku prodaje, uvidi o tokovima prodaje se automatski generišu za vaš izveštaj. 

Uvide u tokove prodaje možete da vidite iz sledećih kategorija, i na glavnom i na nivoima koraka: 

 - Stopa konverzije 
 - Vreme prelaska 
 - Vreme završetka 

Pomoću ovih uvida dublje istražite ponašanje klijenata i bolje razumite mesta odustajanja i konverzije za izveštaj o toku prodaje. 

Uvidi u tokove prodaje se ponovo izračunavaju svaka 24 sata ili kada **Sačuvate** vaš izveštaj o toku. 

> [!NOTE]
> Da biste videli uvide za svoj tok prodaje, morate da sačuvate izveštaj svaki put kada unesete izmene. 

