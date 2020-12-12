---
description: 'Dowiedz się więcej na temat: Controls: ogólne klasy pomocy technicznej'
title: 'Formanty ATL: ogólne klasy pomocy technicznej'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- controls [ATL]
- general support classes
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
ms.openlocfilehash: a5b147ef2b30f0cc209fdfdabd52b59d7112c475
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148216"
---
# <a name="controls-general-support-classes"></a>Kontrolki: ogólne klasy pomocy technicznej

Następujące klasy zapewniają ogólną obsługę formantów ATL:

- [CComControl](../atl/reference/ccomcontrol-class.md) Składa się z funkcji pomocnika i składowych danych, które są niezbędne dla formantów ATL.

- [IOleControlImpl](../atl/reference/iolecontrolimpl-class.md) Zapewnia metody niezbędne do kontroli.

- [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) Zapewnia podstawowe metody, za pomocą których kontener komunikuje się z kontrolką. Zarządza aktywacją i dezaktywacją formantów w miejscu.

- [IQuickActivateImpl](../atl/reference/iquickactivateimpl-class.md) Łączy inicjalizację w jedno wywołanie, aby ułatwić kontenery, unikając opóźnień podczas ładowania formantów.

- [IPointerInactiveImpl](../atl/reference/ipointerinactiveimpl-class.md) Zapewnia minimalną interakcję myszy dla nieaktywnej kontrolki w przeciwnym razie.

## <a name="sample-program"></a>Przykładowy program

[ATLFire](../overview/visual-cpp-samples.md)

## <a name="related-articles"></a>Powiązane artykuły

[Samouczek ATL](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../atl/atl-class-overview.md)
