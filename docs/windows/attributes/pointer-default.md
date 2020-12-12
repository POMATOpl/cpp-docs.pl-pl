---
description: 'Dowiedz się więcej na temat: pointer_default'
title: pointer_default (atrybut C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pointer_default
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
ms.openlocfilehash: 0c7768227a5922bca7e1b48b3ad82821bb62ea54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329687"
---
# <a name="pointer_default"></a>pointer_default

Określa domyślny atrybut wskaźnika dla wszystkich wskaźników, z wyjątkiem wskaźników najwyższego poziomu, które pojawiają się na listach parametrów.

## <a name="syntax"></a>Składnia

```cpp
[ pointer_default(value) ]
```

### <a name="parameters"></a>Parametry

*wartość*<br/>
Wartość opisująca typ wskaźnika: **PTR**, **ref** lub **Unique**.

## <a name="remarks"></a>Uwagi

Atrybut **pointer_default** C++ ma takie same funkcje jak atrybut [pointer_default](/windows/win32/Midl/pointer-default) MIDL.

## <a name="example"></a>Przykład

Zobacz przykład dla elementu [DefaultValue](defaultvalue.md) dla przykładowego zastosowania **pointer_default**.

## <a name="requirements"></a>Wymagania

| Kontekst atrybutu | Wartość |
|-|-|
|**Dotyczy**|**interfejsu**|
|**Powtarzalność**|Nie|
|**Wymagane atrybuty**|Brak|
|**Nieprawidłowe atrybuty**|Brak|

Aby uzyskać więcej informacji na temat kontekstów atrybutów, zobacz [konteksty atrybutów](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Zobacz też

[Atrybuty IDL](idl-attributes.md)<br/>
[Atrybuty interfejsu](interface-attributes.md)
