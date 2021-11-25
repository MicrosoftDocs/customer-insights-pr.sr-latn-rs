---
title: Semantička mapiranja (verzija za pregled)
description: Pregled semantičkih mapiranja i kako ih koristiti.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: f23c622572ff9f967eca07de7898419d1ffc18b0
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/02/2021
ms.locfileid: "7731960"
---
# <a name="semantic-mappings"></a>Semantička mapiranja

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
