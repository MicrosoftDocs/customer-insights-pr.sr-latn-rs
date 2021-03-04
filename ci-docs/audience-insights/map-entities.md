---
title: Mapiranje entiteta za objedinjavanje podataka
description: Mapirajte podatke da biste kreirali objedinjene profile klijenata.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267052"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="63302-103">Entiteti i atributi mape</span><span class="sxs-lookup"><span data-stu-id="63302-103">Map entities and attributes</span></span>

<span data-ttu-id="63302-104">**Mapiranje** je prva faza u procesu objedinjavanja podataka u uvidima o korisnicima.</span><span class="sxs-lookup"><span data-stu-id="63302-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="63302-105">Mapiranje se sastoji od tri faze:</span><span class="sxs-lookup"><span data-stu-id="63302-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="63302-106">*Izbor entiteta*: Identifikujte kombinovane entitete koji vode do skupa podataka sa potpunijim informacijama o vašim klijentima.</span><span class="sxs-lookup"><span data-stu-id="63302-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="63302-107">*Izbor atributa*: Za svaki entitet odredite kolone koje želite da kombinujete i usaglasite u fazama *podudaranje* i *spajanje*.</span><span class="sxs-lookup"><span data-stu-id="63302-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="63302-108">Ove kolone se zovu *Atributi*.</span><span class="sxs-lookup"><span data-stu-id="63302-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="63302-109">*Izbor primarnog ključa i semantičkog tipa*: Za svaki entitet identifikujte atribut koji želite da definišete kao primarni ključ za taj entitet, a za svaki atribut identifikujte semantički tip koji najbolje opisuje taj atribut.</span><span class="sxs-lookup"><span data-stu-id="63302-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="63302-110">Za više informacija o opštem toku objedinjavanja podataka, pogledajte [Ujednačavanje](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="63302-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="63302-111">Izaberite prve entitete</span><span class="sxs-lookup"><span data-stu-id="63302-111">Select the first entities</span></span>

1. <span data-ttu-id="63302-112">U uvidima o korisnicima idite na **Podaci** > **Objedini** > **Mapiraj**.</span><span class="sxs-lookup"><span data-stu-id="63302-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="63302-113">Započnite fazu mapiranja odabirom **Izaberi entitete**.</span><span class="sxs-lookup"><span data-stu-id="63302-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="63302-114">Izaberite entitete i atribute koje želite da koristite u fazama *podudaranje* i *spajanje*.</span><span class="sxs-lookup"><span data-stu-id="63302-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="63302-115">Možete da izaberete tražene atribute pojedinačno iz entiteta ili da uključite sve atribute iz entiteta izborom polja za potvrdu **Uključi sva polja** na nivou entiteta.</span><span class="sxs-lookup"><span data-stu-id="63302-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="63302-116">Preporučujemo da izaberete najmanje dva entiteta koji će imati koristi od procesa objedinjavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="63302-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="63302-117">![Primer dodavanja entiteta](media/data-manager-configure-map-add-entities-example.png "Primer dodavanja entiteta")</span><span class="sxs-lookup"><span data-stu-id="63302-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="63302-118">U ovom primeru dodajemo entitete **eCommerceContacts** i **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="63302-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="63302-119">Odabirom ovih entiteta možete steći uvid u to koji od poslovnih korisnika na mreži su članovi programa lojalnosti.</span><span class="sxs-lookup"><span data-stu-id="63302-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="63302-120">Možete pretraživati ključne reči po svim atributima i entitetima da biste izabrali potrebne atribute koje želite da mapirate.</span><span class="sxs-lookup"><span data-stu-id="63302-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="63302-121">![Primer polja za pretragu](media/data-manager-configure-map-search-fields-example.png "Primer polja za pretragu")</span><span class="sxs-lookup"><span data-stu-id="63302-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="63302-122">Izaberite **Primeni** da biste potvrdili svoje izbore.</span><span class="sxs-lookup"><span data-stu-id="63302-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="63302-123">Izaberite primarni ključ i semantički tip za atribute</span><span class="sxs-lookup"><span data-stu-id="63302-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="63302-124">Nakon izbora entiteta, na stranici **Mapa** se navode izabrani entiteti za pregled.</span><span class="sxs-lookup"><span data-stu-id="63302-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="63302-125">Definišite primarni ključ za entitet i identifikujte semantički tip za atribut u entitetu.</span><span class="sxs-lookup"><span data-stu-id="63302-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="63302-126">**Primarni ključ**: Izaberite jedan atribut kao primarni ključ za svaki vaš entitet.</span><span class="sxs-lookup"><span data-stu-id="63302-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="63302-127">Da bi atribut bio važeći primarni ključ, ne bi trebalo da sadrži duplirane vrednosti, nedostajuće vrednosti ili prazne vrednosti.</span><span class="sxs-lookup"><span data-stu-id="63302-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="63302-128">Atributi tipa podataka niska, ceo broj i GUID podržani su kao primarni ključevi i biće prikazani u polju za odabir.</span><span class="sxs-lookup"><span data-stu-id="63302-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="63302-129">**Semantički tip atributa**: Kategorije vaših atributa, kao što su adresa e-pošte ili ime.</span><span class="sxs-lookup"><span data-stu-id="63302-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="63302-130">Da biste koristili modele veštačke inteligencije za pametno predviđanje semantike, uštedite vreme i poboljšajte tačnost, podesite **Inteligentno mapiranje** na **Da**.</span><span class="sxs-lookup"><span data-stu-id="63302-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="63302-131">Inteligentno mapiranje ističe preporuke o semantici zasnovane na veštačkoj inteligenciji u polju **Tip**.</span><span class="sxs-lookup"><span data-stu-id="63302-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="63302-132">Ako ga podesite na **ISKLJUČENO**, videćete naše redovne preporuke za mapiranje.</span><span class="sxs-lookup"><span data-stu-id="63302-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="63302-133">Možete odabrati bilo koji semantički tip sa dostupne liste opcija i zameniti predloženi izbor.</span><span class="sxs-lookup"><span data-stu-id="63302-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63302-134">![Tip atributa i semantičko predviđanje](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Tip atributa i semantičko predviđanje")</span><span class="sxs-lookup"><span data-stu-id="63302-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="63302-135">Takođe je moguće dodati prilagođeni semantički tip.</span><span class="sxs-lookup"><span data-stu-id="63302-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="63302-136">Izaberite polje tipa za taj atribut i unesite svoje prilagođeno semantičko ime tipa.</span><span class="sxs-lookup"><span data-stu-id="63302-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="63302-137">Tako takođe možete da promenite vrste atributa koje je sistem identifikovao.</span><span class="sxs-lookup"><span data-stu-id="63302-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="63302-138">Svi atributi za koje je semantički tip automatski identifikovan grupisani su u odeljku **Pregled mapiranih polja**.</span><span class="sxs-lookup"><span data-stu-id="63302-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="63302-139">Pregledajte ove atribute i njihove semantičke tipove, jer će se koristiti za kombinovanje vaših entiteta u koraku objedinjavanja tokom ujednačavanja podataka.</span><span class="sxs-lookup"><span data-stu-id="63302-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="63302-140">Atributi koji nisu automatski mapirani u semantički tip grupisani su u odeljku **Definisanje podataka u nemapiranim poljima**.</span><span class="sxs-lookup"><span data-stu-id="63302-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="63302-141">Izaberite polje semantičkog tipa za nemapirane atribute ili unesite naziv prilagođenog tipa atributa.</span><span class="sxs-lookup"><span data-stu-id="63302-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="63302-142">![Primarni ključ i vrsta atributa](media/data-manager-configure-map-add-attributes.png "Primarni ključ i vrsta atributa")</span><span class="sxs-lookup"><span data-stu-id="63302-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="63302-143">Jedno polje bi trebalo da se mapira u semantički tip Person.FullName da bi se ime klijenta popunilo u korisničkoj kartici.</span><span class="sxs-lookup"><span data-stu-id="63302-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="63302-144">U suprotnom, kartice klijenata će se prikazivati bez imena.</span><span class="sxs-lookup"><span data-stu-id="63302-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="63302-145">Dodavanje i uklanjanje atributa i entiteta</span><span class="sxs-lookup"><span data-stu-id="63302-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="63302-146">U dijalogu **Ujednačavanje** > **Mapa**, izaberite **Uredi polja**.</span><span class="sxs-lookup"><span data-stu-id="63302-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="63302-147">U oknu **Uredi polja**, dodajte ili uklonite atribute i entitete.</span><span class="sxs-lookup"><span data-stu-id="63302-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="63302-148">Koristite pretragu ili listajte da biste pronašli i izabrali svoje atribute i entitete od interesa.</span><span class="sxs-lookup"><span data-stu-id="63302-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="63302-149">Ne možete ukloniti atribut ili entitet ako se već podudaraju.</span><span class="sxs-lookup"><span data-stu-id="63302-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="63302-150">![Dodajte ili uklonite atribute](media/configure-data-map-edit.png "Dodajte ili uklonite atribute")</span><span class="sxs-lookup"><span data-stu-id="63302-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="63302-151">Izaberite **Primeni**.</span><span class="sxs-lookup"><span data-stu-id="63302-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="63302-152">Dodavanje slika profilima</span><span class="sxs-lookup"><span data-stu-id="63302-152">Add images to profiles</span></span>

