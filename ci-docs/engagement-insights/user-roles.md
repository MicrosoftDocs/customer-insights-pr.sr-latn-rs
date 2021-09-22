---
title: Uloge i dozvole
description: Pregled dostupnih uloga i dozvola za članove radnog prostora.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036710"
---
# <a name="roles-and-permissions"></a>Uloge i dozvole

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Radni prostor je način na koji skladištite i upravljate događajima i izveštajima. Član je korisnik koji može pristupiti radnom prostoru. Možete da dodelite članove svom radnom prostoru i da definišete njihove uloge i dozvole. Uloge administratora upravljaju radnim prostorima i okruženjima i konfigurišu uvide u angažovanje za druge korisnike. Uloge saradnika namenjene su analitičarima koji ne moraju da konfigurišu uvide u angažovanje, već žele da kreiraju sopstvene izveštaje, tokove prodaje ili segmente.

## <a name="permissions"></a>Dozvole
  
Sledeći grafikon identifikuje dozvole za svaku ulogu. 

| Dozvola | Administrator okruženja | Administrator radnog prostora | Saradnik na okruženju | Saradnik na radnom prostoru | 
|--|--|--|--|--|
| Kreiranje okruženja (autor automatski postaje administrator okruženja) | X* | X* | X* | X* |  
| Konfigurisanje okruženja (članovi okruženja, brisanje okruženja) | X |  |  |  |  
| Kreiranje radnih prostora | X |  |  |  |  
| Konfigurisanje radnih prostora (članova radnog prostora, brisanje radnog prostora) | X | X |  |  |  
| Konfigurisanje događaja i prečišćenih događaja | X | X | |  |  
| Prikaz događaja radnog prostora i prečišćenih događaja | X | X | |  |  
| Prikaz resursa radnog prostora (izveštaji, segmenti i metrika)| X | X | X | X |  
| Kreiranje prilagođenih izveštaja i tokova prodaje | X | X | X | X |  
| Kreiranje osnovnih pokazatelja i aspekata| X | X |  |  |  
| Kreiranje segmenata| X | X | X | X |  

*Može samo da kreira probna okruženja u verziji za pregled. 

## <a name="add-members"></a>Dodajte članove

Možete da dodajete i uklanjate članove iz radnih prostora i okruženja. Za više informacija pogledajte [Okruženja i radni prostori](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
