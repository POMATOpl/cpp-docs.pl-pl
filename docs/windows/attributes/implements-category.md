---
description: 'Dowiedz się więcej na temat: implements_category'
title: implements_category (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.implements_category
helpviewer_keywords:
- implements_category attribute
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
ms.openlocfilehash: 0efc240394c67ab7d470523b8dfe5025b7a0f978
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289546"
---
# <a name="implements_category"></a>implements_category

Określa kategorie składników zaimplementowane przez klasę docelową.

## <a name="syntax"></a>Składnia

```cpp
[ implements_category(implements_category="uuid") ]
```

### <a name="parameters"></a>Parametry

*implements_category*<br/>
Identyfikator zaimplementowanej kategorii.

## <a name="remarks"></a>Uwagi

Atrybut **implements_category** C++ określa kategorie składników zaimplementowane przez klasę docelową. Jest to realizowane przez utworzenie mapy kategorii i dodanie oddzielnych wpisów określonych przez atrybut **implements_category** . Aby uzyskać więcej informacji, zobacz [kategorie składników i jak działają](/windows/win32/com/component-categories-and-how-they-work).

Ten atrybut wymaga, aby atrybut [coclass](coclass.md), [ProgID](progid.md)lub [vi_progid](vi-progid.md) (lub inny atrybut, który implikuje jeden z tych) został również zastosowany do tego samego elementu. W przypadku użycia dowolnego pojedynczego atrybutu zostaną automatycznie zastosowane pozostałe dwa. Na przykład, jeśli `progid` jest stosowany, `vi_progid` i `coclass` są również stosowane.

## <a name="example"></a>Przykład

Poniższy kod określa, że poniższy obiekt implementuje `Control` kategorię.

```cpp
// cpp_attr_ref_implements_category.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="MyLib")];
[ coclass, implements_category("CATID_Control"),
  uuid("20a0d0cc-5172-40f5-99ae-5e032f3205ae")]
class CMyClass {};
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**`class`**, **`struct`**|
|**Powtarzalność**|Tak|
|**Wymagane atrybuty**|Jeden z następujących: `coclass` , `progid` , lub `vi_progid`|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty COM](com-attributes.md)<br/>
[Atrybuty klasy](class-attributes.md)<br/>
[IMPLEMENTED_CATEGORY](../../atl/reference/category-macros.md#implemented_category)
