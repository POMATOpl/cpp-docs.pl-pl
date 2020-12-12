---
description: 'Dowiedz się więcej na temat: eksport'
title: Export (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.export
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
ms.openlocfilehash: 40c802f906d62d72be2c3126159b089c4d24d5b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236298"
---
# <a name="export"></a>eksportowanie

Powoduje, że struktura danych zostanie umieszczona w pliku IDL.

## <a name="syntax"></a>Składnia

```cpp
[export]
```

## <a name="remarks"></a>Uwagi

**`[export]`** Atrybut C++ powoduje, że struktura danych powinna zostać umieszczona w pliku. idl, a następnie dostępna w bibliotece typów w formacie zgodnym z binarnym, dzięki czemu można go używać z dowolnym językiem.

Nie można zastosować **`[export]`** atrybutu do klasy, nawet jeśli klasa ma tylko publiczne składowe (odpowiednik a **`struct`** ).

Jeśli eksportujesz nienazwane **`enum`** lub **`struct`** , otrzymasz nazwę zaczynającą się od **__unnamed**<em>x</em>, gdzie *x* jest numerem sekwencyjnym.

Elementy typedef są prawidłowe dla eksportu są typami podstawowymi, strukturami, związkami, wyliczeniami lub identyfikatorami typów.  [`typedef`](/windows/win32/Midl/typedef)Aby uzyskać więcej informacji, zobacz.

## <a name="example"></a>Przykład

Poniższy kod pokazuje, jak używać **`[export]`** atrybutu:

```cpp
// cpp_attr_ref_export.cpp
// compile with: /LD
[module(name="MyLibrary")];

[export]
struct MyStruct {
   int i;
};
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**`union`**, **`typedef`** , **`enum`** , **`struct`** lub **`interface`**|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty kompilatora](compiler-attributes.md)<br/>
[Atrybuty typedef, enum, Union i struct](typedef-enum-union-and-struct-attributes.md)
