---
description: 'Dowiedz się więcej na temat: ReadOnly (C++)'
title: ReadOnly (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.readonly
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
ms.openlocfilehash: 5a970fa091747e1264d56550bdb11c3b66d81259
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327336"
---
# <a name="readonly-c"></a>readonly (C++)

Zabrania przypisania do elementu członkowskiego danych.

## <a name="syntax"></a>Składnia

```cpp
[readonly]
```

## <a name="remarks"></a>Uwagi

Atrybut **tylko do odczytu** ma taką samą funkcjonalność jak atrybut MIDL [tylko do odczytu](/windows/win32/Midl/readonly) .

Jeśli chcesz zabronić modyfikacji parametru metody, Użyj atrybutu [in](in-cpp.md) .

## <a name="example"></a>Przykład

Poniższy kod przedstawia użycie atrybutu **ReadOnly** :

```cpp
// cpp_attr_ref_readonly.cpp
// compile with: /LD
[idl_quote("midl_pragma warning(disable:2461)")];
#include "unknwn.h"
[module(name="ATLFIRELib")];

[dispinterface, uuid(11111111-1111-1111-1111-111111111111)]
__interface IFireTabCtrl
{
   [readonly, id(1)] int i();
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
[Atrybuty elementu członkowskiego danych](data-member-attributes.md)
