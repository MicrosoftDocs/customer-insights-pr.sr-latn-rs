---
title: Obogatite profile klijenata podacima iz Microsoft Office 365
description: Koristite vlasničke podatke da biste Microsoft Office obogatili profile klijenata podacima o angažovanju.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 938a9de83fd8f5ff0c9ae815d626cdfa35228aba
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228491"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Obogatite profile klijenata podacima o angažovanju (pregled)

Koristite podatke Microsoft Office 365 iz da biste obogatili profile korisničkog naloga uvidom o angažovanju putem Office 365 aplikacija. Podaci o angažovanju se sastoje od aktivnosti e-pošte i sastanka, koja se prikuplja na nivou naloga. Na primer, broj e-poruka sa poslovnog naloga ili broj sastanaka sa nalogom. Podaci o pojedinačnim korisnicima nisu dostupni. 

Ovo bogaćenje je dostupno u sledećim regionima: Velikoj Britaniji, Evropi, Severnoj Americi.

## <a name="prerequisites"></a>Preduslovi

Da biste konfigurisali bogaćenje, moraju biti ispunjeni sledeći preduslovi:

- Imate aktivnu licencu Office 365 u oblaku.
- Imate objedinjene [profile klijenata](customer-profiles.md) na osnovu poslovnih [naloga](work-with-business-accounts.md).
- Vaše okruženje "Uvidi kupaca" mora imati priloženu [Microsoft Dataverse organizaciju](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Imate [administratorske](permissions.md#administrator) dozvole.
- Imate ili možete da dobijete saglasnost administratora Office 365 stanara da koristite podatke Office 365 da biste obezbedili **uvide za organizaciju** u okviru Dynamics 365 aplikacija.

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. U uvidima o korisnicima idite na **Podaci** > **Obogaćivanje**.

1. Idite na karticu " **Otkrij** " i izaberite stavku Obogati **moje podatke** na pločici **"Angažovanje** naloga".

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Pločica za angažovanje naloga.":::
   
1. U **koraku** pregleda kliknite **na dugme** "Dalje" i unesite e-adrese iz organizacije za koje će podaci sistema Office biti zbirni. Samo podaci sa navedenih e-adresa se obrađuju za relevantnu komunikaciju. Najbolja praksa je da koristite grupe e-pošte, na primer, *tim američke prodaje*, kojima se lako upravlja u Office 365. Broj e-adresa u grupama je rešen i prikazan. Ukupan broj e-adresa mora biti najmanje 2 i ne može da premaši 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="E-adrese za angažovanje naloga.":::

1. Pregledajte izjavu o saglasnosti, potvrdite izbor u polju **za potvrdu** "Slažem se" i kliknite na dugme " **Dalje"**.

1. Izaberite grupu kupaca skup podataka kliknite na dugme **Dalje**.

1. Mapiraj polje e-adrese kontakta i kliknite na dugme **Dalje**.

1. Pregledajte konfiguraciju obogaćivanja, dajte ime bogaćenju i izaberite Sačuvaj bogaćenje **da biste** sačuvali bogaćenje.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 saglasnost administratora stanara

Za aktiviranje bogaćenja Office 365 potrebna je saglasnost administratora stanara. E-poruka se šalje Office 365 administratorima zakupaca kada se obogaćenje sačuva, što od njih traži da pregledaju i pristanu da dozvole Dynamics 365 aplikacijama da Office 365 koriste podatke vaših preduzeća kako bi obezbedili **uvide u organizaciju**. Administrator Office 365 stanara takođe može da pristane direktno u svojoj Office 365 administrativnoj konzoli, tako što će izabrati **opciju "Uvidi za organizaciju"**.

## <a name="running-the-enrichment-for-the-first-time"></a>Pokretanje bogaćenja po prvi put

Kada se obogaćivanje započne po prvi put, nakon što Office 365 administrator stanara da saglasnost, preuzimanje podataka počinje sa početka Office 365. Za ovaj proces je potrebno neko vreme. Planirano je da se prva ogoljenje održi sa zakašnjenjem od šest sati. Po završetku obogaćivanja možete da vidite broj dana koje podaci pokrivaju na stranici za pregled angažovanja naloga. Sa velikim volumenom podataka, ponovo pokrenite obogaćivanje nakon nekoliko dana. Obezbeđuje da podaci budu dovršeni za ceo vremenski prozor, što je godinu dana.

Da biste započeli proces, kliknite na dugme **"Pokreni"** na stranici za konfiguraciju angažovanja naloga. Pored toga, možete dozvoliti sistemu da automatski pokrene obogaćivanje kao deo planiranog [osvežavanja](system.md#schedule-tab). Po podrazumevanoj vrednosti, obogaćivanje se pokreće jednom nedeljno.

U zavisnosti od veličine Office podataka, pokretanje obogaćivanja može potrajati nekoliko sati.

Kada pokrenete bogaćenje, Microsoft će podatke obraditi Office 365 unutar granice usaglašenosti da bi kreirao zbirne uvide koji se zatim dodaju u okruženje "Uvidi kupaca". Nikakvi podaci na pojedinačnom nivou (na primer, telo bilo koje e-pošte ili poziva kalendara) ne postaju dostupni korisnicima korisničkih uvida. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Rezultati obogaćivanja

Nakon pokretanja procesa obogaćivanja, idite na **Moja bogaćenja da** pregledate rezultate obogaćivanja. Videćete ukupan broj obogaćenih kupaca i pregled rezultata obogaćivanja. On uključuje broj obrađenih e-poruka i sastanaka, broj dana za koje su podaci prikupljeni i još mnogo toga.

Takođe ćete vremenom pronaći grafikon sa brojem obogaćenih klijenata i pregledom podataka o obogaćivanju.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Pregled rezultata nakon pokretanja procesa obogaćivanja.":::

Svi podaci se prikupljaju do nivoa naloga. Sistem izračunava rezultat angažovanja, koji se kreće od 0 do 100, za svaki nalog. Rezultat angažovanja obezbeđuje složenu meru angažovanja naloga putem e-pošte i sastanaka u odnosu na druge naloge. Sledeća lista sadrži zbirne podatke koje obogaćivanje angažovanja naloga pruža:



| Podaci                                                                              | Naziv kolone                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Ocena interakcije                                                                  |  EngagementScore                         |
| Broj e-poruka na nalog                                                       |  NoOfEmails_ToAccount                    |
| Broj e-poruka sa naloga                                                     |  NoOfEmails_FromAccount                  | 
| Broj sastanaka započetih nalogom                                           |  NoOfMeetings_FromAccount                | 
| Broj sastanaka koje je inicirala vaša organizacija                                 |  NoOfMeetings_ToAccount                  | 
| Broj osoba iz vaše organizacije na sastancima sa nalogom                  |  NoOfContactsInvolved_Meetings           | 
| Broj osoba iz vaše organizacije u razgovorima putem e-pošte sa nalogom       |  NoOfContactsInvolved_Emails             | 
| Broj osoba sa naloga na sastancima sa vašom organizacijom                  |  NoOfAccountContactsInvolved_Meetings    | 
| Broj osoba sa naloga u razgovorima e-poštom sa vašom organizacijom       |  NoOfAccountContactsInvolved_Emails      | 
| Datum početka angažovanja (prva e-pošta ili sastanak u podacima)                        |  EngagementStartDate                     | 
| Dani od poslednje e-pošte                                                             |  DaysSinceLastEmail                      | 
| Dani od poslednjeg sastanka                                                           |  DaysSinceLastMeeting                    | 
| Prosečno trajanje sastanaka                                                      |  AverageDuration_Of_Meetings             | 
| Prosečno trajanje odgovora na e-poštu sa naloga                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Datum početka agregacije                                                            |  AggregationStartDate                    | 
| Nivo agregacije (godina, mesec ili sedmica)                                          |  AgregationLevel                        | 


Pregledajte obogaćene podatke tako što ćete u odeljku **za pregled izabrati** stavku "Pogledajte više". *Otvara Office* entitet. Entitet naveden u grupi "Obogaćenje" možete pronaći i **u entitetima** **podataka** > **·**. Takođe ćete pronaći Office_UserEntity *ID*-ove aktivnog direktorijuma za e-adrese koje su odabrane tokom konfiguracije obogaćivanja 

## <a name="see-enrichment-data-on-the-customer-card"></a>Pogledajte podatke o obogaćivanju na kartici klijenta

Angažovanje naloga se takođe može videti na pojedinačnim karticama kupaca. Idite na **Klijenti** i izaberite profil klijenta. Na kartici kupca ćete pronaći rezultat angažovanja naloga, ukupan broj e-poruka i ukupan broj sastanaka koji su se sakupljeni tokom prošle godine. Takođe pronalazite grafikone koji prikazuju istoriju e-pošte i sastanka.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kartica klijenta sa obogaćenim podacima.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Kreiranje segmenata i mera na osnovu obogaćenih podataka

Obogaćeni podaci se mogu koristiti za kreiranje segmenata i mera kao što je detaljno opisano u nastavku. Na primer, segment koji sadrži sve kupce koji imaju vrednost preko 60 dana od poslednje *e-pošte i* dana *od poslednjeg sastanka*. Taj segment sadrži ustaljene naloge koje možete pokušati ponovo da aktivirate. 

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
