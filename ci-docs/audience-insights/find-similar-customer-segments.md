---
title: Pronađite slične klijente pomoću AI
description: Pronađite slične segmente klijenta pomoću veštačke inteligencije.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406808"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="833dc-103">Slični kupci (verzija za pregled)</span><span class="sxs-lookup"><span data-stu-id="833dc-103">Similar Customers (preview)</span></span>

<span data-ttu-id="833dc-104">Ova funkcija vam omogućava da pronađete slične klijente u svojoj korisničkoj bazi koristeći veštačku inteligenciju.</span><span class="sxs-lookup"><span data-stu-id="833dc-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="833dc-105">Da biste koristili ovu funkciju, morate da imate bar jedan kreiran segment.</span><span class="sxs-lookup"><span data-stu-id="833dc-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="833dc-106">Proširenje kriterijuma postojećeg segmenta pomaže u pronalaženju klijenata koji su slični tom segmentu.</span><span class="sxs-lookup"><span data-stu-id="833dc-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="833dc-107">*Pronađite slične kupce* koristi automatizovana sredstva za procenu podataka i pravljenje predviđanja na osnovu tih podataka, pa se zato može koristiti kao način profilisanja, termin koji je definisan Opštom uredbom o zaštiti podataka („GDPR“).</span><span class="sxs-lookup"><span data-stu-id="833dc-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="833dc-108">Klijentovo korišćenje ove funkcije za obradu podataka može da bude podložno GDPR-u ili drugim zakonima ili propisima.</span><span class="sxs-lookup"><span data-stu-id="833dc-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="833dc-109">Odgovorni ste za to da koristite Dynamics 365 Customer Insights, uključujući predviđanja, u skladu sa svim važećim zakonima i propisima, uključujući zakone koji se odnose na privatnost, lične podatke, biometrijske podatke, zaštitu podataka i poverljivost komunikacija.</span><span class="sxs-lookup"><span data-stu-id="833dc-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="833dc-110">Pronalaženje sličnih klijenata</span><span class="sxs-lookup"><span data-stu-id="833dc-110">Finding similar customers</span></span>

1. <span data-ttu-id="833dc-111">U uvidima o korisnicima idite na **Segmenti** i izaberite segment na kojem želite da zasnivate novi segment.</span><span class="sxs-lookup"><span data-stu-id="833dc-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="833dc-112">To je vaš *izvorni segment*.</span><span class="sxs-lookup"><span data-stu-id="833dc-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="833dc-113">Na traci radnji izaberite **Pronađi slične kupce**.</span><span class="sxs-lookup"><span data-stu-id="833dc-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="833dc-114">Pregledajte predloženi naziv za svoj novi segment i promenite ga ako je potrebno.</span><span class="sxs-lookup"><span data-stu-id="833dc-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="833dc-115">Pregledajte polja koja definišu vaš novi segment.</span><span class="sxs-lookup"><span data-stu-id="833dc-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="833dc-116">Ova polja definišu osnovu na kojoj će sistem pokušati da nađe kupce slične vašem izvornom segmentu.</span><span class="sxs-lookup"><span data-stu-id="833dc-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="833dc-117">Sistem će podrazumevano izabrati preporučena polja.</span><span class="sxs-lookup"><span data-stu-id="833dc-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="833dc-118">Polja koja mogu značajno smanjiti performanse modela automatski se isključuju:</span><span class="sxs-lookup"><span data-stu-id="833dc-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="833dc-119">Polja sa sledećim tipovima podataka: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="833dc-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="833dc-120">Polja sa kardinalnošću (broj elemenata u polju) manjom od 2 ili više od 30</span><span class="sxs-lookup"><span data-stu-id="833dc-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="833dc-121">Izaberite da li želite da uključite **Sve kupce** ili samo neke kupce u **Specifični postojeći segment** u vašem novom segmentu.</span><span class="sxs-lookup"><span data-stu-id="833dc-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="833dc-122">Isključite kupce iz svog izvornog segmenta izborom polja za potvrdu **Izuzmi sve iz izvornog segmenta**.</span><span class="sxs-lookup"><span data-stu-id="833dc-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="833dc-123">Sistem podrazumevano predlaže da u izlaznu vrednost uključite samo 20% ciljne grupe.</span><span class="sxs-lookup"><span data-stu-id="833dc-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="833dc-124">Uredite ovu graničnu vrednost po potrebi.</span><span class="sxs-lookup"><span data-stu-id="833dc-124">Edit this threshold as needed.</span></span> <span data-ttu-id="833dc-125">Povećanje granične vrednosti će smanjiti preciznost.</span><span class="sxs-lookup"><span data-stu-id="833dc-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="833dc-126">Izaberite **Pokreni** u dnu stranice da biste započeli zadatak binarne klasifikacije (vid mašinskog učenja) koji analizira skup podataka.</span><span class="sxs-lookup"><span data-stu-id="833dc-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="833dc-127">Prižažite sličan segment</span><span class="sxs-lookup"><span data-stu-id="833dc-127">View the similar segment</span></span>

