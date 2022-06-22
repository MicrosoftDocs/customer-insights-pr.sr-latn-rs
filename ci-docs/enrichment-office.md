---
title: Obogatite profile klijenata podacima iz Microsoft Office 365
description: Koristite vlasničke podatke da biste Microsoft Office obogatili profile klijenata podacima o angažovanju.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954150"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Obogatite profile klijenata podacima o angažovanju (pregled)

Koristite podatke Microsoft Office 365 iz da biste obogatili profile korisničkog naloga uvidom o angažovanju putem Office 365 aplikacija. Podaci o angažovanju se sastoje od aktivnosti e-pošte i sastanka, koja se prikuplja na nivou naloga. Na primer, broj e-poruka sa poslovnog naloga ili broj sastanaka sa nalogom. Podaci o pojedinačnim korisnicima nisu dostupni.

## <a name="supported-countries-or-regions"></a>Podržane zemlje ili regioni

Trenutno podržavamo sledeće regione: Veliku Britaniju, Evropu, Severnu Ameriku.

## <a name="prerequisites"></a>Preduslovi

- Aktivna licenca Office 365 u oblaku.
- [Objedinjeni profili klijenata](customer-profiles.md) zasnovani na [poslovnim nalozima](work-with-business-accounts.md).
- Organizacija [Microsoft Dataverse priložena u vašem](create-environment.md#step-3-connect-to-microsoft-dataverse) okruženju "Uvidi kupaca".
- [Administratorske](permissions.md#admin) dozvole.
- Saglasnost administratora zakupca Office 365 da koristi podatke Office 365 za obezbeđivanje uvida **za organizaciju u** okviru Dynamics 365 aplikacija.

## <a name="configure-the-enrichment"></a>Konfigurisanje obogaćivanja

1. Idite do kartice **Podaci** > **Obogaćivanje** i izaberite karticu **Otkrij**.

1. Izaberite **stavku Obogati moje podatke** na pločici **"Angažovanje** naloga".

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Pločica za angažovanje naloga.":::

1. Pregledajte pregled, a zatim kliknite na dugme **Dalje**.

1. Unesite e-adrese iz vaše organizacije za koje će podaci sistema Office biti sakupljeni. Samo podaci sa navedenih e-adresa se obrađuju za relevantnu komunikaciju. Najbolja praksa je da koristite grupe e-pošte, na primer, *tim američke prodaje*, u kojem možete da upravljate Office 365. Broj e-adresa u grupama je rešen i prikazan. Ukupan broj e-adresa mora biti najmanje 2 i ne može da premaši 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="E-adrese za angažovanje naloga.":::

1. Pregledajte i obezbedite saglasnost za saglasnost [Office 365 administratora stanara](#office-365-tenant-administrator-consent) izborom **saglasnosti**.

1. Izaberite **Sledeće**.

1. Izaberite grupu **skup podataka i** odaberite profil koji želite da obogatite. Izaberite **Sledeće**.

1. Mapiraj polje e-adrese kontakta i kliknite na dugme **Dalje**.

1. Navedite **ime** za bogaćenje i izlazni **entitet**.

1. Izaberite **Sačuvaj obogaćivanje** nakon pregleda vaših izbora.

1. Kliknite na **dugme "** Zatvori" da biste se vratili na stranicu **"Obogaćenja** ".

### <a name="office-365-tenant-administrator-consent"></a>Office 365 saglasnost administratora stanara

Za aktiviranje bogaćenja Office 365 potrebna je saglasnost administratora stanara. E-poruka se šalje Office 365 administratorima zakupaca kada se obogaćenje sačuva, što od njih traži da pregledaju i pristanu da dozvole Dynamics 365 aplikacijama da Office 365 koriste podatke vaših preduzeća kako bi obezbedili **uvide u organizaciju**. Administrator Office 365 stanara takođe može da pristane direktno u svojoj Office 365 administrativnoj konzoli, tako što će izabrati **opciju "Uvidi za organizaciju"**.

## <a name="running-the-enrichment-for-the-first-time"></a>Pokretanje bogaćenja po prvi put

Kada se obogaćivanje započne po prvi put, nakon što Office 365 administrator stanara da saglasnost, preuzimanje podataka počinje sa početka Office 365. Za ovaj proces je potrebno neko vreme. Planirano je da se prva ogoljenje održi sa zakašnjenjem od šest sati. Po završetku obogaćivanja možete da vidite broj dana koje podaci pokrivaju na stranici za pregled angažovanja naloga. Sa velikim volumenom podataka, ponovo pokrenite obogaćivanje nakon nekoliko dana. On obezbeđuje da podaci budu dovršeni za ceo vremenski prozor, što je godinu dana.

U zavisnosti od veličine Office podataka, pokretanje obogaćivanja može potrajati nekoliko sati.

Kada pokrenete bogaćenje, Microsoft će podatke obraditi Office 365 unutar granice usaglašenosti da bi kreirao zbirne uvide koji se zatim dodaju u okruženje "Uvidi kupaca". Nikakvi podaci na pojedinačnom nivou (na primer, telo bilo koje e-pošte ili poziva kalendara) ne postaju dostupni korisnicima korisničkih uvida.

Kliknite **na dugme** "Pokreni" da biste započeli proces obogaćivanja.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Rezultati obogaćivanja

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Ovo je *Office* entitet. Ovaj *Office_UserEntity ID-ove* aktivnog direktorijuma za e-adrese koje su odabrane tokom konfiguracije obogaćivanja.

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

## <a name="see-enrichment-data-on-the-customer-card"></a>Pogledajte podatke o obogaćivanju na kartici klijenta

Angažovanje naloga se takođe može videti na pojedinačnim karticama kupaca. Idite na **Klijenti** i izaberite profil klijenta. Na kartici kupca ćete pronaći rezultat angažovanja naloga, ukupan broj e-poruka i ukupan broj sastanaka koji su se sakupljeni tokom prošle godine. Takođe pronalazite grafikone koji prikazuju istoriju e-pošte i sastanka.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kartica klijenta sa obogaćenim podacima.":::

## <a name="next-steps"></a>Sledeći koraci

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Na primer, segment koji sadrži sve kupce koji imaju vrednost preko 60 dana od poslednje *e-pošte i* dana *od poslednjeg sastanka*. Taj segment sadrži ustaljene naloge koje možete pokušati ponovo da aktivirate.

[!INCLUDE [footer-include](includes/footer-banner.md)]
