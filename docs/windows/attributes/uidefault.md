---
description: 'Dowiedz się więcej na temat: uidefault'
title: uidefault (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.uidefault
helpviewer_keywords:
- uidefault attribute
ms.assetid: 200de0e0-2e34-40a2-bae4-8d485a62264d
ms.openlocfilehash: a173679ebdecf31b475fb276741a5ac217cab410
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329523"
---
# <a name="uidefault"></a>uidefault

Wskazuje, że element członkowski informacji o typie jest domyślnym elementem członkowskim do wyświetlania w interfejsie użytkownika.

## <a name="syntax"></a>Składnia

```cpp
[uidefault]
```

## <a name="remarks"></a>Uwagi

Atrybut **uidefault** C++ ma takie same funkcje jak atrybut [uidefault](/windows/win32/Midl/uidefault) MIDL.

## <a name="example"></a>Przykład

Poniższy kod przedstawia przykład **uidefault**:

```cpp
// cpp_attr_ref_uidefault.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface ICustom{
   HRESULT Custom([in] long l, [out, retval] long *pLong);
   [uidefault]HRESULT id0([in] long l);
   [uidefault]HRESULT id1([in] long l);

   [uidefault, propget] HRESULT get_y(int *y);
   [uidefault, propput] HRESULT put_y(int y);
};
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Interface — Metoda|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty metody](method-attributes.md)
