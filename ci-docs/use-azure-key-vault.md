---
title: Donesite svoj vlastiti Azure Key Vault (verzija za pregled)
description: Saznajte kako da konfigurišete uvide klijenata da koriste sopstveni Azure ključni trezor za upravljanje tajnama.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246172"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Donesite svoj vlastiti Azure Key Vault (verzija za pregled)

Povezivanje namenskog Azure [ključa trezora sa okruženjem](/azure/key-vault/general/basic-concepts) uvida klijenata pomaže organizacijama da ispune uslove usaglašenosti.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Povezivanje ključnog trezora sa okruženjem uvida kupaca

Podesite namenski ključni trezor da organizuje i koristi tajne na granici usaglašenosti organizacije.

### <a name="prerequisites"></a>Preduslovi

- Aktivna pretplata na uslugu Azure.

- Uloga [administratora](permissions.md#admin) dodeljena [u uvidima](permissions.md#add-users) klijenata.

- [saradnik administratora](/azure/role-based-access-control/built-in-roles#contributor)[i administratora](/azure/role-based-access-control/built-in-roles#user-access-administrator) korisničkog pristupa na ključnom trezoru ili grupi resursa kojoj pripada ključni trezor. Za još informacija idite na [Dodavanje ili uklanjanje Azure dodela uloga koristeći Azure portal](/azure/role-based-access-control/role-assignments-portal). Ako nemate ulogu administratora korisničkog pristupa u trezoru ključa, posebno podesite dozvole za kontrolu pristupa zasnovane na ulozi za direktora Azure Dynamics 365 Customer Insights usluge. Pratite korake da biste [koristili principala usluge Azure](connect-service-principal.md) za bezbednosno skladište koje treba povezati.

- Ključ mora da ima onemogućen zaštitni zid ključnog **trezora**.

- Ključni trezor je na istoj [Azure lokaciji kao](https://azure.microsoft.com/global-infrastructure/geographies/#overview) i okruženje "Uvidi kupaca". U opciji "Uvidi klijenata" idite na karticu **"Admin** > **sistem**" i na **karticu** "Osnovni podaci" da biste prikazali region okruženja.

### <a name="recommendations"></a>Preporuke

- [Koristite poseban ili namenski trezor ključa](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) koji sadrži samo tajne potrebne za uvide klijenata.

- Pratite [najbolje prakse za korišćenje bezbednosnih skladišta](/azure/key-vault/general/best-practices#turn-on-logging) za opcije kontrole pristupa, pravljenja rezervnih kopija, revizije i oporavka.

### <a name="link-a-key-vault-to-the-environment"></a>Povezivanje bezbednosnog skladišta sa okruženjem

1. Idite na **administratorsko** > **obezbeđenje**, a zatim izaberite karticu **"Trezor ključa**".
1. Na pločici **Bezbednosno skladište**, izaberite **Podešavanje**.
1. Odaberite **pretplatu**.
1. Odaberite bezbednosno skladište sa padajuće liste **Bezbednosno skladište**. Ako je dostupno previše ključnih trezora, izaberite grupu resursa da biste ograničili rezultate pretrage.
1. Pregledajte [Privatnost podataka i usklađenost](connections.md#data-privacy-and-compliance) i izaberite **Slažem se**.
1. Izaberite **Sačuvaj**.

Pločica **"Ključni** trezor" prikazuje ime povezanog ključa trezora, pretplatu i grupu resursa. Spreman je za korišćenje u podešavanju veze.
Za detalje o tome koje dozvole za ključni trezor se dodeljuju uvidima klijenata pogledajte [dozvole dodeljene u ključnom trezoru](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Korišćenje bezbednosnog skladišta u podešavanju veze

Kada [podešavate veze](connections.md) sa [podržanim sistemima nezavisnih proizvođača](#supported-connection-types), koristite tajne iz povezanog trezora ključa da biste konfigurisali veze.

1. Idite na **Administrator** > **Veze**.
1. Izaberite **Dodaj vezu**.
1. Za podržane tipove veza, prekidač za **Koristite bezbednosno skladište** je dostupan ako ste povezali bezbednosno skladište.
1. Umesto ručnog unošenja tajne, odaberite tajno ime koje ukazuje na tajnu vrednost u ključnom trezoru.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Okno za povezivanje sa SFTP vezom koja koristi tajnu bezbednosnog skladišta.":::

1. Kliknite na **dugme** Sačuvaj da biste kreirali vezu.

## <a name="supported-connection-types"></a>Podržani tipovi veza

Sledeće veze za [izvoz](export-destinations.md) su podržane:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google oglasi](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Odobrene dozvole za ključni trezor

Sledeće dozvole se dodeljuju programu Customer Insights u povezanom trezoru ako je omogućena [smernica za pristup](/azure/key-vault/general/assign-access-policy?tabs=azure-portal)[ključnom trezoru ili Azure kontrole](/azure/key-vault/general/rbac-guide?tabs=azure-cli) pristupa zasnovane na ulozi.

### <a name="key-vault-access-policy"></a>Politika pristupa za Key Vault

| Tip        | Dozvole          |
| ----------- | -------------------- |
| Taster         | [Pribavite ključeve](/rest/api/keyvault/keys/get-keys/get-keys), [Pribavite ključ](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Tajni      | [Pribavite tajne](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Pribavite tajnu](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Certifikat | [Pribavite certifikate](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Pribavite certifikat](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Prethodne vrednosti su minimum za navođenje i čitanje tokom izvršavanja.

### <a name="azure-role-based-access-control"></a>Azure kontrola pristupa zasnovana na ulogama

Ključne [uloge čitalac i ključne trezor tajne](/azure/key-vault/general/rbac-guide?tabs=azure-cli) biće dodate za uvide klijenata.

## <a name="frequently-asked-questions"></a>Najčešća pitanja

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Da li "Uvidi kupaca" mogu da napišu tajne ili da preprave tajne u ključni trezor?

Ne. Samo dozvole za čitanje i liste navedene u odobrenim [dozvolama dodeljuje](#permissions-granted-on-the-key-vault) se uvidima klijenata. Sistem ne može da dodaje, briše ili zamenjuje tajne u bezbednosnom skladištu. To je i razlog zašto ne možete da unesete akreditive kada veza koristi Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Mogu li da promenim vezu sa korišćenja tajni za Key Vault na podrazumevanu potvrdu identiteta?

Ne. Ne možete se vratiti na podrazumevanu vezu nakon što ste je konfigurisali pomoću tajne iz povezanog bezbednosnog skladišta. Kreirajte zasebnu vezu i izbrišite staru ako vam više ne treba.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Kako mogu da opozovem pristup ključnom trezoru za uvide klijenata?

Ako su [omogućene smernice za pristup](/azure/key-vault/general/assign-access-policy?tabs=azure-portal)[ključu trezora ili Azure kontrole pristupa zasnovane](/azure/key-vault/general/rbac-guide?tabs=azure-cli) na ulozi, uklonite dozvole za glavnicu usluge `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` sa imenom `Dynamics 365 AI for Customer Insights`. Sve veze koje koriste bezbednosno skladište će prestati da rade.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Tajna koja se koristi u vezi uklonjena je iz bezbednosnog skladišta. Šta mogu da uradim?

Obaveštenje se pojavljuje u "Uvidima kupaca" kada konfigurisana tajna iz trezora ključa više nije dostupna. Omogućite [meko brisanje](/azure/key-vault/general/soft-delete-overview) u bezbednosnom skladištu za vraćanje tajni ako su slučajno uklonjene.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Veza ne funkcioniše, ali moja tajna je u bezbednosnom skladištu. Šta bi mogao biti uzrok?

Obaveštenje se pojavljuje u uvidima klijenata kada ne može da pristupi trezoru ključa. Uzrok bi mogao biti:

- Dozvole za direktora usluge "Uvid u korisnike" su uklonjene. Potrebno ih je ručno vratiti.

- Zaštitni zid na bezbednosnom skladištu je omogućen. Zaštitni zid mora biti onemogućen da bi ključni trezor ponovo bio dostupan za uvide klijenata.
