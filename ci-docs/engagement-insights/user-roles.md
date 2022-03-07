---
title: Uloge i dozvole
description: Pregled dostupnih uloga i dozvola za članove radnog prostora.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ccc6a1b87b4cc28701e276b6e35432356e7647c4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227556"
---
# <a name="roles-and-permissions"></a>Uloge i dozvole

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Radni prostor je mesto gde skladištite i upravljajte događajima i izveštajima. Za više informacija pogledajte [Kreiranje radnog prostora i dodavanje članova](create-workspace.md). 

Radni prostor može da sadrži sledeće uloge i dozvole:

- Uloge *Član* su korisnici koji mogu pristupiti radnom prostoru. Možete da dodelite članove svom radnom prostoru i da definišete njihove uloge i dozvole. 
- Uloge *Administrator* upravljaju radnim prostorima i okruženjima i konfigurišu uvide u angažovanje za druge korisnike. 
- Uloge *Saradnik* su namenjene analitičarima koji ne moraju da konfigurišu uvide u angažovanje, već žele da kreiraju sopstvene izveštaje, tokove prodaje ili segmente.

## <a name="permissions"></a>Dozvole
  
Sledeća tabela identifikuje dozvole za svaku ulogu. 

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
