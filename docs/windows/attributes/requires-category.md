---
description: 'Dowiedz się więcej na temat: requires_category'
title: requires_category (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.requires_category
helpviewer_keywords:
- requires_category attribute
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
ms.openlocfilehash: 4d2a68e682c4247174ffba630126b5d2f6061788
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327306"
---
# <a name="requires_category"></a>requires_category

Określa kategorie wymaganych składników klasy docelowej.

## <a name="syntax"></a>Składnia

```cpp
[ requires_category(
  requires_category) ]
```

### <a name="parameters"></a>Parametry

*requires_category*<br/>
Identyfikator wymaganej kategorii.

## <a name="remarks"></a>Uwagi

Atrybut **requires_category** C++ określa kategorie składników wymagane przez klasę docelową. Aby uzyskać więcej informacji, zobacz [REQUIRED_CATEGORY](../../atl/reference/category-macros.md#required_category).

Ten atrybut wymaga, aby atrybut [coclass](coclass.md), [ProgID](progid.md)lub [vi_progid](vi-progid.md) (lub inny atrybut, który implikuje jeden z tych) został również zastosowany do tego samego elementu.

## <a name="example"></a>Przykład

Poniższy kod wymaga, aby obiekt zaimplementował kategorię kontroli.

```cpp
// cpp_attr_ref_requires_category.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="MyLibrary")];

[ coclass, requires_category("CATID_Control"),
  uuid("1e1a2436-f3ea-4ff3-80bf-5409370e8144")]
class CMyClass {};
```

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**`class`**, **`struct`**|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Co najmniej jeden z następujących elementów: `coclass` , `progid` , lub `vi_progid` .|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty COM](com-attributes.md)<br/>
[implements_category](implements-category.md)
