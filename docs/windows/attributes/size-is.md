---
description: 'Dowiedz się więcej na temat: size_is'
title: size_is (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.size_is
helpviewer_keywords:
- size_is attribute
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
ms.openlocfilehash: f61124dc286de1c8893f093454c921b4d6e46037
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329609"
---
# <a name="size_is"></a>size_is

Określ rozmiar pamięci przydzieloną dla wskaźników rozmiaru, wskaźniki rozmiaru do wskaźników rozmiaru i tablic pojedynczych lub wielowymiarowych.

## <a name="syntax"></a>Składnia

```cpp
[ size_is("expression") ]
```

### <a name="parameters"></a>Parametry

*expression*<br/>
Rozmiar pamięci przydzieloną dla wskaźników rozmiaru.

## <a name="remarks"></a>Uwagi

Atrybut **size_is** C++ ma takie same funkcje jak atrybut [size_is](/windows/win32/Midl/size-is) MIDL.

## <a name="example"></a>Przykład

Zapoznaj się z przykładem [first_is](first-is.md) , aby uzyskać przykład sposobu określania sekcji tablicy.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|Pole w **`struct`** lub **`union`** , parametr interfejsu, metoda interfejsu|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|`max_is`|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty typedef, enum, Union i struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Atrybuty parametru](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[max_is](max-is.md)<br/>
[length_is](length-is.md)
