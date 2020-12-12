---
description: 'Dowiedz się więcej na temat: klasy punktów połączenia'
title: Klasy punktów połączenia (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- classes [C++], connection points
- connection points classes
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
ms.openlocfilehash: 28d41f15aeafd98c8c9bcac27fde25d0b2037765
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148242"
---
# <a name="connection-points-classes"></a>Klasy punktów połączenia

Następujące klasy zapewniają obsługę punktów połączenia:

- [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) Implementuje kontener punktu połączenia.

- [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) Implementuje punkt połączenia.

- [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) Implementuje punkt połączenia reprezentujący Interfejs [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) .

- [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) Zarządza nieograniczoną liczbą połączeń między punktem połączenia a jego ujściam.

- [CComUnkArray](../atl/reference/ccomunkarray-class.md) Zarządza stałą liczbą połączeń między punktem połączenia a jego ujściam.

- [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) Powiadamia ujścia klienta o zmianie właściwości obiektu lub o zmianie.

- [IDispEventImpl](../atl/reference/idispeventimpl-class.md) Zapewnia obsługę punktów połączenia dla obiektu ATL COM. Te punkty połączenia są mapowane na mapę ujścia zdarzeń, która jest dostarczana przez obiekt COM.

- [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) Działa w połączeniu z mapą ujścia zdarzeń w klasie w celu kierowania zdarzeń do odpowiedniej funkcji obsługi.

## <a name="related-articles"></a>Powiązane artykuły

[Punkty połączenia](../atl/atl-connection-points.md)

[Obsługa zdarzeń i ATL](../atl/event-handling-and-atl.md)

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../atl/atl-class-overview.md)<br/>
[Makra punktów połączenia](../atl/reference/connection-point-macros.md)<br/>
[Funkcje globalne punktu połączenia](../atl/reference/connection-point-global-functions.md)
