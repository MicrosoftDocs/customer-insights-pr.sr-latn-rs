---
title: Predvideti pretplatu churn (sadrži video)
description: Predvidite da li je klijent ugrožen zbog toga što više ne koristi proizvode ili usluge vašeg preduzeća sa pretplatom.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610253"
---
# <a name="predict-subscription-churn"></a>Predviđanje gubitka pretplata

Predvidite da li je klijent ugrožen zbog toga što više ne koristi proizvode ili usluge vašeg preduzeća sa pretplatom. Podaci o pretplati uključuju aktivne i neaktivne pretplate za svakog kupca tako da postoji više stavki po ID-u kupca.

Morate imati poslovno znanje da biste razumeli šta churn znači za vaš posao. Mi podržavamo definicije zasnovane na vremenu, što znači da se smatra da je klijent čučao određeni vremenski period nakon završetka pretplate.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Isprobajte pretplatnički churn predviđanje koristeći probne podatke: [Vodič za predviđanje churn](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Preduslovi

- Barem [Dozvole saradnika](permissions.md).
- Najmanje 10 profila kupaca, po mogućstvu više od 1.000 jedinstvenih kupaca.
- Identifikator kupca, jedinstveni identifikator koji odgovara pretplatama na kupce.
- Podaci o pretplati za najmanje dvostruko više od izabranog vremenskog prozora. Poželjno je dve do tri godine podataka o pretplati. Istorija pretplate mora da sadrži:
  - **ID pretplate:** Jedinstveni identifikator pretplate.
  - **Datum završetka pretplate:** Datum isteka pretplate za kupca.
  - **Datum početka pretplate:** Datum početka pretplate za kupca.
  - **Datum transakcije: Datum** kada se desila promena pretplate. Na primer, klijent kupuje ili otkazuje pretplatu.
  - **Da li je to periodična pretplata:** Bulovi true/false polje koje određuje da li će se pretplata obnoviti istim ID-om pretplate bez intervencije kupca.
  - **Učestalost ponavljanja (mesecima): Za periodične** pretplate, mesec kada će se pretplata obnoviti. Na primer, godišnja pretplata koja se automatski obnavlja kod klijenta svake godine na još godinu dana ima vrednost 12.
  - **Iznos pretplate**: Iznos valute koju kupac plaća za obnavljanje pretplate. Može vam pomoći da identifikujete obrasce za različite nivoe pretplate.
- Najmanje dva zapisa aktivnosti za 50% kupaca za koje želite da izračunate. Aktivnosti kupaca moraju da uključuju:
  - **Primarni ključ:** Jedinstveni identifikator za aktivnost. Na primjer, poseta veb-lokaciji ili evidencija o upotrebi koja prikazuje da je klijent odgledao epizodu TV emisije.
  - **Vremenska osa:** Datum i vreme događaja identifikovani primarnim ključem.
  - **Događaj:** Ime događaja koji želite da koristite. Na primer, polje pod nazivom „UserAction“ u striming video usluzi može imati vrednost „Pregledano“.
  - **Detalji:** Detaljne informacije o događaju. Na primer, polje pod nazivom „ShowTitle“ u striming video usluzi može imati vrednost video zapisa koji je klijent odgledao.
- Vrednostima koje nedostaju manje od 20% u polju podataka navedenog entiteta.

## <a name="create-a-subscription-churn-prediction"></a>Kreiranje predviđanja gubitka pretplata

U **svakom trenutku izaberite** stavku Sačuvaj radnu verziju da biste sačuvali predviđanje kao radnu verziju. Radna verzija predviđanje na kartici "**Moja predviđanja**".

1. Idite na **obaveštajna** > **predviđanja**.

1. Na kartici **Kreiranje** izaberite stavku **Korišćenje modela** na pločici **modela Customer churn**.

1. Izaberite **pretplatu** za tip churn-a, a zatim prvi **koraci**.

1. **Dajte ime ovom modelu** i **Izlazni naziv entiteta** da ih razlikujete od ostalih modela ili entiteta.

1. Izaberite **Sledeće**.

### <a name="define-customer-churn"></a>Definisanje gubitka klijenata

1. Unesite broj za **Dani od završetka pretplate** i to je period za koji preduzeće smatra da je status klijenta Izgubljen. Ovaj period je obično povezan sa poslovnim aktivnostima kao što su ponude ili drugi marketinški napori koji pokušavaju da spreče gubitak kupca.

1. Unesite broj dana za **istraživanje budućnosti da biste predvideli churn**. Na primer, predvidite rizik od gubitka klijenata tokom sledećih 90 dana kako biste se uskladili sa vašim marketinškim naporima za zadržavanje. Predviđanje rizika odliva na duži ili kraći vremenski period može otežati adresiranje faktora u vašem profilu rizika od gubitka klijenta, u zavisnosti od vaših specifičnih poslovnih zahteva.

1. Izaberite **Sledeće**.

### <a name="add-required-data"></a>Dodavanje obaveznih podataka

1. Izaberite **opciju Dodaj podatke** za istoriju **pretplate**.

1. Izaberite tip semantičke aktivnosti Pretplata **koja** sadrži potrebne informacije o istoriji pretplate. Ako aktivnost nije podešena, izaberite je **ovde i** kreirajte je.

1. U **okviru** Aktivnosti, ako su atributi aktivnosti semantički mapirani prilikom kreiranja aktivnosti, odaberite određene atribute ili entitet na koji želite da se izračunavanje fokusira. Ako nije došlo do semantičkog mapiranja, izaberite opciju Uredi **i** mapiraj svoje podatke.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Dodavanje potrebnih podataka za model Subscription churn":::

1. Kliknite **na** dugme "Dalje" i pregledajte atribute potrebne za ovaj model.

1. Izaberite **Sačuvaj**.

1. Izaberite **opciju Dodaj podatke** za **aktivnosti klijenta**.

1. Izaberite vrstu semantičke aktivnosti koja obezbeđuje informacije o aktivnostima klijenta. Ako aktivnost nije podešena, izaberite je **ovde i** kreirajte je.

1. U **okviru** Aktivnosti, ako su atributi aktivnosti semantički mapirani prilikom kreiranja aktivnosti, odaberite određene atribute ili entitet na koji želite da se izračunavanje fokusira. Ako nije došlo do semantičkog mapiranja, izaberite opciju Uredi **i** mapiraj svoje podatke.

1. Kliknite **na** dugme "Dalje" i pregledajte atribute potrebne za ovaj model.

1. Izaberite **Sačuvaj**.

1. Dodajte još aktivnosti ili kliknite na dugme " **Dalje"**.

### <a name="set-update-schedule"></a>Podešavanje rasporeda ažuriranja

1. Odaberite učestalost prekvalifikacije modela. Ova postavka je važna za ažuriranje tačnosti predviđanja jer se novi podaci unose u uvide klijenata. Većina preduzeća može da obavi ponovnu obuku jednom mesečno i dobije precizna predviđanja.

1. Izaberite **Sledeće**.

### <a name="review-and-run-the-model-configuration"></a>Pregledajte i pokrenite konfiguraciju modela

Korak **"Rediguj** i pokreni" prikazuje rezime konfiguracije i pruža šansu za promene pre nego što kreirate predviđanje.

1. Izaberite **stavku Uredi** na bilo kom koraku da biste redigoli i napravili bilo kakve promene.

1. Ako ste zadovoljni izborom, izaberite sačuvaj i pokreni **da biste počeli** da pokrenete model. Izaberite **Gotovo**. Kartica **"Moja predviđanja**" prikazuje se predviđanje se kreira sadržaj. Za završetak procesa može biti potrebno nekoliko sati, u zavisnosti od količine podataka korišćenih u predviđanju.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prikaži predviđanje rezultate

1. Idite na **obaveštajna** > **predviđanja**.

1. Na kartici **Moja predviđanja** izaberite predviđanje želite da prikažete.

Postoje tri primarna odeljka podataka na stranici sa rezultatima:

- **Performanse modela** obuke: Ocene A, B ili C ukazuju na performanse predviđanje-a i mogu vam pomoći da donesete odluku o korišćenju rezultata uskladištenih u izlaznom entitetu.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Slika informativnog okvira za ocenu modela sa klasom A.":::

  Klase se određuju na osnovu sledećih pravila:
  - **Kada** je model tačno predvideo najmanje 50% ukupnih predviđanja, i kada je procenat tačnih predviđanja za kupce koji su se udubljeni veći od istorijske prosečne stope churn-a za najmanje 10%.
  - **B** kada je model tačno predvideo najmanje 50% ukupnih predviđanja, i kada je procenat tačnih predviđanja za kupce koji su se pojavili i do 10% veći od istorijske prosečne stope churn-a.
  - **C** kada je model tačno predvideo manje od 50% ukupnih predviđanja, ili kada je procenat tačnih predviđanja za kupce koji su se kretali manji od istorijske prosečne stope churn-a.
  
- **Verovatnoća gubitka (broj klijenata)**: Grupe klijenata na osnovu predviđenog rizika od gubitka. Opcionalno, [kreirajte segmente kupaca](prediction-based-segment.md) sa visokim rizikom. Takvi segmenti vam pomažu da razumete gde treba da bude prekid članstva u segmentu.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Grafikon koji prikazuje raspodelu rezultata gubitaka, podeljen u opsege od 0-100%":::

- **Najuticajniji faktori:** Mnogo je faktora koji se uzimaju u obzir pri kreiranju predviđanja. Svaki od faktora ima svoj značaj izračunat za agregirana predviđanja koja model kreira. Koristite ove faktore da biste proverili valjanost predviđanje rezultata. Ili koristite ove informacije kasnije da biste kreirali [segmente koji](.//prediction-based-segment.md) bi mogli da utiču na rizik za kupce.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Lista koja pokazuje uticajne faktore i njihovu važnost u predviđanju rezultata gubitaka.":::

> [!NOTE]
> U izlaznom entitetu za ovaj model, *ChurnScore* je predviđena verovatnoća churn-a *, a IsChurn je binarna* oznaka *zasnovana na ChurnScore* sa 0,5 pragom. Ako ovaj podrazumevani prag ne funkcioniše za vaš scenario, kreirajte [novi segment sa](segments.md) željenim pragom. Da biste prikazali churn rezultat, idite na **entitete** > **podataka** i prikažite karticu sa podacima za izlazni entitet koji ste definisali za ovaj model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
