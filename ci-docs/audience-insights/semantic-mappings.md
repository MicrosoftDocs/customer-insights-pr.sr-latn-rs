---
title: Semantička mapiranja (verzija za pregled)
description: Pregled semantičkih mapiranja i kako ih koristiti.
ms.date: 12/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: 08b257b97704b219bb3277042516e00deb886a49
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881847"
---
# <a name="semantic-mappings-preview"></a>Semantička mapiranja (verzija za pregled)

Semantička mapiranja vam omogućavaju da mapirate podatke o neaktivnosti u unapred definisane šeme. Ove šeme pomažu uvidima u ciljnu grupu da bolje razumeju vaše atribute podataka. Semantičko mapiranje i dati podaci omogućavaju nove uvide i funkcije u uvidima u ciljnu grupu. Da biste podatke o aktivnostima mapirali u šeme, pregledajte dokumentaciju [aktivnosti](activities.md).

**Semantička mapiranja su trenutno omogućena za okruženja zasnovana na poslovnim nalozima**. *ContactProfile* je jedini tip semantičkog mapiranja koji je trenutno dostupan u uvidima u ciljnu grupu.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definišite mapiranje semantičkog entiteta ContactProfile

1. U uvidima u ciljnu grupu, idite na **Podaci** > **Semantička mapiranja (verzija za pregled)**.

1. Izaberite **Dodaj semantičko mapiranje** da biste započeli navođeno iskustvo.

1. U koraku **Podaci o entitetu**, podesite vrednosti za sledeća polja:

   - **Naziv mapiranja semantičkog entiteta**: navedite naziv za mapiranje semantičkog entiteta.
   - **Izvorni entitet**: izaberite entitet koji sadrži podatke o kontaktu.
   - **Primarni ključ**: Izaberite polje koje jedinstveno identifikuje zapis kontakta. Ono ne bi smelo da sadrži duplikate, prazne vrednosti ili vrednosti koje nedostaju.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Podesite mapiranje semantičkog entiteta sa imenom, izvornim entitetom i primarnim ključem.":::

1. Izaberite **Dalje** za nastavak.

