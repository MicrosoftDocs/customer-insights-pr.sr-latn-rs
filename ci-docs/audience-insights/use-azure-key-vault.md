---
title: Donesite svoj vlastiti Azure Key Vault za upravljanje tajnama
description: Naučite kako da konfigurišete Customer Insights da koristite sopstveni Azure Key Vault.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: 6f521dfce3e0922238d16beee3be8e1bbcfc63a5
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606126"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Donesite svoj vlastiti Azure Key Vault (verzija za pregled)

Povezivanje namenskog [Azure Key Vaulta](/azure/key-vault/general/basic-concepts) u okruženje uvida u ciljnu grupu pomaže organizacijama da ispune zahteve usklađenosti.
Namensko bezbednosno skladište može da se koristi za postavljanje i korišćenje tajni u granicama usklađenosti organizacije. Uvidi u ciljnu grupu mogu koristiti tajne u Azure Key Vaultu za [uspostavljanje veza](connections.md) sa sistemima trećih strana.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Povezivanje bezbednosnog skladišta sa okruženjem uvida u ciljnu grupu

### <a name="prerequisites"></a>Preduslovi

Da biste konfigurisali bezbednosno skladište u uvidima u ciljnu grupu, moraju biti ispunjeni sledeći preduslovi:

- Imate aktivnu Azure pretplatu.

