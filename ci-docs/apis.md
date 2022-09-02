---
title: Radite sa Customer Insights API-jem
description: Koristite API-je i shvatite ograničenja.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387357"
---
# <a name="work-with-customer-insights-apis"></a>Radite sa Customer Insights API-jem

Dynamics 365 Customer Insights pruža API-je za izgradnju vlastitih aplikacija na osnovu vaših podataka u usluzi Customer Insights.

> [!IMPORTANT]
> Detalji ovih API-ja navedeni su u članku [Referenca za Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Sadrže dodatne informacije o operacijama, parametrima i odgovorima.

Isprobajte API-je za korisničke uvide, kreirajte Azure registraciju aplikacija i prvi koraci u bibliotekama klijenata.

## <a name="get-started-trying-the-customer-insights-apis"></a>Započnite uz isprobavanje Customer Insights API-ja

Omogućite API-je korisničkih uvida i isprobajte ih. Administrator "Uvidi klijenata" mora da omogući API pristup uvidima klijenata. Kada se omogući pristup, svaki korisnik može da koristi API sa ključem za pretplatu.

1. [Prijavite se](https://home.ci.ai.dynamics.com) u Customer Insights. Ako još uvek nemate pretplatu, [prijavite se za probnu verziju usluge Customer Insights](https://aka.ms/tryci).

1. Idite na **administratorske** > **mere bezbednosti** i izaberite **karticu API.**

1. Ako API pristup okruženju nije podešen, izaberite opciju **Omogući**.

   Omogućavanje API-ja kreira primarni i sekundarni ključ pretplate za vašu instancu koji se koristi u API zahtevima. Da biste ponovo generisali ključeve, na **kartici "APIS" izaberite** **stavku "Regeneriši primarnu** **ili regeneriši sekundarnu"**.

1. Izaberite [**stavku Istražite naše API-je**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) da biste isprobali API-je.

1. Potražite i izaberite API operaciju i izaberite **pokušajte**.

   :::image type="content" source="media/try-api.png" alt-text="Kako da testirate API-je.":::

1. U bočnom oknu, podesite vrednost u padajućem meniju **Ovlašćenje** na **implicitno**. Zaglavlje `Authorization` se dodaje sa tokenom nosioca. Ključ za pretplatu se automatski popunjava.
  
1. Po želji dodajte sve potrebne parametre upita.

1. Pomerite se do dna bočnog okna i izaberite **Pošalji**.

   HTTP odgovor se prikazuje na dnu okna.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Napravite novu registraciju aplikacije na Azure portalu

Kreirajte novu registraciju [aplikacija](/graph/auth-register-app-v2) da biste koristili API-je korisničkih uvida u Azure aplikaciji koristeći delegirane dozvole.

1. Dovršite odeljak [Prvi koraci](#get-started-trying-the-customer-insights-apis).

1. Prijavite se na [Azure portal](https://portal.azure.com) pomoću naloga koji može pristupiti Customer Insights podacima.

1. Potražite, a zatim izaberite **stavke Registracije aplikacija**.

1. Izaberite **Nova registracija**, navedite naziv aplikacije i odaberite tip naloga.

   Opcionalno dodajte URL preusmeravanja. http://localhost je dovoljan za razvoj aplikacije na vašem lokalnom računaru.

1. Izaberite **Registracija**.

1. Na novoj registraciji aplikacije idite na **Dozvole za API-je**.

1. U **bočnom oknu izaberite** stavku **Dodaj dozvolu i izaberite Dynamics 365 AI za uvide** klijenata.

1. Za **Tip dozvole**, izaberite **Delegirane dozvole**, a zatim izaberite dozvolu **user_impersonation**.

1. Izaberite stavku **Dodajte dozvole**.

1. Izaberite **Dajte saglasnost administratora za...** da biste dovršili registraciju aplikacije.

1. Da biste pristupili API-u bez prijavljivanja korisnika, idite na [dozvole aplikacije "Server-to-server"](#server-to-server-application-permissions).

ID aplikacije/klijenta možete koristiti za [registraciju ove aplikacije u Microsoft biblioteci za potvrdu identiteta (MSAL)](/azure/active-directory/develop/msal-overview) da biste dobili oznaku nosioca koju ćete poslati API-u.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Za informacije o korišćenju API-ja u našim klijentskim bibliotekama, pogledajte [Customer Insights klijentske biblioteke](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Dozvole za aplikacije sa servera na server

Kreirajte registraciju aplikacije za koju nije potrebna interakcija korisnika i može se pokrenuti na serveru.

1. Pri registraciji aplikacije na Azure portalu idite na **Dozvole za API-je**.

1. Izaberite **Dodaj dozvolu**.

1. Izaberite karticu **API-ji koje koristi moja organizacija** karticu i sa liste izaberite **Dynamics 365 AI za Customer Insights**.

1. Za **Tip dozvole**, izaberite **Dozvole za aplikaciju**, a zatim izaberite dozvolu **CustomerInsights.Api.All**.

1. Izaberite stavku **Dodajte dozvole**.

1. Na novoj registraciji aplikacije vratite se na **Dozvole za API-je**.

1. Izaberite **Dajte saglasnost administratora za...** da biste dovršili registraciju aplikacije.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Dodajte ime registracije aplikacije kao korisnika u uvid kupca.

   1. Otvorite opciju "Uvidi klijenata", idite u **administrator bezbednost** > **i** izaberite stavku **Dodaj korisnike**.

   1. Potražite ime registracije aplikacije, izaberite je iz rezultata pretrage i izaberite **Sačuvaj**.

## <a name="sample-queries"></a>Probni upiti

Da bi kratka lista probnih upita OData radila sa API-jem, pogledajte [primere upita OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Customer Insights klijentske biblioteke

Prvi koraci u korišćenju biblioteka klijenata dostupnih za API-je korisničkih uvida. Sav izvorni kôd biblioteke i primeri aplikacija mogu se naći na [Customer Insights GitHub stranici](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Koristite biblioteke C# klijenata iz NuGet.org. Trenutno je na meti paketa netstandard2.0 i netcoreapp2.0 frameworks. Više informacija o paketu potražite NuGet u članku [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Dodajte C# klijentsku biblioteku u C# projekat

1. U programu Visual Studio, otvorite **NuGet menadžer paketa** za projekat.

1. Potražite **Microsoft.Dynamics.CustomerInsights.Api**.

1. Izaberite **Instaliraj** za dodavanje paketa u projekat.

   Alternativno, pokrenite ovu komandu u **NuGet konzoli menadžera paketa**:`Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Koristite C# klijentsku biblioteku

1. Koristite [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) da biste dobili `AccessToken` koristeći svoje postojeću [registraciju Azure aplikacije](#create-a-new-app-registration-in-the-azure-portal).

1. Nakon uspešne potvrde identiteta i pribavljanja simbola, `HttpClient` napravite novi ili koristite postojeći sa "Ovlašćenjima" podrazumevanih nosilaca postavljenim na "Token za pristup"**i** Ocp-Apim-Subscription-Key **postavljenim na** ključ pretplate iz **okruženja "Uvidi kupaca"**[**·**.](#get-started-trying-the-customer-insights-apis)   

   Resetujte zaglavlje **Ovlašćenje** po potrebi. Na primer, kada je token istekao.

1. Prosledite `HttpClient` u konstrukciju `CustomerInsights` klijenta.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Pozivajte sa klijentom za „metode produženja“, na primer, `GetAllInstancesAsync`. Ako je željeni pristup osnovnoj`Microsoft.Rest.HttpOperationResponse`, koristite "http metode poruke", na primer. `GetAllInstancesWithHttpMessagesAsync`

1. Odgovor je verovatno tip jer `object` metod može da vrati više tipova (na primer, `IList<InstanceInfo>` i `ApiErrorResult`). Da biste proverili tip povraćaja, koristite objekte u tipovima odgovora navedenim na stranici [API detalja za](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) tu operaciju.

   Ako su potrebne dodatne informacije o zahtevu, koristite **http metode poruka** za pristup neobrađenom objektu odgovora.

### <a name="nodejs-package"></a>NodeJS paket

Koristite NodeJS klijentske biblioteke dostupne preko NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python paket

Koristite Python klijentske biblioteke dostupne preko PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
