---
description: 'Dowiedz się więcej na temat: licencjonowane'
title: licencjonowane (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.licensed
helpviewer_keywords:
- licensed attribute
ms.assetid: 09cf3b4a-d3f2-43e3-9180-d420333b23bf
ms.openlocfilehash: 348180412c1e8b19994cf5ef3e9bedb4115bfbda
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327526"
---
# <a name="licensed"></a>licensed

Wskazuje, że obiekt COM, do którego ma zastosowanie, jest licencjonowany i musi być skonkretyzowany przy użyciu `IClassFactory2` .

## <a name="syntax"></a>Składnia

```cpp
[licensed]
```

## <a name="remarks"></a>Uwagi

**Licencjonowany** atrybut C++ ma taką samą funkcjonalność jak [licencjonowany](/windows/win32/Midl/licensed) atrybut MIDL.

## <a name="example"></a>Przykład

```cpp
// cpp_attr_ref_licensed.cpp
// compile with: /LD
#include "unknwn.h"
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI : IUnknown {
   HRESULT f();
};

[coclass, version("2.1"), uuid(12345678-1111-2222-3333-123456789012),
licensed, threading(free), progid(some.name)]
class CSample : public IMyI {
public:
   int nSize;
};

[module(name="MyLibrary", version="1.0", helpstring="My Library Block")];
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**`class`**, **`struct`**|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|`coclass`|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty klasy](class-attributes.md)
