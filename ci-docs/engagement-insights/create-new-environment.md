---
title: Kreirajte novo okruženje
description: Svrha okruženja i kako da kreirate novo.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 5e301b4ff0a7586fb143b154b773791b3bd645b7
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: sr-Latn-RS
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648134"
---
# <a name="create-a-new-environment"></a>Kreirajte novo okruženje 

## <a name="overview"></a>Pregled

Okruženje je prostor u kojem upravljate svojim radnim prostorima i vezama. Način na koji koristite okruženja zavisi od vaše organizacije i slučaja upotrebe. Na primer, možete da kreirate:

- Jedno okruženje.
- Zasebna okruženja za testiranje i proizvodnju.
- Zasebna okruženja za određene timove ili odeljenja u vašoj organizaciji koja sadrže relevantne događaje za svaku ciljnu grupu.
- Zasebna okruženja za različite globalne ogranke vaše kompanije.
- Veze sa Customer Insights mogućnošću uvida u ciljnu grupu.

## <a name="create-a-new-environment"></a>Kreirajte novo okruženje

1. Na desnoj strani glavnog banera izaberite birač okruženja, a zatim **+Novo**.

   :::image type="content" source="media/environment-picker.png" alt-text="Izaberite birač okruženja.":::

1. U oknu **Podešavanja**, unesite **Naziv okruženja**.

1. Odaberite **Tip** naloga, u zavisnosti od tipa plana.

1. Odaberite **Region** i izaberite **Dalje**. 

1. Unesite **Naziv radnog prostora**, koji vam omogućava prikupljanje podataka za određene veb-lokacije ili aplikacije. Više informacija potražite u članku [Kreiranje radnog prostora](create-workspace.md).

1. Odaberite **Tip radnog prostora** (veb ili mobilni) koji želite da kreirate. 

1. Izaberite **Prikaži napredna podešavanja** da biste omogućili ili onemogućili ova opciona podešavanja:

   - Prebacite **Nepoznato u poznato** na „omogućeno“ za povezivanje veb-događaja sa korisnicima koji su prethodno izvršili potvrdu identiteta. Za više informacija pogledajte [Prepoznavanje veb-događaja posetilaca koji su prethodno izvršili potvrdu identiteta](unknown-to-known.md)
   - Prebacite **Filtriraj saobraćaj robota** na „omogućeno“ za uklanjanje veb-saobraćaja robota za ovaj radni prostor. 

1. Izaberite **Dovrši** kada završite. 

1. Instalirajte isečak koda da biste počeli da primate podatke, a zatim izaberite **Završi** za kreiranje radnog prostora. Za više informacija, pogledajte [Pregled resursa za programere](developer-resources.md).

> [!NOTE]
> Sada možete dodati članove i dodeliti im nivo dozvola sa liste **Uloga**. Za više informacija pogledajte [Uloge i dozvole](user-roles.md). 

Za više informacija pogledajte [Upravljanje okruženjima i radnim prostorima](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Rad sa novim okruženjem

- [Kreirajte radni prostor](../engagement-insights/create-workspace.md) i dodajte članove.
- [Dodajte kod svojoj veb-lokaciji](../engagement-insights/instrument-website.md) ili [aplikaciji za mobilne uređaje](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Prikažite [izveštaj u realnom vremenu](../engagement-insights/view-reports.md) ili kreirajte [prilagođene izveštaje](../engagement-insights/custom-reports.md).
- [Kreirajte prečišćene događaje](../engagement-insights/refined-events.md) za izvoz.
- [Izvezite podatke](../engagement-insights/export-events.md) u Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
