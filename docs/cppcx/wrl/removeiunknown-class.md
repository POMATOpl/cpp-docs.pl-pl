---
description: 'Dowiedz się więcej na temat: Klasa RemoveIUnknown'
title: RemoveIUnknown — Klasa
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
ms.openlocfilehash: 0ef00ee9859a27252550aaeec6fb9b4f9ef2d5b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278730"
---
# <a name="removeiunknown-class"></a>RemoveIUnknown — Klasa

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
template <typename T>
struct RemoveIUnknown;

template <typename T>
class RemoveIUnknown : public T;
```

### <a name="parameters"></a>Parametry

*T*<br/>
Klasa.

## <a name="remarks"></a>Uwagi

Tworzy typ, który jest odpowiednikiem `IUnknown` typu opartego na typie, ale ma funkcje niewirtualne `QueryInterface` `AddRef` i `Release` składowe.

Domyślnie metody COM zapewniają `QueryInterface` metody wirtualne, `AddRef` i `Release` . `ComPtr`Nie wymaga jednak nakładów związanych z metodami wirtualnymi. `RemoveIUnknown` Eliminuje to narzuty, zapewniając prywatne, niewirtualne `QueryInterface` `AddRef` i `Release` metody.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|`ReturnType`|Synonim dla typu, który jest odpowiednikiem parametru szablonu *T* , ale ma niewirtualne `IUnknown` składowe.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`T`

`RemoveIUnknown`

## <a name="requirements"></a>Wymagania

**Nagłówek:** Client. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL::D etails — przestrzeń nazw](microsoft-wrl-details-namespace.md)
