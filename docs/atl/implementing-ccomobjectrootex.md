---
description: 'Dowiedz się więcej o: implementowanie CComObjectRootEx'
title: Implementowanie klasy CComObjectRootEx
ms.date: 11/04/2016
helpviewer_keywords:
- CComObjectRoot class, implementing
- CComObjectRootEx class
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
ms.openlocfilehash: 235d10a8c390311230057da5dda11e5a8f093445
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152844"
---
# <a name="implementing-ccomobjectrootex"></a>Implementowanie klasy CComObjectRootEx

[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) jest istotna; wszystkie obiekty ATL muszą mieć jedno wystąpienie `CComObjectRootEx` lub [klasy CComObjectRoot](../atl/reference/ccomobjectroot-class.md) w dziedziczeniu. `CComObjectRootEx` zapewnia domyślny `QueryInterface` mechanizm oparty na wpisach mapy com.

Za pomocą swojej mapy COM interfejsy obiektu są udostępniane klientowi, gdy klient wysyła zapytanie dotyczące interfejsu. Zapytanie jest wykonywane przez `CComObjectRootEx::InternalQueryInterface` . `InternalQueryInterface` obsługuje tylko interfejsy w tabeli mapy COM.

Możesz wprowadzić interfejsy w tabeli mapy modelu COM za pomocą makra [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry) lub jednego z jego wariantów. Na przykład poniższy kod wprowadza interfejsy `IDispatch` , `IBeeper` , i `ISupportErrorInfo` do tabeli mapy com:

[!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]

## <a name="see-also"></a>Zobacz też

[Podstawowe informacje o obiektach COM ATL](../atl/fundamentals-of-atl-com-objects.md)<br/>
[Makra mapy modelu COM](../atl/reference/com-map-macros.md)
