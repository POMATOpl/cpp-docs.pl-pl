---
description: 'Dowiedz się więcej na temat: platform:: Collections, przestrzeń nazw'
title: 'Platform:: Collections, przestrzeń nazw'
ms.date: 01/18/2018
ms.topic: reference
f1_keywords:
- collection/Platform::Collections
helpviewer_keywords:
- Platform::Collections Namespace
ms.assetid: b5042864-5f22-40b7-b7a5-c0691f65cc47
ms.openlocfilehash: d80479ed73183450dedd86119dda2da1fab800e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340414"
---
# <a name="platformcollections-namespace"></a>Platform:: Collections, przestrzeń nazw

Przestrzeń nazw platform:: Collections zawiera `Map` `MapView` klasy,, `Vector` i `VectorView` . Te klasy to konkretne implementacje odpowiednich interfejsów, które są zdefiniowane w przestrzeni nazw [Windows:: Foundation:: Collections](/uwp/api/windows.foundation.collections) . Typy konkretnych kolekcji nie są przenośne przez ABI (na przykład gdy program JavaScript lub C# wywołuje składnik C++), ale są niejawnie konwertowane na odpowiednie typy interfejsów. Na przykład w przypadku zaimplementowania metody publicznej, która wypełnia i zwraca kolekcję, użyj funkcji [platform:: Collections:: Vector](../cppcx/platform-collections-vector-class.md) w celu zaimplementowania kolekcji wewnętrznie i użyj funkcji [Windows:: Foundation:: Collections:: IVector](/uwp/api/windows.foundation.collections.ivector-1) jako typu zwracanego. Aby uzyskać więcej informacji, zobacz [kolekcje](../cppcx/collections-c-cx.md) i [Tworzenie składników Środowisko wykonawcze systemu Windows w języku C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

Można skonstruować platformę:: Collections:: Vector z [klasy std:: Vector](../standard-library/vector-class.md) i [platform:: Collections:: map](../cppcx/platform-collections-map-class.md) z wartości [std:: map](../standard-library/map-class.md).

Ponadto przestrzeń nazw platform:: Collections zapewnia obsługę wstawień INSERT i iteratorów wejściowych oraz `Vector` `VectorView` iteratorów.

`#include`Aby używać typów w przestrzeni nazw platform:: Collections, należy uwzględnić () nagłówek Collection. h.

## <a name="syntax"></a>Składnia

```cpp
#include <collection.h>
using namespace Platform::Collections;
```

### <a name="members"></a>Elementy członkowskie

Ta przestrzeń nazw zawiera następujących członków.

|Nazwa|Opis|
|----------|-----------------|
|[Platform:: Collections:: BackInsertIterator, Klasa](../cppcx/platform-collections-backinsertiterator-class.md)|Reprezentuje iterator, który wstawia element na końcu kolekcji.|
|[Platform:: Collections:: InputIterator, Klasa](../cppcx/platform-collections-inputiterator-class.md)|Reprezentuje iterator, który wstawia element na początku kolekcji.|
|[Platform:: Collections:: map, Klasa](../cppcx/platform-collections-map-class.md)|Reprezentuje modyfikowalną kolekcję par klucz-wartość, do których uzyskuje dostęp klucz. Podobne do [std:: map](../standard-library/map-class.md).|
|[Platform:: Collections:: MapView, Klasa](../cppcx/platform-collections-mapview-class.md)|Reprezentuje kolekcję par klucz-wartość, do których dostęp jest uzyskiwany za pomocą klucza.|
|[Platform:: Collections:: Vector, Klasa](../cppcx/platform-collections-vector-class.md)|Przedstawia modyfikowalną sekwencję elementów. Podobne do [std:: Vector](../standard-library/vector-class.md).|
|[Platform:: Collections:: VectorIterator, Klasa](../cppcx/platform-collections-vectoriterator-class.md)|Reprezentuje iterator, który przechodzi przez `Vector` kolekcję.|
|[Platform:: Collections:: VectorView, Klasa](../cppcx/platform-collections-vectorview-class.md)|Reprezentuje sekwencję elementów tylko do odczytu.|
|[Platform:: Collections:: VectorViewIterator, Klasa](../cppcx/platform-collections-vectorviewiterator-class.md)|Reprezentuje iterator, który przechodzi przez `VectorView` kolekcję.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[Przestrzeń nazw platformy](../cppcx/platform-namespace-c-cx.md)

### <a name="requirements"></a>Wymagania

**Metadane:** obiekt platform. winmd

**Przestrzeń nazw:** Platform:: Collections

**Opcja kompilatora:** /zw

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw platformy](../cppcx/platform-namespace-c-cx.md)
