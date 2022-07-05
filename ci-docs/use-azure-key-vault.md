---
title: Donesite svoj vlastiti Azure Key Vault (verzija za pregled)
description: Saznajte kako da konfigurišete uvide klijenata da koriste sopstveni Azure ključni trezor za upravljanje tajnama.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 8fdb131de35c7d936d2921265f03faa5682db6f6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082645"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Donesite svoj vlastiti Azure Key Vault (verzija za pregled)

Povezivanje namenskog Azure [ključa trezora sa okruženjem](/azure/key-vault/general/basic-concepts) uvida klijenata pomaže organizacijama da ispune uslove usaglašenosti.
Namensko bezbednosno skladište može da se koristi za postavljanje i korišćenje tajni u granicama usklađenosti organizacije. Uvidi klijenata mogu da koriste tajne u Azure ključ trezoru za [podešavanje veza sa sistemima](connections.md) nezavisnih proizvođača.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Povezivanje ključnog trezora sa okruženjem uvida kupaca

### <a name="prerequisites"></a>Preduslovi

Da biste konfigurisali ključni trezor u uvidima klijenata, moraju biti ispunjeni sledeći preduslovi:

- Imate aktivnu Azure pretplatu.

- Imate ulogu administratora [u](permissions.md#admin) "Uvidima klijenata". Saznajte više o korisničkim [dozvolama u fascikli "Uvidi klijenata"](permissions.md#assign-roles-and-permissions).

- Imate uloge [Saradnik](/azure/role-based-access-control/built-in-roles#contributor) i [Administrator korisničkog pristupa](/azure/role-based-access-control/built-in-roles#user-access-administrator) u bezbednosnom skladištu ili grupi resursa kojoj pripada bezbednosno skladište. Za još informacija idite na [Dodavanje ili uklanjanje Azure dodela uloga koristeći Azure portal](/azure/role-based-access-control/role-assignments-portal). Ako nemate ulogu administratora korisničkog pristupa u bezbednosnom skladištu, morate zasebno uspostaviti dozvole kontrole pristupa zasnovane na ulogama za principala usluge Azure za Dynamics 365 Customer Insights. Pratite korake da biste [koristili principala usluge Azure](connect-service-principal.md) za bezbednosno skladište koje treba povezati.

- Bezbednosno skladište mora imati **onemogućen** zaštitni zid usluge Key Vault.

- Ključni trezor je na istoj Azure [lokaciji kao](https://azure.microsoft.com/global-infrastructure/geographies/#overview) i okruženje "Uvidi kupaca". Region okruženja u uvidima klijenata naveden je u okviru stavke **Admin** > **System** > **About** > **Region**.

### <a name="link-a-key-vault-to-the-environment"></a>Povezivanje bezbednosnog skladišta sa okruženjem

1. Idite na **administratorsko** > **obezbeđenje**, a zatim izaberite karticu **"Trezor ključa**".
1. Na pločici **Bezbednosno skladište**, izaberite **Podešavanje**.
1. Odaberite **pretplatu**.
1. Odaberite bezbednosno skladište sa padajuće liste **Bezbednosno skladište**. Ako se prikazuje previše bezbednosnih skladišta, izaberite grupu resursa da biste ograničili rezultate pretrage.
1. Prihvatite izjavu o **Privatnosti podataka i usklađenosti**.
1. Izaberite **Sačuvaj**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Koraci za podešavanje povezanog trezora ključa u uvidima kupaca.":::

Pločica **Bezbednosno skladište** sada prikazuje naziv povezanog bezbednosnog skladišta, grupu resursa i pretplatu. Spreman je za korišćenje u podešavanju veze.
Za detalje o tome koje dozvole na ključnom trezoru se dodele uvidima klijenata, idite na [dozvole odobrene u ključnom trezoru](#permissions-granted-on-the-key-vault), kasnije u ovom članku.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Korišćenje bezbednosnog skladišta u podešavanju veze

Kada [podešavate veze](connections.md) sa sistemima trećih strana, tajne iz povezanog Key Vaulta mogu se koristiti za konfigurisanje veza.

1. Idite na **Administrator** > **Veze**.
1. Izaberite **Dodaj vezu**.
1. Za podržane tipove veza, prekidač za **Koristite bezbednosno skladište** je dostupan ako ste povezali bezbednosno skladište.
1. Umesto da ručno unosite tajnu, možete izabrati naziv tajne koji ukazuje na vrednost tajne u bezbednosnom skladištu.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Okno za povezivanje sa SFTP vezom koja koristi tajnu bezbednosnog skladišta.":::

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

Ključna uloga čitalac i ključnih trezora tajni biće dodata za uvid klijenata. Za detalje o ovim ulogama idite na [Ugrađene Azure uloge za operacije ravni podataka u Key Vaultu](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Preporuke

- Koristite poseban ili namenski trezor ključa koji sadrži samo tajne potrebne za uvide klijenata. Pročitajte više o tome zašto [se preporučuju zasebna bezbednosna skladišta](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Pratite [najbolje prakse za korišćenje bezbednosnih skladišta](/azure/key-vault/general/best-practices#turn-on-logging) za opcije kontrole pristupa, pravljenja rezervnih kopija, revizije i oporavka.

## <a name="frequently-asked-questions"></a>Najčešća pitanja

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Da li "Uvidi kupaca" mogu da napišu tajne ili da preprave tajne u ključni trezor?

Ne. Samo dozvole za čitanje i liste navedene u odeljku [sa odobrenim dozvolama](#permissions-granted-on-the-key-vault) ranije u ovom članku dodeljivanje su uvidima korisnika. Sistem ne može da dodaje, briše ili zamenjuje tajne u bezbednosnom skladištu. To je i razlog zašto ne možete da unesete akreditive kada veza koristi Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Mogu li da promenim vezu sa korišćenja tajni za Key Vault na podrazumevanu potvrdu identiteta?

Ne. Ne možete se vratiti na podrazumevanu vezu nakon što ste je konfigurisali pomoću tajne iz povezanog bezbednosnog skladišta. Kreirajte zasebnu vezu i izbrišite staru ako vam više ne treba.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Kako mogu da opozovem pristup ključnom trezoru za uvide klijenata?

U zavisnosti od toga da li je omogućeno [Politika pristupa za Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ili [Azure kontrola pristupa zasnovana na ulogama](/azure/key-vault/general/rbac-guide?tabs=azure-cli), morate ukloniti dozvole za principala usluge `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` sa imenom `Dynamics 365 AI for Customer Insights`. Sve veze koje koriste bezbednosno skladište će prestati da rade.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Tajna koja se koristi u vezi uklonjena je iz bezbednosnog skladišta. Šta mogu da uradim?

Obaveštenje se pojavljuje u "Uvidima kupaca" kada konfigurisana tajna iz trezora ključa više nije dostupna. Omogućite [meko brisanje](/azure/key-vault/general/soft-delete-overview) u bezbednosnom skladištu za vraćanje tajni ako su slučajno uklonjene.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Veza ne funkcioniše, ali moja tajna je u bezbednosnom skladištu. Šta bi mogao biti uzrok?

Obaveštenje se pojavljuje u uvidima klijenata kada ne može da pristupi trezoru ključa. Uzrok bi mogao biti:

- Dozvole za direktora usluge "Uvid u korisnike" su uklonjene. Potrebno ih je ručno vratiti.

- Zaštitni zid na bezbednosnom skladištu je omogućen. Zaštitni zid mora biti onemogućen da bi ključni trezor ponovo bio dostupan za uvide klijenata.
