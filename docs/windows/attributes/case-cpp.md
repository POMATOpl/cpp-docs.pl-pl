---
description: 'Dowiedz się więcej o: Case (C++)'
title: Case (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.case
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
ms.openlocfilehash: d851e662387425ca94cc6a03877babf011c7028b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247439"
---
# <a name="case-c"></a>case (C++)

Używany z atrybutem [switch_type](switch-type.md) w **`union`** .

## <a name="syntax"></a>Składnia

```cpp
[ case(value) ]
```

#### <a name="parameters"></a>Parametry

*wartość*<br/>
Możliwa wartość wejściowa, dla której ma zostać przetworzone przetwarzanie. Typ **wartości** może być jednym z następujących typów:

- **`int`**

- **`char`**

- `boolean`

- **`enum`**

lub identyfikator takiego typu.

## <a name="remarks"></a>Uwagi

Atrybut **Case** języka C++ ma takie same funkcje jak atrybut MIDL **przypadku** . Ten atrybut jest używany tylko z atrybutem [switch_type](switch-type.md) .

## <a name="example"></a>Przykład

Poniższy kod przedstawia użycie atrybutu **Case** :

```cpp
// cpp_attr_ref_case.cpp
// compile with: /LD
#include <unknwn.h>
[export]
struct SizedValue2 {
   [switch_type(char), switch_is(kind)] union {
      [case(1), string]
          wchar_t* wval;
      [default, string]
          char* val;
   };
    char kind;
};
[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Składowa a **`class`** lub **`struct`**|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty typedef, enum, Union i struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Atrybuty klasy](class-attributes.md)