- Imate ulogu [administratora](permissions.md#administrator) u uvidima u ciljnu grupu. Saznajte više o [korisničkim dozvolama u uvidima u ciljnu grupu](permissions.md#assign-roles-and-permissions).

- Imate uloge [Saradnik](/azure/role-based-access-control/built-in-roles#contributor) i [Administrator korisničkog pristupa](/azure/role-based-access-control/built-in-roles#user-access-administrator) u bezbednosnom skladištu ili grupi resursa kojoj pripada bezbednosno skladište. Za još informacija idite na [Dodavanje ili uklanjanje Azure dodela uloga koristeći Azure portal](/azure/role-based-access-control/role-assignments-portal). Ako nemate ulogu administratora korisničkog pristupa u bezbednosnom skladištu, morate zasebno uspostaviti dozvole kontrole pristupa zasnovane na ulogama za principala usluge Azure za Dynamics 365 Customer Insights. Pratite korake da biste [koristili principala usluge Azure](connect-service-principal.md) za bezbednosno skladište koje treba povezati.

- Bezbednosno skladište mora imati **onemogućen** zaštitni zid usluge Key Vault.

- Bezbednosno skladište je na istoj [Azure lokaciji](https://azure.microsoft.com/global-infrastructure/geographies/#overview) kao okruženje uvida u ciljnu grupu. Region okruženja u uvidima u ciljnu grupu je naveden u okviru opcije **Administrator** > **Sistem** > **O sistemu** > **Region**.

### <a name="link-a-key-vault-to-the-environment"></a>Povezivanje bezbednosnog skladišta sa okruženjem

1. Idite u **Administrator** > **Sistem**, a zatim izaberite karticu **Bezbednost**.
1. Na pločici **Bezbednosno skladište**, izaberite **Podešavanje**.
1. Odaberite **pretplatu**.
1. Odaberite bezbednosno skladište sa padajuće liste **Bezbednosno skladište**. Ako se prikazuje previše bezbednosnih skladišta, izaberite grupu resursa da biste ograničili rezultate pretrage.
1. Prihvatite izjavu o **Privatnosti podataka i usklađenosti**.
1. Izaberite stavku **Sačuvaj**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Koraci za uspostavljanje povezanog bezbednosnog skladišta u uvidima u ciljnu grupu.":::

Pločica **Bezbednosno skladište** sada prikazuje naziv povezanog bezbednosnog skladišta, grupu resursa i pretplatu. Spreman je za korišćenje u podešavanju veze.
Za detalje o tome koje su dozvole za bezbednosno skladište dodeljene uvidima u ciljnu grupu, idite na [Date dozvole u bezbednosnom skladištu za uvide u ciljnu grupu](#permissions-granted-on-the-key-vault-to-audience-insights), kasnije u ovom članku.

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

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Dozvole date u bezbednosnom skladištu za uvide u ciljnu grupu

Sledeće dozvole su odobrene uvidima u ciljnu grupu na povezanom bezbednosnom skladištu ako su omogućeni ili [Politika pristupa za Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ili [Azure kontrola pristupa zasnovana na ulogama](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

### <a name="key-vault-access-policy"></a>Politika pristupa za Key Vault

| Tip        | Dozvole          |
| ----------- | -------------------- |
| Taster         | [Pribavite ključeve](/rest/api/keyvault/get-keys), [Pribavite ključ](/rest/api/keyvault/get-key)                                 |
| Tajni      | [Pribavite tajne](/rest/api/keyvault/get-secrets), [Pribavite tajnu](/rest/api/keyvault/get-secret)                     |
| Certifikat | [Pribavite certifikate](/rest/api/keyvault/get-certificates), [Pribavite certifikat](/rest/api/keyvault/get-certificate) |

Prethodne vrednosti su minimum za navođenje i čitanje tokom izvršavanja.

### <a name="azure-role-based-access-control"></a>Azure kontrola pristupa zasnovana na ulogama

Korisničke uloge Čitač bezbednosnog skladišta i Tajne bezbednosnog skladišta biće dodate za uvide u ciljnu grupu. Za detalje o ovim ulogama idite na [Ugrađene Azure uloge za operacije ravni podataka u Key Vaultu](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Preporuke

- Koristite zasebno ili namensko bezbednosno skladište koje sadrži samo tajne potrebne za uvide u ciljnu grupu. Pročitajte više o tome zašto [se preporučuju zasebna bezbednosna skladišta](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Pratite [najbolje prakse za korišćenje bezbednosnih skladišta](/azure/key-vault/general/best-practices#turn-on-logging) za opcije kontrole pristupa, pravljenja rezervnih kopija, revizije i oporavka.

## <a name="frequently-asked-questions"></a>Najčešća pitanja

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Mogu li uvidi u ciljnu grupu upisati tajne ili zameniti ih u bezbednosnom skladištu?

Ne. Samo dozvole za čitanje i navođenje na listi navedene u odeljku [odobrene dozvole](#permissions-granted-on-the-key-vault-to-audience-insights) ranije u ovom članku imaju dozvolu za pristup uvidima u ciljnu grupu. Sistem ne može da dodaje, briše ili zamenjuje tajne u bezbednosnom skladištu. To je i razlog zašto ne možete da unesete akreditive kada veza koristi Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Mogu li da promenim vezu sa korišćenja tajni za Key Vault na podrazumevanu potvrdu identiteta?

Ne. Ne možete se vratiti na podrazumevanu vezu nakon što ste je konfigurisali pomoću tajne iz povezanog bezbednosnog skladišta. Kreirajte zasebnu vezu i izbrišite staru ako vam više ne treba.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Kako mogu opozvati pristup bezbednosnom skladištu za uvide u ciljnu grupu?

U zavisnosti od toga da li je omogućeno [Politika pristupa za Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ili [Azure kontrola pristupa zasnovana na ulogama](/azure/key-vault/general/rbac-guide?tabs=azure-cli), morate ukloniti dozvole za principala usluge `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` sa imenom `Dynamics 365 AI for Customer Insights`. Sve veze koje koriste bezbednosno skladište će prestati da rade.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Tajna koja se koristi u vezi uklonjena je iz bezbednosnog skladišta. Šta mogu da uradim?

Obaveštenje se pojavljuje u uvidima o ciljnoj grupi kada konfigurisana tajna iz bezbednosnog skladišta više nije dostupna. Omogućite [meko brisanje](/azure/key-vault/general/soft-delete-overview) u bezbednosnom skladištu za vraćanje tajni ako su slučajno uklonjene.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Veza ne funkcioniše, ali moja tajna je u bezbednosnom skladištu. Šta bi mogao biti uzrok?

Obaveštenje se pojavljuje u uvidima o ciljnoj grupi kada ne može da pristupi bezbednosnom skladištu. Uzrok bi mogao biti:

- Uklonjene su dozvole za principala usluge uvida u ciljnu grupu. Potrebno ih je ručno vratiti.

- Zaštitni zid na bezbednosnom skladištu je omogućen. Zaštitni zid mora biti onemogućen kako bi bezbednosno skladište ponovo bilo dostupno za uvide u ciljnu grupu.