1. U koraku **Odnosi**, konfigurišite detalje za povezivanje podataka o kontaktu sa odgovarajućim podacima o poslovnom kontaktu. Ovaj korak vizualizuje vezu između entiteta.  

   Postoje dve vrste putanja odnosa koji se mogu primeniti: **Direktni odnosi** i **Indirektni odnosi**. Za više informacija idite na [direktne i indirektne putanje odnosa](relationships.md#relationship-paths).

   1. Izaberite **Dodaj odnos** da biste konfigurisali odnos.
   1. Odaberite atribut iz izvornog entiteta koji povezuje vaš entitet kontakta sa drugim entitetom.
   1. Odaberite entitet sa kojim ćete povezati svoj entitet kontakta. Možete izabrati entitet iz odeljka **Entiteti naloga** ili **Posrednički entitet**. Ako izaberete posrednički entitet, morate definisati drugi odnos da biste se povezali sa entitetom ciljnog naloga.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Izaberite entitet Nalog ili posrednički entitet.":::

   1. Navedite **Naziv odnosa**. Ako odnos između vaših entiteta već postoji, naziv odnosa je samo za čitanje. Ako ne postoji odnos, biće kreiran novi odnos sa nazivom koji navedete.
   1. Izaberite **Primeni** da biste dovršili konfiguraciju odnosa.

   > [!NOTE]
   > Možete da konfigurišete više odnosa između entiteta kontakta i drugih entiteta naloga sa posredničkim entitetima.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Vizuelizacija različitih odnosa povezuje entitete kontakta sa entitetima naloga.":::

1. Izaberite **Sledeće** kada završite sa konfiguracijom odnosa.

1. U koraku **Podesite semantički tip**, izaberite **Semantički tip**. Trenutno postoji jedan **Semantički tip** pod nazivom *ContactProfile*.

1. Mapirajte podatke u *ContactProfile* **Semantički tip** za prikazana polja.
   - Obavezno polje: ID kontakta
   - Opciona polja: ime, prezime, datum rođenja, pol, primarna e-pošta i primarni telefon

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mapirajte atribute svojih podataka o kontaktu sa navedenim obaveznim i opcionim poljima.":::

1. Izaberite **Dalje** za nastavak.

1. U koraku **Pregled**, pogledajte konfiguraciju semantičkog mapiranja. Izaberite **Uredi** da biste uneli izmene u odgovarajući odeljak.

1. Izaberite **Sačuvaj** da biste sačuvali svoje novo **Semantičko mapiranje**.

1. Nakon čuvanja, možete izabrati **Pokreni** da biste obradili semantičko mapiranje ili možete izabrati **Zatvori** da biste sačuvali svoje semantičko mapiranje bez njegove obrade.

1. Da biste kasnije pokrenuli semantičko mapiranje, izaberite semantičko mapiranje i izaberite **Osveži**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Upravljanje postojećim semantičkim mapiranjima

Na **Podaci** > **Semantička mapiranja (verzija za pregled)**, možete pregledati sva sačuvana semantička mapiranja i upravljati njima. Svako semantičko mapiranje predstavljeno je posebnim redom. Naći ćete detalje o izvornom entitetu, semantičkom tipu, tipu mapiranja i njegovom statusu.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opcije za upravljanje semantičkim mapiranjima.":::

- **Uredi**: otvara konfiguraciju podešavanja semantičkog mapiranja u koraku provere. Možete promeniti trenutnu konfiguraciju. Izaberite **Sačuvaj** i **Pokreni** da biste obradili promene.

- **Osveži**: Osvežava izabrano semantičko mapiranje najnovijim podacima iz entiteta koji su deo njegove konfiguracije. Osvežavanje bilo kog datog semantičkog mapiranja osvežiće sva semantička mapiranja istog tipa.

- **Preimenuj**: Otvara dijalog u koji možete uneti drugačije ime za izabrano semantičko mapiranje. Izaberite **Sačuvaj** da primenite promene.

- **Izbriši**: Otvara dijalog za potvrdu brisanja izabranog semantičkog mapiranja. Takođe možete izbrisati više semantičkih mapiranja odjednom odabirom semantičkih mapiranja i ikone za brisanje. Izaberite **Izbriši** da biste potvrdili brisanje.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Korišćenje mapiranja semantičkog entiteta KontaktProfile za kreiranje aktivnosti na nivou kontakta

Nakon kreiranja *mapiranja* semantičkog entiteta ContactProfile, možete da uhvatite aktivnosti kontakata. Omogućava vam da vidite vremensku osu aktivnosti za konto koji je kontakt odgovoran za svaku aktivnost. Većina koraka sledi tipičnu konfiguraciju mapiranja aktivnosti.

   > [!NOTE]
   > Da bi aktivnosti na nivou kontakta uspele, morate imati **ID naloga i** **atribute "ID** kontaktA" za svaki zapis u okviru podataka o aktivnostima.

1. [Definišite *mapiranje* semantičkog entiteta KontaktProfile.](#define-a-contactprofile-semantic-entity-mapping) I pokreni semantičko mapiranje.

1. U uvidima o korisnicima idite na **Podaci** > **Aktivnosti**.

1. Kliknite **na dugme** "Dodaj aktivnost" da biste kreirali novu aktivnost.

1. Imenuj aktivnost, izaberite entitet izvorne aktivnosti i izaberite primarni ključ entiteta aktivnosti.

1. U odnosi **koraku** kreirajte indirektnu relaciju između izvornih podataka aktivnosti sa nalozima, koristeći podatke o kontaktu kao posrednički entitet. Više informacija potražite u [direktnim i indirektnim putanjama relacija](relationships.md#relationship-paths).
   - Primer relacije za aktivnost koja se zove *"Nabavke":*
      - **Podaci o kontaktu izvorne** > **aktivnosti** nabavke na atributu **ID kontakta**
      - **Podaci o** > **nalogu podataka** kontakta na **ID-u naloga atributa**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Primer podešavanja relacija.":::

1. Kada podešavate odnosi, kliknite **na dugme** "Dalje" i dovršite konfiguraciju mapiranja aktivnosti. Detaljne korake kreiranja aktivnosti pogledajte [u članku Definisanje aktivnosti](activities.md).

1. Pokrenite mapiranja aktivnosti.

1. Aktivnosti na nivou kontakta će sada biti vidljive na vremenskoj osi kupca.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Konačni rezultat nakon konfigurisanja aktivnosti kontakta":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtriranje vremenske ose na nivou aktivnosti na nivou kontakta

Nakon konfigurisanja mapiranja aktivnosti na nivou kontakta i njegovog pokretanja, vremenska osa aktivnosti za kupce će biti ažurirana. On uključuje njihove ID-ove ili imena, u zavisnosti od *konfiguracije ContactProfile* datoteke, za aktivnosti na kojima su delovali. Aktivnosti možete filtrirati po kontaktima na vremenskoj osi da biste videli određene kontakte koji vas interesuju. Pored toga, možete da vidite sve aktivnosti koje nisu dodeljene određenom kontaktu tako što ćete **izabrati stavku Aktivnosti koje nisu mapirane kontaktu**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opcije filtriranja dostupne za aktivnosti na nivou kontakta.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