<span data-ttu-id="833dc-128">Nakon obrade sličnog segmenta, novi segment ćete naći navedenog stranici **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="833dc-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="833dc-129">![Segment sličnih klijenata](media/expanded-segment.png "Segment sličnih klijenata")</span><span class="sxs-lookup"><span data-stu-id="833dc-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="833dc-130">Izaberite **Prikaži** na traci sa radnjama da biste otvorili detalje segmenta.</span><span class="sxs-lookup"><span data-stu-id="833dc-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="833dc-131">Ovaj prikaz sadrži informacije o raspodeli rezultata kroz [ocene sličnosti](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="833dc-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="833dc-132">Takođe ćete naći sličnosti u vrednostima rezultata u **Pregled članova segmenta**.</span><span class="sxs-lookup"><span data-stu-id="833dc-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="833dc-133">Koristite izlaz sličnog segmenta</span><span class="sxs-lookup"><span data-stu-id="833dc-133">Use the output of a similar segment</span></span>

<span data-ttu-id="833dc-134">Možete da [radite sa izlaznom vrednošću sličnog segmenta](segments.md) kao i kod drugih segmenata.</span><span class="sxs-lookup"><span data-stu-id="833dc-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="833dc-135">Na primer, izveite segment ili izgradite meru.</span><span class="sxs-lookup"><span data-stu-id="833dc-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="833dc-136">Osvežite i uredite sličan segment</span><span class="sxs-lookup"><span data-stu-id="833dc-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="833dc-137">Da biste osvežili sličan segment, izaberite ga na stranici **Segmenti**, a zatim izaberite **Osveži** sa trake radnji.</span><span class="sxs-lookup"><span data-stu-id="833dc-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="833dc-138">Uređivanjem sličnog segmenta ponovo ćete obraditi vaše podatke.</span><span class="sxs-lookup"><span data-stu-id="833dc-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="833dc-139">Prethodno kreiran segment se ažurira uz osvežene podatke.</span><span class="sxs-lookup"><span data-stu-id="833dc-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="833dc-140">Da biste uredili sličan segment, izaberite ga na stranici **Segmenti**, a zatim izaberite **Uredi** sa trake radnji.</span><span class="sxs-lookup"><span data-stu-id="833dc-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="833dc-141">Primenite promene i izaberite **Pokreni** da biste započeli obradu.</span><span class="sxs-lookup"><span data-stu-id="833dc-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="833dc-142">Izbrišite sličan segment</span><span class="sxs-lookup"><span data-stu-id="833dc-142">Delete a similar segment</span></span>

<span data-ttu-id="833dc-143">Izaberite segment na stranici **Segmenti**, a zatim izaberite **Izbriši** sa trake radnji.</span><span class="sxs-lookup"><span data-stu-id="833dc-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="833dc-144">Zatim potvrdite brisanje.</span><span class="sxs-lookup"><span data-stu-id="833dc-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="833dc-145">O ocenama sličnosti</span><span class="sxs-lookup"><span data-stu-id="833dc-145">About similarity scores</span></span>

<span data-ttu-id="833dc-146">Model mašinskog učenja binarne klasifikacije dodeljuje rezultat kupcima u sličnom segmentu.</span><span class="sxs-lookup"><span data-stu-id="833dc-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="833dc-147">Rezultat je zasnovan na sličnosti sa kupcima u izvornom segmentu.</span><span class="sxs-lookup"><span data-stu-id="833dc-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="833dc-148">Rezultati sličnosti ispod 0,55 su kupci koje je sistem klasifikovo kao *nije slično* sa kupcima u izvornom segmentu</span><span class="sxs-lookup"><span data-stu-id="833dc-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="833dc-149">Rezultati sličnosti između 0,55 - 0,7 klasifikovani su kao *pomalo slično*</span><span class="sxs-lookup"><span data-stu-id="833dc-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="833dc-150">Rezultati sličnosti između 0,7 - 0,85 klasifikovani su kao *slično*</span><span class="sxs-lookup"><span data-stu-id="833dc-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="833dc-151">Rezultati sličnosti između 0,85 - 1 su kupci koje je sistem klasifikovo *vrlo slično*</span><span class="sxs-lookup"><span data-stu-id="833dc-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="833dc-152">Kupci sa rezultatima sličnosti ispod 0,4 nisu uključeni u izlaznu vrednost modela.</span><span class="sxs-lookup"><span data-stu-id="833dc-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="833dc-153">Sistem ih ne smatra dovoljno sličnim izvornim segmentima.</span><span class="sxs-lookup"><span data-stu-id="833dc-153">The system doesn't consider them similar enough to the source segment.</span></span>
