---
description: 'Dowiedz się więcej o: śledzenie'
title: Trackery
ms.date: 11/04/2016
helpviewer_keywords:
- trackers [MFC]
- OLE applications [MFC], trackers
- applications [OLE], trackers
- tracking OLE items [MFC]
- OLE containers [MFC], trackers
- CDC class [MFC], trackers
- CRectTracker class [MFC], implementing trackers
- OLE server applications [MFC], trackers
ms.assetid: dcd09399-6637-4621-80e5-d12670429787
ms.openlocfilehash: e82766ecfabf2b5ebb0147b9f2c462f3b4460869
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264250"
---
# <a name="trackers"></a>Trackery

Klasa [CRectTracker](../mfc/reference/crecttracker-class.md) udostępnia interfejs użytkownika między prostokątnymi elementami aplikacji a użytkownikiem, dostarczając różne style wyświetlania. Te style obejmują obramowania stałe, kreskowane lub kreskowane; wzorzec rozkreskowany, który obejmuje element; i Zmień rozmiar uchwytów, które mogą znajdować się na zewnątrz lub wewnątrz obramowania. Śledzenie są często używane w połączeniu z elementami OLE, czyli obiektami pochodnymi z `COleClientItem` . Prostokąty śledzenia dają wizualne podpowiedzi dotyczące bieżącego stanu elementu.

Przykład [OCLIENT](../overview/visual-cpp-samples.md) MFC OLE ilustruje typowy interfejs przy użyciu elementów śledzących i klienta OLE z punktu widzenia aplikacji kontenera. Aby zapoznać się z różnymi stylami i możliwościami obiektu śledzenia, zobacz Ogólne przykładowe [śledzenie](../overview/visual-cpp-samples.md)MFC.

Aby uzyskać więcej informacji na temat implementowania programu śledzącego w aplikacji OLE, zobacz [śledzące: implementowanie śledzenia w aplikacji OLE](../mfc/trackers-implementing-trackers-in-your-ole-application.md)

## <a name="see-also"></a>Zobacz też

[OLE](../mfc/ole-in-mfc.md)<br/>
[Klasa COleClientItem](../mfc/reference/coleclientitem-class.md)
