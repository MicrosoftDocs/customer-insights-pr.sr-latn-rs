---
title: Rad sa API-jima
description: Koristite API-je i shvatite ograničenja.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304759"
---
# <a name="work-with-customer-insights-apis"></a>Radite sa Customer Insights API-jem

Dynamics 365 Customer Insights pruža API-je za izgradnju vlastitih aplikacija na osnovu vaših podataka u usluzi Customer Insights.

> [!IMPORTANT]
> Detalji ovih API-ja navedeni su u članku [Referenca za Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Sadrže dodatne informacije o operacijama, parametrima i odgovorima.

Ovaj članak opisuje kako da pristupite Customer Insights API-jima, kreirate registraciju Azure aplikacije i započnete sa dostupnim bibliotekama klijenata.

## <a name="get-started-trying-the-customer-insights-apis"></a>Započnite uz isprobavanje Customer Insights API-ja

1. [Prijavite se](https://home.ci.ai.dynamics.com) u Customer Insights. Ako još uvek nemate pretplatu, [prijavite se za probnu verziju usluge Customer Insights](https://aka.ms/tryci).

1. Da biste omogućili API-je u vašem Customer Insights okruženju, idite na **Administrator** > **Dozvole**. Za to će vam trebati dozvole administratora.

1. Idi na karticu **API-ji** i izaberite dugme **Omogući**.    
 
   Omogućavanje API-ja kreira primarni i sekundarni ključ pretplate za vašu instancu koji se koristi u API zahtevima. Ključeve možete da ponovo generišete tako što ćete izabrati **Ponovo generiši primarni** ili **Ponovo generiši sekundarni** na **Administrator** > **Dozvole** > **API-ji**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Omogućavanje Customer Insights API-ja":::

1. Izaberite **Istražite naše API-je** da [isprobate API-je](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Izaberite operaciju API-ja i izaberite **Isprobajte**.

1. U bočnom oknu, podesite vrednost u padajućem meniju **Ovlašćenje** na **implicitno**. Zaglavlje `Authorization` se dodaje sa tokenom nosioca. Ključ pretplate će se automatski popuniti.
  
1. Po želji dodajte sve potrebne parametre upita.

1. Pomerite se do dna bočnog okna i izaberite **Pošalji**.

HTTP odgovor će se uskoro pojaviti ispod.

   :::image type="content" source="media/try-apis.gif" alt-text="Kako da testirate API-je.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Napravite novu registraciju aplikacije na Azure portalu

Ovi koraci vam pomažu da započnete sa korišćenjem Customer Insights API-ja u Azure aplikaciji pomoću delegiranih dozvola. Obavezno prvo popunite [odeljak „Prvi koraci“](#get-started-trying-the-customer-insights-apis).

1. Prijavite se na [Azure portal](https://portal.azure.com) pomoću naloga koji može pristupiti Customer Insights podacima.

1. S leve strane izaberite **Registracije aplikacija**.

1. Izaberite **Nova registracija**, navedite naziv aplikacije i odaberite tip naloga.
 
   Opcionalno dodajte URL preusmeravanja. http://localhost je dovoljan za razvoj aplikacije na vašem lokalnom računaru.

1. Na novoj registraciji aplikacije idite na **Dozvole za API-je**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Kako se podešavaju dozvole za API u registraciji aplikacije.":::

1. Izaberite **Dodajte dozvolu** i izaberite **Customer Insights** u bočnom oknu.

1. Za **Tip dozvole**, izaberite **Delegirane dozvole**, a zatim izaberite dozvolu **user_impersonation**.

1. Izaberite stavku **Dodajte dozvole**. Ako vam je potreban pristup API-ju bez prijavljivanja korisnika, pregledajte odeljak [Dozvole za aplikacije od servera do servera](#server-to-server-application-permissions).

1. Izaberite **Dajte saglasnost administratora za...** da biste dovršili registraciju aplikacije.

Možete da koristite ID aplikacije/klijenta za registraciju ove aplikacije u Microsoft Authentication Library (MSAL) da biste dobili token nosioca koji ćete sa zahtevom poslati u API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Kako da odobrite saglasnost administratora.":::

Za više informacija o MSAL-u, pogledajte [Pregled Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).

Za više informacija o registraciji aplikacija u usluzi Azure, pogledajte [Registrovanje aplikacije](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

Za informacije o korišćenju API-ja u našim klijentskim bibliotekama, pogledajte [Customer Insights klijentske biblioteke](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Dozvole za aplikacije sa servera na server

[Odeljak za registraciju aplikacija](#create-a-new-app-registration-in-the-azure-portal) opisuje kako se registruje aplikacija koja zahteva da se korisnik prijavi radi potvrde identiteta. Saznajte kako da kreirate registraciju aplikacije koja ne zahteva interakciju korisnika i koja se može pokrenuti na serveru.

1. Pri registraciji aplikacije na Azure portalu idite na **Dozvole za API-je**.

1. Izaberite **Dodaj dozvolu**. 

1. Izaberite karticu **API-ji koje koristi moja organizacija** karticu i sa liste izaberite **Dynamics 365 AI za Customer Insights**. 

1. Za **Tip dozvole**, izaberite **Dozvole za aplikaciju**, a zatim izaberite dozvolu **CustomerInsights.Api.All**.

1. Izaberite stavku **Dodajte dozvole**.

1. Na novoj registraciji aplikacije vratite se na **Dozvole za API-je**.

1. Izaberite **Dajte saglasnost administratora za...** da biste dovršili registraciju aplikacije.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Kako da odobrite saglasnost administratora.":::

1. Da zaključimo, moramo da dodamo ime registracije aplikacije kao korisnika u Customer Insights.  
   
   Otvorite Customer Insights, idite na **Administrator** > **Dozvole** i izaberite **Dodaj korisnika**.

1. Potražite ime registracije aplikacije, izaberite je iz rezultata pretrage i izaberite **Sačuvaj**.

## <a name="customer-insights-client-libraries"></a>Customer Insights klijentske biblioteke

Ovaj odeljak vam pomaže da započnete korišćenje klijentskih biblioteka dostupnih za Customer Insights API-je. Sav izvorni kôd biblioteke i primeri aplikacija mogu se naći na [Customer Insights GitHub stranici](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Saznajte kako da započnete korišćenje C# klijentskih biblioteka sa NuGet.org. Za više informacija o NuGet paketu, vidite [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Trenutno ovaj paket cilja okvire netstandard2.0 i netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Dodajte C# klijentsku biblioteku u C# projekat

1. U programu Visual Studio, otvorite **NuGet menadžer paketa** za projekat.

1. Potražite **Microsoft.Dynamics.CustomerInsights.Api**.

1. Izaberite **Instaliraj** za dodavanje paketa u projekat.
 
   Alternativno, pokrenite ovu komandu u **NuGet konzoli menadžera paketa**:`Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Dodajte NuGet paket u Visual Studio projekat":::

#### <a name="use-the-c-client-library"></a>Koristite C# klijentsku biblioteku

1. Koristite [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) da biste dobili `AccessToken` koristeći svoje postojeću [registraciju Azure aplikacije](#create-a-new-app-registration-in-the-azure-portal).

1. Nakon uspešne potvrde identiteta i pribavljanja tokena, napravite novi ili koristite postojeći `HttpClient` sa dodatnim **DefaultRequestHeaders "Authorization"** podešenim na **Nosilac<access token>** i **Ocp-Apim-Subscription-Key** podešenim na [**ključ pretplate** iz vašeg Customer Insights okruženja](#get-started-trying-the-customer-insights-apis).   
 
   Resetujte zaglavlje **Ovlašćenje** po potrebi. Na primer, kada je token istekao.

1. Prosledite `HttpClient` u konstrukciju `CustomerInsights` klijenta.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Uzorak httpclient-a":::

1. Upućujte pozive klijentu za „metode proširenja“, na primer, `GetAllInstancesAsync`. Ako je potreban pristup osnovnom `Microsoft.Rest.HttpOperationResponse`, koristite „metode http poruka“ – na primer, `GetAllInstancesWithHttpMessagesAsync`.

1. Odgovor će verovatno biti tipa `object` jer metod može da vrati više tipova (na primer, `IList<InstanceInfo>` i `ApiErrorResult`). Da biste proverili tip povratka, možete eksplicitno konvertovati objekte u tipove odgovora navedene na [stranici sa detaljima API-ja](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) za tu operaciju.    
   
   Ako su potrebne dodatne informacije o zahtevu, koristite **http metode poruka** za pristup neobrađenom objektu odgovora.

### <a name="nodejs-package"></a>NodeJS paket

Koristite NodeJS klijentske biblioteke dostupne preko NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python paket

Koristite Python klijentske biblioteke dostupne preko PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
