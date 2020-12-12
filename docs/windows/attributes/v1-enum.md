---
description: 'Dowiedz się więcej na temat: v1_enum'
title: v1_enum (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.v1_enum
helpviewer_keywords:
- v1_enum attribute
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
ms.openlocfilehash: c096ec78971e8980b68572c7f0bbb4510d03d3d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327203"
---
# <a name="v1_enum"></a>v1_enum

Określa, że określony typ wyliczeniowy ma być przekazywany jako jednostka 32-bitowa, a nie wartość domyślna 16-bitowa.

## <a name="syntax"></a>Składnia

```cpp
[v1_enum]
```

## <a name="remarks"></a>Uwagi

Atrybut **v1_enum** C++ ma takie same funkcje jak atrybut [v1_enum](/windows/win32/Midl/v1-enum) MIDL.

## <a name="example"></a>Przykład

Poniższy kod ilustruje użycie **v1_enum**:

```cpp
// cpp_attr_ref_v1_enum.cpp
// compile with: /LD
[module(name="MyLibrary")];

[export, v1_enum]
enum eList {
   e1 = 1, e2 = 2
};
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Typ wyliczeniowy|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty typedef, enum, Union i struct](typedef-enum-union-and-struct-attributes.md)