<span data-ttu-id="63302-153">Ako entitet sadrži URL adrese javno dostupnih slika ili logotipa profila, možete ih dodati u objedinjeni profil klijenta.</span><span class="sxs-lookup"><span data-stu-id="63302-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="63302-154">Izaberite entitet i pronađite polje koje sadrži URL do slike profila.</span><span class="sxs-lookup"><span data-stu-id="63302-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="63302-155">U polje za unos **Tip** ručno unesite sledeću vrednost:</span><span class="sxs-lookup"><span data-stu-id="63302-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="63302-156">Za osobu: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="63302-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="63302-157">Za organizaciju: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="63302-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="63302-158">Nastavite sa koracima objedinjavanja i uverite se da je atribut koji sadrži URL adresu slike takođe dodat u korak [Spajanje](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="63302-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="63302-159">Podešavanje atributa za organizacije</span><span class="sxs-lookup"><span data-stu-id="63302-159">Set attributes for organizations</span></span>

<span data-ttu-id="63302-160">Za organizacije (pregled), tip atributa treba da bude mapiran na „Organization.Name“</span><span class="sxs-lookup"><span data-stu-id="63302-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="63302-161">![Primarni ključ i vrsta atributa B2B](media/configure-data-map-edit-b2b.png "Primarni ključ i vrsta atributa B2B")</span><span class="sxs-lookup"><span data-stu-id="63302-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="63302-162">Sledeći korak</span><span class="sxs-lookup"><span data-stu-id="63302-162">Next step</span></span>

<span data-ttu-id="63302-163">Kao deo procesa objedinjavanja podataka, idite na stranicu **Podudaranje**.</span><span class="sxs-lookup"><span data-stu-id="63302-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="63302-164">Posetite članak [**Podudaranje**](match-entities.md) da biste više saznali o ovoj fazi.</span><span class="sxs-lookup"><span data-stu-id="63302-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="63302-165">Pogledajte sledeći video: [Prvi koraci: Kreiranje jedinstvenog profila klijenta](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="63302-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]