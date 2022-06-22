---
title: Korišćenje sopstvenog Azure Data Lake Storage Gen2 naloga
author: mukeshpo
description: Saznajte više o zahtevima za korišćenje sopstvenog naloga Azure Data Lake Storage za skladištenje podataka "Uvidi kupaca".
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5acb58906c1a9db54337f3b4dc2ab7891db7954e
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011950"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Korišćenje sopstvenog Azure Data Lake Storage Gen2 naloga

Dynamics 365 Customer Insights pruža opciju čuvanja svih podataka u programu [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

Čuvanjem podataka u Data Lake Storage,slažete se da će podaci biti preneti i uskladišteni na odgovarajućoj geografskoj lokaciji za taj Azure nalog za skladištenje. Više informacija potražite u Microsoft [centru za pouzdanost](https://www.microsoft.com/trust-center).

Administratori u uvidima klijenata mogu da [kreiraju okruženja](create-environment.md) i [navedu opciju skladištenja podataka](create-environment.md#step-2-configure-data-storage) u tom procesu.

## <a name="prerequisites-to-use-your-storage-account"></a>Preduslovi za korišćenje naloga za skladištenje

- Azure Data Lake Storage konta moraju biti u istoj Azure oblasti koju ste izabrali prilikom kreiranja okruženja "Uvidi kupaca". Oblast okruženja "Uvidi kupaca" možete proveriti u okviru stavke **Osnovni podaci o sistemu** > **·** > **administratora**.
- Skladište jezera podataka mora biti Gen2 i [hijerarhijski prostor za ime](/azure/storage/blobs/create-data-lake-storage-account). Gen1 nalozi za skladištenje nisu podržani.
- Imenovani kontejner `customerinsights` mora da postoji na nalogu za skladištenje. Morate da ga kreirate pre nego što koristite sopstveno skladište Data Lake u uvidima kupaca. Administratoru koji podešava okruženje "Uvid u kupce" potrebna je uloga "Storage Blob Data saradnik" ili "Storage Blob Data Owner" na nalogu za skladištenje ili kontejneru`customerinsights`. Više informacija o dodeli dozvole na nalogu za skladištenje potražite u članku Kreiranje [naloga za skladištenje](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Povezivanje uvida klijenata sa nalogom za skladištenje

Kada kreirate novo okruženje, uverite se da nalog skladišta u jezeru podataka postoji i da li su ispunjeni svi preduslovi.

1. U koraku skladištenja **podataka** tokom kreiranja okruženja postavite podatke **za čuvanje** na **Azure Data Lake Storage Gen2**.
1. Odaberite način povezivanja **skladišta**. Možete da birate između opcije zasnovane na resursima i opcije zasnovane na pretplati za potvrdu identiteta. Više informacija potražite u članku [Povezivanje sa Azure Data Lake Storage nalogom pomoću direktora Azure usluge](connect-service-principal.md).
   - Za **Azure pretplatu** odaberite nalog **pretplate**, **grupe** resursa i **skladišta** koji sadrži `customerinsights` kontejner.
   - Za **ključ naloga** navedite ime **naloga** i ključ **naloga za** nalog skladišta u jezeru podataka. Korišćenje ovog metoda potvrde identiteta podrazumeva da budete informisani ako vaša organizacija rotira ključeve. Morate ažurirati [konfiguraciju okruženja](manage-environments.md#edit-an-existing-environment) novim ključem kada se rotira.
1. Odaberite da li želite da koristite Azure privatnu vezu da biste se povezali sa nalogom za skladištenje [i kreirali vezu sa privatnom](security-overview.md#private-links-tab) vezom sa procesom u dva koraka.

Kada se sistemski procesi kao što je unos podataka dovrše, sistem kreira odgovarajuće fascikle u nalogu za skladištenje. Datoteke sa podacima i *model.json* datoteke se kreiraju i dodaju u fascikle na osnovu naziva procesa.

Ako kreirate više okruženja usluge Customer Insights i odaberete da sačuvate izlazne entitete iz tih okruženja na svoj nalog za skladištenje, Customer Insights kreira zasebne fascikle za svako okruženje sa `ci_environmentID` u kontejneru.
