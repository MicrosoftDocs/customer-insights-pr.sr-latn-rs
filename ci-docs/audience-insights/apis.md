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
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="71293-103">Radite sa Customer Insights API-jem</span><span class="sxs-lookup"><span data-stu-id="71293-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="71293-104">Dynamics 365 Customer Insights pruža API-je za izgradnju vlastitih aplikacija na osnovu vaših podataka u usluzi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="71293-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71293-105">Detalji ovih API-ja navedeni su u članku [Referenca za Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="71293-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="71293-106">Sadrže dodatne informacije o operacijama, parametrima i odgovorima.</span><span class="sxs-lookup"><span data-stu-id="71293-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="71293-107">Ovaj članak opisuje kako da pristupite Customer Insights API-jima, kreirate registraciju Azure aplikacije i započnete sa dostupnim bibliotekama klijenata.</span><span class="sxs-lookup"><span data-stu-id="71293-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="71293-108">Započnite uz isprobavanje Customer Insights API-ja</span><span class="sxs-lookup"><span data-stu-id="71293-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="71293-109">[Prijavite se](https://home.ci.ai.dynamics.com) u Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="71293-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="71293-110">Ako još uvek nemate pretplatu, [prijavite se za probnu verziju usluge Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="71293-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="71293-111">Da biste omogućili API-je u vašem Customer Insights okruženju, idite na **Administrator** > **Dozvole**.</span><span class="sxs-lookup"><span data-stu-id="71293-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="71293-112">Za to će vam trebati dozvole administratora.</span><span class="sxs-lookup"><span data-stu-id="71293-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="71293-113">Idi na karticu **API-ji** i izaberite dugme **Omogući**.</span><span class="sxs-lookup"><span data-stu-id="71293-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="71293-114">Omogućavanje API-ja kreira primarni i sekundarni ključ pretplate za vašu instancu koji se koristi u API zahtevima.</span><span class="sxs-lookup"><span data-stu-id="71293-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="71293-115">Ključeve možete da ponovo generišete tako što ćete izabrati **Ponovo generiši primarni** ili **Ponovo generiši sekundarni** na **Administrator** > **Dozvole** > **API-ji**.</span><span class="sxs-lookup"><span data-stu-id="71293-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Omogućavanje Customer Insights API-ja":::

1. <span data-ttu-id="71293-117">Izaberite **Istražite naše API-je** da [isprobate API-je](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="71293-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="71293-118">Izaberite operaciju API-ja i izaberite **Isprobajte**.</span><span class="sxs-lookup"><span data-stu-id="71293-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="71293-119">U bočnom oknu, podesite vrednost u padajućem meniju **Ovlašćenje** na **implicitno**.</span><span class="sxs-lookup"><span data-stu-id="71293-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="71293-120">Zaglavlje `Authorization` se dodaje sa tokenom nosioca.</span><span class="sxs-lookup"><span data-stu-id="71293-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="71293-121">Ključ pretplate će se automatski popuniti.</span><span class="sxs-lookup"><span data-stu-id="71293-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="71293-122">Po želji dodajte sve potrebne parametre upita.</span><span class="sxs-lookup"><span data-stu-id="71293-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="71293-123">Pomerite se do dna bočnog okna i izaberite **Pošalji**.</span><span class="sxs-lookup"><span data-stu-id="71293-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="71293-124">HTTP odgovor će se uskoro pojaviti ispod.</span><span class="sxs-lookup"><span data-stu-id="71293-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="Kako da testirate API-je.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="71293-126">Napravite novu registraciju aplikacije na Azure portalu</span><span class="sxs-lookup"><span data-stu-id="71293-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="71293-127">Ovi koraci vam pomažu da započnete sa korišćenjem Customer Insights API-ja u Azure aplikaciji pomoću delegiranih dozvola.</span><span class="sxs-lookup"><span data-stu-id="71293-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="71293-128">Obavezno prvo popunite [odeljak „Prvi koraci“](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="71293-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="71293-129">Prijavite se na [Azure portal](https://portal.azure.com) pomoću naloga koji može pristupiti Customer Insights podacima.</span><span class="sxs-lookup"><span data-stu-id="71293-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="71293-130">S leve strane izaberite **Registracije aplikacija**.</span><span class="sxs-lookup"><span data-stu-id="71293-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="71293-131">Izaberite **Nova registracija**, navedite naziv aplikacije i odaberite tip naloga.</span><span class="sxs-lookup"><span data-stu-id="71293-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="71293-132">Opcionalno dodajte URL preusmeravanja.</span><span class="sxs-lookup"><span data-stu-id="71293-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="71293-133">http://localhost je dovoljan za razvoj aplikacije na vašem lokalnom računaru.</span><span class="sxs-lookup"><span data-stu-id="71293-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="71293-134">Na novoj registraciji aplikacije idite na **Dozvole za API-je**.</span><span class="sxs-lookup"><span data-stu-id="71293-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Kako se podešavaju dozvole za API u registraciji aplikacije.":::

1. <span data-ttu-id="71293-136">Izaberite **Dodajte dozvolu** i izaberite **Customer Insights** u bočnom oknu.</span><span class="sxs-lookup"><span data-stu-id="71293-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="71293-137">Za **Tip dozvole**, izaberite **Delegirane dozvole**, a zatim izaberite dozvolu **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="71293-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="71293-138">Izaberite stavku **Dodajte dozvole**.</span><span class="sxs-lookup"><span data-stu-id="71293-138">Select **Add permissions**.</span></span> <span data-ttu-id="71293-139">Ako vam je potreban pristup API-ju bez prijavljivanja korisnika, pregledajte odeljak [Dozvole za aplikacije od servera do servera](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="71293-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="71293-140">Izaberite **Dajte saglasnost administratora za...** da biste dovršili registraciju aplikacije.</span><span class="sxs-lookup"><span data-stu-id="71293-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="71293-141">Možete da koristite ID aplikacije/klijenta za registraciju ove aplikacije u Microsoft Authentication Library (MSAL) da biste dobili token nosioca koji ćete sa zahtevom poslati u API.</span><span class="sxs-lookup"><span data-stu-id="71293-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Kako da odobrite saglasnost administratora.":::

<span data-ttu-id="71293-143">Za više informacija o MSAL-u, pogledajte [Pregled Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="71293-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="71293-144">Za više informacija o registraciji aplikacija u usluzi Azure, pogledajte [Registrovanje aplikacije](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span><span class="sxs-lookup"><span data-stu-id="71293-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="71293-145">Za informacije o korišćenju API-ja u našim klijentskim bibliotekama, pogledajte [Customer Insights klijentske biblioteke](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="71293-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="71293-146">Dozvole za aplikacije sa servera na server</span><span class="sxs-lookup"><span data-stu-id="71293-146">Server-to-server application permissions</span></span>

<span data-ttu-id="71293-147">[Odeljak za registraciju aplikacija](#create-a-new-app-registration-in-the-azure-portal) opisuje kako se registruje aplikacija koja zahteva da se korisnik prijavi radi potvrde identiteta.</span><span class="sxs-lookup"><span data-stu-id="71293-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="71293-148">Saznajte kako da kreirate registraciju aplikacije koja ne zahteva interakciju korisnika i koja se može pokrenuti na serveru.</span><span class="sxs-lookup"><span data-stu-id="71293-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="71293-149">Pri registraciji aplikacije na Azure portalu idite na **Dozvole za API-je**.</span><span class="sxs-lookup"><span data-stu-id="71293-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="71293-150">Izaberite **Dodaj dozvolu**.</span><span class="sxs-lookup"><span data-stu-id="71293-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="71293-151">Izaberite karticu **API-ji koje koristi moja organizacija** karticu i sa liste izaberite **Dynamics 365 AI za Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="71293-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="71293-152">Za **Tip dozvole**, izaberite **Dozvole za aplikaciju**, a zatim izaberite dozvolu **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="71293-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="71293-153">Izaberite stavku **Dodajte dozvole**.</span><span class="sxs-lookup"><span data-stu-id="71293-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="71293-154">Na novoj registraciji aplikacije vratite se na **Dozvole za API-je**.</span><span class="sxs-lookup"><span data-stu-id="71293-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="71293-155">Izaberite **Dajte saglasnost administratora za...** da biste dovršili registraciju aplikacije.</span><span class="sxs-lookup"><span data-stu-id="71293-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Kako da odobrite saglasnost administratora.":::

1. <span data-ttu-id="71293-157">Da zaključimo, moramo da dodamo ime registracije aplikacije kao korisnika u Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="71293-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="71293-158">Otvorite Customer Insights, idite na **Administrator** > **Dozvole** i izaberite **Dodaj korisnika**.</span><span class="sxs-lookup"><span data-stu-id="71293-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="71293-159">Potražite ime registracije aplikacije, izaberite je iz rezultata pretrage i izaberite **Sačuvaj**.</span><span class="sxs-lookup"><span data-stu-id="71293-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="71293-160">Customer Insights klijentske biblioteke</span><span class="sxs-lookup"><span data-stu-id="71293-160">Customer Insights client libraries</span></span>

<span data-ttu-id="71293-161">Ovaj odeljak vam pomaže da započnete korišćenje klijentskih biblioteka dostupnih za Customer Insights API-je.</span><span class="sxs-lookup"><span data-stu-id="71293-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="71293-162">Sav izvorni kôd biblioteke i primeri aplikacija mogu se naći na [Customer Insights GitHub stranici](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="71293-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="71293-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="71293-163">C# NuGet</span></span>

<span data-ttu-id="71293-164">Saznajte kako da započnete korišćenje C# klijentskih biblioteka sa NuGet.org. Za više informacija o NuGet paketu, vidite [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="71293-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="71293-165">Trenutno ovaj paket cilja okvire netstandard2.0 i netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="71293-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="71293-166">Dodajte C# klijentsku biblioteku u C# projekat</span><span class="sxs-lookup"><span data-stu-id="71293-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="71293-167">U programu Visual Studio, otvorite **NuGet menadžer paketa** za projekat.</span><span class="sxs-lookup"><span data-stu-id="71293-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="71293-168">Potražite **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="71293-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="71293-169">Izaberite **Instaliraj** za dodavanje paketa u projekat.</span><span class="sxs-lookup"><span data-stu-id="71293-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="71293-170">Alternativno, pokrenite ovu komandu u **NuGet konzoli menadžera paketa**:`Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="71293-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Dodajte NuGet paket u Visual Studio projekat":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="71293-172">Koristite C# klijentsku biblioteku</span><span class="sxs-lookup"><span data-stu-id="71293-172">Use the C# client library</span></span>

1. <span data-ttu-id="71293-173">Koristite [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) da biste dobili `AccessToken` koristeći svoje postojeću [registraciju Azure aplikacije](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="71293-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="71293-174">Nakon uspešne potvrde identiteta i pribavljanja tokena, napravite novi ili koristite postojeći `HttpClient` sa dodatnim **DefaultRequestHeaders "Authorization"** podešenim na **Nosilac<access token>** i **Ocp-Apim-Subscription-Key** podešenim na [**ključ pretplate** iz vašeg Customer Insights okruženja](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="71293-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="71293-175">Resetujte zaglavlje **Ovlašćenje** po potrebi.</span><span class="sxs-lookup"><span data-stu-id="71293-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="71293-176">Na primer, kada je token istekao.</span><span class="sxs-lookup"><span data-stu-id="71293-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="71293-177">Prosledite `HttpClient` u konstrukciju `CustomerInsights` klijenta.</span><span class="sxs-lookup"><span data-stu-id="71293-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Uzorak httpclient-a":::

1. <span data-ttu-id="71293-179">Upućujte pozive klijentu za „metode proširenja“, na primer, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="71293-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="71293-180">Ako je potreban pristup osnovnom `Microsoft.Rest.HttpOperationResponse`, koristite „metode http poruka“ – na primer, `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="71293-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="71293-181">Odgovor će verovatno biti tipa `object` jer metod može da vrati više tipova (na primer, `IList<InstanceInfo>` i `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="71293-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="71293-182">Da biste proverili tip povratka, možete eksplicitno konvertovati objekte u tipove odgovora navedene na [stranici sa detaljima API-ja](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) za tu operaciju.</span><span class="sxs-lookup"><span data-stu-id="71293-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="71293-183">Ako su potrebne dodatne informacije o zahtevu, koristite **http metode poruka** za pristup neobrađenom objektu odgovora.</span><span class="sxs-lookup"><span data-stu-id="71293-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="71293-184">NodeJS paket</span><span class="sxs-lookup"><span data-stu-id="71293-184">NodeJS package</span></span>

<span data-ttu-id="71293-185">Koristite NodeJS klijentske biblioteke dostupne preko NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="71293-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="71293-186">Python paket</span><span class="sxs-lookup"><span data-stu-id="71293-186">Python package</span></span>

<span data-ttu-id="71293-187">Koristite Python klijentske biblioteke dostupne preko PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="71293-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
