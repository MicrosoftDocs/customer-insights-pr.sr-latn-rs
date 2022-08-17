---
title: Pregled veza (verzija za pregled)
description: Veze sa ostalim uslugama iz usluge Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245528"
---
# <a name="connections-preview-overview"></a>Pregled veza (verzija za pregled)

Veze su ključ za omogućavanje deljenja podataka u uslugu Customer Insights i iz nje. Svaka veza uspostavlja deljenje podataka sa određenom uslugom. Koristite veze za konfigurisanje [obogaćivanja nezavisnih proizvođača](enrichment-hub.md) i [konfigurisanje izvoza](export-destinations.md). Ista veza se može koristiti više puta. Na primer, jedna veza sa uslugom Dynamics 365 Marketing funkcioniše za više izvoza, a jedna Leadspace veza može se koristiti za nekoliko obogaćivanja.

## <a name="export-connections"></a>Izvezi veze

Samo administratori mogu da konfigurišu nove veze, ali mogu da [odole saradnicima](#allow-contributors-to-use-a-connection-for-exports) da koriste postojeće veze. Administratori kontrolišu kuda podaci mogu da idu, saradnici definišu korisne podatke i učestalost u skladu sa svojim potrebama.

## <a name="enrichment-connections"></a>Veze sa obogaćivanjem

Samo administratori mogu da konfigurišu nove veze, ali kreirane veze su uvek dostupne i administratorima i saradnicima. Administratori upravljaju akreditivima i daju saglasnost za prenos podataka. Veze tada mogu da koriste administratori i saradnici za obogaćivanja.

## <a name="add-a-new-connection"></a>Dodavanje nove veze

### <a name="prerequisites"></a>Preduslovi

- [Dozvole administratora](permissions.md)
- Druge Microsoft usluge, ako postoje, su u istoj organizaciji

1. Idite na **Administrator** > **Veze**.

1. Izaberite **dodaj vezu** i odaberite tip veze koji želite da kreirate. Ili idite na karticu " **Otkrivanje** " i izaberite **stavku "Podesi** " na pločici veze.

1. Dajte vezi prepoznatljivo ime u polju **Ime za prikaz**. Ime za prikaz i vrsta veze opisuju ovu vezu. Preporučujemo da odaberete naziv koji objašnjava svrhu i cilj veze.

1. Unesite potrebne detalje. Tačna polja zavise od servisa sa kojima se povezujete. Za detalje određenog tipa veze pogledajte članak o ciljnoj usluzi.

1. Ako [koristite sopstveni Key Vault](use-azure-key-vault.md) za čuvanje tajni, aktivirajte **Koristi Key Vault** i izaberite tajnu sa liste.

1. Pregledajte privatnost i usaglašenost podataka i izaberite I **slažem se**.

1. Kliknite na **dugme** Sačuvaj da biste kreirali vezu.

### <a name="data-privacy-and-compliance"></a>Privatnost podataka i usaglašenost

Kada omogućite prenos Dynamics 365 Customer Insights podataka trećim licima ili drugim Microsoft proizvodima, dozvoljavate prenos podataka izvan granice usaglašenosti Dynamics 365 Customer Insights za, uključujući potencijalno osetljive podatke kao što su lični podaci. Microsoft će preneti takve podatke po vašem uputstvu, ali vi ste odgovorni da osigurate da treće strane ispunjava sve obaveze privatnosti ili bezbednosti koje možda imate. Za više informacija pogledajte [Izjavu o privatnosti kompanije Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights može da ukloni vezu u bilo kom trenutku da bi prekinuti korišćenje funkcionalnosti.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Dozvolite saradnicima da koriste vezu za izvoz

Prilikom podešavanja ili uređivanja izvozne veze odaberite koji korisnici smeju da koriste ovu određenu vezu za definisanje [izvoza](export-destinations.md). Po podrazumevanoj vrednosti, veza je dostupna korisnicima sa ulogom administratora. Promenite postavku **"Odaberi ko može da koristi ovu** vezu" da biste korisnicima sa saradnik da koriste ovu vezu.

- Saradnici neće moći da vide ili izmene vezu. Oni će videti samo ime za prikaz i njegov tip prilikom kreiranja izvoza.
- Deljenjem veze omogućavate saradnicima da je koriste. Saradnici će videti zajedničke veze kada uspostave izvoz. Oni mogu upravljati svakim izvozom koji koristi ovu specifičnu vezu.
- Možete da promenite ovo podešavanje, a da zadržite izvoz koji su već definisali saradnici.

## <a name="manage-existing-connections"></a>Upravljanje postojećim vezama

1. Idite na **Administrator** > **Veze**.

1. Izaberite karticu **"** Obogaćivanje **·**" ili "Izvoz" da biste prikazali listu veza za obogaćivanje ili izvoz, tip veze, vreme kreiranja i ko ima pristup. Listu veza možete da sortirate po bilo kojoj koloni.

1. Izaberite vezu da biste prikazali dostupne radnje.

   - **Uredite** vezu.
   - [**Uklonite**](#remove-a-connection) vezu.

### <a name="remove-a-connection"></a>Uklanjanje veze

Ako vezu koju uklanjate koriste obogaćivanja ili izvoz, prvo ih odvojite ili uklonite. Uklanjanje dijaloga vodi vas do relevantnih obogaćivanja ili izvoza.

> [!TIP]
> Deaktivirana obogaćivanja i odvojeni izvoz postaju neaktivni. Ponovo ih aktivirate dodavanjem druge veze sa njima na stranici [Obogaćivanja](enrichment-hub.md) ili [Izvozi](export-destinations.md).

1. Idite na **Administrator** > **Veze**.

1. Izaberite karticu **Obogaćivanje** **ili** izvoz.

1. Izaberite vezu koju želite da uklonite.

1. Izaberite **Ukloni** iz padajućeg menija. Prikazuje se dijalog za potvrdu.

   1. Ako postoje obogaćivanja ili izvozi koji koriste ovu vezu, izaberite dugme da biste videli šta koristi vezu.
      - **Izvoz: Odaberite** da uklonite **izvoz** ili da **odvojite vezu**. Odvajanje veze zadržava izvozni konfig, ali neće biti pokrenuti dok joj se ne doda druga veza.
      - **Obogaćivanje:** Odaberite da **izbrišete** **ili deaktivite** obogaćivanje.
   1. Kada veza nema više zavisnosti, vratite se na **Administrator** > **Veze** i pokušajte ponovo da uklonite vezu.

1. Da biste potvrdili brisanje, izaberite **Ukloni**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Uspostavljanje veza sa tajnama kojima upravlja vaš Key Vault

Nekim vezama su potrebne tajne, poput API ključeva ili lozinki. Neke veze podržavaju tajne sačuvane u vašem Key Vaultu. Saznajte više o podržanim vezama i kako da se podesite na sopstvenom [ključnom trezoru za uvide klijenata](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
