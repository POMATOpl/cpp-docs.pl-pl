---
description: 'Dowiedz się więcej o: implementowanie interfejsu obsługi zdarzeń'
title: Implementowanie interfejsu obsługi zdarzeń
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, event handling
- event handling, ATL
- interfaces, event and event sink
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
ms.openlocfilehash: 109fbb1fbdd4f18d0eb4c295fbc08de2b7cc3a35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152766"
---
# <a name="implementing-the-event-handling-interface"></a>Implementowanie interfejsu obsługi zdarzeń

ATL ułatwia wszystkie trzy elementy wymagane do obsługi zdarzeń: implementowanie interfejsu zdarzenia, doradzanie źródłem zdarzenia i niedoradzanie źródła zdarzeń. Dokładne kroki, które należy wykonać, zależą od typu interfejsu zdarzenia oraz wymagań dotyczących wydajności aplikacji.

Najczęstszym sposobem implementacji interfejsu przy użyciu biblioteki ATL są:

- Bezpośrednie wyprowadzanie z interfejsu niestandardowego.

- Wyprowadzanie z [IDispatchImpl](../atl/reference/idispatchimpl-class.md) dla podwójnych interfejsów opisanych w bibliotece typów.

- Wyprowadzanie z [IDispEventImpl](../atl/reference/idispeventimpl-class.md) dla dispinterfaces opisanego w bibliotece typów.

- Wyprowadzanie z [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) dla dispinterfaces nie zostało opisane w bibliotece typów lub w celu zwiększenia wydajności przez nie załadowania informacji o typie w czasie wykonywania.

W przypadku implementowania niestandardowego lub podwójnego interfejsu należy zalecić Źródło zdarzenia przez wywołanie [AtlAdvise](reference/connection-point-global-functions.md#atladvise) lub [CComPtrBase:: Advise](../atl/reference/ccomptrbase-class.md#advise). Trzeba będzie śledzić plik cookie zwracany przez wywołanie samodzielnie. Wywołaj [AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise) , aby przerwać połączenie.

Jeśli wdrażasz dispinterface przy użyciu `IDispEventImpl` lub `IDispEventSimpleImpl` , należy zalecić Źródło zdarzenia, wywołując [IDispEventSimpleImpl::D ispeventadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise). Wywołaj [IDispEventSimpleImpl::D ispeventunadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise) , aby przerwać połączenie.

Jeśli używasz `IDispEventImpl` jako klasy bazowej kontrolki złożonej, w źródłach zdarzeń wymienionych na mapie ujścia zostanie zadoradzane i niezalecane automatyczne użycie [CComCompositeControl:: AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).

`IDispEventImpl`Klasy i `IDispEventSimpleImpl` zarządzają plikiem cookie.

## <a name="see-also"></a>Zobacz też

[Obsługa zdarzeń](../atl/event-handling-and-atl.md)
