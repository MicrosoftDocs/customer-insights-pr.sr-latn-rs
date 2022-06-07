---
title: Najčešća pitanja o probnoj verziji usluge Dynamics 365 Customer Insights
description: Rešenja za uobičajena pitanja vezana za podešavanje probne verzije usluge Customer Insights i upravljanje njome. Saznajte kako da rešite probleme specifične za platformu i aplikacije.
author: m-hartmann
ms.author: mhart
ms.date: 02/10/2022
ms.topic: get-started
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: c0db75afdde91bbd60fbece77eb2660a38b84860
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833785"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Najčešća pitanja o probnoj verziji usluge Dynamics 365 Customer Insights

## <a name="sign-up"></a>Registrovanje

### <a name="what-are-the-system-requirements-for-the-trial"></a>Koji su sistemski zahtevi za probnu verziju?

Ova aplikacija je usluga zasnovana u oblaku koja ne zahteva zaseban softver izuzev ažurnog veb-pregledača, iako se primenjuju neka ograničenja. Za najbolje iskustvo probne verzije, izbegavajte pristup probnoj lokaciji u režimu bez arhiviranja i izaberite probnu lokaciju koja vam je najbliža. [Saznajte više o zahtevima za veb-aplikaciju.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Kako da se prijavim za suđenje bez stanara Microsoft 365?

Možete uneti adresu e-pošte koja nije radna, a mi ćemo kreirati nalog i zakupca za vas.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Da li mogu da se registrujem za više Dynamics 365 aplikacija kao što su Sales, Marketing i Customer Service?

Da, možete. Da biste videli sve dostupne probne verzije, [posetite stranicu čvorišta za probne verzije](https://dynamics.microsoft.com/dynamics-365-free-trial). Možete da koristite isti nalog e-pošte da biste se prijavili za različite probne verzije. Međutim, nije moguće imati više aplikacija na istoj probnoj lokaciji. Svaka probna verzija će imati zasebnu organizaciju i URL adresu. Probni podaci neće biti deljeni u svim aplikacijama.

## <a name="trial-app"></a>Probna aplikacija

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Nisam primio/la e-poruku sa detaljima probne verzije nakon prijave, šta da radim?

Kada se registrujete za probnu verziju, dobićete e-poruku sa detaljima probne verzije. Ako ne vidite e-poruku u prijemnom poštanskom sandučetu, proverite fasciklu za bezvrednu poštu. Druga mogućnost je da koristite sledeće korake za pristup aplikaciji:

1. Idite na probnu lokaciju i izaberite **Isprobajte besplatno**.
1. Unesite ID e-pošte koji ste koristili da biste se prijavili za probnu verziju. Bićete preusmereni na probnu aplikaciju.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Kako da dodam više korisnika probnoj verziji?

Da biste dodali korisnike, idite u [Microsoft 365 centar administracije](https://admin.microsoft.com) koristeći probni administratorski nalog. Pratite [smernice za centar administracije](/microsoft-365/admin/add-users/add-users) da biste dodali korisnike u okviru ograničenja probne licence. Ako korisnik kojeg dodajete već ima nalog Microsoft 365, dodelite mu odgovarajuću bezbednosna uloga u probnoj org. Više informacija potražite u članku [Dodeljivanje bezbednosna uloga korisniku](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Koliko korisnika mogu da dodam u probno okruženje?

Probnom okruženju možete dodati neograničen broj korisnika.

### <a name="how-do-i-reset-the-trial-environment"></a>Kako da resetujem probno okruženje?

Ne možete resetovati probno okruženje. Međutim, možete da sačekate da se probni period završi, a zatim da se ponovo prijavite za novu probnu verziju.

## <a name="trial-expiration-and-extension"></a>Istek i produženje probne verzije

### <a name="how-do-i-extend-the-trial"></a>Kako da produžim probnu verziju?

Probni period u aplikaciji možete produžiti direktno. Probni period možete produžiti jednom.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Da li mogu da konvertujem probnu verziju u plaćenu licencu?

Uopšteno, preporučujemo da počnete iznova sa sopstvenim podacima prilikom nadogradnje na plaćenu verziju rešenja Customer Insights. 

Opcionalno, ako koristite samo uvid kupca, možete kopirati podatke iz probnog okruženja ako kupite uvid kupca. Morate biti administrator probne datoteke "Uvidi klijenata" i globalni administrator vašeg zakupca Microsoft 365 ili Dynamics 365 administrator u vašoj organizaciji da biste migrirali postavke iz probnog okruženja u plaćeno okruženje.

Nakon što se prvi put prijavite na svoju plaćenu instancu rešenja Customer Insights od vas će biti zatraženo da kreirate novo okruženje. U ovom procesu možete izabrati da kopirate konfiguraciju iz postojećeg okruženja i da migrirate većinu podešavanja. Ako imate gorenavedene dozvole, probno okruženje će se prikazati na ovoj listi. Još informacija potražite u članku [Kopiranje konfiguracije okruženja](create-environment.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Koja su ograničenja i kvote probne verzije?

- Ne možete da koristite sopstveni Azure Data Lake nalog za skladištenje izlaznih podataka tokom probne verzije programa Customer Insights. Međutim, možete unositi podatke iz Data Lake Storage naloga.
- Možete da uskladištite podatke do 3 GB u Dataverse okruženje koje se automatski obezbeđuje kada pokrenete probnu verziju rešenja Customer Insights.

## <a name="customer-insights-specific-questions"></a>Pitanja specifična za Customer Insights

### <a name="how-do-i-start-using-the-trial"></a>Kako da počnem da koristim probnu verziju?

Kada se registrujete za probnu verziju, stići ćete na glavni ekran aplikacije. Glavni ekran obezbeđuje veze ka korisničkim vodičima i uputstvima. Da biste saznali više, posetite veze u odeljku [Dodatni resursi](trial-signup.md#additional-resources) na stranici za prijavljivanje.

### <a name="what-features-are-available-in-the-trial"></a>Koje funkcije su dostupne u probnoj verziji?

Većina funkcija Customer Insights mogućnosti dostupna je u probnoj verziji.

Sledeće funkcije nisu **dostupne**:

- Ne možete da kreirate nova okruženja koja koriste sopstveni Azure Data Lake Storage nalog.
- Probno okruženje ne možete izbrisati.

### <a name="how-long-does-the-trial-last"></a>Koliko traje probna verzija?

Probna verzija usluge Customer Insights traje 30 dana. Probni period možete produžiti jednom nakon 23 dana kada se prijavite u probno okruženje.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Kako da uklonim probne podatke iz probne verzije?

Ne možete da uklonite probne podatke iz probne verzije.
