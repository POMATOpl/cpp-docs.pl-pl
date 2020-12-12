---
description: 'Dowiedz się więcej o: ciąg (C++)'
title: String (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.string
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
ms.openlocfilehash: fadfd0b12a8054dedb275e9e2c33c23206856102
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329585"
---
# <a name="string-c"></a>string (C++)

Wskazuje, że tablica Jednowymiarowa **`char`** , **`wchar_t`** , `byte` (lub równoważna) lub wskaźnik do takiej tablicy musi być traktowana jako ciąg.

## <a name="syntax"></a>Składnia

```cpp
[string]
```

## <a name="remarks"></a>Uwagi

Atrybut **C++ ma** taką samą funkcjonalność, jak atrybut MIDL [ciągu](/windows/win32/Midl/string) .

## <a name="example"></a>Przykład

Poniższy kod pokazuje, jak używać **ciągu** w interfejsie i w typedef:

```cpp
// cpp_attr_ref_string.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export, string] typedef char a[21];
[dispinterface, restricted, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   [id(1)] HRESULT Method3([in, string] char *pC);
};
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Tablica lub wskaźnik do tablicy, parametr interfejsu, metoda interfejsu|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty tablicy](array-attributes.md)<br/>
[wywozu](export.md)
