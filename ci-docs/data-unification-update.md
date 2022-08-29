---
title: Ažuriranje postavki ujedinjenja klijenta, naloga ili kontakta
description: Ažurirajte duplirana pravila, pravila podudaranja ili objedinjena polja u postavkama ujedinjenja kupca ili naloga.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: f2c14c169f5973b5f400989b9eeea593eba09182
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304352"
---
# <a name="update-unification-settings"></a>Ažuriranje postavki ujedinjenja

Izvršite sledeće korake da biste pregledali ili promenili postavke ujedinjenja kada se kreira objedinjeni profil.

1. Idite na " **Ujedinjenje** > **podataka"**.

   Za pojedinačne kupce (B-to-C), stranica **"Ujedini** " prikazuje broj objedinjenih profila klijenata i pločica za svaki od koraka ujedinjenja.

   :::image type="content" source="media/m3_unified.png" alt-text="Snimak ekrana stranice &quot;Ujedinjavanje podataka&quot; nakon objedinjenih podataka." lightbox="media/m3_unified.png":::

   Za poslovne naloge (od B do B), stranica **"Ujedini** " prikazuje broj objedinjenih profila naloga i pločica za svaki od koraka ujedinjenja naloga. Ako su kontakti objedinjeni, prikazuje se broj objedinjenih profila kontakata i pločica za svaki od koraka ujedinjenja kontakta. Odaberite odgovarajuću pločicu u okviru **"Ujedini naloge** " ili **"Ujedini kontakte" (pregled)** u zavisnosti od toga šta želite da ažurirate.

   :::image type="content" source="media/b2b_unified.png" alt-text="Snimak ekrana stranice &quot;Ujedinjenje podataka&quot; nakon objedinjenih podataka naloga i kontakata." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > Pločica **"Podudarni** uslovi" prikazuje se samo ako je izabrano više entiteta.

