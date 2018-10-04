---
title: Synchronizuj (atrybut C++ COM) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.synchronize
dev_langs:
- C++
helpviewer_keywords:
- synchronize attribute
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 740d99bfbc0da4c290a09a95f5d4f8f227a11fc8
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789637"
---
# <a name="synchronize"></a>synchronize

Synchronizuje dostęp do metody docelowej.

## <a name="syntax"></a>Składnia

```cpp
[synchronize]
```

## <a name="remarks"></a>Uwagi

**Zsynchronizować** atrybut C++ zapewnia obsługę synchronizacji metodę docelowego obiektu. Synchronizacja umożliwia wielu obiektów, które korzystają z typowych zasobu (np. metody klasy) poprzez kontrolowanie dostępu do metody docelowej.

Kod wstawione przez ten atrybut wywołuje odpowiednią `Lock` — metoda (określany przez model wątkowy) na początku metody docelowej. Gdy metoda jest został zakończony, `Unlock` jest wywoływana automatycznie. Aby uzyskać więcej informacji na temat tych funkcji, zobacz [CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock)

Ten atrybut wymaga, aby [coclass](coclass.md), [progid](progid.md), lub [vi_progid —](vi-progid.md) atrybutów (lub innego atrybutu, który oznacza jeden z nich) również będą stosowane do tego samego elementu. Jeśli dowolny pojedynczy atrybut jest używany, pozostałe dwa są automatycznie stosowane. Na przykład jeśli `progid` zastosowaniu `vi_progid` i `coclass` są również stosowane.

## <a name="example"></a>Przykład

Poniższy kod zawiera synchronizację `UpdateBalance` metody `CMyClass` obiektu.

```cpp
// cpp_attr_ref_synchronize.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module(name="SYNC")];

[coclass,
threading(both),
vi_progid("MyProject.MyClass"),
progid("MyProject.MyClass.1"),
uuid("7a7baa0d-59b8-4576-b754-79d07e1d1cc3")  
]
class CMyClass {
   float m_nBalance;

   [synchronize]
   void UpdateBalance(float nAdjust) {
      m_nBalance += nAdjust;
   }
};
```

## <a name="requirements"></a>Wymagania

### <a name="attribute-context"></a>Kontekst atrybutu

|||
|-|-|
|**Dotyczy**|Metody klasy, metoda|
|**Powtarzalne**|Nie|
|**Wymaganych atrybutów**|Co najmniej jeden z następujących czynności: `coclass`, `progid`, lub `vi_progid`.|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat konteksty atrybutu zobacz [konteksty atrybutu](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty COM](com-attributes.md)  