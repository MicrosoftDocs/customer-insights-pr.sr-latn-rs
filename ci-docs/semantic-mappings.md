---
title: Semantička mapiranja (verzija za pregled)
description: Pregled semantičkih mapiranja i kako ih koristiti.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183648"
---
# <a name="semantic-mappings-preview"></a>Semantička mapiranja (verzija za pregled)

Semantička mapiranja vam omogućavaju da mapirate podatke o neaktivnosti u unapred definisane šeme. Ove šeme pomažu uvidima klijenata da bolje razumeju atribute podataka. Semantičko mapiranje i obezbeđeni podaci omogućavaju nove uvide i funkcije u uvidima klijenata. Da biste podatke o aktivnostima mapirali u šeme, pregledajte dokumentaciju [aktivnosti](activities.md).

**Semantička mapiranja su trenutno omogućena za okruženja zasnovana na poslovnim nalozima**. *ContactProfile je* jedini tip semantičkog mapiranja koji je trenutno dostupan u programu Customer Insights.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definišite mapiranje semantičkog entiteta ContactProfile

1. Idite **na Data** > **Semantic mapiranja (pregled)**.

1. Izaberite **Dodaj semantičko mapiranje** da biste započeli navođeno iskustvo.

1. U koraku **Podaci o entitetu**, podesite vrednosti za sledeća polja:

   - **Ime mapiranja semantičkog entiteta**: Ime za mapiranje semantičkog entiteta.
   - **Izvorni entitet**: Entitet koji uključuje podatke o kontaktima.
   - **Primarni ključ**: Polje koje jedinstveno identifikuje zapis kontakta. Ono ne bi smelo da sadrži duplikate, prazne vrednosti ili vrednosti koje nedostaju.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Podesite mapiranje semantičkog entiteta sa imenom, izvornim entitetom i primarnim ključem.":::

1. Izaberite **Sledeće**.