1. Odaberite šta želite da ažurirate:
   - [Izvorna polja](#edit-source-fields) za dodavanje entiteta ili atributa ili menjanje tipova atributa.
   - [Duplirani zapisi](#manage-deduplication-rules) za upravljanje pravilima deduplikacije ili željenim opcijama objedinjavanja.
   - [Podudarni](#manage-match-rules) uslovi za ažuriranje pravila podudaranja u dva ili više entiteta.
   - [Objedinjena polja kupaca](#manage-unified-fields) za kombinovanje ili isključivanje polja. Povezane profile možete grupišeti i u klastere.
   - [Semantička polja za upravljanje](#manage-semantic-fields-for-unified-contacts) semantičkim tipovima za objedinjena polja kontakata.
   - [odnosi da](#manage-contact-and-account-relationships) biste upravljali kontaktom do relacije naloga.

1. Nakon što izvršite promene, odaberite sledeću opciju:

   - [Pokrenite uslove](#run-matching-conditions) podudaranja da biste brzo procenili kvalitet uslova podudaranja (pravila deduplikacije i podudaranja) bez ažuriranja objedinjenog profila. Opcija **"Pokreni uslove podudaranja** " nije prikazana samo za jedan entitet.
   - [Ujedinite profile da biste](#run-updates-to-the-unified-profile) pokrenuli uslove podudaranja i ažurirali objedinjeni entitet profila bez uticaja na zavisnosti (kao što su obogaćivanje, segmenti ili mere). Zavisni procesi se ne pokreću, ali će biti osveženi kao što je definisano [u rasporedu osvežavanja](schedule-refresh.md).
   - [Ujedinite profile i zavisnosti da biste pokrenuli](#run-updates-to-the-unified-profile) uslove podudaranja, ažurirali objedinjeni entitet profila i ažurirali sve zavisnosti (kao što su obogaćivanje, segmenti ili mere). Svi procesi se automatski ponovo ponište. U programu B-to-B, ujedinjenje se vodi i na konto i na entitetima kontakata koji ažuriraju objedinjene profile.

## <a name="edit-source-fields"></a>Uređivanje izvornih polja

Ne možete ukloniti atribut ili entitet ako su već objedinjeni.

1. Na **pločici** "Izvorna **polja" izaberite stavku** "Uredi".

   :::image type="content" source="media/m3_source_edit.png" alt-text="Snimak ekrana stranice izvornih polja koja prikazuje broj primarnih ključeva, mapiranih i nemaskidiranih polja":::

   Prikazan je broj mapiranih i nemasapisanih polja.

1. Izaberite entitete i polja da biste dodali druge **atribute ili entitete**.

1. Opcionalno, možete da promenite primarni ključ za entitet, tipove atributa i **da prebacite inteligentno mapiranje na** ili van njega. Više informacija potražite u članku [Izbor izvornih polja](map-entities.md).

1. Kliknite **na dugme** "Dalje" da biste napravili promene u pravilima deduplikacije ili izaberite **stavku Sačuvaj i zatvori i** vrati se na Ažuriranje [postavki ujedinjenja](#update-unification-settings).

## <a name="manage-deduplication-rules"></a>Upravljanje pravilima deduplikacije

1. Na **pločici** "Duplirani **zapisi" izaberite stavku** "Uredi".

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Snimak ekrana stranice &quot;Duplirani zapisi&quot; koji prikazuje broj dupliranih zapisa" lightbox="media/m3_duplicates_edit.png":::

   Broj pronađenih dupliranih zapisa prikazuje se u okviru "Duplikati **"**. Kolona **"Zapisi deduplicated** " prikazuje koji entiteti su imali duplirane zapise i procenat dupliranih zapisa.

1. Da biste koristili obogaćeni entitet, izaberite opciju **Korišćenje obogaćenih entiteta**. Više informacija potražite u članku [Obogaćivanje izvora podataka](data-sources-enrichment.md).

1. Da biste upravljali pravilima deduplikacije, odaberite neku od sledećih opcija:
   - **Kreirajte novo pravilo**: Izaberite **dodaj pravilo** pod odgovarajućim entitetom. Više informacija potražite u članku [Definisanje pravila deduplikacije](remove-duplicates.md#define-deduplication-rules).
   - **Promenite uslove pravila**: Izaberite pravilo, a zatim **uredite**. Promenite polja, dodajte ili uklonite uslove ili dodajte ili uklonite izuzetke.
   - **Pregled**: Izaberite pravilo, a zatim pregledaj **da** biste prikazali rezultate poslednjeg pokretanje za ovo pravilo.
   - **Deaktivirajte pravilo: Izaberite** pravilo **, a zatim deaktivirajte da biste** zadržali pravilo deduplikacije dok ga isključujete iz procesa podudaranja.
   - **Dupliraj pravilo: Izaberite** pravilo, a zatim dupliraj **da** biste kreirali slično pravilo sa izmenama.
   - **Izbrišite pravilo**: Izaberite pravilo, a zatim **izbrišite**.

1. Izaberite entitet da biste promenili željene postavke objedinjavanja. Željene postavke možete da promenite samo ako je pravilo kreirano.
   1. Izaberite **uredi željene opcije objedinjavanja** i promenite opciju **"Zapis" da biste zadržali** opciju.
   1. Da biste promenili željene postavke objedinjavanja na pojedinačnim atributima entiteta, izaberite opciju **Više opcija** i izvršite neophodne promene.

   1. Izaberite **Gotovo**.

1. Kliknite **na dugme** "Dalje" da biste napravili promene uslova podudaranja ili izaberite stavku **Sačuvaj i zatvori** i vrati se na [Postavke ujedinjenja ažuriranja](#update-unification-settings).

## <a name="manage-match-rules"></a>Upravljanje pravilima za podudaranje

Možete da konfigurišete i fino podesite većinu parametara podudaranja. Entitete ne možete da dodajete ili brišete. Pravila podudaranja se ne primenjuju na jedan entitet.

1. Na pločici **"** Podudarni **uslovi" izaberite stavku** "Uredi".

   :::image type="content" source="media/m3_match_edit.png" alt-text="Snimak ekrana stranice &quot;Podudaranje pravila i uslova&quot; sa statistikom." lightbox="media/m3_match_edit.png":::

   Stranica prikazuje redosled podudaranja i definisana pravila i sledeću statistiku:
   - **Jedinstveni zapisi izvora** prikazuju broj pojedinačnih izvornih zapisa koji su obrađeni u poslednjem pokretanjem meča.
   - **Podupreni i neuklonjeni** zapisi naglašavaju koliko je jedinstvenih zapisa ostalo nakon obrade pravila podudaranja.
   - **Upareni zapisi** prikazuju samo broj podudaranja u svim parovima podudaranja.

1. Da biste prikazali rezultate svih pravila i njihove rezultate, izaberite stavku Prikaži **poslednje pokretanje**. Rezultati se prikazuju, uključujući ID-ove alternativnih kontakata. Rezultate možete preuzeti.

1. Da biste prikazali rezultate i rezultate određenog pravila, izaberite pravilo, a zatim **pregled**. Rezultati se prikazuju. Rezultate možete preuzeti.

1. Da biste prikazali rezultate određenog uslova na pravilu, izaberite pravilo, a zatim **uredite**. U oknu "Uređivanje" izaberite **stavku** Pregled pod uslovom. Rezultate možete preuzeti.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafički prikaz nenadmašnih i podudarnih zapisa, uključujući listu podataka.":::

1. Ako ste dodali obogaćeni entitet, izaberite opciju Korišćenje **obogaćenih entiteta**. Više informacija potražite u članku [Obogaćivanje izvora podataka](data-sources-enrichment.md).

1. Da biste upravljali pravilima, odaberite neku od sledećih opcija:
   - **Kreirajte novo pravilo**: Izaberite **dodaj pravilo** pod odgovarajućim entitetom. Više informacija potražite u članku [Definisanje pravila za parove podudaranja](match-entities.md#define-rules-for-match-pairs).
   - **Promenite redosled pravila ako ste** definisali više pravila: Prevucite i otpustite pravila u redosled koji želite. Više informacija potražite u članku [Preciziranje redosleda podudaranja](match-entities.md#specify-the-match-order).
   - **Promenite uslove pravila**: Izaberite pravilo, a zatim **uredite**. Promenite polja, dodajte ili uklonite uslove ili dodajte ili uklonite izuzetke.
   - **Deaktivirajte pravilo: Izaberite** pravilo **, a zatim deaktivirajte da biste zadržali** pravilo podudaranja dok ga isključujete iz procesa podudaranja.
   - **Dupliraj pravilo: Izaberite** pravilo, a zatim dupliraj **da** biste kreirali slično pravilo sa izmenama.
   - **Izbrišite pravilo**: Izaberite pravilo, a zatim **izbrišite**.

1. Kliknite **na dugme "** Dalje" da biste napravili promene u objedinjenim poljima ili izaberite **stavku Sačuvaj i zatvori** i vrati se [na Ažuriranje postavki ujedinjenja](#update-unification-settings).

## <a name="manage-unified-fields"></a>Upravljanje objedinjenim poljima

1. Na pločici **"** Objedinjena **polja kupca" izaberite** stavku "Uredi".

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Snimak ekrana objedinjenih polja kupaca":::

1. Pregledajte kombinovana i isključena polja i izvršite sve promene po potrebi. Dodajte ili uredite ID klijenta ili grupne profile u klastere. Više informacija potražite u članku [Objedinjavanje polja kupaca](merge-entities.md).

1. Za kupce ili naloge kliknite na dugme **"Dalje** " da biste pregledali [i ažurirali objedinjeni profil i zavisnosti](#run-updates-to-the-unified-profile). Ili izaberite sačuvaj **i zatvori i** vratite se na postavke [ujedinjenja ažuriranja da](#update-unification-settings) biste napravili još promena.

   Za kontakte izaberite opciju Dalje **za** upravljanje semantičkim poljima. Ili izaberite sačuvaj **i zatvori i** vratite se na postavke [ujedinjenja ažuriranja da](#update-unification-settings) biste napravili još promena.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Upravljanje semantičkim poljima za objedinjene kontakte

1. Na **pločici** " **Semantička polja" izaberite stavku** "Uređivanje".

1. Izaberite novi tip da biste promenili semantički tip za objedinjeno polje. Više informacija potražite u članku [Definisanje semantičkih polja za objedinjene kontakte](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Kliknite **na dugme** "Dalje" da biste upravljali odnosom između naloga i kontakata **ili izaberite stavku Sačuvaj i zatvori i** vrati se [na Ažuriranje postavki ujedinjenja](#update-unification-settings) da biste napravili još promena.

## <a name="manage-contact-and-account-relationships"></a>Upravljanje kontaktom i kontakt odnosi

1. Na **pločici** "**odnosi" izaberite stavku** "Uređivanje".

1. Da biste promenili odnos kontakta i naloga, promenite neku od sledećih informacija:

   - **Strani ključ iz entiteta kontakta**: Odaberite atribut koji povezuje entitet kontakta sa nalogom.
   - **Da biste nalogili** entitet: Odaberite entitet naloga povezan sa kontaktom.

1. Kliknite **na dugme** "Dalje" da biste pregledali postavke ujedinjenja [i ažurirali objedinjeni](#run-updates-to-the-unified-profile) profil i zavisnosti ili izaberite **stavku Sačuvaj i zatvori i**[vrati se na Ažuriranje postavki ujedinjenja](#update-unification-settings) da biste napravili još promena.

## <a name="run-matching-conditions"></a>Pokretanje uslova podudaranja

Uslovi podudaranja pokreću deduplication i podudaraju se samo sa pravilima i *ažuriraju Deduplication_** *i ConflationMatchPair* entitete.

1. Sa stranice "Ujedinjenje **podataka** > **" izaberite opciju Pokreni** samo uslove podudaranja **.**

   Duplikati **zapisa i** pločice **uslova podudaranja** prikazuju status " **Red čekanja"** ili " **Osvežavanje** ".

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Kada se proces podudaranja dovrši, na pločici " **Podudarni** uslovi" izaberite **stavku "** Uredi".

   :::image type="content" source="media/match-KPIs.png" alt-text="Izrezani snimak ekrana ključnih metrika na stranici Podudaranje sa brojevima i detaljima.":::

1. Da biste napravili promene, pogledajte [članak Upravljanje pravilima deduplikacije ili](#manage-deduplication-rules) Upravljanje [pravilima podudaranja](#manage-match-rules).

1. Ponovo pokrenite proces podudaranja ili [pokrenite ispravke profila](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Pokretanje ispravki objedinjenog profila

- Da biste pokrenuli uslove podudaranja i ažurirali objedinjeni entitet profila bez uticaja na zavisnosti (kao što su kartice *kupaca*, obogaćivanja, segmenti ili mere), **izaberite Opciju Ujedini profile klijenata**. Za naloge izaberite Opciju **Ujedini naloge** > **Ujedini profile**. Za kontakte izaberite Opciju **Ujedini kontakte (pregled)** > **Ujedini profile**. Zavisni procesi se ne pokreću, ali će biti osveženi kao što je definisano [u rasporedu osvežavanja](schedule-refresh.md).
- Da biste pokrenuli uslove podudaranja, ažurirajte objedinjeni profil i pokrenite sve zavisnosti, izaberite **Opciju Ujedini profile i zavisnosti klijenata**. Svi procesi se automatski ponovo ponište. Za naloge i kontakte izaberite **opciju Ujedini naloge** > **Ujedini profile i zavisnosti**. Uslovi podudaranja se pokreću i za naloge i za kontakte koji ažuriraju objedinjene profile i sve druge zavisnosti.

Sve pločice osim polja izvora **prikazuju polje "** Red **čekanja" ili "** Osvežavanje **"**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Rezultati uspešnog prikazivanja na stranici "Ujedini **"** prikazuju broj objedinjenih profila.
