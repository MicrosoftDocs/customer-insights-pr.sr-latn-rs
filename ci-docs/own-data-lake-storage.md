---
title: Korišćenje sopstvenog Azure Data Lake Storage Gen2 naloga
author: mukeshpo
description: Saznajte više o zahtevima za korišćenje sopstvenog naloga Azure Data Lake Storage za skladištenje podataka "Uvidi kupaca".
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304398"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Korišćenje sopstvenog Azure Data Lake Storage Gen2 naloga

Dynamics 365 Customer Insights pruža opciju čuvanja svih podataka u programu [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction). Čuvanjem podataka u Data Lake Storage,slažete se da će podaci biti preneti i uskladišteni na odgovarajućoj geografskoj lokaciji za taj Azure nalog za skladištenje. Više informacija potražite u Microsoft [centru za pouzdanost](https://www.microsoft.com/trust-center).

Administratori u uvidima klijenata mogu da [kreiraju okruženja](create-environment.md) i [navedu opciju skladištenja podataka](create-environment.md#step-2-configure-data-storage) u tom procesu.

## <a name="prerequisites"></a>Preduslovi

- Azure Data Lake Storage konta moraju biti u istoj Azure oblasti koju ste izabrali prilikom kreiranja okruženja "Uvidi kupaca". Da biste znali region okruženja, idite na **Admin** > **System** > **About** in Customer Insights.
- Data Lake Storage nalog mora biti Gen2. Azure Data Lake Gen1 nalozi za skladištenje nisu podržani.
- Nalog za skladištenje u jezeru Data mora [hijerarhijski omogućen prostor za ime](/azure/storage/blobs/data-lake-storage-namespace).
- Imenovani kontejner `customerinsights` mora da postoji na nalogu za skladištenje. Kreirajte ga pre nego što upotrebite sopstveno skladište jezera podataka u uvidima kupaca.
- Administratoru koji podešava okruženje "Uvid u kupce" potrebna je uloga "Storage Blob Data saradnik" ili "Storage Blob Data Owner" na nalogu za skladištenje ili kontejneru`customerinsights`. Više informacija o dodeli dozvole na nalogu za skladištenje potražite u članku Kreiranje [naloga za skladištenje](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Povezivanje uvida klijenata sa nalogom za skladištenje

Kada kreirate novo okruženje, uverite se da nalog skladišta u jezeru podataka postoji i da li su ispunjeni svi preduslovi.

1. U koraku skladištenja **podataka** tokom kreiranja okruženja postavite podatke **za čuvanje** na **Azure Data Lake Storage Gen2**.
1. Odaberite način povezivanja **skladišta**. Možete da birate između opcije zasnovane na resursima i opcije zasnovane na pretplati za potvrdu identiteta. Više informacija potražite u članku [Povezivanje sa Azure Data Lake Storage nalogom pomoću direktora Azure usluge](connect-service-principal.md).
   - Za **Azure pretplatu** odaberite nalog **pretplate**, **grupe** resursa i **skladišta** koji sadrži `customerinsights` kontejner.
   - Za **ključ naloga** navedite ime **naloga** i ključ **naloga za** nalog skladišta u jezeru podataka. Korišćenje ovog metoda potvrde identiteta podrazumeva da budete informisani ako vaša organizacija rotira ključeve. Morate ažurirati [konfiguraciju okruženja](manage-environments.md#edit-an-existing-environment) novim ključem kada se rotira.
1. Odaberite da li želite da koristite Azure privatnu vezu da biste se povezali sa nalogom za skladištenje i [kreirali vezu sa privatnom vezom](security-overview.md#set-up-an-azure-private-link).

Kada se sistemski procesi kao što je unos podataka dovrše, sistem kreira odgovarajuće fascikle u nalogu za skladištenje. Datoteke sa podacima i model.json datoteke se kreiraju i dodaju u fascikle na osnovu naziva procesa.

Ako kreirate više okruženja usluge Customer Insights i odaberete da sačuvate izlazne entitete iz tih okruženja na svoj nalog za skladištenje, Customer Insights kreira zasebne fascikle za svako okruženje sa `ci_environmentID` u kontejneru.