1. U koraku **Odnosi**, konfigurišite detalje za povezivanje podataka o kontaktu sa odgovarajućim podacima o poslovnom kontaktu. Ovaj korak vizualizuje vezu između entiteta.  

   Postoje dve vrste putanja odnosa koji se mogu primeniti: **Direktni odnosi** i **Indirektni odnosi**. Za više informacija idite na [direktne i indirektne putanje odnosa](relationships.md#relationship-paths).

   1. Kliknite na **dugme "Dodaj relaciju** " da biste konfigurisali relaciju.
   1. Odaberite atribut iz izvornog entiteta koji povezuje vaš entitet kontakta sa drugim entitetom.
   1. Odaberite entitet sa kojim ćete povezati svoj entitet kontakta. Odaberite entitet iz entiteta naloga **ili iz** odeljka Entitet **posrednika**. Ako izaberete posrednički entitet, definišite drugu relaciju za povezivanje sa entitetom ciljnog naloga.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Izaberite entitet Nalog ili posrednički entitet.":::

   1. Navedite **Naziv odnosa**. Ako odnos između vaših entiteta već postoji, naziv odnosa je samo za čitanje. Ako ne postoji odnos, biće kreiran novi odnos sa nazivom koji navedete.
   1. Izaberite **Primeni** da biste dovršili konfiguraciju odnosa.

   > [!NOTE]
   > Možete da konfigurišete više odnosa između entiteta kontakta i drugih entiteta naloga sa posredničkim entitetima.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Vizuelizacija različitih odnosa povezuje entitete kontakta sa entitetima naloga.":::

1. Izaberite **Sledeće**.

1. U koraku **Podesite semantički tip**, izaberite **Semantički tip**. Trenutno postoji jedan **Semantički tip** pod nazivom *ContactProfile*.

1. Mapirajte ID kontakta na *semantički* tip **KontaktProfile**. Opcionalno, mapiraj druga polja kao što su ime, prezime, pol ili e-pošta.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mapirajte atribute svojih podataka o kontaktu sa navedenim obaveznim i opcionim poljima.":::

1. Izaberite **Sledeće**.

1. U **koraku** "Pregled" pregledajte konfiguraciju semantičkog mapiranja. Da biste napravili promene, izaberite **uredi** za odgovarajući odeljak.

1. Izaberite **Sačuvaj**.

1. Da biste obradili semantičko mapiranje, izaberite **pokreni**. Ili kliknite **na dugme** "Zatvori" da biste sačuvali semantičko mapiranje bez njegove obrade. Da biste ga pokrenuli kasnije, izaberite semantičko mapiranje i izaberite stavku **Osveži**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Upravljanje postojećim semantičkim mapiranjima

Idite **na Data** > **Semantic mapiranja (preview)** da biste prikazali sačuvana semantička mapiranja, njihov izvorni entitet, semantički tip, tip mapiranja i status.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opcije za upravljanje semantičkim mapiranjima.":::

Izaberite semantičko mapiranje da biste videli dostupne radnje.
- **Uredite** trenutnu konfiguraciju. Izaberite **Sačuvaj** i **Pokreni** da biste obradili promene.
- **Osvežite** semantičko mapiranje da biste uključili najnovije podatke. Osvežavanje bilo kog datog semantičkog mapiranja osvežiće sva semantička mapiranja istog tipa.
- **Preimenujte** semantičko mapiranje. Izaberite **Sačuvaj**.
- **Izbrišite** semantičko mapiranje. Da biste istovremeno izbrisali više semantičkih mapiranja, izaberite semantička mapiranja i ikonu za brisanje. Izaberite **Izbriši** da biste potvrdili brisanje.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Korišćenje mapiranja semantičkog entiteta KontaktProfile za kreiranje aktivnosti na nivou kontakta

Nakon kreiranja mapiranja *semantičkog entiteta ContactProfile*, možete da uhvatite aktivnosti kontakata. Omogućava vam da vidite vremensku osu aktivnosti za konto koji je kontakt odgovoran za svaku aktivnost. Većina koraka sledi tipičnu konfiguraciju mapiranja aktivnosti.

   > [!NOTE]
   > Da bi aktivnosti na nivou kontakta uspele, morate imati **ID** **naloga i atribute "ID** kontaktA" za svaki zapis u okviru podataka o aktivnostima.

1. [Definišite *mapiranje semantičkog entiteta* KontaktProfile](#define-a-contactprofile-semantic-entity-mapping) i pokrenite semantičko mapiranje.

1. Idite na aktivnosti **sa** > **podacima**.

1. Kliknite **na dugme "Dodaj** aktivnost" da biste kreirali novu aktivnost.

1. Imenuj aktivnost, izaberite entitet izvorne aktivnosti i izaberite primarni ključ entiteta aktivnosti.

1. U odnosi **koraku** kreirajte indirektnu relaciju između izvornih podataka aktivnosti sa nalozima, koristeći podatke o kontaktu kao posrednički entitet. Više informacija potražite u direktnim [i indirektnim putanjama odnosa](relationships.md#relationship-paths).
   - Primer relacije za aktivnost koja se zove "Nabavke *"*:
      - **Podaci o kontaktu izvorne aktivnosti** > **nabavke** na atributu ID **kontakta**
      - **Podaci o nalogu** > **podataka** kontakta na ID-u **naloga atributa**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Primer podešavanja relacija.":::

1. Kada podešavate odnosi, kliknite na dugme **"** Dalje" i dovršite konfiguraciju mapiranja aktivnosti. Detaljne korake kreiranja aktivnosti pogledajte u članku [Definisanje aktivnosti](activities.md).

1. Pokrenite mapiranja aktivnosti.

1. Kada se pokreće mapiranje aktivnosti na nivou kontakta, izaberite stavku **Kupci**. Aktivnosti na nivou kontakta prikazuju se na vremenskoj osi kupca.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Konačni rezultat nakon konfigurisanja aktivnosti kontakta":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtriranje vremenske ose na nivou aktivnosti na nivou kontakta

Vremenska osa aktivnosti za vaše klijente uključuje njihove ID-ove ili imena, u zavisnosti od *konfiguracije ContactProfile datoteke*, za aktivnosti na kojima su postupili. Filtrirajte aktivnosti po kontaktima na vremenskoj osi da biste videli određene kontakte za koje ste zainteresovani. Da biste prikazali sve aktivnosti koje nisu dodeljene određenom kontaktu, izaberite **aktivnosti koje nisu mapirane kontaktu**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Opcije filtriranja dostupne za aktivnosti na nivou kontakta.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
