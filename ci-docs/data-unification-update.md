---
title: Ažuriranje postavki ujedinjenja
description: Ažurirajte duplirana pravila, podudaranje pravila ili objedinjena polja u postavkama ujedinjenja.
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: be399da9b98d8803d7d1a90f44a40e0d638a8d47
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755607"
---
# <a name="update-the-unification-settings"></a>Ažuriranje postavki ujedinjenja

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Izvršite sledeće korake da biste pregledali ili promenili postavke ujedinjenja kada se kreira objedinjeni profil.

1. Idite na " **Ujedinjenje** > **podataka"**.

   :::image type="content" source="media/m3_unified.png" alt-text="Snimak ekrana stranice &quot;Ujedinjavanje podataka&quot; nakon objedinjenih podataka.":::

   > [!TIP]
   > Pločica **"Podudarni** uslovi" prikazuje se samo ako je izabrano više entiteta.

1. Odaberite šta želite da ažurirate:
   - [Izvorna polja](#edit-source-fields) za dodavanje entiteta ili atributa ili menjanje tipova atributa.
   - [Duplirani zapisi](#manage-deduplication-rules) za upravljanje pravilima deduplikacije ili željenim opcijama objedinjavanja.
   - [Podudarni](#manage-match-rules) uslovi za ažuriranje pravila podudaranja u dva ili više entiteta.
   - [Objedinjena polja kupaca](#manage-unified-fields) za kombinovanje ili isključivanje polja. Povezane profile možete grupišeti i u klastere.

1. Nakon što izvršite promene, odaberite sledeću opciju:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Snimak ekrana stranice &quot;Ujedinjavanje podataka&quot; sa istaknutim opcijama &quot;Ujedini&quot;.":::

   - Da biste ažurirali objedinjeni korisnički profil (sa ili bez zavisnosti), pogledajte [članak Pokretanje ispravki profila klijenta](#run-updates-to-the-unified-customer-profile).
   - Da biste procenili kvalitet podudarnih uslova bez ažuriranja objedinjenog profila, pogledajte članak Pokreni [uslove podudaranja](#run-matching-conditions). Opcija **"Pokreni uslove podudaranja** " nije prikazana samo za jedan entitet.

## <a name="edit-source-fields"></a>Uređivanje izvornih polja

Ne možete ukloniti atribut ili entitet ako su već objedinjeni.

1. Na **pločici** "Izvorna **polja" izaberite stavku** "Uredi".

   :::image type="content" source="media/m3_source_edit.png" alt-text="Snimak ekrana stranice izvornih polja koja prikazuje broj primarnih ključeva, mapiranih i nemaskidiranih polja":::

   Prikazan je broj mapiranih i nemasapisanih polja.

1. Izaberite **izaberite entitete i polja** da biste dodali druge atribute ili entitete. Koristite pretragu ili listajte da biste pronašli i izabrali svoje atribute i entitete od interesa. Izaberite **Primeni**.

1. Opcionalno, možete da promenite primarni ključ za entitet, tipove atributa i **da prebacite inteligentno mapiranje na** ili van njega. Više informacija potražite u članku [Izbor primarnog ključa i semantičkog tipa za atribute](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Kliknite **na dugme** "Dalje" da biste napravili promene u pravilima deduplikacije ili izaberite **stavku Sačuvaj i zatvori** i vrati se [da biste ažurirali postavke ujedinjenja](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Upravljanje pravilima deduplikacije

1. Na **pločici** "Duplirani **zapisi" izaberite stavku** "Uredi".

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Snimak ekrana stranice &quot;Duplirani zapisi&quot; koji prikazuje broj dupliranih zapisa" lightbox="media/m3_duplicates_edit.png":::

   Broj pronađenih dupliranih zapisa prikazuje se u okviru "Duplikati **"**. Kolona **"Zapisi deduplicated** " prikazuje koji entiteti su imali duplirane zapise i procenat dupliranih zapisa.

1. Ako ste dodali obogaćeni entitet, izaberite opciju Korišćenje **obogaćenih entiteta**. Više informacija potražite u članku [Obogaćivanje izvora podataka](data-sources-enrichment.md).

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

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Snimak ekrana naprednih željenih opcija za objedinjavanje koji prikazuje najnoviju e-poštu i najdovršnju adresu":::

   1. Izaberite **Gotovo**.

1. Kliknite **na dugme** "Dalje" da biste napravili promene uslova podudaranja ili izaberite **stavku Sačuvaj i zatvori** i vrati se [da biste ažurirali postavke ujedinjenja](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Upravljanje pravilima za podudaranje

Možete da konfigurišete i fino podesite većinu parametara podudaranja. Entitete ne možete da dodajete ili brišete. Pravila podudaranja se ne primenjuju na jedan entitet.

1. Na pločici **"** Podudarni **uslovi" izaberite stavku** "Uredi".

   :::image type="content" source="media/m3_match_edit.png" alt-text="Snimak ekrana stranice &quot;Podudaranje pravila i uslova&quot; sa statistikom." lightbox="media/m3_match_edit.png":::

   Stranica prikazuje redosled podudaranja i definisana pravila i sledeću statistiku:
   - **Jedinstveni izvorni zapisi** pokazuje broj pojedinačnih izvornih zapisa koji su obrađeni u poslednjem pokretanju podudaranja.
   - **Podudarni i nepodudarni zapisi** ističe koliko jedinstvenih zapisa ostaje nakon obrade pravila podudaranja.
   - **Samo odgovarajući zapisi** pokazuje broj podudaranja u svim vašim parovima podudaranja.

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

1. Kliknite **na dugme** "Dalje" da biste napravili promene u objedinjenim poljima ili izaberite **stavku Sačuvaj i** zatvori i vratite [se da biste ažurirali postavke ujedinjenja](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Upravljanje objedinjenim poljima

1. Na pločici **"** Objedinjena **polja kupca" izaberite** stavku "Uredi".

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Snimak ekrana objedinjenih polja kupaca":::

1. Pregledajte kombinovana i isključena polja i izvršite sve promene po potrebi. Dodajte ili uredite ID klijenta ili grupne profile u klastere. Više informacija potražite u članku [Objedinjavanje polja kupaca](merge-entities.md).

1. Kliknite **na dugme** "Dalje" da biste pregledali postavke ujedinjenja [i ažurirali objedinjeni profil i zavisnosti](#run-updates-to-the-unified-customer-profile) ili izaberite **stavku Sačuvaj i zatvori i**[vrati se na Ažuriranje postavki ujedinjenja](#update-the-unification-settings) da biste napravili još promena.

## <a name="run-matching-conditions"></a>Pokretanje uslova podudaranja

1. Sa stranice "Ujedinjenje **podataka** > **" izaberite opciju Pokreni** samo uslove podudaranja **.**

   Duplikati zapisa i pločica **uslova podudaranja** prikazuju red **ili osvežavanje** **·**.**·**

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

1. Kada se proces podudaranja dovrši, na pločici " **Podudarni** uslovi" izaberite **stavku "** Uredi".

   :::image type="content" source="media/match-KPIs.png" alt-text="Izrezani snimak ekrana ključnih metrika na stranici Podudaranje sa brojevima i detaljima.":::

1. Da biste napravili promene, pogledajte [članak Upravljanje pravilima deduplikacije ili](#manage-deduplication-rules) Upravljanje [pravilima podudaranja](#manage-match-rules).

1. Ponovo pokrenite proces podudaranja ili [pokrenite ispravke profila klijenta](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Pokretanje ispravki za objedinjeni profil korisnika

1. Sa stranice **"** > **Ujedinjenje podataka** " izaberite:

   - **Ujedinite profile klijenata**: Ažurira objedinjeni entitet profila klijenata bez uticaja na zavisnosti (kao što su obogaćivanja, segmenti ili mere). Zavisni procesi se ne pokreću, ali će biti osveženi kao što je definisano [u rasporedu osvežavanja](system.md#schedule-tab).

   - **Ujedinite profile i zavisnosti klijenata**: Ažurira objedinjeni profil i sve zavisnosti. Svi procesi se automatski ponovo ponište. Kada se svi nizvodni procesi završe, profil kupca odražava ažurirane podatke.

   Duplikati **zapisa, podudarnih** uslova **i objedinjene** pločice polja kupaca **prikazuju redosled** ili **osvežavanje** **.**

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]
